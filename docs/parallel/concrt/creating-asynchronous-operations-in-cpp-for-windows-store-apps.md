---
title: UWP uygulamaları için içinde C++ zaman uyumsuz işlemler oluşturma
ms.date: 11/19/2018
helpviewer_keywords:
- Windows 8.x apps, creating C++ async operations
- Creating C++ async operations
ms.assetid: a57cecf4-394a-4391-a957-1d52ed2e5494
ms.openlocfilehash: 2ceb22afa5e6d071c1cb8dae79327eaaf08e3ee1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445113"
---
# <a name="creating-asynchronous-operations-in-c-for-uwp-apps"></a>UWP uygulamaları için içinde C++ zaman uyumsuz işlemler oluşturma

Bu belgede, bir Evrensel Windows Çalışma Zamanı (UWP) uygulamasında Windows ThreadPool tabanlı zaman uyumsuz işlemler oluşturmak için görev sınıfını kullandığınızda göz önünde bulundurmanız gereken bazı önemli noktaları açıklanmaktadır.

Zaman uyumsuz programlama kullanımı, uygulamaların kullanıcı girişine yanıt vermeye devam etmesini sağladığından Windows Çalışma Zamanı uygulama modelinde bir anahtar bileşendir. UI iş parçacığını engellemeden uzun süre çalışan bir görev başlatabilir ve görevin sonuçlarını daha sonra alabilirsiniz. Ayrıca görevleri iptal edebilir ve görevler arka planda çalıştırıldığında ilerleme bildirimleri alabilirsiniz. [' Deki C++ belge zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) , UWP uygulamaları oluşturmak için görselde C++ bulunan zaman uyumsuz düzene genel bir bakış sağlar. Bu belge, zaman uyumsuz Windows Çalışma Zamanı işlemleri için hem tüketme hem de oluşturma hakkında öğretir. Bu bölümde, başka bir Windows Çalışma Zamanı bileşeni tarafından tüketilen ve zaman uyumsuz çalışmanın nasıl yürütüleceğini denetleyen zaman uyumsuz işlemler oluşturmak için ppltasks. h içindeki türlerin nasıl kullanılacağı açıklanmaktadır. Ayrıca, ve XAML kullanan C++ bir Windows çalışma zamanı uygulaması olan Tepo 'da zaman uyumsuz işlemleri uygulamak için görev sınıfını nasıl kullandığımızda bilgi edinmek için, [Po 'da zaman uyumsuz programlama düzenlerini ve Ipuçlarını (Windows MAĞAZASı uygulamaları ve XAML kullanarak C++ )](/previous-versions/windows/apps/jj160321(v=win.10)) okumayı düşünün.

> [!NOTE]
> Bir UWP uygulamasında [paralel Desenler kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (ppl) ve [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanabilirsiniz. Ancak, Görev Zamanlayıcı veya Kaynak Yöneticisi kullanamazsınız. Bu belgede, PPL 'nin yalnızca bir UWP uygulaması tarafından kullanılabilen ve bir masaüstü uygulamasına yönelik olarak sağladığı ek özellikler açıklanmaktadır.

## <a name="key-points"></a>Önemli noktalar

- Diğer bileşenler tarafından kullanılabilecek (dışındaki dillerde yazılmış olabilecek C++) zaman uyumsuz işlemler oluşturmak için [concurrency:: create_async](reference/concurrency-namespace-functions.md#create_async) kullanın.

- Zaman uyumsuz işlemlerinizi çağıran bileşenlere ilerleme bildirimleri bildirmek için [eşzamanlılık::p rogress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) kullanın.

- İç zaman uyumsuz işlemlerin iptal edilmesine olanak tanımak için iptal belirteçlerini kullanın.

- `create_async` işlevinin davranışı, kendisine geçirilen çalışma işlevinin dönüş türüne bağlıdır. Bir görevi döndüren (`task<T>` ya da `task<void>`) bir iş işlevi `create_async`adlı bağlamda zaman uyumlu olarak çalışır. `T` veya `void` döndüren bir iş işlevi, rastgele bir bağlamda çalışır.

- Daha sonra çalışan bir görev zinciri oluşturmak için [concurrency:: task:: then](reference/task-class.md#then) yöntemini kullanabilirsiniz. UWP uygulamasında, bir görevin devamlılıkları için varsayılan bağlam, bu görevin nasıl oluşturulduğuna bağlıdır. Görev, görev oluşturucusuna zaman uyumsuz bir eylem geçirilerek veya zaman uyumsuz bir eylem döndüren bir lambda ifadesi geçirerek oluşturulduysa, bu görevin tüm devamlılıkları için varsayılan bağlam geçerli bağlamdır. Görev zaman uyumsuz bir eylemden oluşturulmuşsa, varsayılan olarak görevin devamlılıkları için rastgele bir bağlam kullanılır. Varsayılan bağlamı [concurrency:: task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfıyla geçersiz kılabilirsiniz.

## <a name="in-this-document"></a>Bu belgede

- [Zaman uyumsuz Işlemler oluşturma](#create-async)

- [Örnek: C++ Windows çalışma zamanı bileşeni oluşturma](#example-component)

- [Yürütme Iş parçacığını denetleme](#exethread)

- [Örnek: ve XAML ile C++ Windows çalışma zamanı uygulamasında yürütmeyi denetleme](#example-app)

## <a name="create-async"></a>Zaman uyumsuz Işlemler oluşturma

Paralel Desenler kitaplığındaki (PPL) görev ve devamlılık modelini, önceki görev tamamlandığında çalışan ek görevlerin yanı sıra arka plan görevlerini tanımlamak için de kullanabilirsiniz. Bu işlevsellik [concurrency:: Task](../../parallel/concrt/reference/task-class.md) sınıfı tarafından sağlanır. Bu model ve `task` sınıfı hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Windows Çalışma Zamanı, yalnızca özel bir işletim sistemi ortamında çalışan UWP uygulamaları oluşturmak için kullanabileceğiniz bir programlama arabirimidir. Bu uygulamalar, yetkili işlevleri, veri türlerini ve cihazları kullanır ve Microsoft Store dağıtılır. Windows Çalışma Zamanı, *uygulama Ikili arabirimi* (ABI) tarafından temsil edilir. ABı, Windows Çalışma Zamanı API 'Lerinin görsel C++gibi programlama dillerini kullanabilmesini sağlayan temel bir ikili sözleşmedir.

Windows Çalışma Zamanı kullanarak, çeşitli programlama dillerinin en iyi özelliklerini kullanabilir ve bunları tek bir uygulamada birleştirebilirsiniz. Örneğin, Kullanıcı arabiriminizi JavaScript 'te oluşturabilir ve bir C++ bileşende yoğun hesaplama gerektiren uygulama mantığını gerçekleştirebilirsiniz. Arka planda bu hesaplama yoğunluklu işlemleri gerçekleştirme özelliği, UI 'nizi yanıt vermeye yönelik önemli bir faktördür. `task` sınıfı öğesine C++özgü olduğundan, zaman uyumsuz işlemleri diğer bileşenlere (dışındaki dillerde yazılmış olabilecek C++) iletmek için bir Windows çalışma zamanı arabirimi kullanmanız gerekir. Windows Çalışma Zamanı, zaman uyumsuz işlemleri temsil etmek için kullanabileceğiniz dört arabirim sağlar:

[Windows:: Foundation:: IAsyncAction](/uwp/api/windows.foundation.iasyncaction)<br/>
Zaman uyumsuz bir eylemi temsil eder.

[Windows:: Foundation:: IAsyncActionWithProgress\<TProgress >](/uwp/api/Windows.Foundation.IAsyncActionWithProgress_TProgress_)<br/>
İlerlemeyi raporlayan bir zaman uyumsuz eylemi temsil eder.

[Windows:: Foundation:: IAsyncOperation\<TResult >](/uwp/api/windows.foundation.iasyncoperation_tresult_)<br/>
Bir sonuç döndüren zaman uyumsuz bir işlemi temsil eder.

[Windows:: Foundation:: IAsyncOperationWithProgress\<TResult, TProgress >](/uwp/api/windows.foundation.iasyncoperationwithprogress_tresult_tprogress_)<br/>
Bir sonuç döndüren ve raporların ilerlemesini veren zaman uyumsuz bir işlemi temsil eder.

Bir *eylemin* kavramı, zaman uyumsuz görevin bir değer üretmeyeceği anlamına gelir (`void`döndüren bir işlevi düşünün). Bir *işlemin* kavramı, zaman uyumsuz görevin bir değer üretmesi anlamına gelir. *İlerleme* kavramı, görevin işlem iletilerini çağırana bildirebileceği anlamına gelir. JavaScript, .NET Framework ve görsel C++ her bırı, ABI sınırında kullanılmak üzere bu arabirimlerin örneklerini oluşturmak için kendi yolunu sağlar. Görsel C++için ppl, [concurrency:: create_async](reference/concurrency-namespace-functions.md#create_async) işlevini sağlar. Bu işlev, bir görevin tamamlandığını temsil eden Windows Çalışma Zamanı zaman uyumsuz bir eylem veya işlem oluşturur. `create_async` işlevi bir iş işlevini (genellikle bir lambda ifadesi) alır, dahili olarak bir `task` nesnesi oluşturur ve bu görevi dört zaman uyumsuz Windows Çalışma Zamanı arabirimlerinden birine kaydırır.

> [!NOTE]
> Yalnızca başka bir dilden veya başka bir Windows Çalışma Zamanı bileşeninden erişilebilen işlevsellik oluşturmanız gerektiğinde `create_async` kullanın. İşlemin hem aynı bileşen içindeki kod tarafından C++ üretildiğini hem de tüketildiğini bildiğiniz durumlarda `task` sınıfını kullanın.

`create_async` dönüş türü, bağımsız değişkenlerinin türüne göre belirlenir. Örneğin, çalışma işleviniz bir değer döndürmezse ve ilerleme bildirmezse `create_async` `IAsyncAction`döndürür. Çalışma işleviniz bir değer döndürmezse ve ayrıca ilerleme durumu bildirirse, `create_async` `IAsyncActionWithProgress`döndürür. İlerlemeyi raporlamak için, iş işlevinizin parametresi olarak bir [eşzamanlılık::p rogress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) nesnesi sağlayın. İlerlemeyi bildirebilme özelliği, ne kadar çalışma miktarı ve ne kadar devam ettiğini (örneğin, yüzde olarak) rapor etmenizi sağlar. Ayrıca, sonuçları kullanılabilir hale geldiğinde rapor etmenizi sağlar.

`IAsyncAction`, `IAsyncActionWithProgress<TProgress>`, `IAsyncOperation<TResult>` ve `IAsyncActionOperationWithProgress<TProgress, TProgress>` arabirimlerinin her biri zaman uyumsuz işlemi iptal etmenizi sağlayan bir `Cancel` metodu sunar. `task` sınıfı, iptal belirteçleriyle birlikte kullanılır. İşi iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı bu belirtece abone olan yeni çalışmayı başlatmaz. Zaten etkin olan iş iptal belirtecini izleyebilir ve ne zaman durabilir. Bu mekanizma [, PPL 'deki belge iptalinden](cancellation-in-the-ppl.md)daha ayrıntılı olarak açıklanmıştır. Windows Çalışma Zamanı`Cancel` yöntemleriyle görev iptalini iki şekilde bağlayabilirsiniz. İlk olarak, bir [eşzamanlılık:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) nesnesi almak için `create_async` geçirdiğiniz iş işlevini tanımlayabilirsiniz. `Cancel` yöntemi çağrıldığında, bu iptal belirteci iptal edilir ve normal iptal kuralları `create_async` çağrısını destekleyen temel `task` nesnesi için geçerlidir. Bir `cancellation_token` nesnesi belirtmezseniz, temel alınan `task` nesnesi örtük olarak bir nesne tanımlar. Çalışma işlevinizde bir iptali işbirliği halinde olarak yanıtlamanız gerektiğinde bir `cancellation_token` nesnesi tanımlayın. Bölüm [örneği: C++ ve xaml ile bir Windows çalışma zamanı uygulamasında yürütmeyi denetlemek](#example-app) , ile C# Evrensel Windows platformu (UWP) uygulamasında ve özel bir Windows çalışma zamanı C++ bileşeni kullanan xaml 'de iptali gerçekleştirmeye yönelik bir örnek gösterir.

> [!WARNING]
> Bir görev devamlılığı zincirinde, her zaman durumu temizleyin ve iptal belirteci iptal edildiğinde [eşzamanlılık:: cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) çağırın. `cancel_current_task`çağırmak yerine erken geri dönerseniz, işlem iptal edildi durumuna geçiş yerine tamamlanmış duruma geçer.

Aşağıdaki tabloda, uygulamanızda zaman uyumsuz işlemleri tanımlamak için kullanabileceğiniz birleşimler özetlenmektedir.

|Bu Windows Çalışma Zamanı arabirimini oluşturmak için|Bu türü `create_async` döndür|Örtük bir iptal belirteci kullanmak için bu parametre türlerini iş işlevinize geçirin|Açık bir iptal belirteci kullanmak için bu parametre türlerini iş işlevinize geçirin|
|----------------------------------------------------------------------------------|------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|`IAsyncAction`|`void` veya `task<void>`|seçim|(`cancellation_token`)|
|`IAsyncActionWithProgress<TProgress>`|`void` veya `task<void>`|(`progress_reporter`)|(`progress_reporter``cancellation_token`)|
|`IAsyncOperation<TResult>`|`T` veya `task<T>`|seçim|(`cancellation_token`)|
|`IAsyncActionOperationWithProgress<TProgress, TProgress>`|`T` veya `task<T>`|(`progress_reporter`)|(`progress_reporter``cancellation_token`)|

`create_async` işlevine geçirdiğiniz iş işlevinden bir değer veya `task` nesnesi döndürebilirsiniz. Bu çeşitlemeler farklı davranışlar üretir. Bir değer döndürdüğünüzde, bir arka plan iş parçacığında çalıştırılabilmesi için iş işlevi bir `task` sarmalanır. Ayrıca, temeldeki `task` örtük bir iptal belirteci kullanır. Buna karşılık, bir `task` nesnesi döndürtakdirde, iş işlevi zaman uyumlu olarak çalışır. Bu nedenle, bir `task` nesnesi döndürürler, iş işlevinizdeki tüm uzun işlemlerin, uygulamanızın yanıt vermiyor olarak kalmasını sağlamak için görev olarak da çalıştığından emin olun. Ayrıca, temeldeki `task` örtük bir iptal belirteci kullanmaz. Bu nedenle, `create_async`bir `task` nesnesi döndürdüğünüzde iptal için desteğe ihtiyacınız varsa, `cancellation_token` nesne almak için iş işlevinizi tanımlamanız gerekir.

Aşağıdaki örnek, başka bir Windows Çalışma Zamanı bileşeni tarafından tüketilen `IAsyncAction` nesne oluşturmanın çeşitli yollarını gösterir.

[!code-cpp[concrt-windowsstore-primes#100](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_1.cpp)]

## <a name="example-component"></a>Örnek: C++ Windows çalışma zamanı bileşen oluşturma ve bunu C 'den kullanma\#

İşlem yoğunluklu işlemleri gerçekleştirmek için XAML kullanan C# ve Kullanıcı arabirimini ve bir C++ Windows çalışma zamanı bileşeni tanımlamak için bir uygulama düşünün. Bu örnekte, C++ bileşen belirli bir aralıktaki hangi sayıların asal olduğunu hesaplar. Dört Windows Çalışma Zamanı zaman uyumsuz görev arabirimleri arasındaki farkları göstermek için, Visual Studio 'da, **boş bir çözüm** oluşturup `Primes`adlandırarak başlatın. Daha sonra çözüme bir **Windows çalışma zamanı bileşen** projesi ekleyin ve `PrimesLibrary`olarak adlandırın. Oluşturulan C++ üst bilgi dosyasına aşağıdaki kodu ekleyin (Bu örnek, Class1. h 'Yi Primes. h olarak yeniden adlandırır). Her `public` yöntemi, dört zaman uyumsuz arabirimden birini tanımlar. Bir değer döndüren yöntemler bir [Windows:: Foundation:: Collections:: IVector\<int >](/uwp/api/Windows.Foundation.Collections.IVector_T_) nesnesi döndürür. İlerlemeyi rapor eden yöntemler, tamamlanan genel çalışmanın yüzdesini tanımlayan `double` değerler üretir.

[!code-cpp[concrt-windowsstore-primes#1](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_2.h)]

> [!NOTE]
> Kurala göre, Windows Çalışma Zamanı zaman uyumsuz yöntem adları genellikle "Async" ile biter.

Oluşturulan C++ kaynak dosyaya aşağıdaki kodu ekleyin (Bu örnek, Class1. cpp öğesini Primes. cpp olarak yeniden adlandırır). `is_prime` işlevi, girişinin asal olup olmadığını belirler. Kalan Yöntemler `Primes` sınıfını uygular. Her `create_async` çağrısı, çağrıldığı yöntemle uyumlu bir imza kullanır. Örneğin, `Primes::ComputePrimesAsync` `IAsyncAction`döndürdüğünden `create_async` için sunulan çalışma işlevi bir değer döndürmez ve parametresi olarak bir `progress_reporter` nesnesi almaz.

[!code-cpp[concrt-windowsstore-primes#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_3.cpp)]

Her yöntem ilk olarak giriş parametrelerinin negatif olmamasını sağlamak için doğrulama gerçekleştirir. Bir giriş değeri negatifse Yöntem [Platform:: InvalidArgumentException](../../cppcx/platform-invalidargumentexception-class.md)oluşturur. Hata işleme bu bölümde daha sonra açıklanmaktadır.

Bu yöntemleri UWP uygulamasından kullanmak için, Visual Studio çözümüne ikinci bir C# proje eklemek için görsel **boş uygulama (XAML)** şablonunu kullanın. Bu örnekte projenin `Primes`adı vardır. Sonra, `Primes` projeden, `PrimesLibrary` projesine bir başvuru ekleyin.

Aşağıdaki kodu MainPage. xaml öğesine ekleyin. Bu kod, C++ bileşeni çağırabilmeniz ve sonuçları görüntüedebilmeniz için Kullanıcı arabirimini tanımlar.

[!code-xml[concrt-windowsstore-primes#3](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_4.xaml)]

Aşağıdaki kodu MainPage. xaml içindeki `MainPage` sınıfına ekleyin. Bu kod, bir `Primes` nesnesini ve düğme olay işleyicilerini tanımlar.

[!code-cs[concrt-windowsstore-primes#4](../../parallel/concrt/codesnippet/csharp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_5.cs)]

Bu yöntemler, zaman uyumsuz işlemler tamamlandıktan sonra Kullanıcı arabirimini güncelleştirmek için `async` ve `await` anahtar sözcüklerini kullanır. UWP uygulamalarında zaman uyumsuz kodlama hakkında daha fazla bilgi için bkz. [Threading and Async Programming](/windows/uwp/threading-async).

`getPrimesCancellation` ve `cancelGetPrimes` yöntemleri, kullanıcının işlemi iptal edebilmesini sağlamak için birlikte çalışır. Kullanıcı **iptal** düğmesini seçtiğinde `cancelGetPrimes` yöntemi [IAsyncOperationWithProgress\<TResult öğesini çağırır. işlemi Iptal etmek için TProgress >:: Cancel](/uwp/api/windows.foundation.iasyncinfo.cancel) . Temel alınan zaman uyumsuz işlemi yöneten Eşzamanlılık Çalışma Zamanı, iptalinin tamamlandığını bildirmek için Windows Çalışma Zamanı tarafından yakalanan bir iç özel durum türü oluşturur. İptal modeli hakkında daha fazla bilgi için bkz. [iptal](../../parallel/concrt/cancellation-in-the-ppl.md).

> [!IMPORTANT]
> PPL 'nin işlemi iptal ettiği Windows Çalışma Zamanı doğru bir şekilde rapor kurmasını sağlamak için bu iç özel durum türünü yakalamayın. Diğer bir deyişle, tüm özel durumları da yakalamayın (`catch (...)`). Tüm özel durumları yakalarsanız, Windows Çalışma Zamanı iptal işlemini tamamlayabilmesi için özel durumu yeniden oluşturun.

Aşağıdaki çizimde her bir seçenekten sonra `Primes` uygulaması gösterilmektedir.

![Windows Çalışma Zamanı Primes uygulaması](../../parallel/concrt/media/concrt_windows_primes.png "Windows Çalışma Zamanı Primes uygulaması")

Diğer diller tarafından tüketilen zaman uyumsuz görevler oluşturmak için `create_async` kullanan örnekler için bkz. PPL ile [Içinde C++ ](/previous-versions/windows/apps/hh699891(v=vs.140)) [ C++ ](https://code.msdn.microsoft.com/windowsapps/windows-8-asynchronous-08009a0d)Bing Haritalar seyahat Iyileştirici örneği ve Windows 8 zaman uyumsuz işlemlerinde kullanma.

## <a name="exethread"></a>Yürütme Iş parçacığını denetleme

Windows Çalışma Zamanı COM iş parçacığı modelini kullanır. Bu modelde, nesneler kendi eşitlemesini nasıl işleydiklerine bağlı olarak farklı apartmanlar halinde barındırılır. İş parçacığı güvenli nesneleri, çok iş parçacıklı grupta (MTA) barındırılır. Tek bir iş parçacığı tarafından erişilmesi gereken nesneler tek iş parçacıklı bir grupta (STA) barındırılır.

Bir kullanıcı arabirimine sahip bir uygulamada, ASTA (Application STA) iş parçacığı, pencere iletilerinin pompadan sorumludur ve işlemdeki tek iş parçacığıdır ve STA barındırılan UI denetimlerini güncelleştirebilir. Bunun iki sonucu vardır. İlk olarak, uygulamanın yanıt vermeye devam etmesi için tüm CPU yoğunluklu ve g/ç işlemlerinin ASTA iş parçacığında çalıştırılmamalıdır. İkincisi, Kullanıcı arabirimini güncelleştirmek için arka plan iş parçacıklarından gelen sonuçların ASTA 'ya geri sıralanması gerekir. C++ UWP uygulamasında, `MainPage` ve diğer XAML sayfaları atsa üzerinde çalışır. Bu nedenle, ASTA 'da belirtilen görev devamlılığı varsayılan olarak çalıştırılır, böylece doğrudan devamlılık gövdesinde denetimleri güncelleştirebilirsiniz. Bununla birlikte, bir görevi başka bir görevde yuvadıysanız, bu iç içe görev üzerindeki devamlılıklar MTA 'da çalışır. Bu nedenle, bu Devamlılıkların hangi bağlamda çalıştırılacağını açıkça belirtmeyeceğinizi göz önünde bulundurmanız gerekir.

`IAsyncOperation<TResult>`gibi zaman uyumsuz bir işlemden oluşturulan bir görev, iş parçacığı ayrıntılarını yoksaymaya yardımcı olabilecek özel semantikler kullanır. Bir işlem, bir arka plan iş parçacığında çalışabilse de (veya hiç bir iş parçacığı tarafından yedeklenmez), devamlılığı varsayılan olarak, devamlılık operasyonlarını Başlatan apartman üzerinde (diğer bir deyişle, `task::then`adlı gruptan) çalışır. Devamlılığın Yürütme bağlamını denetlemek için [concurrency:: task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfını kullanabilirsiniz. `task_continuation_context` nesneleri oluşturmak için bu statik yardımcı yöntemleri kullanın:

- Devamlılığın arka plan iş parçacığında çalıştığını belirtmek için [concurrency:: task_continuation_context:: use_arbitrary](reference/task-continuation-context-class.md#use_arbitrary) kullanın.

- Devamlılığın `task::then`çağıran iş parçacığında çalıştığını belirtmek için [concurrency:: task_continuation_context:: use_current](reference/task-continuation-context-class.md#use_current) kullanın.

Devam eden yürütme bağlamını açıkça denetlemek için bir `task_continuation_context` nesnesini [Task:: then](reference/task-class.md#then) yöntemine geçirebilir veya görevi başka bir gruba geçirebilir ve sonra yürütme bağlamını örtük olarak denetlemek için `task::then` metodunu çağırabilirsiniz.

> [!IMPORTANT]
> UWP uygulamalarının ana UI iş parçacığı STA altında çalıştığı için, bu STA 'da oluşturduğunuz devamlılıklar, STA 'da varsayılan olarak çalışır. Buna uygun olarak, MTA 'da oluşturduğunuz devamlılıklar MTA üzerinde çalışır.

Aşağıdaki bölümde, diskten bir dosyayı okuyan bir uygulama gösterilmektedir, bu dosyadaki en yaygın kelimeleri bulur ve ardından Kullanıcı arabirimindeki sonuçları gösterir. Kullanıcı arabirimini güncelleştiren son işlem, UI iş parçacığında gerçekleşir.

> [!IMPORTANT]
> Bu davranış, UWP uygulamalarına özeldir. Masaüstü uygulamaları için Devamlılıkların nerede çalışacağını kontrol edersiniz. Bunun yerine Zamanlayıcı, her devamlılığın çalıştırılacağı bir çalışan iş parçacığı seçer.

> [!IMPORTANT]
> [Concurrency:: task::](reference/task-class.md#wait) STA üzerinde çalışan devamlılık gövdesinde bekle. Aksi takdirde, çalışma zamanı [eşzamanlılık:: invalid_operation](../../parallel/concrt/reference/invalid-operation-class.md) oluşturur, çünkü bu yöntem geçerli iş parçacığını engeller ve uygulamanın yanıt vermemesine neden olabilir. Ancak, görev tabanlı devamlılık içinde öncül görevin sonucunu almak için [concurrency:: task:: Get](reference/task-class.md#get) yöntemini çağırabilirsiniz.

## <a name="example-app"></a>Örnek: ve XAML ile C++ Windows çalışma zamanı uygulamasında yürütmeyi denetleme

Diskten bir C++ dosyayı okuyan bir xaml uygulaması düşünün, bu dosyadaki en yaygın kelimeleri bulur ve sonra sonuçları Kullanıcı arabiriminde gösterir. Bu uygulamayı oluşturmak için, Visual Studio 'da, **boş bir uygulama (Evrensel Windows)** projesi oluşturup `CommonWords`adlandırarak başlatın. Uygulama bildiriminizde, uygulamanın Belgeler klasörüne erişmesini sağlamak için **belge kitaplığı** özelliğini belirtin. Ayrıca, uygulama bildiriminin bildirimler bölümüne metin (. txt) dosya türünü de ekleyin. Uygulama özellikleri ve bildirimler hakkında daha fazla bilgi için bkz. [Windows uygulamalarının paketlenmesi, dağıtılması ve sorgu](/windows/win32/appxpkg/appx-portal).

MainPage. xaml içindeki `Grid` öğesini bir `ProgressRing` öğesi ve bir `TextBlock` öğesi içerecek şekilde güncelleştirin. `ProgressRing` işlemin devam ettiğini ve `TextBlock` hesaplamanın sonuçlarını gösterdiğini gösterir.

[!code-xml[concrt-windowsstore-commonwords#1](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_6.xaml)]

Aşağıdaki `#include` deyimlerini *pch. h*öğesine ekleyin.

[!code-cpp[concrt-windowsstore-commonwords#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_7.h)]

Aşağıdaki yöntem bildirimlerini `MainPage` sınıfına ekleyin (MainPage. h).

[!code-cpp[concrt-windowsstore-commonwords#3](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_8.h)]

Aşağıdaki `using` deyimlerini MainPage. cpp öğesine ekleyin.

[!code-cpp[concrt-windowsstore-commonwords#4](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_9.cpp)]

MainPage. cpp ' de `MainPage::MakeWordList`, `MainPage::FindCommonWords`ve `MainPage::ShowResults` yöntemlerini uygulayın. `MainPage::MakeWordList` ve `MainPage::FindCommonWords` hesaplama yoğun işlemler gerçekleştirir. `MainPage::ShowResults` yöntemi, Kullanıcı arabirimindeki hesaplamanın sonucunu görüntüler.

[!code-cpp[concrt-windowsstore-commonwords#5](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_10.cpp)]

`MainPage` *oluşturucusunu, Kullanıcı* arabiriminde ortak kelimeleri barındırıcı tarafından görünen bir devamlılık görevlerinin zinciri oluşturacak şekilde değiştirin. Metni tek tek sözcüklere bölmek ve ortak sözcükleri bulmak için ilk iki devamlılık görevi zaman alıcı olabilir ve bu nedenle açıkça arka planda çalışacak şekilde ayarlanır. Kullanıcı arabirimini güncelleştiren son devamlılık görevi, devamlılık bağlamı olmadığını belirtir ve bu nedenle apartman iş parçacığı kurallarını izler.

[!code-cpp[concrt-windowsstore-commonwords#6](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_11.cpp)]

> [!NOTE]
> Bu örnek, yürütme bağlamlarının nasıl belirtileceğini ve devamlılık zincirinin nasıl oluşturulacağını gösterir. Varsayılan olarak, bir zaman uyumsuz işlemden oluşturulan bir görevin devamlılığını `task::then`adlı apartman üzerinde çalıştırmasını hatırlayın. Bu nedenle, bu örnek, bir arka plan iş parçacığında kullanıcı arabirimini içermeyen işlemlerin gerçekleştirilmesini belirtmek için `task_continuation_context::use_arbitrary` kullanır.

Aşağıdaki çizim `CommonWords` uygulamasının sonuçlarını gösterir.

![Windows Çalışma Zamanı CommonWords uygulaması](../../parallel/concrt/media/concrt_windows_common_words.png "Windows Çalışma Zamanı CommonWords uygulaması")

Bu örnekte, `create_async` destekleyen `task` nesneleri örtük bir iptal belirteci kullandığından iptali desteklemek mümkündür. Görevleriniz, İptalin bir şekilde iptal 'e yanıt vermesi gerekiyorsa `cancellation_token` nesne almak için iş işlevinizi tanımlayın. PPL 'de iptal hakkında daha fazla bilgi için bkz [. PPL 'de iptal](cancellation-in-the-ppl.md)

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)
