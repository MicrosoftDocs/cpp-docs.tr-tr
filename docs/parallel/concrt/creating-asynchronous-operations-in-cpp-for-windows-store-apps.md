---
title: UWP Uygulamaları için C++ Uygulamasında Zaman Uyumsuz İşlemler Oluşturma
ms.date: 11/19/2018
helpviewer_keywords:
- Windows 8.x apps, creating C++ async operations
- Creating C++ async operations
ms.assetid: a57cecf4-394a-4391-a957-1d52ed2e5494
ms.openlocfilehash: 8e1183464d3ecf9b12fabcc6fb4f1fd99b7b0083
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353401"
---
# <a name="creating-asynchronous-operations-in-c-for-uwp-apps"></a>UWP Uygulamaları için C++ Uygulamasında Zaman Uyumsuz İşlemler Oluşturma

Bu belge, Evrensel Windows Runtime (UWP) uygulamasında Windows ThreadPool tabanlı eşkenar ayin işlemleri oluşturmak için görev sınıfını kullandığınızda göz önünde bulundurulması gereken bazı önemli noktaları açıklar.

Eşzamanlı programlamanın kullanımı, uygulamaların kullanıcı girişine yanıt vermesini sağladığından, Windows Runtime uygulama modelinde önemli bir bileşendir. UI iş parçacığı engellemeden uzun süren bir görev başlatabilir ve daha sonra görevin sonuçlarını alabilirsiniz. Görevler arka planda çalışırken görevleri iptal edebilir ve ilerleme bildirimleri de alabilirsiniz. [C++'daki Asynchronous programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) belgesi, UWP uygulamaları oluşturmak için Visual C++'da bulunan eşzamanlı deseningenel görünümünü sağlar. Bu belge, eşzamanlı Windows Runtime işlemlerinin zincirlerini nasıl tüketeceklerini hem de oluşturmayı öğretir. Bu bölümde, başka bir Windows Runtime bileşeni tarafından tüketilebilen eşzamanlı işlemler üretmek için ppltasks.h'deki türlerin nasıl kullanılacağı ve eşzamanlı çalışmanın nasıl yürütüldeceğinin nasıl denetlenir. Ayrıca, C++ ve XAML kullanan bir Windows Runtime uygulaması olan Hilo'da asynchronous işlemleri uygulamak için görev sınıfını nasıl kullandığımızı öğrenmek için [Hilo'daki Async programlama desenlerini ve ipuçlarını (C++ ve XAML kullanan Windows Mağazası uygulamaları)](/previous-versions/windows/apps/jj160321(v=win.10)) okumayı da düşünün.

> [!NOTE]
> UWP uygulamasında [Paralel Desenler Kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) ve Eşzamanlı [Aracılar Kitaplığını](../../parallel/concrt/asynchronous-agents-library.md) kullanabilirsiniz. Ancak, Görev Zamanlayıcısı'nı veya Kaynak Yöneticisi'ni kullanamazsınız. Bu belge, PPL'nin sağladığı ve bir masaüstü uygulaması için değil, yalnızca bir UWP uygulaması için kullanılabilen ek özellikleri açıklar.

## <a name="key-points"></a>Önemli noktalar

- [Eşzamanlılık kullanın::create_async](reference/concurrency-namespace-functions.md#create_async) diğer bileşenler tarafından kullanılabilecek (C++dışındaki dillerde yazılmış olabilecek) eşzamanlı işlemler oluşturmak için kullanılır.

- [Eşzamanlılık::progress_reporter'ı](../../parallel/concrt/reference/progress-reporter-class.md) kullanarak ilerleme bildirimlerini eşzamanlı işlemlerinizi arayan bileşenlere bildirin.

- Dahili eşzamanlı işlemlerin iptal edilmesini sağlamak için iptal belirteçlerini kullanın.

- `create_async` İşlevin davranışı, ona geçirilen iş işlevinin dönüş türüne bağlıdır. Bir görevi döndüren bir `task<T>` `task<void>`iş işlevi (ya da) `create_async`adlı bağlamda eşzamanlı olarak çalışır. Rasgele bir bağlamda `T` `void` döndüren veya çalışan bir iş işlevi.

- [Eşzamanlılık kullanabilirsiniz::görev::sonra](reference/task-class.md#then) yöntem birbiri ardına çalışan görevler zinciri oluşturmak için. Bir UWP uygulamasında, görevin devamı için varsayılan bağlam, bu görevin nasıl oluşturulduruna bağlıdır. Görev, görev oluşturucuya bir eşyokuz eylemi geçirerek veya bir eşzamanlı eylem döndüren bir lambda ifadesi geçirerek oluşturulduysa, bu görevin tüm devamı için varsayılan bağlam geçerli bağlamdır. Görev eşzamanlı bir eylemden oluşturulmazsa, görevin devamı için varsayılan olarak rasgele bir bağlam kullanılır. [Eşzamanlılık::task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfı yla varsayılan bağlamı geçersiz kılabilirsiniz.

## <a name="in-this-document"></a>Bu belgede

- [Eşzamanlı İşlemler Oluşturma](#create-async)

- [Örnek: C++ Windows Runtime Bileşeni Oluşturma](#example-component)

- [Yürütme İş parçacığı nın denetleilmesi](#exethread)

- [Örnek: C++ ve XAML ile Windows Runtime Uygulamasında Yürütmeyi Denetleme](#example-app)

## <a name="creating-asynchronous-operations"></a><a name="create-async"></a>Eşzamanlı İşlemler Oluşturma

Paralel Desenler Kitaplığı'ndaki (PPL) görev ve devam modelini, önceki görev tamamlandığında çalışan ek görevlerin yanı sıra arka plan görevlerini tanımlamak için kullanabilirsiniz. Bu işlevsellik [eşzamanlılık:görev](../../parallel/concrt/reference/task-class.md) sınıfı tarafından sağlanır. Bu model ve sınıf `task` hakkında daha fazla bilgi için [Görev Paralelliği'ne](../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın.

Windows Runtime, yalnızca özel bir işletim sistemi ortamında çalışan UWP uygulamaları oluşturmak için kullanabileceğiniz bir programlama arabirimidir. Bu tür uygulamalar yetkili işlevleri, veri türlerini ve cihazları kullanır ve Microsoft Mağazası'ndan dağıtılır. Windows *Runtime, Uygulama İkili Arabirimi* (ABI) ile temsil edilir. ABI, Windows Runtime API'lerini Visual C++ gibi programlama dilleri için kullanılabilir kılan temel bir ikili sözleşmedir.

Windows Runtime'ı kullanarak, çeşitli programlama dillerinin en iyi özelliklerini kullanabilir ve bunları tek bir uygulamada birleştirebilirsiniz. Örneğin, JavaScript'te uI'nizi oluşturabilir ve bir C++ bileşeninde hesaplama açısından yoğun uygulama mantığını gerçekleştirebilirsiniz. Bu hesaplama açısından yoğun işlemleri arka planda gerçekleştirebilme yeteneği, uI'nizin yanıt vermesini sağlamada önemli bir faktördür. `task` Sınıf C++'a özgü olduğundan, diğer bileşenlere (C++dışındaki dillerde yazılmış olabilecek) asenkron işlemleri iletmek için bir Windows Runtime arabirimi kullanmanız gerekir. Windows Runtime, eşzamanlı işlemleri temsil etmek için kullanabileceğiniz dört arabirim sağlar:

[Windows::Foundation::IAsyncAction](/uwp/api/windows.foundation.iasyncaction)<br/>
Eşzamanlı bir eylemi temsil eder.

[Windows::Foundation::IAsyncActionWithProgress\<TProgress>](/uwp/api/Windows.Foundation.IAsyncActionWithProgress_TProgress_)<br/>
İlerlemeyi bildiren eşzamanlı bir eylemi temsil eder.

[Windows::Foundation::IAsyncOperation\<TResult>](/uwp/api/windows.foundation.iasyncoperation_tresult_)<br/>
Bir sonucu döndüren eşzamanlı bir işlemi temsil eder.

[Windows::Foundation::IAsyncOperationWithProgress\<TResult, TProgress>](/uwp/api/windows.foundation.iasyncoperationwithprogress_tresult_tprogress_)<br/>
Bir sonucu döndüren ve ilerlemeyi bildiren eşzamanlı bir işlemi temsil eder.

*Eylem* kavramı, eşzamanlı görevin bir değer oluşturmadığı anlamına gelir (döndüren `void`bir işlev düşünün). Bir *işlem* kavramı, eşzamanlı görevin bir değer ürettiği anlamına gelir. *İlerleme* kavramı, görevin ilerleme iletilerini arayana bildirebileceği anlamına gelir. JavaScript, .NET Framework ve Visual C++ her biri ABI sınırı boyunca kullanılmak üzere bu arabirimlerin örneklerini oluşturmak için kendi yolunu sağlar. Visual C++için PPL [eşzamanlılık sağlar::create_async](reference/concurrency-namespace-functions.md#create_async) işlevi. Bu işlev, bir görevin tamamlanmasını temsil eden bir Windows Runtime eşzamanlı eşzamanlı eylem veya işlem oluşturur. İşlev `create_async` bir iş işlevi (genellikle bir lambda ifadesi) `task` alır, dahili olarak bir nesne oluşturur ve bu görevi dört eşzamanlı Windows Runtime arabiriminden birinde sarar.

> [!NOTE]
> Yalnızca `create_async` başka bir dilden veya başka bir Windows Runtime bileşeninden erişilebilen işlevsellik oluşturmanız gerektiğinde kullanın. İşlemin `task` aynı bileşende C++ kodu tarafından hem üretildiğini hem de tüketildiğini bildiğinizde sınıfı doğrudan kullanın.

İade türü, `create_async` bağımsız değişkenlerinin türüne göre belirlenir. Örneğin, çalışma işleviniz bir değer döndürmüyorsa ve `create_async` ilerlemeyi bildirmiyorsa, geri döner. `IAsyncAction` Çalışma işleviniz bir değer döndürmüyorsa `create_async` ve `IAsyncActionWithProgress`ilerlemeyi de bildiriyorsa, döndürür. İlerlemeyi bildirmek için, iş işlevinizin parametresi olarak [eşzamanlılık::progress_reporter](../../parallel/concrt/reference/progress-reporter-class.md) nesnesi sağlayın. İlerlemeyi bildirme yeteneği, ne miktarda çalışma gerçekleştirildive hangi miktarın hala kaldığını (örneğin, yüzde olarak) bildirmenize olanak tanır. Ayrıca, sonuçları kullanılabilir olduklarında bildirmenize de olanak tanır.

`IAsyncAction`, `IAsyncActionWithProgress<TProgress>`, `IAsyncOperation<TResult>` ve `IAsyncActionOperationWithProgress<TProgress, TProgress>` arabirimlerinin her biri zaman uyumsuz işlemi iptal etmenizi sağlayan bir `Cancel` metodu sunar. Sınıf `task` iptal jetonları ile çalışır. İşi iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı bu belirteci abone yeni çalışma başlatmaz. Zaten etkin olan çalışma, iptal belirteci izleyebilir ve gerektiğinde durdurabilir. Bu [mekanizma, PPL'deki İptal belgesinde](cancellation-in-the-ppl.md)daha ayrıntılı olarak açıklanmıştır. Görev iptalini Windows Runtime`Cancel` yöntemleriyle iki şekilde bağlayabilirsiniz. İlk olarak, eşzamanlılık almak için `create_async` geçtiğiniz iş işlevini tanımlayabilirsiniz::cancellation_token nesnesi. [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) `Cancel` Yöntem çağrıldığında, bu iptal belirteci iptal edilir ve normal `task` iptal kuralları `create_async` aramayı destekleyen alttaki nesneye uygulanır. Bir `cancellation_token` nesnesi belirtmezseniz, temel alınan `task` nesnesi örtük olarak bir nesne tanımlar. Çalışma işlevinizde bir iptali işbirliği halinde olarak yanıtlamanız gerektiğinde bir `cancellation_token` nesnesi tanımlayın. Örnek: [C++ ve XAML içeren bir Windows Runtime Uygulamasında Yürütmeyi Denetleme,](#example-app) özel bir Windows Runtime C++ bileşeni kullanan C# ve XAML içeren Evrensel Windows Platformu (UWP) uygulamasında iptalin nasıl gerçekleştirilecekine dair bir örnek gösterir.

> [!WARNING]
> Görev devamı zincirinde, her zaman durumu temizleyin ve ardından [eşzamanlılığı arayın::iptal](reference/concurrency-namespace-functions.md#cancel_current_task) belirteci iptal edildiğinde cancel_current_task. Aramak `cancel_current_task`yerine erken dönerseniz, işlem iptal edilen durum yerine tamamlanmış duruma geçiş eder.

Aşağıdaki tablo, uygulamanızda eşzamanlı işlemleri tanımlamak için kullanabileceğiniz kombinasyonları özetlemektedir.

|Bu Windows Runtime arabirimini oluşturmak için|Bu tür döndürme`create_async`|Örtük bir iptal belirteci kullanmak için bu parametre türlerini iş işlevinize geçirin|Açık bir iptal belirteci kullanmak için bu parametre türlerini iş işlevinize geçirin|
|----------------------------------------------------------------------------------|------------------------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|`IAsyncAction`|`void` veya `task<void>`|(yok)|(`cancellation_token`)|
|`IAsyncActionWithProgress<TProgress>`|`void` veya `task<void>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|
|`IAsyncOperation<TResult>`|`T` veya `task<T>`|(yok)|(`cancellation_token`)|
|`IAsyncActionOperationWithProgress<TProgress, TProgress>`|`T` veya `task<T>`|(`progress_reporter`)|(`progress_reporter`, `cancellation_token`)|

İşlev için geçtiğiniz `task` iş işlevinden bir değer veya nesne döndürebilirsiniz. `create_async` Bu varyasyonlar farklı davranışlar üretir. Bir değer döndürdüğünde, iş işlevi arka `task` plan iş parçacığı üzerinde çalıştırılabilsin diye bir şekilde sarılır. Buna ek olarak, altta yatan `task` örtülü bir iptal belirteci kullanır. Tersine, bir `task` nesne döndürerseniz, iş işlevi eşzamanlı olarak çalışır. Bu nedenle, bir `task` nesne döndürürseniz, çalışma işlevinizdeki uzun işlemlerin uygulamanızın yanıt vermesini sağlamak için görev olarak da çalıştığından emin olun. Buna ek olarak, altta yatan `task` örtülü bir iptal belirteci kullanmaz. Bu nedenle, bir `cancellation_token` `task` nesneyi ' den `create_async`döndürdüğünde iptal için destek gerekiyorsa, bir nesneyi almak için iş işlevinizi tanımlamanız gerekir.

Aşağıdaki örnek, başka bir Windows `IAsyncAction` Runtime bileşeni tarafından tüketilebilen bir nesne oluşturmanın çeşitli yollarını gösterir.

[!code-cpp[concrt-windowsstore-primes#100](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_1.cpp)]

## <a name="example-creating-a-c-windows-runtime-component-and-consuming-it-from-c"></a><a name="example-component"></a>Örnek: C++ Windows Runtime Bileşeni Oluşturma ve C'den Tüketme\#

Bilgi işlem yoğun işlemleri gerçekleştirmek için UI ve C++ Windows Runtime bileşenini tanımlamak için XAML ve C# kullanan bir uygulama düşünün. Bu örnekte, C++ bileşeni belirli bir aralıktaki sayıların asal olduğunu hesaplar. Dört Windows Runtime asynchronous görev arabirimleri arasındaki farklılıkları göstermek için, Boş Bir **Çözüm** oluşturarak ve adlandırma yaparak Visual Studio'da başlatın. `Primes` Sonra çözüme bir **Windows Runtime Bileşeni** `PrimesLibrary`projesi ekleyin ve adlandırma . Oluşturulan C++ üstbilgi dosyasına aşağıdaki kodu ekleyin (bu örnek Class1.h'yi Asal olarak yeniden adlandırır). Her `public` yöntem dört eşzamanlı arabirimden birini tanımlar. Bir değeri döndüren yöntemler [Windows::Foundation::Collections::IVector\<int>](/uwp/api/Windows.Foundation.Collections.IVector_T_) nesnesi. İlerlemeyi bildiren yöntemler, tamamlanan genel çalışma yüzdesini tanımlayan değerler üretir. `double`

[!code-cpp[concrt-windowsstore-primes#1](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_2.h)]

> [!NOTE]
> Kural kuralına göre, Windows Runtime'daki eşzamanlı yöntem adları genellikle "Async" ile sona erer.

Oluşturulan C++ kaynak dosyasına aşağıdaki kodu ekleyin (bu örnek Class1.cpp'yi Asal.cpp olarak yeniden adlandırır). İşlev, `is_prime` girişinin asal olup olmadığını belirler. Kalan yöntemler `Primes` sınıfı uygular. Her çağrı, `create_async` çağrıldığı yöntemle uyumlu bir imza kullanır. Örneğin, `Primes::ComputePrimesAsync` döndürdüğünden, `IAsyncAction` `create_async` sağlanan iş işlevi bir değer döndürmez ve nesneyi `progress_reporter` parametresi olarak almaz.

[!code-cpp[concrt-windowsstore-primes#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_3.cpp)]

Her yöntem, giriş parametrelerinin negatif olmadığından emin olmak için önce doğrulama gerçekleştirir. Bir giriş değeri negatifse, yöntem [Platform atar::Geçersiz Bağımsız Değişken Özel Durum](../../cppcx/platform-invalidargumentexception-class.md). Hata işleme daha sonra bu bölümde açıklanmıştır.

Bir UWP uygulamasından bu yöntemleri kullanmak için Visual Studio çözümüne ikinci bir proje eklemek için Visual C# **Blank App (XAML)** şablonundan yararlanın. Bu örnekte `Primes`proje adlandırır. Daha sonra, `Primes` projeden projeye bir `PrimesLibrary` başvuru ekleyin.

MainPage.xaml'a aşağıdaki kodu ekleyin. Bu kod, C++ bileşenini arayabilmeniz ve sonuçları görüntüleyebilmeniz için UI'yi tanımlar.

[!code-xml[concrt-windowsstore-primes#3](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_4.xaml)]

MainPage.xaml'deki `MainPage` sınıfa aşağıdaki kodu ekleyin. Bu kod bir `Primes` nesne ve düğme olay işleyicileri tanımlar.

[!code-cs[concrt-windowsstore-primes#4](../../parallel/concrt/codesnippet/csharp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_5.cs)]

Bu yöntemler, `async` `await` eşzamanlı işlemler tamamlandıktan sonra Kullanıcı GKullanımını güncelleştirmek için anahtar kelimeleri ve anahtar kelimeleri kullanır. UWP uygulamalarında eşzamanlı kodlama hakkında bilgi için [İş Parçacığı ve async programlama](/windows/uwp/threading-async)ya da iş parçacığı bilgisine bakın.

Ve `getPrimesCancellation` `cancelGetPrimes` yöntemler, kullanıcının işlemi iptal etmesini sağlamak için birlikte çalışır. Kullanıcı **İptal** düğmesini seçtiğinde, `cancelGetPrimes` yöntem [iAsyncOperationWithProgress\<TResult, TProgress>::İşlemi](/uwp/api/windows.foundation.iasyncinfo.cancel) iptal etmek için iptal eder. Altta yatan eşzamanlı işlemi yöneten Eşzamanlılık Çalışma Süresi, iptalişleminin tamamlandığını bildirmek için Windows Runtime tarafından yakalanan bir dahili özel durum türü atar. İptal modeli hakkında daha fazla bilgi için [İptal'e](../../parallel/concrt/cancellation-in-the-ppl.md)bakın.

> [!IMPORTANT]
> PPL'nin işlemi iptal ettiğini Windows Runtime'a doğru bir şekilde bildirmesini sağlamak için bu iç özel durum türünü yakalayamayın. Bu da tüm özel durumlar (`catch (...)`) yakalamak gerektiği anlamına gelir. Tüm özel durumları yakalamanız gerekiyorsa, Windows Runtime'ın iptal işlemini tamamlayabilmesini sağlamak için özel durumu yeniden atın.

Aşağıdaki resimde, `Primes` her seçenek seçildikten sonra uygulama gösterilmektedir.

![Windows Runtime Primes uygulaması](../../parallel/concrt/media/concrt_windows_primes.png "Windows Runtime Primes uygulaması")

Diğer diller `create_async` tarafından tüketilebilen eşzamanlı görevler oluşturmak için kullanılan örnekler için [bkz.](/previous-versions/windows/apps/hh699891(v=vs.140)) [Windows 8 Asynchronous Operations in C++ with PPL](https://code.msdn.microsoft.com/windowsapps/windows-8-asynchronous-08009a0d)

## <a name="controlling-the-execution-thread"></a><a name="exethread"></a>Yürütme İş parçacığı nın denetleilmesi

Windows Runtime, COM iş parçacığı modelini kullanır. Bu modelde, nesneler senkronizasyonlarını nasıl ele aldıklarına bağlı olarak farklı dairelerde barındırılır. İş parçacığı güvenli nesneler çok dişli daire (MTA) barındırılan. Tek bir iş parçacığı tarafından erişilmesi gereken nesneler, tek dişli bir dairede (STA) barındırılır.

Kullanıcı arabirimi olan bir uygulamada, ASTA (Application STA) iş parçacığı pencere iletilerini pompalamaktan sorumludur ve sta tarafından barındırılan Kullanıcı Arabirimi denetimlerini güncelleştirebilen işlemdeki tek iş parçacığıdır. Bunun iki sonucu var. İlk olarak, uygulamanın yanıt vermeye devam etmesini sağlamak için, tüm CPU yoğun ve G/Ç işlemleri ASTA iş parçacığı üzerinde çalıştırılmamalıdır. İkinci olarak, arka plan iş parçacığı gelen sonuçlar kullanıcı kullanıcı yı güncelleştirmek için ASTA geri marshaled gerekir. Bir C++ UWP `MainPage` uygulamasında ve diğer XAML sayfalarında tüm bunlar ATSA'da çalışır. Bu nedenle, ASTA'da bildirilen görev devamları varsayılan olarak burada çalıştırılır, böylece denetimleri doğrudan devam gövdesinde güncelleştirebilirsiniz. Ancak, bir görevi başka bir göreve yerle bir ederseniz, iç içe olan görevin devamı MTA'da çalıştırılır. Bu nedenle, bu devamların hangi bağlamda çalışmasını açıkça belirtmeniz gerekir.

Bir eşzamanlı işlemden oluşturulan bir görev, örneğin, `IAsyncOperation<TResult>`iş parçacığı ayrıntılarını yoksaymanıza yardımcı olabilecek özel anlamsal bilgiler kullanır. Bir işlem arka plan iş parçacığı üzerinde çalışabilir (veya hiç bir iş parçacığı tarafından desteklenen olmayabilir), devamı varsayılan olarak devam işlemleri (diğer bir deyişle, `task::then`denilen daireden) başlatan daire üzerinde çalıştırmak için garanti edilir. [Eşzamanlılık::task_continuation_context](../../parallel/concrt/reference/task-continuation-context-class.md) sınıfı bir devamı yürütme bağlamında denetlemek için kullanabilirsiniz. Nesneleri oluşturmak `task_continuation_context` için bu statik yardımcı yöntemleri kullanın:

- Devamın bir arka plan iş parçacığı üzerinde çalıştığını belirtmek için [eşzamanlılık::task_continuation_context::use_arbitrary](reference/task-continuation-context-class.md#use_arbitrary) kullanın.

- Eşzamanlılık [kullanın::task_continuation_context::use_current](reference/task-continuation-context-class.md#use_current) devamı adlı `task::then`iş parçacığı üzerinde çalıştığını belirtmek için .

Bir `task_continuation_context` nesneyi göreve [geçirebilirsiniz::sonra,](reference/task-class.md#then) devamın yürütme bağlamını açıkça denetlemek için yöntem veya görevi başka `task::then` bir daireye geçirip yürütme bağlamını dolaylı olarak denetlemek için yöntemi arayabilirsiniz.

> [!IMPORTANT]
> UWP uygulamalarının ana UI iş parçacığı STA altında çalıştırıldığı için, sta'da varsayılan olarak oluşturduğunuz devamlar STA'da çalıştırın. Buna göre, MTA üzerinde oluşturduğunuz devamlar MTA üzerinde çalıştırın.

Aşağıdaki bölümde, diskten bir dosyayı okuyan bir uygulama gösterilmektedir, bu dosyadaki en yaygın sözcükleri bulur ve sonuçları UI'da gösterir. UI'yi güncelleştirmek üzere son işlem, UI iş parçacığında gerçekleşir.

> [!IMPORTANT]
> Bu davranış UWP uygulamalarına özgüdür. Masaüstü uygulamaları için, devamların nerede yayınlaşacağını denetlemezsiniz. Bunun yerine, zamanlayıcı her devamı çalıştırmak için hangi bir alt iş parçacığı seçer.

> [!IMPORTANT]
> [Eşzamanlılık arama::görev::STA](reference/task-class.md#wait) üzerinde çalışan bir devamı gövdesinde bekleyin. Aksi takdirde, çalışma zamanı [eşzamanlılık atar::invalid_operation](../../parallel/concrt/reference/invalid-operation-class.md) çünkü bu yöntem geçerli iş parçacığı engeller ve uygulamanın yanıt vermiyor olmasına neden olabilir. Ancak, [eşzamanlılık çağırabilirsiniz::görev::görev](reference/task-class.md#get) tabanlı bir devamı nda öncül görevin sonucunu almak için yöntem almak.

## <a name="example-controlling-execution-in-a-windows-runtime-app-with-c-and-xaml"></a><a name="example-app"></a>Örnek: C++ ve XAML ile Windows Runtime Uygulamasında Yürütmeyi Denetleme

Bir dosyayı diskten okuyan, o dosyadaki en yaygın sözcükleri bulan ve sonuçları UI'de gösteren bir C++ XAML uygulamasını düşünün. Bu uygulamayı oluşturmak için Visual Studio'da boş bir **uygulama (Evrensel Windows)** projesi oluşturup adını `CommonWords`vererek başlayın. Uygulama bildiriminizde, uygulamanın Belgeler klasörüne erişmesini sağlamak için **Belgeler Kitaplığı** özelliğini belirtin. Ayrıca, uygulama bildiriminin bildirimler bölümüne Metin (.txt) dosya türünü de ekleyin. Uygulama özellikleri ve bildirimleri hakkında daha fazla bilgi için [Windows uygulamalarının Paketlenmesi, dağıtımı ve sorgusu bölümüne](/windows/win32/appxpkg/appx-portal)bakın.

MainPage.xaml'daki öğeyi `Grid` bir `ProgressRing` öğe `TextBlock` ve bir öğe içerecek şekilde güncelleştirin. İşlemin `ProgressRing` devam ettiğini gösterir ve `TextBlock` hesaplama sonuçlarını gösterir.

[!code-xml[concrt-windowsstore-commonwords#1](../../parallel/concrt/codesnippet/xaml/creating-asynchronous-operations-in-cpp-for-windows-store-apps_6.xaml)]

`#include` *pch.h*için aşağıdaki ifadeleri ekleyin.

[!code-cpp[concrt-windowsstore-commonwords#2](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_7.h)]

`MainPage` Sınıfa aşağıdaki yöntem bildirimleri ekleyin (MainPage.h).

[!code-cpp[concrt-windowsstore-commonwords#3](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_8.h)]

MainPage.cpp'ye aşağıdaki `using` ifadeleri ekleyin.

[!code-cpp[concrt-windowsstore-commonwords#4](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_9.cpp)]

MainPage.cpp'de `MainPage::MakeWordList`, `MainPage::FindCommonWords`, `MainPage::ShowResults` ve yöntemleri uygulayın. `MainPage::MakeWordList` Hesaplamalı `MainPage::FindCommonWords` yoğun işlemleri gerçekleştirin. Yöntem, `MainPage::ShowResults` UI'deki hesaplama nın sonucunu görüntüler.

[!code-cpp[concrt-windowsstore-commonwords#5](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_10.cpp)]

Homer'ın `MainPage` *İlyada* kitabındaki ortak sözcükleri UI'de gösteren bir devam görevleri zinciri oluşturmak için oluşturucuyu değiştirin. Metni tek tek sözcüklere bölen ve ortak sözcükleri bulan ilk iki devam görevi zaman alabilir ve bu nedenle açıkça arka planda çalışacak şekilde ayarlanır. UI'yi güncelleyen son devam görevi, devam bağlamı belirtmezse ve bu nedenle daire iş parçacığı kurallarını izler.

[!code-cpp[concrt-windowsstore-commonwords#6](../../parallel/concrt/codesnippet/cpp/creating-asynchronous-operations-in-cpp-for-windows-store-apps_11.cpp)]

> [!NOTE]
> Bu örnek, yürütme bağlamlarının nasıl belirtilen ve devamı zinciri nin nasıl oluşturulabildiğini gösterir. Varsayılan olarak, eşzamanlı bir işlemden oluşturulan bir görevin devamlarını ' . `task::then` Bu nedenle, `task_continuation_context::use_arbitrary` bu örnek, kullanıcı bir arka plan iş parçacığı üzerinde gerçekleştirilmeye ui içermeyen işlemleri belirtmek için kullanır.

Aşağıdaki resimde uygulamanın `CommonWords` sonuçları gösterilmektedir.

![Windows Runtime CommonWords uygulaması](../../parallel/concrt/media/concrt_windows_common_words.png "Windows Runtime CommonWords uygulaması")

Bu örnekte, destekleyen `task` `create_async` nesneler örtülü bir iptal belirteci kullandığından iptali desteklemek mümkündür. Görevlerinizin iptale `cancellation_token` işbirliği ne şekilde yanıt vermesi gerekiyorsa, bir nesneyi almak için iş işlevinizi tanımlayın. PPL'deki iptal hakkında daha fazla bilgi için [PPL'deki İptal'e](cancellation-in-the-ppl.md) bakın

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı](../../parallel/concrt/concurrency-runtime.md)
