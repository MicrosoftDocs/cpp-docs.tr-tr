---
title: UWP uygulamaları için C++ ' da zaman uyumsuz Işlemler oluşturma
ms.date: 11/19/2018
helpviewer_keywords:
- Windows 8.x apps, creating C++ async operations
- Creating C++ async operations
ms.assetid: a57cecf4-394a-4391-a957-1d52ed2e5494
ms.openlocfilehash: a12900f3145f0dde797fe56c893442e1632cc01c
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404518"
---
# <a name="creating-asynchronous-operations-in-c-for-uwp-apps"></a>UWP uygulamaları için C++ ' da zaman uyumsuz Işlemler oluşturma

Bu belgede, bir Evrensel Windows Çalışma Zamanı (UWP) uygulamasında Windows ThreadPool tabanlı zaman uyumsuz işlemler oluşturmak için görev sınıfını kullandığınızda göz önünde bulundurmanız gereken bazı önemli noktaları açıklanmaktadır.

Zaman uyumsuz programlama kullanımı, uygulamaların kullanıcı girişine yanıt vermeye devam etmesini sağladığından Windows Çalışma Zamanı uygulama modelinde bir anahtar bileşendir. UI iş parçacığını engellemeden uzun süre çalışan bir görev başlatabilir ve görevin sonuçlarını daha sonra alabilirsiniz. Ayrıca görevleri iptal edebilir ve görevler arka planda çalıştırıldığında ilerleme bildirimleri alabilirsiniz. [C++ ' da belge zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) , UWP uygulamaları oluşturmak için Visual C++ ' de bulunan zaman uyumsuz düzene genel bir bakış sağlar. Bu belge, zaman uyumsuz Windows Çalışma Zamanı işlemleri için hem tüketme hem de oluşturma hakkında öğretir. Bu bölümde, başka bir Windows Çalışma Zamanı bileşeni tarafından tüketilen ve zaman uyumsuz çalışmanın nasıl yürütüleceğini denetleyen zaman uyumsuz işlemler oluşturmak için ppltasks. h içindeki türlerin nasıl kullanılacağı açıklanmaktadır. Ayrıca, bir C++ ve XAML kullanan Windows Çalışma Zamanı bir uygulama olan Tepo 'da zaman uyumsuz işlemleri uygulamak için görev sınıfını nasıl kullandığımızda bilgi edinmek için, [Windows Mağazası 'Ndaki zaman uyumsuz programlama düzenlerini ve ipuçlarını (c++ ve XAML kullanarak Windows Mağazası uygulamaları)](/previous-versions/windows/apps/jj160321(v=win.10)) okumayı düşünün.

> [!NOTE]
> Bir UWP uygulamasında [paralel Desenler kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (ppl) ve [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanabilirsiniz. Ancak, Görev Zamanlayıcı veya Kaynak Yöneticisi kullanamazsınız. Bu belgede, PPL 'nin yalnızca bir UWP uygulaması tarafından kullanılabilen ve bir masaüstü uygulamasına yönelik olarak sağladığı ek özellikler açıklanmaktadır.

## <a name="key-points"></a>Önemli noktalar

- Diğer bileşenler tarafından kullanılabilecek (C++ dışındaki dillerde yazılmış olabilecek) zaman uyumsuz işlemler oluşturmak için [concurrency:: create_async](reference/concurrency-namespace-functions.md#create_async) kullanın.

- Zaman uyumsuz işlemlerinizi çağıran bileşenlere ilerleme bildirimleri bildirmek için [eşzamanlılık::p rogress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) kullanın.

- İç zaman uyumsuz işlemlerin iptal edilmesine olanak tanımak için iptal belirteçlerini kullanın.

- İşlevin davranışı, `create_async` kendisine geçirilen çalışma işlevinin dönüş türüne bağlıdır. Bir görevi döndüren ( `task<T>` veya `task<void>` ) zaman uyumlu olarak çağıran bağlamda çalışan bir çalışma işlevi `create_async` . Rastgele bir bağlamda döndüren veya çalıştırılan bir iş işlevi `T` `void` .

- Daha sonra çalışan bir görev zinciri oluşturmak için [concurrency:: task:: then](reference/task-class.md#then) yöntemini kullanabilirsiniz. UWP uygulamasında, bir görevin devamlılıkları için varsayılan bağlam, bu görevin nasıl oluşturulduğuna bağlıdır. Görev, görev oluşturucusuna zaman uyumsuz bir eylem geçirilerek veya zaman uyumsuz bir eylem döndüren bir lambda ifadesi geçirerek oluşturulduysa, bu görevin tüm devamlılıkları için varsayılan bağlam geçerli bağlamdır. Görev zaman uyumsuz bir eylemden oluşturulmuşsa, varsayılan olarak görevin devamlılıkları için rastgele bir bağlam kullanılır. Varsayılan bağlamı [concurrency:: task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfıyla geçersiz kılabilirsiniz.

## <a name="in-this-document"></a>Bu belgede

- [Zaman uyumsuz Işlemler oluşturma](#create-async)

- [Örnek: C++ Windows Çalışma Zamanı bileşeni oluşturma](#example-component)

- [Yürütme Iş parçacığını denetleme](#exethread)

- [Örnek: C++ ve XAML ile Windows Çalışma Zamanı uygulamasında yürütmeyi denetleme](#example-app)

## <a name="creating-asynchronous-operations"></a><a name="create-async"></a>Zaman uyumsuz Işlemler oluşturma

Paralel Desenler kitaplığındaki (PPL) görev ve devamlılık modelini, önceki görev tamamlandığında çalışan ek görevlerin yanı sıra arka plan görevlerini tanımlamak için de kullanabilirsiniz. Bu işlevsellik [concurrency:: Task](../../parallel/concrt/reference/task-class.md) sınıfı tarafından sağlanır. Bu model ve sınıf hakkında daha fazla bilgi için `task` bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Windows Çalışma Zamanı, yalnızca özel bir işletim sistemi ortamında çalışan UWP uygulamaları oluşturmak için kullanabileceğiniz bir programlama arabirimidir. Bu uygulamalar, yetkili işlevleri, veri türlerini ve cihazları kullanır ve Microsoft Store dağıtılır. Windows Çalışma Zamanı, *uygulama Ikili arabirimi* (ABI) tarafından temsil edilir. ABı, Windows Çalışma Zamanı API 'Leri Visual C++ gibi programlama dillerinde kullanılabilir hale getiren temel bir ikili sözleşmedir.

Windows Çalışma Zamanı kullanarak, çeşitli programlama dillerinin en iyi özelliklerini kullanabilir ve bunları tek bir uygulamada birleştirebilirsiniz. Örneğin, JavaScript 'te Kullanıcı arabiriminizi oluşturabilir ve bir C++ bileşeninde hesaplama yoğun uygulama mantığını gerçekleştirebilirsiniz. Arka planda bu hesaplama yoğunluklu işlemleri gerçekleştirme özelliği, UI 'nizi yanıt vermeye yönelik önemli bir faktördür. `task`Sınıfı c++ ' a özel olduğundan, zaman uyumsuz işlemleri diğer bileşenlere (C++ dışındaki dillerde yazılmış olabilecek) iletmek için bir Windows çalışma zamanı arabirimi kullanmanız gerekir. Windows Çalışma Zamanı, zaman uyumsuz işlemleri temsil etmek için kullanabileceğiniz dört arabirim sağlar:

[Windows:: Foundation:: IAsyncAction](/uwp/api/windows.foundation.iasyncaction)<br/>
Zaman uyumsuz bir eylemi temsil eder.

[Windows:: Foundation:: IAsyncActionWithProgress\<TProgress>](/uwp/api/windows.foundation.iasyncactionwithprogress-1)<br/>
İlerlemeyi raporlayan bir zaman uyumsuz eylemi temsil eder.

[Windows:: Foundation:: IAsyncOperation\<TResult>](/uwp/api/windows.foundation.iasyncoperation-1)<br/>
Bir sonuç döndüren zaman uyumsuz bir işlemi temsil eder.

[Windows:: Foundation:: IAsyncOperationWithProgress\<TResult, TProgress>](/uwp/api/windows.foundation.iasyncoperationwithprogress-2)<br/>
Bir sonuç döndüren ve raporların ilerlemesini veren zaman uyumsuz bir işlemi temsil eder.

Bir *eylemin* kavramı, zaman uyumsuz görevin bir değer üretmeyeceği anlamına gelir (döndüren bir işlevi düşünün `void` ). Bir *işlemin* kavramı, zaman uyumsuz görevin bir değer üretmesi anlamına gelir. *İlerleme* kavramı, görevin işlem iletilerini çağırana bildirebileceği anlamına gelir. JavaScript, .NET Framework ve Visual C++ her biri, ABı sınırında kullanılmak üzere bu arabirimlerin örneklerini oluşturmak için kendi yolunu sağlar. Visual C++ için PPL [eşzamanlılık:: create_async](reference/concurrency-namespace-functions.md#create_async) işlevi sağlar. Bu işlev, bir görevin tamamlandığını temsil eden Windows Çalışma Zamanı zaman uyumsuz bir eylem veya işlem oluşturur. `create_async`İşlev bir iş işlevi (genellikle bir lambda ifadesi) alır, dahili olarak bir `task` nesne oluşturur ve bu görevi dört zaman uyumsuz Windows çalışma zamanı arabirimlerinden birine kaydırır.

> [!NOTE]
> `create_async`Yalnızca başka bir dilden veya başka bir Windows çalışma zamanı bileşeninden erişilebilen işlevsellik oluşturmanız gerektiğinde kullanın. `task`İşlemin hem işlem hem de aynı bileşendeki C++ kodu tarafından tüketildiğini bildiğiniz zaman doğrudan sınıfını kullanın.

Dönüş türü, `create_async` bağımsız değişkenlerinin türüne göre belirlenir. Örneğin, çalışma işleviniz bir değer döndürmezse ve ilerleme bildirmezse, `create_async` döndürür `IAsyncAction` . Çalışma işleviniz bir değer döndürmezse ve ayrıca ilerlemeyi raporladığında, `create_async` döndürür `IAsyncActionWithProgress` . İlerlemeyi raporlamak için, iş işlevinizin parametresi olarak bir [eşzamanlılık::p rogress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) nesnesi sağlayın. İlerlemeyi bildirebilme özelliği, ne kadar çalışma miktarı ve ne kadar devam ettiğini (örneğin, yüzde olarak) rapor etmenizi sağlar. Ayrıca, sonuçları kullanılabilir hale geldiğinde rapor etmenizi sağlar.

`IAsyncAction`, `IAsyncActionWithProgress<TProgress>`, `IAsyncOperation<TResult>` ve `IAsyncActionOperationWithProgress<TProgress, TProgress>` arabirimlerinin her biri zaman uyumsuz işlemi iptal etmenizi sağlayan bir `Cancel` metodu sunar. `task`Sınıfı, iptal belirteçleriyle birlikte kullanılır. İşi iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı bu belirtece abone olan yeni çalışmayı başlatmaz. Zaten etkin olan iş iptal belirtecini izleyebilir ve ne zaman durabilir. Bu mekanizma [, PPL 'deki belge iptalinden](cancellation-in-the-ppl.md)daha ayrıntılı olarak açıklanmıştır. Görev iptalini Windows Çalışma Zamanı `Cancel` yöntemleriyle iki şekilde bağlayabilirsiniz. İlk olarak, `create_async` bir [eşzamanlılık:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) nesnesi almak için geçirdiğiniz çalışma işlevini tanımlayabilirsiniz. `Cancel`Yöntemi çağrıldığında, bu iptal belirteci iptal edilir ve normal iptal kuralları `task` çağrıyı destekleyen temel nesne için geçerlidir `create_async` . Bir `cancellation_token` nesnesi belirtmezseniz, temel alınan `task` nesnesi örtük olarak bir nesne tanımlar. Çalışma işlevinizde bir iptali işbirliği halinde olarak yanıtlamanız gerektiğinde bir `cancellation_token` nesnesi tanımlayın. [Örnek: c++ ve XAML ile bir Windows çalışma zamanı uygulamasında yürütmeyi denetlemek](#example-app) , C# ve özel bir Windows çalışma zamanı C++ BILEŞENI kullanan XAML ile bir evrensel WINDOWS platformu (UWP) uygulamasında iptali gerçekleştirmeye ilişkin bir örnek gösterir.

> [!WARNING]
> Bir görev devamlılığı zincirinde, her zaman durumu temizleyin ve iptal belirteci iptal edildiğinde [eşzamanlılık:: cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) çağırın. Çağırmak yerine erken geri dönerseniz `cancel_current_task` , işlem iptal edildi durumu yerine tamamlanmış duruma geçer.

Aşağıdaki tabloda, uygulamanızda zaman uyumsuz işlemleri tanımlamak için kullanabileceğiniz birleşimler özetlenmektedir.

|Bu Windows Çalışma Zamanı arabirimini oluşturmak için|Bu türü buradan döndür`create_async`|Örtük bir iptal belirteci kullanmak için bu parametre türlerini iş işlevinize geçirin|Açık bir iptal belirteci kullanmak için bu parametre türlerini iş işlevinize geçirin|
|----------------------------------------------------------------------------------|------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|`IAsyncAction`|`void` veya `task<void>`|(yok)|(`cancellation_token`)|
|`IAsyncActionWithProgress<TProgress>`|`void` veya `task<void>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|
|`IAsyncOperation<TResult>`|`T` veya `task<T>`|(yok)|(`cancellation_token`)|
|`IAsyncActionOperationWithProgress<TProgress, TProgress>`|`T` veya `task<T>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|

`task`İşleve geçirdiğiniz iş işlevinden bir değer veya nesne döndürebilirsiniz `create_async` . Bu çeşitlemeler farklı davranışlar üretir. Bir değer döndürdüğünüzde, çalışma işlevi bir `task` arka plan iş parçacığında çalıştırılabilmesi için bir öğesine sarmalanır. Ayrıca, temeldeki `task` bir örtük iptal belirteci kullanır. Buna karşılık, bir nesnesi döndürdüğünüzde, `task` iş işlevi zaman uyumlu olarak çalışır. Bu nedenle, bir nesnesi döndürdüğünüzde `task` , iş işlevinizdeki uzun işlemlerin, uygulamanızın yanıt vermiyor olarak kalmasını sağlamak için görev olarak da çalıştığından emin olun. Ayrıca, temeldeki `task` bir örtük iptal belirteci kullanmaz. Bu nedenle, `cancellation_token` öğesinden bir nesne döndürdüğünüzde iptal için desteğe ihtiyacınız varsa, bir nesneyi almak için iş işlevinizi tanımlamanız gerekir `task` `create_async` .

Aşağıdaki örnek, `IAsyncAction` başka bir Windows çalışma zamanı bileşeni tarafından tüketilen bir nesne oluşturmanın çeşitli yollarını gösterir.

[!code-cpp[concrt-windowsstore-primes#100](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_1.cpp)]

## <a name="example-creating-a-c-windows-runtime-component-and-consuming-it-from-c"></a><a name="example-component"></a>Örnek: C++ Windows Çalışma Zamanı bileşeni oluşturma ve C 'den kullanma\#

İşlem yoğunluklu işlemleri gerçekleştirmek için UI ve C++ Windows Çalışma Zamanı bileşeni tanımlamak üzere XAML ve C# kullanan bir uygulamayı düşünün. Bu örnekte, C++ bileşeni belirli bir aralıktaki hangi sayıların asal olduğunu hesaplar. Dört Windows Çalışma Zamanı zaman uyumsuz görev arabirimleri arasındaki farkları göstermek için, Visual Studio 'da, **boş bir çözüm** oluşturup dosyayı adlandırarak başlatın `Primes` . Ardından **Windows çalışma zamanı bileşen** projesi çözümüne ekleyin ve bunu yeniden adlandırın `PrimesLibrary` . Oluşturulan C++ üst bilgi dosyasına aşağıdaki kodu ekleyin (Bu örnek, bu örnekte Class1. h 'yi, Primes. h olarak yeniden adlandırır). Her `public` Yöntem dört zaman uyumsuz arabirimden birini tanımlar. Bir değer döndüren yöntemler bir [Windows:: Foundation:: Collections:: IVector \<int> ](/uwp/api/windows.foundation.collections.ivector-1) nesnesi döndürür. İlerlemeyi rapor eden yöntemler, `double` tamamlanan genel çalışmanın yüzdesini tanımlayan değerler üretir.

[!code-cpp[concrt-windowsstore-primes#1](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_2.h)]

> [!NOTE]
> Kurala göre, Windows Çalışma Zamanı zaman uyumsuz yöntem adları genellikle "Async" ile biter.

Oluşturulan C++ kaynak dosyasına aşağıdaki kodu ekleyin (Bu örnek, Class1. cpp öğesini Primes. cpp olarak yeniden adlandırır). `is_prime`İşlevi, girişinin asal olup olmadığını belirler. Kalan Yöntemler `Primes` sınıfını uygular. Her çağrısı `create_async` , çağrıldığı yöntemiyle uyumlu bir imza kullanır. Örneğin,,, `Primes::ComputePrimesAsync` `IAsyncAction` için sağlanmış olan çalışma işlevi `create_async` bir değer döndürmez ve `progress_reporter` parametresi olarak bir nesnesi almaz.

[!code-cpp[concrt-windowsstore-primes#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_3.cpp)]

Her yöntem ilk olarak giriş parametrelerinin negatif olmamasını sağlamak için doğrulama gerçekleştirir. Bir giriş değeri negatifse Yöntem [Platform:: InvalidArgumentException](../../cppcx/platform-invalidargumentexception-class.md)oluşturur. Hata işleme bu bölümde daha sonra açıklanmaktadır.

Bu yöntemleri UWP uygulamasından kullanmak için Visual Studio çözümüne ikinci bir proje eklemek üzere Visual C# **boş uygulama (XAML)** şablonunu kullanın. Bu örnek, projeyi adlandırır `Primes` . Ardından, `Primes` projeden projeye bir başvuru ekleyin `PrimesLibrary` .

Aşağıdaki kodu MainPage. xaml öğesine ekleyin. Bu kod, C++ bileşenini çağırabilmeniz ve sonuçları görüntüedebilmeniz için Kullanıcı arabirimini tanımlar.

[!code-xml[concrt-windowsstore-primes#3](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_4.xaml)]

Aşağıdaki kodu `MainPage` MainPage. xaml içindeki sınıfına ekleyin. Bu kod bir `Primes` nesne ve düğme olay işleyicilerini tanımlar.

[!code-cs[concrt-windowsstore-primes#4](../../parallel/concrt/codesnippet/csharp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_5.cs)]

Bu yöntemler, `async` `await` zaman uyumsuz işlemler tamamlandıktan sonra Kullanıcı arabirimini güncelleştirmek için ve anahtar sözcüklerini kullanır. UWP uygulamalarında zaman uyumsuz kodlama hakkında daha fazla bilgi için bkz. [Threading and Async Programming](/windows/uwp/threading-async).

`getPrimesCancellation`Ve `cancelGetPrimes` yöntemleri, kullanıcının işlemi iptal edebilmesini sağlamak için birlikte çalışır. Kullanıcı **iptal** düğmesini seçtiğinde, `cancelGetPrimes` yöntemi [IAsyncOperationWithProgress \<TResult, TProgress> :: Cancel](/uwp/api/windows.foundation.iasyncinfo.cancel) öğesini çağırarak işlemi iptal eder. Temel alınan zaman uyumsuz işlemi yöneten Eşzamanlılık Çalışma Zamanı, iptalinin tamamlandığını bildirmek için Windows Çalışma Zamanı tarafından yakalanan bir iç özel durum türü oluşturur. İptal modeli hakkında daha fazla bilgi için bkz. [iptal](../../parallel/concrt/cancellation-in-the-ppl.md).

> [!IMPORTANT]
> PPL 'nin işlemi iptal ettiği Windows Çalışma Zamanı doğru bir şekilde rapor kurmasını sağlamak için bu iç özel durum türünü yakalamayın. Diğer bir deyişle, tüm özel durumları da yakalamayın ( `catch (...)` ). Tüm özel durumları yakalarsanız, Windows Çalışma Zamanı iptal işlemini tamamlayabilmesi için özel durumu yeniden oluşturun.

Aşağıdaki çizimde `Primes` her bir seçenek seçildikten sonra uygulama gösterilmektedir.

![Windows Çalışma Zamanı Primes uygulaması](../../parallel/concrt/media/concrt_windows_primes.png "Windows Çalışma Zamanı Primes uygulaması")

`create_async`Diğer diller tarafından tüketilen zaman uyumsuz görevler oluşturmak için kullanan bir örnek için, bkz. [Bing Haritalar seyahat Iyileştirici örneğinde C++ kullanma](/previous-versions/windows/apps/hh699891(v=vs.140)).

## <a name="controlling-the-execution-thread"></a><a name="exethread"></a>Yürütme Iş parçacığını denetleme

Windows Çalışma Zamanı COM iş parçacığı modelini kullanır. Bu modelde, nesneler kendi eşitlemesini nasıl işleydiklerine bağlı olarak farklı apartmanlar halinde barındırılır. İş parçacığı güvenli nesneleri, çok iş parçacıklı grupta (MTA) barındırılır. Tek bir iş parçacığı tarafından erişilmesi gereken nesneler tek iş parçacıklı bir grupta (STA) barındırılır.

Bir kullanıcı arabirimine sahip bir uygulamada, ASTA (Application STA) iş parçacığı, pencere iletilerinin pompadan sorumludur ve işlemdeki tek iş parçacığıdır ve STA barındırılan UI denetimlerini güncelleştirebilir. Bunun iki sonucu vardır. İlk olarak, uygulamanın yanıt vermeye devam etmesi için tüm CPU yoğunluklu ve g/ç işlemlerinin ASTA iş parçacığında çalıştırılmamalıdır. İkincisi, Kullanıcı arabirimini güncelleştirmek için arka plan iş parçacıklarından gelen sonuçların ASTA 'ya geri sıralanması gerekir. Bir C++ UWP uygulamasında `MainPage` ve DIĞER XAML sayfaları ATSA 'da çalışır. Bu nedenle, ASTA 'da belirtilen görev devamlılığı varsayılan olarak çalıştırılır, böylece doğrudan devamlılık gövdesinde denetimleri güncelleştirebilirsiniz. Bununla birlikte, bir görevi başka bir görevde yuvadıysanız, bu iç içe görev üzerindeki devamlılıklar MTA 'da çalışır. Bu nedenle, bu Devamlılıkların hangi bağlamda çalıştırılacağını açıkça belirtmeyeceğinizi göz önünde bulundurmanız gerekir.

Gibi zaman uyumsuz bir işlemden oluşturulan bir görev `IAsyncOperation<TResult>` , iş parçacığı ayrıntılarını yoksaymaya yardımcı olabilecek özel semantikler kullanır. Bir işlem, bir arka plan iş parçacığında çalışabilse de (veya hiç bir iş parçacığı tarafından yedeklenmez), devamlılığı varsayılan olarak, devamlılık operasyonlarını Başlatan apartman üzerinde (diğer bir deyişle, çağıran gruptan `task::then` ) çalışır. Devamlılığın Yürütme bağlamını denetlemek için [concurrency:: task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfını kullanabilirsiniz. Nesneleri oluşturmak için bu statik yardımcı yöntemleri kullanın `task_continuation_context` :

- Devamlılığın arka plan iş parçacığında çalıştığını belirtmek için [concurrency:: task_continuation_context:: use_arbitrary](reference/task-continuation-context-class.md#use_arbitrary) kullanın.

- Devamlılığın çağıran iş parçacığında çalıştığını belirtmek için [concurrency:: task_continuation_context:: use_current](reference/task-continuation-context-class.md#use_current) kullanın `task::then` .

`task_continuation_context`Görevin yürütme bağlamını açıkça denetlemek için bir nesne [:: then](reference/task-class.md#then) yöntemine geçirebilirsiniz veya görevi başka bir gruba geçirebilir ve sonra `task::then` Yürütme bağlamını örtülü olarak denetlemek için yöntemini çağırabilirsiniz.

> [!IMPORTANT]
> UWP uygulamalarının ana UI iş parçacığı STA altında çalıştığı için, bu STA 'da oluşturduğunuz devamlılıklar, STA 'da varsayılan olarak çalışır. Buna uygun olarak, MTA 'da oluşturduğunuz devamlılıklar MTA üzerinde çalışır.

Aşağıdaki bölümde, diskten bir dosyayı okuyan bir uygulama gösterilmektedir, bu dosyadaki en yaygın kelimeleri bulur ve ardından Kullanıcı arabirimindeki sonuçları gösterir. Kullanıcı arabirimini güncelleştiren son işlem, UI iş parçacığında gerçekleşir.

> [!IMPORTANT]
> Bu davranış, UWP uygulamalarına özeldir. Masaüstü uygulamaları için Devamlılıkların nerede çalışacağını kontrol edersiniz. Bunun yerine Zamanlayıcı, her devamlılığın çalıştırılacağı bir çalışan iş parçacığı seçer.

> [!IMPORTANT]
> [Concurrency:: task::](reference/task-class.md#wait) STA üzerinde çalışan devamlılık gövdesinde bekle. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](../../parallel/concrt/reference/invalid-operation-class.md) oluşturur, çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, görev tabanlı devamlılık içinde öncül görevin sonucunu almak için [concurrency:: task:: Get](reference/task-class.md#get) yöntemini çağırabilirsiniz.

## <a name="example-controlling-execution-in-a-windows-runtime-app-with-c-and-xaml"></a><a name="example-app"></a>Örnek: C++ ve XAML ile Windows Çalışma Zamanı uygulamasında yürütmeyi denetleme

Diskten bir dosyayı okuyan bir C++ XAML uygulamasını düşünün, bu dosyadaki en yaygın kelimeleri bulur ve ardından Kullanıcı arabirimindeki sonuçları gösterir. Bu uygulamayı oluşturmak için, Visual Studio 'da, **boş bir uygulama (Evrensel Windows)** projesi oluşturup dosyayı adlandırarak başlatın `CommonWords` . Uygulama bildiriminizde, uygulamanın Belgeler klasörüne erişmesini sağlamak için **belge kitaplığı** özelliğini belirtin. Ayrıca, uygulama bildiriminin bildirimler bölümüne metin (. txt) dosya türünü de ekleyin. Uygulama özellikleri ve bildirimler hakkında daha fazla bilgi için bkz. [Windows uygulamalarının paketlenmesi, dağıtılması ve sorgu](/windows/win32/appxpkg/appx-portal).

`Grid`MainPage. xaml içindeki öğesini bir `ProgressRing` öğe ve bir öğe içerecek şekilde güncelleştirin `TextBlock` . `ProgressRing`İşlemin devam ettiğini ve `TextBlock` Hesaplama sonuçlarının gösterir olduğunu gösterir.

[!code-xml[concrt-windowsstore-commonwords#1](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_6.xaml)]

Aşağıdaki `#include` deyimlerini *pch. h*öğesine ekleyin.

[!code-cpp[concrt-windowsstore-commonwords#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_7.h)]

Aşağıdaki yöntem bildirimlerini `MainPage` sınıfına ekleyin (MainPage. h).

[!code-cpp[concrt-windowsstore-commonwords#3](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_8.h)]

Aşağıdaki `using` deyimlerini MainPage. cpp öğesine ekleyin.

[!code-cpp[concrt-windowsstore-commonwords#4](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_9.cpp)]

MainPage. cpp içinde,, `MainPage::MakeWordList` `MainPage::FindCommonWords` ve `MainPage::ShowResults` yöntemlerini uygulayın. `MainPage::MakeWordList`Ve `MainPage::FindCommonWords` hesaplama yoğun işlemler gerçekleştirir. `MainPage::ShowResults`Yöntemi, Kullanıcı arabirimindeki hesaplamanın sonucunu görüntüler.

[!code-cpp[concrt-windowsstore-commonwords#5](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_10.cpp)]

Oluşturucuyu, `MainPage` Kullanıcı arabiriminde ortak kelimeleri barındırıcı tarafından görünen bir devamlılık görevlerinin zinciri oluşturacak *The Iliad* şekilde değiştirin. Metni tek tek sözcüklere bölmek ve ortak sözcükleri bulmak için ilk iki devamlılık görevi zaman alıcı olabilir ve bu nedenle açıkça arka planda çalışacak şekilde ayarlanır. Kullanıcı arabirimini güncelleştiren son devamlılık görevi, devamlılık bağlamı olmadığını belirtir ve bu nedenle apartman iş parçacığı kurallarını izler.

[!code-cpp[concrt-windowsstore-commonwords#6](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_11.cpp)]

> [!NOTE]
> Bu örnek, yürütme bağlamlarının nasıl belirtileceğini ve devamlılık zincirinin nasıl oluşturulacağını gösterir. Varsayılan olarak, bir zaman uyumsuz işlemden oluşturulan bir görevin devamlılığını çağıran Apartment üzerinde çalıştırmasını hatırlayın `task::then` . Bu nedenle, bu örnek, `task_continuation_context::use_arbitrary` bir arka plan iş parçacığında kullanıcı arabirimini içermeyen işlemlerin gerçekleştirilmesini belirtmek için kullanır.

Aşağıdaki çizimde uygulamanın sonuçları gösterilmektedir `CommonWords` .

![Windows Çalışma Zamanı CommonWords uygulaması](../../parallel/concrt/media/concrt_windows_common_words.png "Windows Çalışma Zamanı CommonWords uygulaması")

Bu örnekte, `task` tarafından desteklenen nesneler `create_async` örtük bir iptal belirteci kullandığından iptali desteklemek mümkündür. `cancellation_token`Görevleriniz, İptalin bir şekilde iptal 'e yanıt vermesi gerekiyorsa, bir nesneyi almak için çalışma işlevinizi tanımlayın. PPL 'de iptal hakkında daha fazla bilgi için bkz [. PPL 'de iptal](cancellation-in-the-ppl.md)

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)
