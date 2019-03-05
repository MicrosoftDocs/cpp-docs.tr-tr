---
title: UWP uygulamaları için C++ uygulamasında zaman uyumsuz işlemler oluşturma
ms.date: 11/19/2018
helpviewer_keywords:
- Windows 8.x apps, creating C++ async operations
- Creating C++ async operations
ms.assetid: a57cecf4-394a-4391-a957-1d52ed2e5494
ms.openlocfilehash: 0284970d57cf4cde65b4fb77338423cb81d5d54b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302279"
---
# <a name="creating-asynchronous-operations-in-c-for-uwp-apps"></a>UWP uygulamaları için C++ uygulamasında zaman uyumsuz işlemler oluşturma

Bu belge Windows iş parçacığı havuzu-tabanlı zaman uyumsuz işlemler bir evrensel Windows çalışma zamanı (UWP) uygulaması oluşturmak için görev sınıfının kullandığınızda akılda tutulması gereken önemli noktaları bazılarını açıklar.

Uygulamalar kullanıcı girişine yanıt verebilir durumda kalmasını sağladığından zaman uyumsuz programlama kullanımını Windows çalışma zamanı uygulama modeli temel bir bileşenidir. UI iş parçacığını engellemeden uzun süre çalışan bir görev başlayabilir ve daha sonra görev sonuçları alabilir. Görevleri iptal etme ve görevler arka planda çalışmaya devam eden bildirimlerin. Belge [C++ zaman uyumsuz programlamada](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) UWP uygulamaları oluşturmak için Visual C++ içinde bulunan zaman uyumsuz desene genel bir bakış sağlar. Bu belge, hem kullanmak ve Windows çalışma zamanı zaman uyumsuz işlemler zincirleri oluşturmak öğretir. Bu bölümde, başka bir Windows çalışma zamanı bileşeni tarafından kullanılabilen zaman uyumsuz işlemler oluşturmak için ppltasks.h türleri kullanmayı açıklar ve ne zaman uyumsuz iş denetlemek nasıl yürütülür. Ayrıca okuma göz önünde bulundurun [zaman uyumsuz programlama desenleri ve Hilo (C++ ve XAML kullanan Windows Store apps) içinde ipuçları](https://msdn.microsoft.com/library/windows/apps/jj160321.aspx) nasıl görev sınıfı zaman uyumsuz işlemler Hilo, C++ ve XAML kullanarak bir Windows çalışma zamanı uygulaması uygulamak için kullandığımız öğrenin.

> [!NOTE]
>  Kullanabileceğiniz [paralel desenler Kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) ve [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) bir UWP uygulamasında. Ancak, Görev Zamanlayıcısı'nı veya Kaynak Yöneticisi'ni kullanamazsınız. Bu belgede, yalnızca bir UWP uygulaması ve bir masaüstü uygulaması için kullanılabilen PPL sağlayan ek özellikleri açıklanmaktadır.

## <a name="key-points"></a>Önemli noktalar

- Kullanım [concurrency::create_async](reference/concurrency-namespace-functions.md#create_async) (C++ dışındaki dillerde yazılmış olabilir) diğer bileşenler tarafından kullanılabilen zaman uyumsuz işlemler oluşturmak için.

- Kullanım [concurrency::progress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) rapor ilerleme bildirimleri göndermek için zaman uyumsuz işlemleri çağırmak bileşenleri.

- Dahili zaman uyumsuz işlemlerin iptal etmek için İptal belirteçlerini kullanın.

- Davranışını `create_async` kendisine geçirilen iş işlevin dönüş türü işlev bağlıdır. Bir görev döndüren bir iş işlev (ya da `task<T>` veya `task<void>`) zaman uyumlu olarak adlandırılan bir bağlamda çalışır `create_async`. Döndüren bir iş işlev `T` veya `void` rastgele bir bağlamda çalışır.

- Kullanabileceğiniz [CONCURRENCY::Task:: then](reference/task-class.md#then) birbiri ardına çalıştırın görevleri zinciri oluşturmak için yöntemi. Bir UWP uygulamasında, bu görevi nasıl oluşturulmuş varsayılan bağlamı için bir görev devamlılıkları bağlıdır. Görev zaman uyumsuz bir eylem görev oluşturucusuna geçirerek oluşturuldu veya zaman uyumsuz bir eylem döndüren bir lambda ifadesi geçirerek, tüm devamlılıklar bu görevin varsayılan bağlamı geçerli bağlam yoktur. Görev üzerinden zaman uyumsuz eylem oluşturulur değil, rastgele bir bağlam için görev devamlılıklarının varsayılan olarak kullanılır. Varsayılan bağlamı ile geçersiz kılabilirsiniz [concurrency::task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfı.

## <a name="in-this-document"></a>Bu belgede

- [Zaman uyumsuz işlemler oluşturma](#create-async)

- [Örnek: Bir C++ Windows çalışma zamanı bileşeni oluşturma](#example-component)

- [Yürütme iş parçacığını denetleme](#exethread)

- [Örnek: C++ ve XAML ile bir Windows çalışma zamanı uygulamasında yürütme denetleme](#example-app)

##  <a name="create-async"></a> Zaman uyumsuz işlemler oluşturma

Paralel Desen kitaplığı (PPL) görev ve devamı modeli, önceki görev tamamlandığında, çalışan ek görevler yanı sıra arka plan görevleri tanımlamak için kullanabilirsiniz. Bu işlev tarafından sağlanan [concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı. Bu model hakkında daha fazla bilgi ve `task` sınıfı [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Windows çalışma zamanı, yalnızca özel işletim sistemi ortamında çalışan UWP uygulamaları oluşturmak için kullanabileceğiniz bir programlama arabirimidir. Bu tür uygulamalar yetkili İşlevler, veri türleri ve cihazlar kullanır ve Microsoft Store dağıtılır. Windows çalışma zamanı tarafından temsil edilen *uygulama ikili arabiriminde* (ABI). ABI Visual C++ gibi programlama dilleri için Windows çalışma zamanı API'ları kullanılabilmesini bir temel ikili sözleşmedir.

Windows çalışma zamanı'nı kullanarak, çeşitli programlama dilleri en iyi özelliklerini kullanmak ve bunları tek bir uygulama birleştirebilirsiniz. Örneğin, JavaScript'te oluşturmanıza ve bir C++ bileşeni işlem bakımından yoğun uygulama mantığını gerçekleştirirler. Bu işlem bakımından yoğun işlemleri arka planda gerçekleştirmek için kullanıcı Arabirimi yanıt tutma önemli bir etken yeteneğidir. Çünkü `task` sınıfı için C++ belirli, zaman uyumsuz işlemler (hangi C++ dışındaki dillerde yazılmış olabilir) diğer bileşenlere iletişim kurmak için bir Windows çalışma zamanı arabirimini kullanmanız gerekir. Windows çalışma zamanı zaman uyumsuz işlemleri temsil etmek için kullanabileceğiniz dört arabirimleri sağlar:

[Iasyncoperation](https://msdn.microsoft.com/library/windows/apps/windows.foundation.iasyncaction.aspx)<br/>
Zaman uyumsuz bir eylemi temsil eder.

[Windows::Foundation:: ıasyncactionwithprogress\<TProgress >](https://msdn.microsoft.com/library/windows/apps/br206581.aspx)<br/>
İlerleme durumunu raporlayan zaman uyumsuz bir eylemi temsil eder.

[Iasyncoperation\<TResult >](https://msdn.microsoft.com/library/windows/apps/br206598.aspx)<br/>
Bir sonuç döndüren bir zaman uyumsuz işlemi temsil eder.

[Windows::Foundation:: ıasyncoperationwithprogress\<TResult, TProgress >](https://msdn.microsoft.com/library/windows/apps/br206594.aspx)<br/>
Sonuç ve raporların ilerleme durumunu döndüren zaman uyumsuz bir işlemi temsil eder.

Kavramı bir *eylem* zaman uyumsuz görev değer üretemez anlamına gelir (döndüren bir işlev düşünün `void`). Kavramı bir *işlemi* zaman uyumsuz görev bir değer üreten anlamına gelir. Kavramı *ilerleme* görev ilerleme iletilerini çağırana bildirebilirsiniz anlamına gelir. Her JavaScript, .NET Framework ve Visual C++ örnekleri kullanmak için bu arabirimlerin ABI sınırında oluşturmak için kendi yolunu sağlar. Visual C++ için PPL sağlar [concurrency::create_async](reference/concurrency-namespace-functions.md#create_async) işlevi. Bu işlev, bir Windows çalışma zamanı zaman uyumsuz eylem veya görevi tamamlama belirten işlemi oluşturur. `create_async` İşlevi iş işlevi (genellikle bir lambda ifadesi) alır, dahili olarak oluşturur bir `task` nesne ve dört zaman uyumsuz Windows çalışma zamanı arabirimlerinden birini görev sarar.

> [!NOTE]
>  Kullanım `create_async` yalnızca olduğunda, başka bir dil veya başka bir Windows çalışma zamanı bileşeni erişilebilir işlevselliği oluşturmanız gerekir. Kullanım `task` işlemi hem üretilen ve aynı bileşende C++ kod tarafından tüketilen olduğunu bildiğinizde doğrudan sınıf.

Dönüş türünü `create_async` bağımsız değişkenlerinin türleri tarafından belirlenir. Örneğin, iş işlevi bir değer döndürmez ve ilerleme bildirmez `create_async` döndürür `IAsyncAction`. Çalışma işlevinizde bir değer döndürmez ve ayrıca, ilerleme raporları `create_async` döndürür `IAsyncActionWithProgress`. İlerleme raporu sağlamak için bir [concurrency::progress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) iş işlevinize parametre olarak nesne. İlerleme durumunu raporlamak hangi iş miktarını gerçekleştirildi ve hangi tutar (örneğin, yüzde olarak) kalıyor bildirmenize olanak sağlar. Ayrıca, kullanıma sunuldukça sonuçlarını sağlar.


  `IAsyncAction`, `IAsyncActionWithProgress<TProgress>`, `IAsyncOperation<TResult>` ve `IAsyncActionOperationWithProgress<TProgress, TProgress>` arabirimlerinin her biri zaman uyumsuz işlemi iptal etmenizi sağlayan bir `Cancel` metodu sunar. `task` Sınıfı iptal belirteçleri ile çalışır. İşi iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı için bu belirteci abone yeni iş başlamıyor. Zaten etkin olan iş, iptal belirteci izleyebilir ve mümkün olduğunda durdurun. Bu mekanizma belge içinde daha ayrıntılı anlatılan [ppl'de iptal](cancellation-in-the-ppl.md). Görev iptali Windows çalışma zamanı ile bağlanabilir`Cancel` metotlarıyla iki şekilde. İlk olarak, geçirdiğiniz çalışma işlevini tanımlayabilirsiniz `create_async` gerçekleştirilecek bir [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) nesne. Zaman `Cancel` yöntemi çağrıldığında, bu iptal belirteci iptal edilir ve temel alınan normal iptal kuralları uygulanır `task` destekleyen nesne `create_async` çağırın. Bir `cancellation_token` nesnesi belirtmezseniz, temel alınan `task` nesnesi örtük olarak bir nesne tanımlar. Çalışma işlevinizde bir iptali işbirliği halinde olarak yanıtlamanız gerektiğinde bir `cancellation_token` nesnesi tanımlayın. Bölüm [örneği: C++ ve XAML ile bir Windows çalışma zamanı uygulamasında yürütme denetleme](#example-app) bir evrensel Windows Platformu (UWP) uygulaması iptal gerçekleştirme örneği gösterilmektedir C# ve XAML kullanan özel bir Windows çalışma zamanı C++ bileşeni.

> [!WARNING]
>  Görev devamlılıkları oluşan bir zincir, durumu her zaman temiz ve sonra çağrı [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) iptal belirteci iptal edildi zaman. Çağırmak yerine erken dönüş yaparsa `cancel_current_task`, tamamlanmış duruma iptal edilmiş duruma yerine işlemi geçişler.

Uygulamanıza zaman uyumsuz işlemleri tanımlamak için kullanabileceğiniz birleşimleri aşağıdaki tabloda özetlenmiştir.

|Bu Windows çalışma zamanı arabirimi oluşturmak için|Bu türden döndürür `create_async`|Bu parametre türleri bir örtük iptal belirteci kullanmak için iş işlevinize geçirin|Bu parametre türleri bir açık bir iptal belirteci kullanmak için iş işlevinize geçirin|
|----------------------------------------------------------------------------------|------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|`IAsyncAction`|`void` veya `task<void>`|(hiçbiri)|(`cancellation_token`)|
|`IAsyncActionWithProgress<TProgress>`|`void` veya `task<void>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|
|`IAsyncOperation<TResult>`|`T` veya `task<T>`|(hiçbiri)|(`cancellation_token`)|
|`IAsyncActionOperationWithProgress<TProgress, TProgress>`|`T` veya `task<T>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|

Bir değer döndürebilir veya `task` öğesine geçirdiğiniz çalışma işlevini bir nesneden `create_async` işlevi. Bu farklılıkların farklı davranış üretir. Bir değer döndürmediğinde çalışma işlevi içindeki sarmalandıktan bir `task` böylece bir arka plan iş parçacığı üzerinde çalıştırılabilir. Ayrıca, arka plandaki `task` örtük iptal belirtecini kullanır. Buna karşılık, döndürürse, bir `task` nesnesi, iş işlevi zaman uyumlu olarak çalışır. Bu nedenle, döndürmesi durumunda bir `task` nesne, uzun süren işlemleri çalışma yanıt verebilir durumda kalması için uygulamanızı etkinleştirmek için görevleri olarak çalıştırdığınızdan emin olun. Ayrıca, arka plandaki `task` bir örtük iptal belirteci kullanmaz. Bu nedenle, yapılacak iş işlevinizi tanımlamanız gereken bir `cancellation_token` döndüğünüzde, destek için İptal gerektirip gerektirmediğini nesnesi bir `task` nesnesinden `create_async`.

Aşağıdaki örnek, oluşturmak için çeşitli yollar gösterir. bir `IAsyncAction` başka bir Windows çalışma zamanı bileşeni tarafından kullanılabilen bir nesne.

[!code-cpp[concrt-windowsstore-primes#100](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_1.cpp)]

##  <a name="example-component"></a> Örnek: Bir C++ Windows çalışma zamanı bileşeni oluşturma ve ondan kullanmaC#

Yoğun işlem gücü kullanımlı işlemleri gerçekleştirmek için kullanıcı Arabirimi ve bir C++ Windows çalışma zamanı bileşeni tanımlamak için XAML ve C# kullanan bir uygulamayı göz önünde bulundurun. Bu örnekte, hangi sayılardır asal belirli bir aralıktaki C++ bileşeni hesaplar. Dört Windows çalışma zamanı zaman uyumsuz görev arabirimleri arasındaki farklar göstermek için Visual Studio'da oluşturarak başlayın bir **boş çözüm** ve adlandırma `Primes`. Sonra çözüme eklemek bir **Windows çalışma zamanı bileşeni** proje ve adlandırma `PrimesLibrary`. (Bu örnekte Class1.h Primes.h için yeniden adlandırır) oluşturulan C++ üstbilgi dosyasına aşağıdaki kodu ekleyin. Her `public` yöntemi dört zaman uyumsuz arabirimlerinden birini tanımlar. Dönüş değeri döndüren yöntemler bir [Windows::Foundation::Collections::IVector\<int >](https://msdn.microsoft.com/library/windows/apps/br206631.aspx) nesne. İlerleme raporu yöntemleri `double` tamamladığı toplam iş yüzdesini tanımlayan değerleri.

[!code-cpp[concrt-windowsstore-primes#1](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_2.h)]

> [!NOTE]
>  Kural gereği, Windows çalışma zamanı zaman uyumsuz yöntem adları genellikle "Async" ile bitmelidir.

(Bu örnekte Class1.cpp Primes.cpp için yeniden adlandırır) oluşturulan C++ kaynak dosyaya aşağıdaki kodu ekleyin. `is_prime` İşlevi, giriş asal olup olmadığını belirler. Kalan yöntemleri `Primes` sınıfı. Her çağrı `create_async` içinden çağırıldığında yöntemi ile uyumlu bir imzası kullanır. Örneğin, çünkü `Primes::ComputePrimesAsync` döndürür `IAsyncAction`, için sağlanan çalışma işlevi `create_async` bir değer döndürmez ve verdiği hızlı tepkilerden faydalanamamış bir `progress_reporter` parametre olarak nesne.

[!code-cpp[concrt-windowsstore-primes#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_3.cpp)]

Her bir yöntemin ilk giriş parametrelerini negatif olmayan emin olmak için doğrulama gerçekleştirir. Giriş değeri negatifse çağırılıyorsa yöntem [Platform::ınvalidargumentexception](https://msdn.microsoft.com/library/windows/apps/hh755794.aspx). Hata işleme daha sonra bu bölümde açıklanmıştır.

Bu yöntemler bir UWP uygulamasında kullanmak için Visual C# kullanın **boş uygulama (XAML)** Visual Studio çözümü için ikinci bir proje eklemek için şablon. Bu örnek proje adları `Primes`. Ardından `Primes` projesi, bir başvuru ekleyin `PrimesLibrary` proje.

MainPage.xaml için aşağıdaki kodu ekleyin. C++ bileşeni çağırın ve sonuçları görüntülemek için bu kod, kullanıcı arabirimini tanımlar.

[!code-xml[concrt-windowsstore-primes#3](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_4.xaml)]

Aşağıdaki kodu ekleyin `MainPage` MainPage.xaml sınıfta. Bu kodu tanımlayan bir `Primes` nesne ve düğmesi olay işleyicileri.

[!code-cs[concrt-windowsstore-primes#4](../../parallel/concrt/codesnippet/csharp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_5.cs)]

Bu yöntemleri `async` ve `await` zaman uyumsuz işlemler tamamlandıktan sonra kullanıcı arabirimini güncelleştirmek için anahtar sözcükler. UWP uygulamalarında zaman uyumsuz kodlama hakkında daha fazla bilgi için bkz: [parçacıkları ve zaman uyumsuz programlama](/windows/uwp/threading-async).

`getPrimesCancellation` Ve `cancelGetPrimes` yöntemleri için birlikte çalışır kullanıcı işlemi iptal etmek etkinleştirin. Ne zaman kullanıcının seçtiği **iptal** düğmesi `cancelGetPrimes` yöntem çağrılarını [Iasyncoperationwithprogress\<TResult, TProgress >:: İptal](https://msdn.microsoft.com/library/windows/apps/windows.foundation.iasyncinfo.cancel.aspx) işlemi iptal etme. Temel alınan zaman uyumsuz işlem yönetir, eşzamanlılık çalışma Windows iptal tamamlandığını iletişim kurmak için çalışma zamanı tarafından yakalandı bir iç özel durum türü oluşturur. İptal etme modeli hakkında daha fazla bilgi için bkz: [iptal](../../parallel/concrt/cancellation-in-the-ppl.md).

> [!IMPORTANT]
>  İşlemi iptal etti Windows çalışma zamanı için doğru şekilde bildirmek PPL etkinleştirmek için bu iç özel durum türü yakalamayın. Yani, ayrıca tüm yakalamalısınız değil, özel durumlar (`catch (...)`). Tüm catch özel durumları, rethrow Windows çalışma zamanı İptal işlemi tamamlamasını sağlamak için özel durum.

Aşağıdaki çizimde gösterildiği `Primes` her seçeneği seçtikten sonra uygulama.

![Windows çalışma zamanı uygulama Primes](../../parallel/concrt/media/concrt_windows_primes.png "Windows çalışma zamanı Primes uygulama")

Kullanan örnekler `create_async` diğer diller tarafından kullanılabilen zaman uyumsuz görevler oluşturmak için bkz [Bing Haritalar seyahat iyileştirici örneğinde C++ kullanarak](https://msdn.microsoft.com/library/windows/apps/hh699891.aspx) ve [PPLileC++'taWindows8zamanuyumsuzişlemleri](http://code.msdn.microsoft.com/windowsapps/windows-8-asynchronous-08009a0d).

##  <a name="exethread"></a> Yürütme iş parçacığını denetleme

Windows çalışma zamanı iş parçacığı modeli COM kullanır. Bu modelde, nesneleri, eşitleme nasıl işledikleri bağlı olarak farklı apartmanlar içinde barındırılır. İş parçacığı nesneleri, çok iş parçacıklı apartmanda (MTA) barındırılır. Tek bir iş parçacığı tarafından erişilebilir nesneleri, bir tek iş parçacıklı apartmanda (STA) barındırılır.

Bir kullanıcı Arabirimi olan bir uygulama içinde ASTA (ASTA uygulaması) iş parçacığı pencere iletileri Pompalama için sorumludur ve yalnızca iş parçacığı işleminde STA barındırılan UI denetimleri güncelleştirebilirsiniz. Bu iki sonucu vardır. İlk olarak yanıt verebilir durumda kalmasını sağlamak amacıyla, tüm CPU yoğun ve g/ç işlemleri ASTA iş parçacığı üzerinde çalıştırılmamalıdır. İkinci olarak, kullanıcı arabirimini güncelleştirmek için geri ASTA için arka plan iş parçacıklarından gelen sonuçları sıralanması gerekir. Bir C++ UWP uygulamasında `MainPage` ve diğer tüm XAML sayfaları ATSA üzerinde çalıştırın. Bu nedenle, devamlılık gövdesi doğrudan denetimlerinde güncelleştirebilmek ASTA üzerinde bildirilen görev devamlılıkları var. varsayılan olarak çalıştırılır. Ancak, bir görevi başka bir görev içinde iç içe ise, iç içe geçmiş görev üzerinde tüm devamlar MTA'dan çalıştırın. Bu nedenle, hangi bağlamda bu devamlılıklar çalıştırma açıkça belirtmek etkinleştirilip etkinleştirilmeyeceğini dikkate almanız gerekir.

Zaman uyumsuz bir işlemi, gibi oluşturan bir görev `IAsyncOperation<TResult>`, yardımcı olabilecek özel semantiği kullanan iş parçacığı ayrıntıları yoksay. Arka plan iş parçacığında bir işlem çalıştırabilirsiniz (veya, bir iş parçacığı tarafından hiç yedeklenmeyebilir değil), ancak devam işlemleri başlatıldı grup üzerinde çalıştırılması kesin varsayılan olarak kendi devamlılıklarının olan (diğer bir deyişle, adlıGrupöğesinden`task::then`). Kullanabileceğiniz [concurrency::task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) devamlılığı yürütme bağlamı denetlemek için sınıf. Bu statik yardımcı yöntemler oluşturulacağı `task_continuation_context` nesneler:

- Kullanım [concurrency::task_continuation_context::use_arbitrary](reference/task-continuation-context-class.md#use_arbitrary) için devamlılık arka plan iş parçacığında çalışacağını belirtirsiniz.

- Kullanım [concurrency::task_continuation_context::use_current](reference/task-continuation-context-class.md#use_current) devamlılık çağıran iş parçacığında çalıştırmalarda `task::then`.

Geçirebilirsiniz bir `task_continuation_context` nesnesini [task::then](reference/task-class.md#then) yöntemi açıkça devamlılığın veya yürütme bağlamı denetlemek için başka bir grup için görev geçirin ve ardından çağırın `task::then` örtük olarak denetlemek için yöntemi yürütme bağlamı.

> [!IMPORTANT]
>  Ana kullanıcı Arabirimi iş parçacığı UWP uygulamalarını STA altında çalıştığından, devamlılık o STA üzerinde varsayılan olarak oluşturduğunuz STA'da çalıştırın. Buna MTA üzerinde oluşturduğunuz devamlılıklar MTA üzerinde çalıştırın.

Aşağıdaki bölümde, bir dosyayı diskten okur, bu dosyada en yaygın sözcükleri bulur ve daha sonra kullanıcı Arabiriminde sonuçları gösterir bir uygulama gösterilmektedir. UI güncelleştirme işleminin son kullanıcı Arabirimi iş parçacığında oluşur.

> [!IMPORTANT]
> Bu davranış, UWP uygulamalarına özeldir. Masaüstü uygulamaları için devamlılıklar çalıştırdığı kontrol etmez. Bunun yerine, Zamanlayıcı iş parçacığı üzerinde çalışacağı her devamlılık seçer.

> [!IMPORTANT]
> Çağırmayın [CONCURRENCY::Task:: wait](reference/task-class.md#wait) gövdesinde STA'da çalışan bir devamlılık Aksi takdirde, çalışma zamanı oluşturur [concurrency::invalid_operation](../../parallel/concrt/reference/invalid-operation-class.md) çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt veremez duruma gelmesine neden olabilir. Ancak, çağırabilirsiniz [CONCURRENCY::Task:: get](reference/task-class.md#get) görev tabanlı devamlılık içinde öncül görevin sonucunu almak için yöntemi.

##  <a name="example-app"></a> Örnek: C++ ve XAML ile bir Windows çalışma zamanı uygulamasında yürütme denetleme

Bir dosyayı diskten okuduktan, bu dosyada en yaygın sözcükleri bulur ve daha sonra kullanıcı Arabiriminde sonuçları gösterir bir C++ ve XAML uygulaması göz önünde bulundurun. Bu uygulamayı oluşturmak için Visual Studio'da oluşturarak başlayın bir **boş uygulama (Evrensel Windows)** proje ve adlandırma `CommonWords`. Uygulama bildiriminizi belirtin **belge kitaplığı** Belgeler klasörünü erişim sağlamak için özellik. Ayrıca uygulama bildirimi bildirimler bölümüne metin (.txt) dosya türü ekleyin. Uygulama özellikleri ve bildirimleri hakkında daha fazla bilgi için bkz: [uygulama paketleri ve dağıtım](https://msdn.microsoft.com/library/windows/apps/hh464929.aspx).

Güncelleştirme `Grid` içerecek şekilde MainPage.xaml öğesinde bir `ProgressRing` öğesi ve bir `TextBlock` öğesi. `ProgressRing` İşleminin devam ettiğini gösterir ve `TextBlock` hesaplamanın sonuçlarını gösterir.

[!code-xml[concrt-windowsstore-commonwords#1](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_6.xaml)]

Aşağıdaki `#include` pch.h deyimleriyle.

[!code-cpp[concrt-windowsstore-commonwords#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_7.h)]

Aşağıdaki yöntem bildirimleri için ekleme `MainPage` sınıfı (MainPage.h).

[!code-cpp[concrt-windowsstore-commonwords#3](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_8.h)]

Aşağıdaki `using` MainPage.cpp deyimleriyle.

[!code-cpp[concrt-windowsstore-commonwords#4](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_9.cpp)]

MainPage.cpp içinde uygulama `MainPage::MakeWordList`, `MainPage::FindCommonWords`, ve `MainPage::ShowResults` yöntemleri. `MainPage::MakeWordList` Ve `MainPage::FindCommonWords` işlem bakımından yoğun kullanan işlemlerini gerçekleştirin. `MainPage::ShowResults` Yöntemi kullanıcı Arabiriminde biri hesaplama sonucunu görüntüler.

[!code-cpp[concrt-windowsstore-commonwords#5](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_10.cpp)]

Değiştirme `MainPage` kitaptaki ortak kelimeler Arabiriminde görüntüleyen bir devamlılık görevleri zinciri oluşturmak için oluşturucu *Iliad* Homer tarafından. Metnin tek tek sözcüklere bölme ve ortak kelimeler bulun, ilk iki devamlılık görevleri zaman alabilir ve bu nedenle açıkça arka planda çalıştırmak için ayarlanır. Kullanıcı Arabirimi güncelleştirmeleri, son devam görevi hiçbir devamlılık bağlamını belirtir ve bu nedenle Grup Kuralları iş parçacığı izler.

[!code-cpp[concrt-windowsstore-commonwords#6](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_11.cpp)]

> [!NOTE]
>  Bu örnek, yürütme bağlamları belirtme ve devamlılıklar zinciri oluşturmak nasıl gösterir. Varsayılan olarak kendi devamlılıklarının zaman uyumsuz bir işlemden oluşturulan bir görev olarak adlandırılan bir grup üzerinde çalışır geri çağırma `task::then`. Bu nedenle, bu örnekte `task_continuation_context::use_arbitrary` kullanıcı Arabirimi içermeyen işlemleri arka plan iş parçacığında gerçekleştirilmesi belirtmek için.

Sonuçları aşağıdaki çizimde `CommonWords` uygulama.

![Windows çalışma zamanı CommonWords uygulama](../../parallel/concrt/media/concrt_windows_common_words.png "Windows çalışma zamanı CommonWords uygulama")

Bu örnekte, çünkü iptali desteklemek olası `task` nesneleri destekleyen `create_async` bir örtük iptal belirteci kullanın. Yapılacak İş işlevinizi tanımlamak bir `cancellation_token` görevleriniz için İptal çalışılabilir bir yanıt gerektiğinde nesne. Ppl'de iptal hakkında daha fazla bilgi için bkz. [ppl'de iptal](cancellation-in-the-ppl.md)

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)
