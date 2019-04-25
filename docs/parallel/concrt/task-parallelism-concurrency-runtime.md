---
title: Görev Parallelliği (Eşzamanlılık Çalışma Zamanı)
ms.date: 11/04/2016
helpviewer_keywords:
- structured task groups [Concurrency Runtime]
- structured tasks [Concurrency Runtime]
- task groups [Concurrency Runtime]
- task parallelism
- tasks [Concurrency Runtime]
ms.assetid: 42f05ac3-2098-494a-ba84-737fcdcad077
ms.openlocfilehash: c9f18dfd1498538ce3700fd73a27ce6f6088ee42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180049"
---
# <a name="task-parallelism-concurrency-runtime"></a>Görev Parallelliği (Eşzamanlılık Çalışma Zamanı)

Eşzamanlılık Çalışma zamanı içinde bir *görev* , belirli bir işi yapan ve genellikle diğer görevlerle Paralel çalışan iş birimidir. Halinde düzenlenmiştir ek, daha hassas görevlerin görev ayrılmış bir *görev grubu*.

Zaman uyumsuz kod yazar ve bazı işlemlerin zaman uyumsuz işlem tamamlandıktan sonra gerçekleştirilmesini istediğiniz görevleri kullanın. Örneğin, bir dosyadan zaman uyumsuz olarak okumak ve ardından başka bir görev için bir görev kullanabilirsiniz — bir *devamlılık görevi*, bu belgenin sonraki bölümlerinde açıklanan — kullanılabilir hale geldikten sonra veriyi işlemek için. Buna karşılık, paralel işleri küçük parçalara ayırmak için Görev gruplarını kullanabilirsiniz. Örneğin, kalan işi iki bölüme ayıran bir önyinelemeli algoritmanız olduğunu varsayın. Bu bölümleri aynı anda çalıştırmak ve sonra da bölünmüş işin tamamlanmasını bekleyin, görev gruplarını kullanabilirsiniz.

> [!TIP]
> Paralel bir koleksiyonun her öğe için aynı yordamı uygulamak istediğinizde, gibi bir paralel algoritma kullanın [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), görev veya görev grubu yerine. Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="key-points"></a>Önemli Noktalar

- Değişkenleri, bir lambda ifadesi başvuruya göre geçiren, görev bitene kadar konusu değişkenin kullanım ömrünün ermeyeceğini güvence altına almalısınız.

- Görevleri kullanın ( [concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı) zaman uyumsuz kod yazdığınızda. Görev sınıfı değil eşzamanlılık çalışma zamanı, Zamanlayıcı Windows iş parçacığı havuzu kullanır.

- Görev grupları kullanma ( [concurrency::task_group](reference/task-group-class.md) sınıfı veya [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması) paralel işleri küçük parçalara ayırmak ve daha sonra bu küçük bekleyin istediğinizde tamamlamak için parça.

- Kullanım [CONCURRENCY::Task:: then](reference/task-class.md#then) devamlılığını oluşturmak için yöntemi. A *devamlılık* başka bir görev tamamlandıktan sonra çalıştırılan zaman uyumsuz bir görevdir. Devamlılıklar, bir zaman uyumsuz iş zinciri oluşturmak için herhangi bir sayıda bağlanabilirsiniz.

- Öncül görev tamamlandığında, hatta zaman öncül görev iptal edilir ya da bir özel durum oluşturur, bir görev tabanlı devamlılık her zaman yürütme için zamanlanır.

- Kullanım [concurrency::when_all](reference/concurrency-namespace-functions.md#when_all) bir dizi görevin her üyesi tamamlandıktan sonra tamamlanan bir görev oluşturmak için. Kullanım [concurrency::when_any](reference/concurrency-namespace-functions.md#when_any) bir dizi görevin bir üyesi tamamlandıktan sonra tamamlanan bir görev oluşturmak için.

- Görevler ve görev grupları, paralel Desen kitaplığı (PPL) iptal mekanizması içinde yer alabilirler. Daha fazla bilgi için [ppl'de iptal](cancellation-in-the-ppl.md).

- Çalışma zamanının görevler ve görev grupları tarafından oluşturulan özel durumları nasıl işlediğini öğrenmek için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="in-this-document"></a>Bu Belgede

- [Lambda ifadeleri kullanma](#lambdas)

- [Görev sınıfı](#task-class)

- [Devamlılık görevleri](#continuations)

- [Değer tabanlı devamlılığa karşı görev tabanlı devamlılık](#value-versus-task)

- [Görevleri oluşturma](#composing-tasks)

    - [When_all işlevi](#when-all)

    - [When_any işlevi](#when-any)

- [Geciken görevi yürütme](#delayed-tasks)

- [Görev grupları](#task-groups)

- [Task_group'u structured_task_group ile karşılaştırma](#comparing-groups)

- [Örnek](#example)

- [Güçlü programlama](#robust)

##  <a name="lambdas"></a> Lambda ifadeleri kullanma

Kısa sözdizimleri nedeniyle, lambda ifadeleri görevler ve görev grupları tarafından gerçekleştirilen işi tanımlamanın bir ortak yoludur. İşte bazı kullanım ipuçları:

- Görevler genellikle arka plan iş parçacıklarında çalıştığından lambda ifadelerinde değişkenleri zaman yakaladığınız nesne yaşam süresi, unutmayın. Değere göre bir değişken yakaladığınızda, lambda gövdesinde o değişkenin bir kopyasını yapılır. Başvuruya göre yakaladığınızda, kopya yapılmaz. Bu nedenle, başvuruya göre yakaladığınız herhangi bir değişken ömrünün onu kullanan görevin outlives emin olun.

- Göreve bir lambda ifadesi başarıyla sonuçlandıktan sonra başvuruya göre yığında ayrılmış değişkenleri yakalamayın.

- Hangi, takdirde değere göre ve başvuruya göre yakalayacağınızı belirleyebilirsiniz, böylece lambda ifadelerinde yakaladığınız değişkenler ile ilgili olarak açık olabilir. Bu nedenle öneririz, kullanmayın `[=]` veya `[&]` lambda ifadeleri için Seçenekler.

Yaygın bir görevde devamlılık zincirini bir değişkene atar ve başka bir görev bu değişkeni okuduğunda modelidir. Her devamlılık görevinin değişkene ait farklı bir kopyasını alması nedeniyle değere göre alamazsınız. Değişken artık geçerli olmayabilir çünkü yığın ayırma değişkenlerinde, ayrıca başvuruya göre yakalama gerçekleştiremez.

Bu sorunu çözmek için akıllı bir işaretçi gibi kullanın [std::shared_ptr](../../standard-library/shared-ptr-class.md), değişkeni kaydıracak akıllı işaretçiyi değerine göre geçirecek şekilde. Bu şekilde, arka plandaki nesneye atanabilir ve okuma ve onu kullanan görevlerden daha uzun sürmesi. Değişken bir işaretçi veya bir başvuru sayılı tutamaç olsa bile bu tekniği (`^`) için bir Windows çalışma zamanı nesnesi. Basit bir örneği aşağıda verilmiştir:

[!code-cpp[concrt-lambda-task-lifetime#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_1.cpp)]

Lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

##  <a name="task-class"></a> Görev sınıfı

Kullanabileceğiniz [concurrency::task](../../parallel/concrt/reference/task-class.md) görevleri bağımsız işlemler kümesi oluşturmak için sınıf. Bu bileşim modeli kavramı tarafından desteklenir *devamlılıklar*. Ne zaman yürütülecek kodun yürütülebilmesini sağlar önceki veya *öncül*, görev tamamlanır. Öncül görevin sonucu bir veya daha fazla devamlılık görevleri giriş olarak geçirilir. Öncül görev tamamladığında, burada bekleyen herhangi bir devamlılık görevi yürütülmek üzere zamanlanır. Her devamlılık görevi, öncül görevin sonucunun bir kopyasını alır. Sırasıyla bu süreklilik görevleri böylece zinciri görevleri başka süreklilikler için Öncül görevler olabilir. Devamlılıklar, aralarında belirli bağımlılıkları olan görevler rastgele uzunluktaki zincirleri oluşturmanıza yardımcı olur. Ayrıca, çalışırken bir görev iptal ya da bir görevlerden önce başlatılır veya çalışılabilir bir katılabilir. Bu iptal etme modeli hakkında daha fazla bilgi için bkz: [ppl'de iptal](cancellation-in-the-ppl.md).

`task` bir şablon sınıfıdır. Tür parametresi `T` görev tarafından üretilen sonucun türüdür. Bu tür olabilir `void` görev bir değer döndürmezse. `T` kullanamazsınız `const` değiştiricisi.

Bir görev oluşturduğunuzda, sağladığınız bir *iş işlevi* görevin gövdesini gerçekleştiren. Bu iş işlevi lambda işlevi, işlev işaretçisi veya işlev nesnesi biçiminde gelir. Sonuç almadan bitirilecek görevi beklemek için çağrı [CONCURRENCY::Task:: wait](reference/task-class.md#wait) yöntemi. `task::wait` Yöntemi döndürür bir [concurrency::task_status](reference/concurrency-namespace-enums.md#task_group_status) görevin tamamlandığını veya iptal edildiğini tanımlayan bir değer. Görevin sonucunu almak için arama [CONCURRENCY::Task:: get](reference/task-class.md#get) yöntemi. Bu yöntemin çağırdığı `task::wait` görevin bitiş ve bu nedenle geçerli iş parçacığının yürütülmesini engeller sonucu kullanılabilir hale gelene kadar beklenecek.

Aşağıdaki örnek, bir görev oluşturun, sonucunun beklendiğini ve değerinin görüntülendiğini gösterilmektedir. Bu belgedeki örneklerde, bunlar daha kısa sözdizimleri sağladığından lambda işlevleri kullanılmıştır. Ancak, görevleri kullanırken aynı zamanda işlev işaretçilerini ve işlev nesnelerini kullanabilirsiniz.

[!code-cpp[concrt-basic-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_2.cpp)]

Kullanırken [concurrency::create_task](reference/concurrency-namespace-functions.md#create_task) kullanabileceğiniz işlevi `auto` türü bildirmek yerine anahtar sözcüğü. Örneğin, oluşturur ve kimlik matrisi yazdırır bu kodu göz önünde bulundurun:

[!code-cpp[concrt-create-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_3.cpp)]

Kullanabileceğiniz `create_task` eşdeğer işlem oluşturmak için işlevi.

[!code-cpp[concrt-create-task#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_4.cpp)]

Bir görev yürütülürken bir özel durum, çalışma zamanı sonraki çağrısında bu özel durum sürekliliğe devreder `task::get` veya `task::wait`, ya da görev tabanlı devamlılık. Görev özel durum işleme mekanizması hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Kullanan bir örnek için `task`, [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), iptal, bkz: [izlenecek yol: Görevleri ve XML HTTP isteklerini kullanarak bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md). ( `task_completion_event` Sınıfı, bu belgenin sonraki bölümlerinde açıklanmıştır.)

> [!TIP]
>  UWP uygulamalarında görevlere özgü ayrıntıları öğrenmek için bkz [C++ zaman uyumsuz programlamada](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [oluşturma zaman uyumsuz işlemler c++ UWP uygulamaları için](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

##  <a name="continuations"></a> Devamlılık görevleri

Zaman uyumsuz programlama, ikinci bir işlem başlatmak ve ona veri aktarmak için tamamlandığında, bir zaman uyumsuz işlem için çok yaygın. Geleneksel olarak, bu geri arama yöntemleri kullanılarak gerçekleştirilir. Eşzamanlılık Çalışma zamanı içinde aynı işlevler tarafından sağlanan *devamlılık görevleri*. Devamlılık görevi (sadece devamlılık olarak da bilinir) olarak da bilinen başka bir görev tarafından çağrılan zaman uyumsuz bir görevdir *öncül*, öncül görev tamamlandıktan sonra. Devamlılıkları kullanarak şunları yapabilirsiniz:

- Veri öncülden devama geçirin.

- Altında devamlılığın çağrıldığı ya çağrılmayacağı kesin koşulları belirtin.

- Devamlılık, başlamadan önce ya da işbirliği ile çalışırken iptal edin.

- Devamlılığın nasıl zamanlanması gerektiği hakkında ipuçları sağlayın. (Bu, yalnızca evrensel Windows Platformu (UWP) uygulamaları için geçerlidir. Daha fazla bilgi için [oluşturma zaman uyumsuz işlemler c++ UWP uygulamaları için](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).)

- Aynı öncülden gelen birden çok devamlılığını çağırır.

- Tümü veya herhangi biri birden çok öncülün tamamlandığında bir devamlılığı çağırır.

- Birbiri ardına herhangi bir uzunluktaki zincir devamlılıkları.

- Öncülün attığı özel durumları işlemek için devamlılığı kullanın.

Bu özelliklerin ilk görevi tamamladığında bir veya daha fazla görevi yürütmenize olanak sağlar. Örneğin, ilk görevi dosyayı diskten okuduktan sonra bir dosyayı sıkıştıran bir devam oluşturabilirsiniz.

Aşağıdaki örnek Öncekine kullanılacak değiştirir [CONCURRENCY::Task:: then](reference/task-class.md#then) kullanılabilir olduğunda öncül görevin değerini yazdıran bir devamlılık zamanlamak için yöntemi.

[!code-cpp[concrt-basic-continuation#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_5.cpp)]

Zincir ve görevleri art arda iç içe. Bir görev ayrıca birden çok devamlılığa sahip olabilir. Aşağıdaki örnek, önceki görevin değerini üç kez arttıran bir temel devamlılık zincirini göstermektedir.

[!code-cpp[concrt-continuation-chain#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_6.cpp)]

Devamlılık, başka bir görevi de döndürebilir. İptal yoksa bu görev sonraki devamdan önce yürütülür. Bu teknik olarak da bilinen *zaman uyumsuz çözülme*. Zaman uyumsuz çözülme arka planda ek çalışma gerçekleştirmek istediğiniz, ancak geçerli görevin geçerli iş parçacığını engellemesini istemiyorsanız yararlıdır. (Bu devamlılıklar UI iş parçacığı üzerinde çalıştırdığı UWP uygulamalarında yaygındır). Aşağıdaki örnek, üç görev gösterir. İlk görev bir devamlılık görevinden önce çalıştırılan başka bir görev döndürür.

[!code-cpp[concrt-async-unwrapping#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_7.cpp)]

> [!IMPORTANT]
>  Bir görev devamlılığı türünde iç içe geçmiş bir görevi döndürdüğünde `N`, elde edilen görev türüne sahip `N`değil `task<N>`ve iç içe görev tamamlandığında da tamamlanır. Diğer bir deyişle, süreklilik iç içe geçmiş görevin çözülmesini gerçekleştirir.

##  <a name="value-versus-task"></a> Değer tabanlı devamlılığa karşı görev tabanlı devamlılık

Verilen bir `task` , dönüş türü olan nesne `T`, türünde bir değer sağlayabilirsiniz `T` veya `task<T>` bunun devam görevlerine. Türünü alan devamlılık `T` olarak bilinen bir *değer tabanlı devamlılık*. Değer tabanlı devamlılık, öncül görev hatasız olarak tamamlandığında veya iptal zaman yürütme için zamanlanır. Türünü alan devamlılık `task<T>` , parametre olarak bilinen bir *görev tabanlı devamlılık*. Öncül görev tamamlandığında, hatta zaman öncül görev iptal edilir ya da bir özel durum oluşturur, bir görev tabanlı devamlılık her zaman yürütme için zamanlanır. Ardından çağırabilirsiniz `task::get` öncül görevin sonucunu almak için. Öncül görev iptal edilirse `task::get` oluşturur [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md). Öncül görev özel durum oluşturduysa `task::get` o özel durumu yeniden oluşturur. Bir görev tabanlı devamlılık, öncül görev iptal edildiğinde iptal edildi olarak işaretlenmedi.

##  <a name="composing-tasks"></a> Görevleri oluşturma

Bu bölümde açıklanmaktadır [concurrency::when_all](reference/concurrency-namespace-functions.md#when_all) ve [concurrency::when_any](reference/concurrency-namespace-functions.md#when_all) yardımcı olan İşlevler, genel desenleri uygulamak için birden fazla görev oluşturmanıza.

###  <a name="when-all"></a> When_all işlevi

`when_all` İşlevi bir dizi görev tamamlandıktan sonra tamamlanan bir görev oluşturur. Bu işlevi döndürür bir std::[vektör](../../standard-library/vector-class.md) kümedeki her görevin sonucunu içeren nesne. Aşağıdaki temel örnek, kullanır `when_all` üç diğer görevlerin tamamlanmasına temsil eden bir görev oluşturmak için.

[!code-cpp[concrt-join-tasks#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_8.cpp)]

> [!NOTE]
>  Öğesine geçirdiğiniz görevler `when_all` Tekdüzen olmalıdır. Diğer bir deyişle, bunların tümü aynı türü döndürmelidir.

Ayrıca `&&` bir dizi görev tamamlandıktan sonra aşağıdaki örnekte gösterildiği gibi tamamlanan bir görev oluşturmak için söz dizimi.

`auto t = t1 && t2; // same as when_all`

İle birlikte bir devamlılık yaygın `when_all` kümesindeki görevler tamamlandıktan sonra eylemi gerçekleştirmek için. Aşağıdaki örnek üç görevin toplamını yazdırmak için Öncekine değiştirir üretmek her bir `int` sonucu.

[!code-cpp[concrt-join-tasks#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_9.cpp)]

Bu örnekte ayrıca belirtebilirsiniz `task<vector<int>>` bir görev tabanlı süreklilik üretmek için.

Bir dizi görevin herhangi bir görev iptal edilir ya da bir istisna atarsa, `when_all` hemen tamamlanır ve kalan görevlerin tamamlanmasını beklemez. Bir özel durum oluşturulursa, çağırdığınızda çalışma zamanı özel durum beklerseniz `task::get` veya `task::wait` görev nesnesine `when_all` döndürür. Birden fazla görevi oluşturursa çalışma zamanı bunlardan birini seçer. Bu nedenle, tüm görevleri tamamladıktan sonra tüm özel durumları dikkate aldığınızdan emin olun; bir işlenmemiş bir görev özel durumu uygulamanın sonlandırılmasına neden olur.

İşte programınızın tüm özel durumları gözlemlemesini sağlamak için kullanabileceğiniz bir yardımcı program işlevi. Sunulan aralıktaki her görev için `observe_all_exceptions` oluşmuş herhangi bir özel durumu tetikler ve ardından o özel durumu bastırır.

[!code-cpp[concrt-eh-when_all#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_10.cpp)]

C++ ve XAML kullanan ve diske dosyalar kümesi yazan bir UWP uygulaması göz önünde bulundurun. Aşağıdaki örnek nasıl kullanılacağını gösterir `when_all` ve `observe_all_exceptions` programın tüm özel durumları gözlemlemesini sağlamak için.

[!code-cpp[concrt-eh-when_all#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_11.cpp)]

##### <a name="to-run-this-example"></a>Bu örneği çalıştırmak için

1. MainPage.xaml içinde ekleme bir `Button` denetimi.

[!code-xml[concrt-eh-when_all#3](../../parallel/concrt/codesnippet/xaml/task-parallelism-concurrency-runtime_12.xaml)]

1. Mainpage.xaml.h içinde bu düz bildirimleri ekleme `private` bölümünü `MainPage` sınıfının bildirimi.

[!code-cpp[concrt-eh-when_all#4](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_13.h)]

1. Mainpage.xaml.cpp içinde `Button_Click` olay işleyicisi.

[!code-cpp[concrt-eh-when_all#5](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_14.cpp)]

1. Mainpage.xaml.cpp içinde `WriteFilesAsync` örnekte gösterildiği gibi.

> [!TIP]
> `when_all` üretir engelleyici olmayan bir işlev, bir `task` sonuç olarak. Farklı [task::wait](reference/task-class.md#wait), ASTA (ASTA uygulaması) iş parçacığında bir UWP uygulamasında bu işlevi çağırmak güvenlidir.

###  <a name="when-any"></a> When_any işlevi

`when_any` İşlevi bir dizi görevin ilk görevi tamamlandıktan sonra tamamlanan bir görev oluşturur. Bu işlev döndürür bir [std::pair](../../standard-library/pair-structure.md) Tamamlanan görevin sonucu ve bu görevin kümedeki dizinini içeren nesne.

`when_any` İşlev, aşağıdaki senaryolarda özellikle yararlıdır:

- Yedekli işlemler. Birçok şekilde gerçekleştirilen bir algoritma veya işlem düşünün. Kullanabileceğiniz `when_any` önce sona eren işlemi seçmek, sonra da kalan işlemleri iptal etmek için işlevi.

- Dönüşümlü işlemler. Birden çok işlem başlatabilir tüm son kullanın ve gerekir, `when_any` her işlem bittiğinde sonuçları işlemek için işlevi. Bir işlem tamamlandıktan sonra bir veya daha fazla ek görev başlatabilirsiniz.

- Daraltılmış işlemler. Kullanabileceğiniz `when_any` eşzamanlı işlemlerin sayısını sınırlayarak önceki senaryoyu genişletmek için işlevi.

- Süresi dolan işlemler. Kullanabileceğiniz `when_any` arasında bir veya daha fazla görevleri ve belirli bir süre sonunda biten görevi seçmek için işlevi.

Olduğu gibi `when_all`, sahip devamlılık yaygın `when_any` görev kümesindeki ilk sona erdiğinde eylemi gerçekleştirmek için. Aşağıdaki temel örnek, kullanır `when_any` ilk üç görev tamamlandığında tamamlanan bir görev oluşturmak için.

[!code-cpp[concrt-select-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_15.cpp)]

Bu örnekte ayrıca belirtebilirsiniz `task<pair<int, size_t>>` bir görev tabanlı süreklilik üretmek için.

> [!NOTE]
> Olduğu gibi `when_all`, öğesine geçirdiğiniz görevler `when_any` tümü aynı türü döndürmelidir.

Ayrıca `||` bir dizi görevin ilk görevi tamamlandıktan sonra aşağıdaki örnekte gösterildiği gibi tamamlanan bir görev oluşturmak için söz dizimi.

`auto t = t1 || t2; // same as when_any`

> [!TIP]
> Olduğu gibi `when_all`, `when_any` engelleyici olmayan ve bir UWP uygulamasında ASTA iş parçacığı üzerindeki çağrılması güvenlidir.

##  <a name="delayed-tasks"></a> Geciken görevi yürütme

Bazen, bir koşul sağlanana kadar bir görevin yürütülmesini geciktirmek için veya dış bir olaya yanıt olarak bir görevi başlatmak için gerekli olabilir. Örneğin, zaman uyumsuz programlamada bir görevi bir g/ç tamamlama olayına yanıt olarak başlatmak gerekebilir.

Bunu gerçekleştirmenin iki yolu devamlılığı kullanmak veya bir görevi başlatıp görevin çalışma işlevi içindeki olayda bekleyin üzeresiniz. Ancak, durumlar vardır, aşağıdaki tekniklerden birini kullanmak mümkün değildir. Örneğin, bir devam oluşturmak için öncül görev olmalıdır. Ancak, öncül görevin yoksa oluşturabileceğiniz bir *görev tamamlama olayı* ve daha sonra kullanılabilir olduğunda öncül görev tamamlama olayının zincir oluşturma. Ayrıca, bekleyen görev de bir iş parçacığını engeller çünkü zaman uyumsuz bir işlem tamamlandığında çalışmayı gerçekleştirmek için görev tamamlama olaylarını kullanın ve böylece bir iş parçacığını serbest.

[Concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) sınıfı, bu tür bileşimlerini basitleştirmeye yardımcı olur. Gibi `task` sınıfının, tür parametresi `T` görev tarafından üretilen sonucun türüdür. Bu tür olabilir `void` görev bir değer döndürmezse. `T` kullanamazsınız `const` değiştiricisi. Genellikle, bir `task_completion_event` nesnesi, bir iş parçacığı veya bu değeri kullanılabilir olduğunda sinyal veren görev sağlanır. Aynı anda bir veya daha fazla görev bu olayın dinleyicileri ayarlanır. Olay ayarlandığında dinleyici görevleri tamamlayacak ve bunların devamlılığını çalışmak üzere zamanlanır.

Kullanan bir örnek için `task_completion_event` bir gecikmeden sonra tamamlanan bir görev uygulamak için bkz: [nasıl yapılır: Bir gecikmeden sonra tamamlanan bir görev oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md).

##  <a name="task-groups"></a> Görev grupları

A *görev grubu* görev koleksiyonunu düzenler. Görev grupları, görevleri işi kaplayan bir sıraya iter. Zamanlayıcı görevleri bu sıradan çıkarır ve onları kullanılabilir bilgi işlem kaynaklarında yürütür. Bir görev grubuna görevler ekledikten sonra son veya henüz başlamamış görevleri iptal etmek tüm görevlerin tamamlanmasını bekleyebilirsiniz.

PPL kullanan [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) görev gruplarını temsil etmek için sınıfları ve [concurrency::task_handle](../../parallel/concrt/reference/task-handle-class.md) sınıfı Bu gruplarda çalışan görevleri temsil etmek için. `task_handle` Sınıfı, işi gerçekleştiren kod kapsüller. Gibi `task` sınıf, iş işlevi lambda işlevi, işlev işaretçisi veya işlev nesnesi biçiminde gelir. Genellikle ile çalışması gerekmez `task_handle` nesnelerini doğrudan. Bunun yerine, iş işlevlerini bir görev grubuna geçirirsiniz ve görev grubu oluşturur ve yönetir `task_handle` nesneleri.

PPL, bu iki kategoride görev grupları böler: *yapılandırılmamış görev grupları* ve *yapılandırılmış görev grupları*. PPL kullanan `task_group` yapılandırılmamış görev gruplarını temsil etmek için sınıf ve `structured_task_group` yapılandırılmış görev gruplarını temsil eden sınıf.

> [!IMPORTANT]
> PPL ayrıca tanımlar [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını `structured_task_group` sınıfı bir dizi görevi paralel olarak yürütmek için. Çünkü `parallel_invoke` yerine bunu kullanmanızı öneririz, algoritması daha kısa sözdizimine sahip `structured_task_group` sınıfı mümkün olduğunda. Konu [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md) açıklar `parallel_invoke` daha ayrıntılı.

Kullanım `parallel_invoke` zaman aynı anda yürütmek istediğiniz birkaç bağımsız görev varsa ve devam etmeden önce tüm görevlerin bitmesin beklemeniz gerekir. Bu teknik, genellikle olarak adlandırılır *çatallanma ve birleşme* paralellik. Kullanım `task_group` zaman aynı anda yürütmek istediğiniz birkaç bağımsız görev sahip, ancak görevlerin daha sonra son beklemek istiyor. Örneğin, görevler ekleyebilir bir `task_group` nesne ve görevleri başka bir işlev veya başka bir iş parçasından tamamlanmasını bekleyin.

Görev grupları iptali kavramını destekler. İptal, işlemin tamamını iptal etmek istediğinizden, tüm etkin görevlere sinyal olanak tanır. İptal, henüz baştan başlatılmayan görevleri de engeller. İptal işlemleri hakkında daha fazla bilgi için bkz. [ppl'de iptal](cancellation-in-the-ppl.md).

Çalışma zamanı, bir görevden özel durum ve ilişkili görev grubunun tamamlanmasını beklerken o özel durumu işlemenize olanak tanıyan bir özel durum işleme modeli de sağlar. Bu özel durum işleme modeli hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

##  <a name="comparing-groups"></a> Task_group'u structured_task_group ile karşılaştırma

Kullanmanızı öneririz, ancak `task_group` veya `parallel_invoke` yerine `structured_task_group` sınıfı, kullanmak istediğiniz durumlar `structured_task_group`, örneğin, değişken sayıda görevler gerçekleştiren veya gerektiren paralel algoritma yazarken iptal için destek. Bu bölümde arasındaki farklar açıklanmaktadır `task_group` ve `structured_task_group` sınıfları.

`task_group` İş parçacığı açısından güvenli bir sınıftır. Bu nedenle görevler ekleyebilir bir `task_group` nesnesi birden fazla iş parçacığından ve bekleyebilir veya iptal bir `task_group` birden çok iş parçacığından nesne. Oluşturulması ve yıkılması bir `structured_task_group` nesnesi aynı anlamsal bağlamda gerçekleşmelidir. Ayrıca, tüm işlemler bir `structured_task_group` nesne aynı iş parçacığı üzerinde gerçekleşmesi gerekir. Bu kuralın istisnası [CONCURRENCY::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) ve [CONCURRENCY::structured_task_group:: is_canceling](reference/structured-task-group-class.md#is_canceling) yöntemleri. Bir alt görev üst görev grubunu iptal veya herhangi bir zamanda iptali denetlemek için bu yöntemleri çağırabilir.

Ek görevler çalıştırılacağı bir `task_group` çağırdıktan sonra nesne [CONCURRENCY::task_group:: wait](reference/task-group-class.md#wait) veya [run_and_wait](reference/task-group-class.md#run_and_wait) yöntemi. Buna karşılık, ek görevler çalıştırıyorsanız, bir `structured_task_group` çağırdıktan sonra nesne [CONCURRENCY::structured_task_group](reference/structured-task-group-class.md#wait) veya [CONCURRENCY::structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait) yöntemleri , sonra da davranış tanımlanmamıştır.

Çünkü `structured_task_group` sınıfı iş parçacıkları arasında eşitleme, yükü daha az yürütme sahip `task_group` sınıfı. Bu nedenle, sorununuz, gerektirmiyorsa birden çok iş parçacığından zamanlayın ve kullanamazsınız `parallel_invoke` algoritmasını `structured_task_group` sınıfı daha iyi performans gösteren kod yazmanıza yardımcı olabilir.

Kullanıyorsanız `structured_task_group` içinde başka bir nesnenin `structured_task_group` nesnenin iç nesneyi bitmesi gerekir ve dış nesne tamamlanmadan önce yok. `task_group` Sınıfı iç içe geçmiş görev gruplarının dıştaki grup tamamlanmadan bitmesini gerektirmez.

Görev tutamaçlı, yapılandırılmamış görev grupları ve yapılandırılmış görev grupları farklı şekillerde çalışır. İş işlevlerini doğrudan geçirebilirsiniz bir `task_group` nesne; `task_group` nesnesi oluşturur ve sizin için görev tanıtıcısını yönetin. `structured_task_group` Sınıfı yönetmenizi gerektirir bir `task_handle` her görev için nesne. Her `task_handle` nesnesi kendi ilgili kullanım ömrü boyunca geçerli kalmalıdır `structured_task_group` nesne. Kullanım [concurrency::make_task](reference/concurrency-namespace-functions.md#make_task) oluşturmak için işlevi bir `task_handle` aşağıdaki basit örnekte gösterildiği gibi nesne:

[!code-cpp[concrt-make-task-structure#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_16.cpp)]

Değişken sayıda görevler olduğu durumlarda ilişkin görev tanıtıcılarını yönetmek için bir yığın ayırma yordamı gibi kullanın [_malloca](../../c-runtime-library/reference/malloca.md) veya std gibi bir kapsayıcı sınıfı::[vektör](../../standard-library/vector-class.md).

Her ikisi de `task_group` ve `structured_task_group` iptal işlemini destekler. İptal işlemleri hakkında daha fazla bilgi için bkz. [ppl'de iptal](cancellation-in-the-ppl.md).

##  <a name="example"></a> Örnek

Aşağıdaki temel örnek, görev grupları ile çalışmak gösterilmektedir. Bu örnekte `parallel_invoke` iki gerçekleştirmek için algoritması görevleri aynı anda. Her görev alt görevler ekler bir `task_group` nesne. Unutmayın `task_group` görevler eşzamanlı olarak eklemek birden çok görev için sınıf sağlar.

[!code-cpp[concrt-using-task-groups#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_17.cpp)]

Bu örnek için örnek çıktı aşağıda verilmiştir:

```Output
Message from task: Hello
Message from task: 3.14
Message from task: 42
```

Çünkü `parallel_invoke` algoritması görevleri aynı anda çalıştırılır, çıktı iletilerinin sırası değişebilir.

Nasıl kullanılacağını gösteren tam örnekler `parallel_invoke` algoritmasını bkz [nasıl yapılır: Paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) ve [nasıl yapılır: Paralel işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md). Kullanan tam bir örnek `task_group` zaman uyumsuz ileri tarihli işleri uygulamak için bkz: sınıf [izlenecek yol: Vadeli işlemleri uygulama](../../parallel/concrt/walkthrough-implementing-futures.md).

##  <a name="robust"></a> Güçlü programlama

İptal rolünü ve görevleri, görev grupları ve paralel algoritmalar kullandığınızda, özel durum işlemeyi anladığınızdan emin olun. Örneğin, bir paralel iş ağacında iptal edilen bir görev alt görevlerin çalışmasını önleyebilir. Alt görevlerden birini önemli bir kaynağı serbest bırakmak, uygulamanıza bir işlem yaparsa bu sorunlara neden olabilir. Ayrıca, bir alt görev, bir özel durum oluşturursa, bu özel durum bir nesne yokedici yoluyla yayılabilir ve uygulamanızda tanımsız davranışlara neden. Bu noktaları gösteren bir örnek için bkz: [anlayın nasıl iptal ve özel durum işleme etkileyen nesne yok etme](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) paralel desenler kitaplığı belgesi en iyi Pratikler bölümünde. İptal ve özel durum işleme modelleri ppl'de hakkında daha fazla bilgi için bkz. [iptal](../../parallel/concrt/cancellation-in-the-ppl.md) ve [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: Paralel Sıralama Yordamı Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bitonic sıralama algoritmasının performansını artırmak için algoritma.|
|[Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Nasıl kullanılacağını gösterir `parallel_invoke` bir paylaşılan veri kaynağı üzerinde birden çok işlem gerçekleştiren bir programın performansını artırmak için kullanılan algoritma.|
|[Nasıl yapılır: Gecikmeden Sonra Tamamlanan Bir Görev Oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|Nasıl kullanılacağını gösterir `task`, `cancellation_token_source`, `cancellation_token`, ve `task_completion_event` bir gecikmeden sonra tamamlanan bir görev oluşturmak için sınıf.|
|[İzlenecek yol: Vadeli İşlemleri Uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Nasıl daha fazlasını yapan varolan işlevsellikte eşzamanlılık çalışma zamanı değerlerinizden birleştirileceğini gösterir.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eş zamanlı uygulamalar geliştirmeye yönelik zorunlu programlama modeli sağlar PPL açıklar.|

## <a name="reference"></a>Başvuru

[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)

[task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)

[when_all işlevi](reference/concurrency-namespace-functions.md#when_all)

[when_any işlevi](reference/concurrency-namespace-functions.md#when_any)

[task_group Sınıfı](reference/task-group-class.md)

[parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)

[structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)
