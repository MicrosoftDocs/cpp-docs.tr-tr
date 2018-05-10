---
title: UWP uygulamaları için C++ içinde zaman uyumsuz işlemler oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows 8.x apps, creating C++ async operations
- Creating C++ async operations
ms.assetid: a57cecf4-394a-4391-a957-1d52ed2e5494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24ea9cc47ea9fa78c5efaf6c922f9f01dd3ff963
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="creating-asynchronous-operations-in-c-for-uwp-apps"></a>UWP uygulamaları için C++ içinde zaman uyumsuz işlemler oluşturma
Bu belge Windows iş parçacığı havuzu tabanlı zaman uyumsuz işlemlerin bir evrensel Windows çalışma zamanı (UWP) uygulaması oluşturmak için görev sınıfı kullanırken dikkate alınması gereken önemli noktaları bazıları açıklanmaktadır.  
  
 Uygulamalar kullanıcı girişine yanıt verebilir durumda kalmasını sağladığından zaman uyumsuz programlama kullanımını Windows çalışma zamanı uygulama modelindeki anahtar bir bileşenidir. Kullanıcı Arabirimi iş parçacığı engellenmeden uzun süre çalışan bir görev başlayabilir ve görevinin sonucunu daha sonra alabilirsiniz. Ayrıca, görevleri iptal etme ve arka planda çalışan görevler olarak ilerleme bildirimlerin. Belge [c++ zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) UWP uygulamaları oluşturmak için Visual C++ içinde kullanılabilir zaman uyumsuz desene genel bir bakış sağlar. Bu belge, hem kullanmasına ve zaman uyumsuz Windows çalışma zamanı işlemlerinin zincirleri oluşturmak öğretir. Bu bölümde türleri ppltasks.h içinde başka bir Windows çalışma zamanı bileşeni tarafından kullanılabilecek zaman uyumsuz işlemler oluşturmak için nasıl kullanılacağını açıklar ve ne zaman uyumsuz iş denetleme gerçekleştirilir. Ayrıca okuma göz önünde bulundurun [zaman uyumsuz programlama desenleri ve Hilo (C++ ve XAML kullanarak Windows mağazası uygulamaları) ipuçları](http://msdn.microsoft.com/library/windows/apps/jj160321.aspx) nasıl biz görevi sınıfı zaman uyumsuz işlemleri Hilo, C++ ve XAML kullanarak bir Windows çalışma zamanı uygulaması uygulamak için kullanılan öğrenin.  
  
> [!NOTE]
>  Kullanabileceğiniz [paralel Desen kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) ve [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) bir UWP uygulamasında. Ancak, Görev Zamanlayıcısı'nı veya Kaynak Yöneticisi'ni kullanamazsınız. Bu belgede yalnızca bir UWP uygulaması ve değil masaüstü uygulaması için kullanılabilen PPL'de sağladığı ek özellikleri açıklanmaktadır.  
  
## <a name="key-points"></a>Önemli noktalar  

-   Kullanım [concurrency::create_async](reference/concurrency-namespace-functions.md#create_async) (C++ dışındaki dillerde yazılmış olabilir) diğer bileşenler tarafından kullanılan zaman uyumsuz işlemler oluşturmak için.  

  
-   Kullanım [concurrency::progress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) rapor ilerleme bildirimleri göndermek için zaman uyumsuz işlemleri çağrı bileşenleri.  
  
-   İptal etmek iç zaman uyumsuz işlemleri etkinleştirmek için İptal belirteçlerini kullanın.  
  
-   Davranışını `create_async` kendisine geçirilen iş işlevin dönüş türünü işlevi bağlıdır. Bir görev döndürür iş işlevi (ya da `task<T>` veya `task<void>`) olarak adlandırılan bağlamında eşzamanlı olarak çalışan `create_async`. Döndüren bir iş işlev `T` veya `void` rasgele bir bağlamında çalışır.  
  
-   Kullanabileceğiniz [CONCURRENCY::Task:: then](reference/task-class.md#then) , birbiri ardından çalışan görevler zinciri oluşturmak için yöntemi. UWP uygulamasında, bu görevi nasıl oluşturulan bir görevin devamlılıklar varsayılan bağlamının bağlıdır. Görev zaman uyumsuz bir eylem görev oluşturucusuna geçirerek oluşturuldu veya zaman uyumsuz bir eylem döndürür lambda ifadesi geçirerek, tüm devamlılıklar bu görevin varsayılan bağlamının geçerli bağlamı olur. Görev zaman uyumsuz bir eylem değil oluşturulursa, rasgele bir bağlam görevin devamlılıklar için varsayılan olarak kullanılır. Varsayılan bağlamla kılabilirsiniz [concurrency::task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfı.  

  
## <a name="in-this-document"></a>Bu belgede  
  
-   [Zaman uyumsuz işlemler oluşturma](#create-async)  
  
-   [Örnek: bir C++ Windows çalışma zamanı bileşeni oluşturma](#example-component)  
  
-   [Yürütme iş parçacığı denetleme](#exethread)  
  
-   [Örnek: Bir Windows çalışma zamanı uygulamayla C++ ve XAML yürütme denetleme](#example-app)  
  
##  <a name="create-async"></a> Zaman uyumsuz işlemler oluşturma  
 Arka plan görevleri olarak önceki görev tamamlandığında, çalışan ek görevleri tanımlamak için görev ve devamlılık modeli paralel Desen kitaplığı (PPL) kullanabilirsiniz. Bu işlev tarafından sağlanan [concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı. Bu model hakkında daha fazla bilgi ve `task` sınıfı için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Windows çalışma zamanı yalnızca özel işletim sistemi ortamlarında çalışan UWP uygulamaları oluşturmak için kullanabileceğiniz bir programlama arabirimidir. Bu tür uygulamalar yetkili İşlevler, veri türleri ve cihazlar kullanır ve Microsoft Store dağıtılır. Windows çalışma zamanı tarafından temsil edilen *uygulama ikili arabirimi* (ABI). ABI Windows çalışma zamanı API'lerini Visual C++ gibi programlama dilleri tarafından kullanılabilmesini bir temel ikili sözleşmedir.  
  
 Windows çalışma zamanı kullanarak, çeşitli programlama dillerini en iyi özelliklerini kullanabilir ve bunları bir uygulamaya birleştirebilirsiniz. Örneğin, JavaScript, kullanıcı Arabirimi oluşturmak ve bir C++ bileşeni hesaplama yoğunluklu uygulama mantığını gerçekleştirirler. Arka planda bu pkı'ya kullanımı yoğun işlemleri gerçekleştirme yeteneğini UI yanıt verebilir durumda kalmasını önemli bir unsurdur. Çünkü `task` sınıfı için C++ belirli, zaman uyumsuz işlemleri (C++ dışındaki dillerde yazılmış olabilir) diğer bileşenler için iletişim kurmak için bir Windows çalışma zamanı arabirimini kullanmanız gerekir. Windows çalışma zamanı zaman uyumsuz işlemleri temsil etmek için kullanabileceğiniz dört arabirimleri sağlar:  
  
 [Windows::Foundation::IAsyncAction](http://msdn.microsoft.com/library/windows/apps/windows.foundation.iasyncaction.aspx)  
 Zaman uyumsuz bir eylemi ifade eder.  
  
 [Windows::Foundation::IAsyncActionWithProgress\<TProgress >](http://msdn.microsoft.com/library/windows/apps/br206581.aspx)  
 İlerleme durumu raporları zaman uyumsuz bir eylemi temsil eder.  
  
 [Windows::Foundation::IAsyncOperation\<TResult >](http://msdn.microsoft.com/library/windows/apps/br206598.aspx)  
 Bir sonuç döndüren zaman uyumsuz işlemi temsil eder.  
  
 [Windows::Foundation:: ıasyncoperationwithprogress\<TResult, TProgress >](http://msdn.microsoft.com/library/windows/apps/br206594.aspx)  
 Bir sonuç ve raporları ilerleme döndüren zaman uyumsuz işlemi temsil eder.  
  
 Kavramı bir *eylem* zaman uyumsuz görev bir değeri oluşturmuyor anlamına gelir (döndüren bir işlev düşünün `void`). Kavramı bir *işlemi* zaman uyumsuz görev değer oluşturmak anlamına gelir. Kavramı *ilerleme* görev ilerleme iletilerini çağırana raporu olan anlamına gelir. Her JavaScript, .NET Framework ve Visual C++ ABI sınırından kullanmak için bu arabirimleri örneklerini oluşturmak için kendi yolunu sağlar. Visual C++ için PPL'de sağlar [concurrency::create_async](reference/concurrency-namespace-functions.md#create_async) işlevi. Bu işlev bir Windows çalışma zamanı zaman uyumsuz eylem veya bir görevin tamamlanma gösteren işlemi oluşturur. `create_async` İşlev iş işlevi (genellikle bir lambda ifadesi) alır, dahili oluşturur bir `task` nesne ve dört zaman uyumsuz Windows Çalışma Zamanı Modülü arabirimler birinde görev sarar.  
  
> [!NOTE]
>  Kullanım `create_async` yalnızca olduğunda, başka bir dil veya başka bir Windows çalışma zamanı bileşeni erişilebilir işlevselliği oluşturmanız gerekir. Kullanım `task` işlemi hem üretilen ve aynı bileşeninde C++ kodu tarafından tüketilen olduğunu bildiğinizde doğrudan sınıfı.  
  
 Dönüş türü `create_async` değişkenlerinin türüne göre belirlenir. Örneğin, çalışma işlevi bir değer döndürmüyor ve ilerleme bildirmez `create_async` döndürür `IAsyncAction`. Çalışma işlevinizde bir değer döndürmüyor ve ayrıca, ilerleme raporları `create_async` döndürür `IAsyncActionWithProgress`. İlerleme raporu, sağlamak için bir [concurrency::progress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) nesnesi, iş işlevi için parametre olarak. İlerleme durumunu raporlamak hangi tutar iş gerçekleştirildiği ve hangi tutar (örneğin, yüzde olarak) kalıyor bildirmenize olanak sağlar. Ayrıca, rapor sonuçlarını kullanılabilir olduklarında için sağlar.  
  
 `IAsyncAction`, `IAsyncActionWithProgress<TProgress>`, `IAsyncOperation<TResult>`, Ve `IAsyncActionOperationWithProgress<TProgress, TProgress>` arabirimlerinin her sağlayan bir `Cancel` yöntemi zaman uyumsuz işlemi iptal etmek sağlar. `task` Sınıfı iptal belirteçleri ile çalışır. İş iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı bu belirtece abone yeni iş başlatılmaz. Zaten etkin olan iş iptal belirteci izlemek ve mümkün olduğunda durdurun. Bu mekanizma belgedeki daha ayrıntılı anlatılan [PPL'de iptal](cancellation-in-the-ppl.md). Windows çalışma zamanı ile görev iptali bağlanabilir`Cancel` metotlarıyla iki şekilde. İlk olarak, için geçirdiğiniz çalışma işlevini tanımlayabilirsiniz `create_async` yapılacak bir [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) nesnesi. Zaman `Cancel` yöntemi çağrıldığında, bu iptal belirteci iptal edilir ve arka plandaki için normal iptal kuralları uygulanır `task` destekleyen nesne `create_async` çağırın. Belirtmezseniz, bir `cancellation_token` nesnesi, arka plandaki `task` nesne tanımlar örtük olarak. Tanımlayan bir `cancellation_token` nesne çalışma işlevinizde iptali işbirliği ile yanıtlamanız gerektiğinde. Bölüm [örnek: bir Windows çalışma zamanı uygulamayla C++ ve XAML yürütme denetleme](#example-app) iptal bir evrensel Windows Platformu (UWP) uygulaması C# ve özel Windows çalışma zamanı C++ kullanan XAML ile gerçekleştirmek nasıl bir örneği gösterir Bileşen.  
  
> [!WARNING]
>  Görev devamlılıklar zincirindeki, her zaman durumunu temizleyin ve ardından çağıran [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) iptal belirteci iptal edildi zaman. Arama yerine erken dönerseniz `cancel_current_task`, iptal edilen durumu yerine tamamlanmış durumuna işlemi geçişleri.  

  
 Uygulamanızda zaman uyumsuz işlemleri tanımlamak için kullanabileceğiniz bileşimleri aşağıdaki tabloda özetlenmiştir.  
  
|Bu Windows çalışma zamanı arabirim oluşturmak için|Bu türden Döndür `create_async`|Bu parametre türleri örtük iptal belirtecini kullanmak için iş işleve geçirme|Bu parametre türleri, iş işlevi için bir açık iptal belirtecini kullanacak şekilde geçirin|  
|----------------------------------------------------------------------------------|------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|  
|`IAsyncAction`|`void` Veya `task<void>`|(hiçbiri)|(`cancellation_token`)|  
|`IAsyncActionWithProgress<TProgress>`|`void` Veya `task<void>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|  
|`IAsyncOperation<TResult>`|`T` Veya `task<T>`|(hiçbiri)|(`cancellation_token`)|  
|`IAsyncActionOperationWithProgress<TProgress, TProgress>`|`T` Veya `task<T>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|  
  
 Bir değer döndürür veya `task` için geçirdiğiniz çalışma işlevini nesnesinden `create_async` işlevi. Bu değişimler farklı davranışlar üretir. Bir değeri geri döndüğünüzde, iş işlevi içinde kaydırılan bir `task` böylece bir arka plan iş parçacığı üzerinde çalıştırılabilir. Ayrıca, arka plandaki `task` örtük iptal belirtecini kullanır. Buna karşılık, size döndürmesi durumunda bir `task` nesnesi, iş işlevi zaman uyumlu olarak çalışır. Bu nedenle, döndürmesi durumunda bir `task` nesne, çalışma uzun işlemleri yanıt verebilir durumda kalması için uygulamanızı etkinleştirme görevleri olarak çalıştırdığınızdan emin olun. Ayrıca, arka plandaki `task` örtük iptal belirteci kullanmaz. Bu nedenle, almak için çalışma işlevinizde tanımlamanız gerekir bir `cancellation_token` geri döndüğünüzde, destek iptalleri gerektirip gerektirmediğini nesne bir `task` nesnesinin `create_async`.  
  
 Aşağıdaki örnek oluşturmak için kullanılabilecek çeşitli yöntemler gösteren bir `IAsyncAction` başka bir Windows çalışma zamanı bileşeni tarafından kullanılan nesne.  
  
 [!code-cpp[concrt-windowsstore-primes#100](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_1.cpp)]  
  
##  <a name="example-component"></a> Örnek: C++ Windows çalışma zamanı bileşeni oluşturma ve onu C# ' dan kullanma  
 Kullanıcı arabirimini ve Windows çalışma zamanı C++ bileşeni yoğun işlemleri gerçekleştirmek için tanımlamak için XAML ve C# kullanan bir uygulamayı göz önünde bulundurun. Bu örnekte, hangi numaralarıdır asal belirli bir aralıktaki C++ bileşeni hesaplar. Dört Windows çalışma zamanı zaman uyumsuz görev arabirimler arasındaki farkları anlamak için Visual Studio'da oluşturarak başlangıç bir **boş çözüm** ve adlandırma `Primes`. Çözüme eklemek bir **Windows çalışma zamanı bileşeni** proje ve adlandırma `PrimesLibrary`. (Bu örnekte Class1.h Primes.h için yeniden adlandırır) oluşturulan C++ üstbilgi dosyası için aşağıdaki kodu ekleyin. Her `public` yöntemi dört zaman uyumsuz arabirimlerinden biri, tanımlar. Bir değer döndüren yöntemler dönüş bir [Windows::Foundation::Collections::IVector\<int >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) nesnesi. İlerleme raporu yöntemleri `double` tamamlandı genel iş yüzdesi tanımlayan değerleri.  
  
 [!code-cpp[concrt-windowsstore-primes#1](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_2.h)]  
  
> [!NOTE]
>  Kurala göre zaman uyumsuz yöntem adlarında Windows çalışma zamanı "İle zaman uyumsuz" genellikle sonlandırın.  
  
 (Bu örnekte Class1.cpp Primes.cpp için yeniden adlandırır) oluşturulan C++ kaynak dosyasına aşağıdaki kodu ekleyin. `is_prime` İşlevi kendi giriş asal olup olmadığını belirler. Kalan yöntemleri `Primes` sınıfı. Her çağrı `create_async` içinden çağırıldığında yöntemi ile uyumlu bir imzası kullanır. Örneğin, çünkü `Primes::ComputePrimesAsync` döndürür `IAsyncAction`, için sağlanan çalışma işlevi `create_async` bir değer döndürmüyor ve almaz bir `progress_reporter` , parametre olarak nesne.  
  
 [!code-cpp[concrt-windowsstore-primes#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_3.cpp)]  
  
 Her bir yöntemin ilk giriş parametreleri negatif olmayan emin olmak için doğrulama gerçekleştirir. Giriş değeri negatifse yöntemi atar [Platform::InvalidArgumentException](http://msdn.microsoft.com/library/windows/apps/hh755794\(v=vs.110\).aspx). Hata işleme daha sonra bu bölümde anlatılmıştır.  
  
 Bu yöntemler bir UWP uygulaması'ndan kullanmak için Visual C# kullanın **boş uygulama (XAML)** Visual Studio çözümü için ikinci bir proje eklemek için şablon. Bu örnek proje adları `Primes`. Öğesinden sonra `Primes` proje, bir başvuru ekleyin `PrimesLibrary` projesi.  
  
 MainPage.xaml için aşağıdaki kodu ekleyin. C++ bileşeni çağırın ve sonuçları görüntülemek için bu kodu kullanıcı arabirimini tanımlar.  
  
 [!code-xml[concrt-windowsstore-primes#3](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_4.xaml)]  
  
 Aşağıdaki kodu ekleyin `MainPage` MainPage.xaml sınıfta. Bu kodu tanımlayan bir `Primes` nesne ve düğmesi olay işleyicisi.  
  
 [!code-cs[concrt-windowsstore-primes#4](../../parallel/concrt/codesnippet/csharp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_5.cs)]  
  
 Bu yöntemleri `async` ve `await` zaman uyumsuz işlemler tamamlandıktan sonra kullanıcı arabirimini güncelleştirmek için anahtar sözcükler. Zaman uyumsuz UWP uygulamalarında kodlama hakkında daha fazla bilgi için bkz: [parçacıkları ve zaman uyumsuz programlama](/windows/uwp/threading-async).  
  
 `getPrimesCancellation` Ve `cancelGetPrimes` yöntemleri birlikte çalışır kullanıcının işlemi iptal etkinleştirmek için. Ne zaman kullanıcının seçtiği **iptal** düğmesini `cancelGetPrimes` yöntem çağrılarını [IAsyncOperationWithProgress\<TResult, TProgress >:: İptal](http://msdn.microsoft.com/library/windows/apps/windows.foundation.iasyncinfo.cancel.aspx) işlemi iptal etmek için. Temel alınan zaman uyumsuz işlemi yönetir, eşzamanlılık çalışma Windows iptal tamamlandı iletişim kurmak için çalışma zamanı tarafından yakalanan bir iç özel durum türü oluşturur. İptal modeli hakkında daha fazla bilgi için bkz: [iptal](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
> [!IMPORTANT]
>  İşlemi iptal etti Windows çalışma zamanı için doğru şekilde rapor PPL'de etkinleştirmek için bu iç özel durum catch türü değil. Yani, ayrıca tüm catch değil, özel durumlar (`catch (...)`). Tüm catch özel durum, Windows çalışma zamanı iptal işleminin tamamlandığından emin olmak için özel durum yeniden oluşturma.  
  
 Aşağıdaki çizimde gösterildiği `Primes` her seçeneği seçtikten sonra uygulama.  
  
 ![Windows çalışma zamanı Primes uygulama](../../parallel/concrt/media/concrt_windows_primes.png "concrt_windows_primes")  
  
 Kullanma örnekleri için `create_async` diğer diller tarafından kullanılabilecek zaman uyumsuz görevler oluşturmak için bkz: [Bing Haritalar seyahat iyileştirici örneğinde C++ kullanarak](http://msdn.microsoft.com/library/windows/apps/hh699891\(v=vs.110\).aspx) ve [PPLileC++'taWindows8zamanuyumsuzişlemleri](http://code.msdn.microsoft.com/windowsapps/windows-8-asynchronous-08009a0d).  
  
##  <a name="exethread"></a> Yürütme iş parçacığı denetleme  
 Windows çalışma zamanı iş parçacığı modeli COM kullanır. Bu modelde, bunlar kendi eşitleme nasıl işleneceğini bağlı olarak farklı grupların nesneleri barındırılır. İş parçacığı nesneleri birden çok iş parçacıklı grupta (MTA) barındırılır. Tek bir iş parçacığı tarafından erişilen nesneler bir tek iş parçacıklı grupta (STA) barındırılır.  
  
 Bir kullanıcı Arabirimi bir uygulama, ASTA (uygulama STA) iş parçacığı pencere iletileri Pompalama sorumludur ve yalnızca iş parçacığı STA barındırılan UI denetimleri güncelleştirebilirsiniz işleminde değil. Bu iki sonuçları vardır. İlk olarak, yanıt verebilir durumda kalmasını sağlamak amacıyla, tüm CPU-yoğun ve g/ç işlemleri ASTA iş parçacığı üzerinde çalıştırılmamalıdır. İkinci olarak, arka plan iş parçacıklarından gelen sonuçları UI güncelleştirmek için geri ASTA için sıralanmış gerekir. C++ UWP uygulamasında `MainPage` ve tüm diğer XAML sayfaları ATSA üzerinde çalıştırın. Bu nedenle, devamlılık gövde doğrudan denetimlerinde güncelleştirebileceğiniz ASTA üzerinde bildirilen görev devamlılıklar var. varsayılan olarak çalıştırılır. Ancak, başka bir görev bir görevde iç içe varsa, iç içe geçmiş görevde herhangi devamlılıklar MTA'dan çalıştırın. Bu nedenle, bu devamlılıklar hangi bağlamda çalıştırmak açıkça belirtmek kullanılıp dikkate almanız gerekir.  
  
 Zaman uyumsuz bir işlem gibi oluşturulan bir görev `IAsyncOperation<TResult>`, iş parçacığı ayrıntıları yoksay yardımcı olabilecek özel semantiğini kullanır. Devamlılık işlemleri başlatıldı grup üzerinde çalıştırması garantili varsayılan olarak, kendi devamlılıklar bir işlem arka plan iş parçacığında çalıştırmak (veya, bir iş parçacığı tarafından hiç yedeklenmeyebilir değil ancak) (diğer bir deyişle, adlıGrupgelen`task::then`). Kullanabileceğiniz [concurrency::task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) bir devamlılık yürütme bağlamı denetlemek için sınıf. Bu statik yardımcı yöntemler oluşturulacağı `task_continuation_context` nesneler:  
  
-   Kullanım [concurrency::task_continuation_context::use_arbitrary](reference/task-continuation-context-class.md#use_arbitrary) devamlılık arka plan iş parçacığında çalıştığını belirtmek için.  
  
-   Kullanım [concurrency::task_continuation_context::use_current](reference/task-continuation-context-class.md#use_current) devamlılık adlı iş parçacığı üzerinde çalıştığını belirtmek için `task::then`.  

  
 Geçirebilirsiniz bir `task_continuation_context` nesnesini [task::then](reference/task-class.md#then) yöntemi açıkça devamlılık veya yürütme bağlamı denetlemek için görev başka bir grup geçirmek ve'ı çağırın `task::then` örtük olarak denetlemek için yöntemi yürütme bağlamı.  
  
> [!IMPORTANT]
>  UWP uygulamaları ana UI iş parçacığının STA altında çalıştığından, varsayılan olarak bu STA üzerinde oluşturduğunuz devamlılıklar STA üzerinde çalıştırın. Buna göre üzerinde MTA oluşturduğunuz devamlılıklar MTA üzerinde çalıştırın.  
  
 Aşağıdaki bölümde, bir dosya diskten okur, bu dosyada en yaygın sözcükleri bulur ve ardından kullanıcı Arabiriminde sonuçları gösterir bir uygulamayı gösterir. UI güncelleştirme işleminin son kullanıcı Arabirimi iş parçacığı üzerinde oluşur.  
  
> [!IMPORTANT]
>  Bu davranış, UWP uygulamaları için özeldir. Masaüstü uygulamaları için devamlılıklar çalıştırdığı kontrol etmez. Bunun yerine, bir çalışan iş parçacığı her devamlılık çalıştırılacağı Zamanlayıcı seçer.  
  
> [!IMPORTANT]

>  Çağırmayın [concurrency::task::wait](reference/task-class.md#wait) STA üzerinde çalışan bir devamlılık gövdesinde Aksi halde, çalışma zamanı oluşturur [concurrency::invalid_operation](../../parallel/concrt/reference/invalid-operation-class.md) çünkü bu yöntem geçerli iş parçacığının engeller ve uygulama yanıt veremez duruma neden olabilir. Ancak, çağırabilirsiniz [CONCURRENCY::Task](reference/task-class.md#get) bir görev tabanlı devamlılığı öncül görev sonucu almak için yöntem.  
  
##  <a name="example-app"></a> Örnek: Bir Windows çalışma zamanı uygulamayla C++ ve XAML yürütme denetleme  
 Bir dosya diskten okur, bu dosyada en yaygın sözcükleri bulur ve ardından kullanıcı Arabiriminde sonuçları gösterir bir C++ XAML uygulaması göz önünde bulundurun. Bu uygulama oluşturmak için Visual Studio'da oluşturarak başlayın bir **boş uygulama (Evrensel Windows)** proje ve adlandırma `CommonWords`. Uygulama bildiriminizi belirtin **belge kitaplığı** Belgeler klasörünü erişim sağlamak için özelliği. Ayrıca metin (.txt) dosya türü uygulama bildirimi bildirimleri bölümüne ekleyin. Uygulama özellikleri ve bildirimleri hakkında daha fazla bilgi için bkz: [uygulama paketleri ve dağıtım](http://msdn.microsoft.com/library/windows/apps/hh464929.aspx).  
  
 Güncelleştirme `Grid` içerecek şekilde MainPage.xaml öğesinde bir `ProgressRing` öğesi ve bir `TextBlock` öğesi. `ProgressRing` İşlemi devam ediyor gösterir ve `TextBlock` hesaplama sonuçlarını gösterir.  
  
 [!code-xml[concrt-windowsstore-commonwords#1](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_6.xaml)]  
  
 Aşağıdakileri ekleyin `#include` pch.h deyimlerini.  
  
 [!code-cpp[concrt-windowsstore-commonwords#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_7.h)]  
  
 Aşağıdaki yöntem bildirimleri ekleme `MainPage` sınıfı (MainPage.h).  
  
 [!code-cpp[concrt-windowsstore-commonwords#3](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_8.h)]  
  
 Aşağıdakileri ekleyin `using` MainPage.cpp deyimlerini.  
  
 [!code-cpp[concrt-windowsstore-commonwords#4](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_9.cpp)]  
  
 MainPage.cpp içinde uygulamak `MainPage::MakeWordList`, `MainPage::FindCommonWords`, ve `MainPage::ShowResults` yöntemleri. `MainPage::MakeWordList` Ve `MainPage::FindCommonWords` pkı'ya kullanımı yoğun işlemleri. `MainPage::ShowResults` Yöntemi hesaplamanın sonucu kullanıcı Arabiriminde görüntülenir.  
  
 [!code-cpp[concrt-windowsstore-commonwords#5](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_10.cpp)]  
  
 Değiştirme `MainPage` Defteri'nde yaygın sözcükler kullanıcı Arabiriminde görüntüler devamlılık görevlerini zinciri oluşturmak için Oluşturucusu *Iliad* Homer tarafından. Tek tek sözcüklere metni bölmek ve sık kullanılan sözcük bulmak, ilk iki devamlılık görevlerinin zaman alabilir ve bu nedenle açıkça arka planda çalışmaya ayarlanır. Kullanıcı Arabirimi güncelleştirmeleri, son devamlılık görevi devamlılık bağlam belirtir ve bu nedenle Grup Kuralları izler.  
  
 [!code-cpp[concrt-windowsstore-commonwords#6](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_11.cpp)]  
  
> [!NOTE]
>  Bu örnek, yürütme bağlamı belirtme ve devamlılıklar zinciri oluşturmak nasıl gösterilir. Varsayılan olarak kendi devamlılıklar zaman uyumsuz bir işlem oluşturulan bir görev adlı grup üzerinde çalıştırılan geri çağırma `task::then`. Bu nedenle, bu örnek kullanır `task_continuation_context::use_arbitrary` kullanıcı Arabirimi içermeyen işlemleri arka plan iş parçacığında gerçekleştirilmesi belirtmek için.  
  
 Aşağıdaki çizimde sonuçlarını gösterir `CommonWords` uygulama.  
  
 ![Windows çalışma zamanı CommonWords uygulama](../../parallel/concrt/media/concrt_windows_common_words.png "concrt_windows_common_words")  
  
 Bu örnekte, çünkü iptali desteklemek olası `task` nesneleri destekleyen `create_async` örtük iptal belirteci kullanın. Çalışma işlevinizde yapılacak tanımlamak bir `cancellation_token` görevleriniz için İptali İşbirlikçi bir şekilde yanıt gerekip gerekmediğini nesne. PPL'de iptal hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)
