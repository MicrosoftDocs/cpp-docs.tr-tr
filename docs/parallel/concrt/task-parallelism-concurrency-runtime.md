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
ms.openlocfilehash: 09c6153a1440684156226acbda909ca8b0398989
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224935"
---
# <a name="task-parallelism-concurrency-runtime"></a>Görev Parallelliği (Eşzamanlılık Çalışma Zamanı)

Eşzamanlılık Çalışma Zamanı, *görev* , belirli bir işi gerçekleştiren ve genellikle diğer görevlerle paralel olarak çalışan bir çalışma birimidir. Bir görev, bir *görev grubunda*düzenlenmiş ek, daha ayrıntılı görevlere eklenebilir.

Zaman uyumsuz kod yazdığınızda ve bazı işlemin zaman uyumsuz işlem tamamlandıktan sonra gerçekleşmesini istediğinizde görevleri kullanırsınız. Örneğin, bir dosyayı bir dosyadan zaman uyumsuz olarak okumak ve daha sonra verileri kullanılabilir hale geldikten sonra işlemek için başka bir görev (Bu belgede daha sonra açıklanan bir *devamlılık görevi*) kullanmak için kullanabilirsiniz. Buna karşılık, paralel çalışmayı daha küçük parçalara ayırmak için görevler gruplarını kullanabilirsiniz. Örneğin, kalan çalışmayı iki bölüme ayıran özyinelemeli bir algoritmaya sahip olduğunuzu varsayalım. Bu bölümleri aynı anda çalıştırmak için görev gruplarını kullanabilir ve sonra bölünen çalışmanın tamamlanmasını bekleyebilirsiniz.

> [!TIP]
> Aynı yordamı bir koleksiyonun her öğesine paralel olarak uygulamak istediğinizde, bir görev veya görev grubu yerine [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for)gibi bir paralel algoritma kullanın. Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="key-points"></a>Önemli Noktalar

- Değişkenleri başvuruya göre lambda ifadesine geçirdiğinizde, bu değişkenin yaşam süresinin görev bitene kadar devam ettiğinden emin olmanız gerekir.

- Zaman uyumsuz kod yazdığınızda görevleri ( [concurrency:: Task](../../parallel/concrt/reference/task-class.md) sınıfı) kullanın. Görev sınıfı, Eşzamanlılık Çalışma Zamanı değil, zamanlayıcı olarak Windows iş parçacığı adını kullanır.

- Paralel çalışmayı daha küçük parçalara ayırmak ve sonra bu küçük parçaların tamamlanmasını beklemek istediğinizde görev gruplarını ( [concurrency:: task_group](reference/task-group-class.md) Class veya [concurrency::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması) kullanın.

- Devamlılıklar oluşturmak için [concurrency:: task:: then](reference/task-class.md#then) yöntemini kullanın. *Devamlılık* , başka bir görev tamamlandıktan sonra zaman uyumsuz olarak çalışan bir görevdir. Zaman uyumsuz çalışma zinciri oluşturmak için istediğiniz sayıda devamlılığa bağlayabilirsiniz.

- Öncül görev tamamlandığında veya bir özel durum oluşturduğunda bile, öncül görevi bittiğinde, görev tabanlı devamlılık her zaman yürütme için zamanlanır.

- Her bir görev kümesinin her üyesi tamamlandıktan sonra tamamlanan bir görev oluşturmak için [concurrency:: when_all](reference/concurrency-namespace-functions.md#when_all) kullanın. Bir görev kümesinin bir üyesi tamamlandıktan sonra tamamlanan bir görev oluşturmak için [concurrency:: when_any](reference/concurrency-namespace-functions.md#when_any) kullanın.

- Görevler ve görev grupları paralel Desenler kitaplığı (PPL) iptal mekanizmasına katılabilir. Daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

- Çalışma zamanının görevler ve görev grupları tarafından oluşturulan özel durumları nasıl işlediğini öğrenmek için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="in-this-document"></a>Bu Belgede

- [Lambda İfadeleri kullanma](#lambdas)

- [Görev sınıfı](#task-class)

- [Devamlılık görevleri](#continuations)

- [Değer tabanlı ve görev tabanlı devamlılıklar](#value-versus-task)

- [Görevler oluşturuluyor](#composing-tasks)

  - [When_all Işlevi](#when-all)

  - [When_any Işlevi](#when-any)

- [Gecikmeli görev yürütme](#delayed-tasks)

- [Görev grupları](#task-groups)

- [Task_group structured_task_group karşılaştırma](#comparing-groups)

- [Örnek](#example)

- [Güçlü Programlama](#robust)

## <a name="using-lambda-expressions"></a><a name="lambdas"></a>Lambda Ifadeleri kullanma

Kısa sözdizimi nedeniyle, lambda ifadeleri görevler ve görev grupları tarafından gerçekleştirilen işi tanımlamanın yaygın bir yoludur. İşte bazı kullanım ipuçları:

- Görevler genellikle arka plan iş parçacıklarında çalıştığı için, Lambda ifadelerinde değişkenleri yakaladığınızda nesne yaşam süresinden haberdar olun. Bir değişkeni değere göre yakaladığınızda lambda gövdesinde bu değişkenin bir kopyası yapılır. Başvuruya göre yakaladığınızda bir kopya yapılmaz. Bu nedenle, başvuruya göre yakaladığınız herhangi bir değişkenin yaşam süresinin, onu kullanan görevi yaşdığından emin olun.

- Bir göreve lambda ifadesi geçirdiğinizde, yığına başvuruya göre ayrılan değişkenleri yakalamaz.

- Lambda ifadelerinde yakaladığınız değişkenler hakkında açık olun, böylece değere göre yakaladığınızı tanımlayabilmeniz için başvuruya göre. Bu nedenle, `[=]` `[&]` lambda ifadeleri için veya seçeneklerini kullanmanızı öneririz.

Ortak bir model, bir devamlılık zincirindeki bir görevin bir değişkene atadığı ve başka bir görevin o değişkeni okuduğu bir görevdir. Her devamlılık görevi değişkenin farklı bir kopyasını tutacağından değere göre yakalayamazsınız. Yığın tarafından ayrılan değişkenler için aynı zamanda başvuruya göre yakalayamazsınız, çünkü değişken artık geçerli olmayabilir.

Bu sorunu çözmek için, değişkeni kaydırmak ve akıllı işaretçiyi değere göre iletmek için [std:: shared_ptr](../../standard-library/shared-ptr-class.md)gibi akıllı bir işaretçi kullanın. Bu şekilde, temel alınan nesne öğesine atanabilir ve öğesinden okunabilir ve bunu kullanan görevler de kaldırılır. Değişken bir işaretçi veya başvuru sayılı tanıtıcı () bir Windows Çalışma Zamanı nesnesine olduğunda bile bu tekniği kullanın `^` . Basit bir örnek verelim:

[!code-cpp[concrt-lambda-task-lifetime#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_1.cpp)]

Lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

## <a name="the-task-class"></a><a name="task-class"></a>Görev sınıfı

Bir bağımlı işlemler kümesine görevler oluşturmak için [concurrency:: Task](../../parallel/concrt/reference/task-class.md) sınıfını kullanabilirsiniz. Bu bileşim modeli *devamlılık*kavramı tarafından desteklenir. Bir devamlılık, önceki veya *öncül*, görev tamamlandığında kodun yürütülmesini sağlar. Öncül görevin sonucu, bir veya daha fazla devamlılık görevine giriş olarak geçirilir. Bir öncül görevi tamamlandığında, üzerinde bekleyen devamlılık görevleri yürütme için zamanlanır. Her devamlılık görevi, öncül görevinin sonucunun bir kopyasını alır. Buna karşılık, bu devamlılık görevleri diğer devamlılıklar için de öncül görevler olabilir ve böylece bir görev zinciri oluşturur. Devamlılıklar, aralarında belirli bağımlılıklara sahip olan, rastgele uzunlukta görev zincirlerini oluşturmanıza yardımcı olur. Ayrıca, bir görev, bir görev başlamadan önce ya da çalışırken birlikte çalışmaya başlamadan önce iptal edebilir. Bu iptal modeli hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

`task`bir şablon sınıfıdır. Tür parametresi, `T` görev tarafından üretilen sonucun türüdür. **`void`** Görevin bir değer döndürmezse bu tür olabilir. `T`**`const`** değiştirici kullanılamıyor.

Bir görev oluşturduğunuzda, görev gövdesini gerçekleştiren bir *çalışma işlevi* sağlarsınız. Bu çalışma işlevi bir Lambda işlevi, işlev işaretçisi veya işlev nesnesi biçiminde gelir. Sonucu elde etmeden görevin bitmesini beklemek için [concurrency:: task:: wait](reference/task-class.md#wait) metodunu çağırın. `task::wait`Yöntemi, görevin tamamlanıp tamamlanmadığını veya iptal edildiğini açıklayan bir [eşzamanlılık:: task_status](reference/concurrency-namespace-enums.md#task_group_status) değeri döndürür. Görevin sonucunu almak için [concurrency:: task:: Get](reference/task-class.md#get) metodunu çağırın. Bu yöntem, `task::wait` görevin bitmesini beklemek için çağırır ve bu nedenle, sonuç kullanılabilir olana kadar geçerli iş parçacığının yürütülmesini engeller.

Aşağıdaki örnek, bir görevin nasıl oluşturulacağını, sonucunun nasıl bekleneceğini ve değerini görüntülemeyi gösterir. Bu belgelerdeki örnekler, daha kısa bir sözdizimi sağladığından lambda işlevlerini kullanır. Ancak, görevleri kullandığınızda işlev işaretçilerini ve işlev nesnelerini de kullanabilirsiniz.

[!code-cpp[concrt-basic-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_2.cpp)]

[Concurrency:: create_task](reference/concurrency-namespace-functions.md#create_task) işlevini kullanırken, **`auto`** türü bildirmek yerine anahtar sözcüğünü kullanabilirsiniz. Örneğin, kimlik matrisini oluşturan ve yazdıran bu kodu göz önünde bulundurun:

[!code-cpp[concrt-create-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_3.cpp)]

`create_task`Denk işlemi oluşturmak için işlevini kullanabilirsiniz.

[!code-cpp[concrt-create-task#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_4.cpp)]

Bir görevin yürütülmesi sırasında bir özel durum oluşturulursa, çalışma zamanı, sonraki çağrıda veya `task::get` `task::wait` bir görev tabanlı devamlıya yapılan çağrı için bu özel durumu sıralar. Görev özel durum işleme mekanizması hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Şunu kullanan bir örnek için `task` , [eşzamanlılık:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), iptal, bkz. [izlenecek yol: görevleri ve XML http isteklerini kullanarak bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md). ( `task_completion_event` Sınıfı bu belgenin ilerleyen kısımlarında açıklanmıştır.)

> [!TIP]
> UWP uygulamalarındaki görevlere özgü ayrıntıları öğrenmek için bkz. [c++ ' da zaman uyumsuz programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [UWP uygulamaları için C++ ' da zaman uyumsuz işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

## <a name="continuation-tasks"></a><a name="continuations"></a>Devamlılık görevleri

Zaman uyumsuz programlamada, bir zaman uyumsuz işlem için, tamamlandığında ikinci bir işlemi çağırmak ve verileri iletmek için çok yaygındır. Geleneksel olarak, bu işlem geri çağırma yöntemleri kullanılarak yapılır. Eşzamanlılık Çalışma Zamanı, aynı işlevler *devamlılık görevleri*tarafından sağlanır. Devamlılık görevi (sadece devamlılık olarak da bilinir *), öncül*olarak bilinen başka bir görev tarafından çağrılan zaman uyumsuz bir görevdir. Devamlılıkları kullanarak şunları yapabilirsiniz:

- Verileri öncül bilgisayardan devamlıya geçirin.

- Devamlılık çağrıldığında veya çağrılmayan kesin koşulları belirtin.

- Çalışmaya başlamadan önce veya çalışırken devam eden bir devamlılığın iptal edildiğini yapın.

- Devamlılığın nasıl zamanlanması gerektiği hakkında ipuçları sağlayın. (Bu yalnızca Evrensel Windows Platformu (UWP) uygulamaları için geçerlidir. Daha fazla bilgi için bkz. [UWP uygulamaları Için C++ ' da zaman uyumsuz Işlemler oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).)

- Aynı öncül öğesinden birden çok devamlılık çağırın.

- Birden çok öncüllerin tamamlandığında bir devamlılık çağırın.

- Zincirden sonra herhangi bir uzunluğa kadar zincir devamlılıkları.

- Öncül tarafından oluşturulan özel durumları işlemek için devamlılık kullanın.

Bu özellikler, ilk görev tamamlandığında bir veya daha fazla görevi yürütmelerine olanak sağlar. Örneğin, bir dosyayı ilk görev diskten okuduktan sonra sıkıştıran bir devamlılık oluşturabilirsiniz.

Aşağıdaki örnek, bir önceki değerin, kullanılabilir olduğunda öncül görevin değerini yazdıran bir devamlılık zamanlamak için [concurrency:: task:: then](reference/task-class.md#then) yöntemini kullanmak üzere önceki birini değiştirir.

[!code-cpp[concrt-basic-continuation#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_5.cpp)]

Görevleri herhangi bir uzunluğa zincirleyebilir ve iç içe yerleştirebilirsiniz. Bir görevde birden fazla devamlılık de olabilir. Aşağıdaki örnek, önceki görevin değerini üç kez artıran temel bir devamlılık zincirini göstermektedir.

[!code-cpp[concrt-continuation-chain#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_6.cpp)]

Devamlılık başka bir görevi de döndürebilir. İptal yoksa, bu görev sonraki devamlıdan önce yürütülür. Bu teknik, *zaman uyumsuz geri sarma*olarak bilinir. Zaman uyumsuz geri sarma, arka planda ek iş gerçekleştirmek istediğinizde yararlıdır, ancak geçerli görevin geçerli iş parçacığını engellemesini istemezsiniz. (Bu, UWP uygulamalarında, Devamlılıkların Kullanıcı arabirimi iş parçacığında çalıştırılabileceği yaygın olarak ortaktır). Aşağıdaki örnek üç görevi gösterir. İlk görev, bir devamlılık görevinden önce çalıştırılan başka bir görev döndürür.

[!code-cpp[concrt-async-unwrapping#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_7.cpp)]

> [!IMPORTANT]
> Bir görevin devamlılık türü, iç içe geçmiş bir görev döndürdüğünde `N` , sonuçta elde edilen görev türü olur `N` ve işlem `task<N>` iç içe geçmiş görev tamamlandığında tamamlar. Diğer bir deyişle, devamlılık, iç içe geçmiş görevin sarmalanması işlemini gerçekleştirir.

## <a name="value-based-versus-task-based-continuations"></a><a name="value-versus-task"></a>Değer tabanlı ve görev tabanlı devamlılıklar

`task`Dönüş türü olan bir nesne verildiğinde `T` , `T` ya da `task<T>` devamlılık görevlerinde bir değer sağlayabilirsiniz. Bir devamlılık `T` , *değer tabanlı devamlılık*olarak bilinir. Öncül görev hatasız olarak tamamlandığında ve iptal edilmediğinde, değer tabanlı devamlılık yürütme için zamanlanır. Parametresi olarak türü alan bir devamlılık `task<T>` , *görev tabanlı devamlılık*olarak bilinir. Öncül görev tamamlandığında veya bir özel durum oluşturduğunda bile, öncül görevi bittiğinde, görev tabanlı devamlılık her zaman yürütme için zamanlanır. Ardından, `task::get` öncül görevin sonucunu almak için öğesini çağırabilirsiniz. Öncül görev iptal edildiyse `task::get` [eşzamanlılık:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md)oluşturur. Öncül görevi bir özel durum `task::get` oluşturursa, bu özel durumu yeniden oluşturur. Görev tabanlı devamlılık, öncül görevi iptal edildiğinde iptal edildi olarak işaretlenir.

## <a name="composing-tasks"></a><a name="composing-tasks"></a>Görevler oluşturuluyor

Bu bölümde, ortak desenleri uygulamak için birden çok görev oluşturmanıza yardımcı olabilen [eşzamanlılık:: when_all](reference/concurrency-namespace-functions.md#when_all) ve [concurrency:: when_any](reference/concurrency-namespace-functions.md#when_all) işlevleri açıklanmaktadır.

### <a name="the-when_all-function"></a><a name="when-all"></a>When_all Işlevi

`when_all`İşlevi, bir dizi görev tamamlandıktan sonra tamamlanan bir görev oluşturur. Bu işlev, küme içindeki her görevin sonucunu içeren bir std::[Vector](../../standard-library/vector-class.md) nesnesi döndürür. Aşağıdaki temel örnek, `when_all` diğer üç görevin tamamlanmasını temsil eden bir görev oluşturmak için kullanır.

[!code-cpp[concrt-join-tasks#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_8.cpp)]

> [!NOTE]
> ' Ye geçirdiğiniz görevler Tekdüzen olmalıdır `when_all` . Diğer bir deyişle, bunların hepsi aynı türü döndürmelidir.

Ayrıca, `&&` Aşağıdaki örnekte gösterildiği gibi bir dizi görev tamamlandıktan sonra tamamlanan bir görev oluşturmak için söz dizimini kullanabilirsiniz.

`auto t = t1 && t2; // same as when_all`

`when_all`Bir dizi görev tamamlandıktan sonra bir eylem gerçekleştirmek için ile birlikte devamlılığın kullanılması yaygındır. Aşağıdaki örnek, her biri bir sonuç üreten üç görevin toplamını yazdırmak için öncekini değiştirir **`int`** .

[!code-cpp[concrt-join-tasks#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_9.cpp)]

Bu örnekte, `task<vector<int>>` görev tabanlı devamlılık oluşturmak için de belirtebilirsiniz.

Bir görev kümesindeki herhangi bir görev iptal edildiğinde veya bir özel durum oluşturursa, `when_all` hemen tamamlanır ve kalan görevlerin bitmesini beklemez. Bir özel durum oluşursa,, öğesini çağırdığınızda `task::get` veya `task::wait` döndüren görev nesnesi üzerinde özel durumu yeniden oluşturur `when_all` . Birden fazla görev oluşturursa, çalışma zamanı bunlardan birini seçer. Bu nedenle, tüm görevler tamamlandıktan sonra tüm özel durumları gözlemlediğinizden emin olun; işlenmemiş bir görev özel durumu uygulamanın sonlandırılmasına neden olur.

Burada, programınızın tüm özel durumları kullanmasını sağlamak için kullanabileceğiniz bir yardımcı program işlevi verilmiştir. Verilen aralıktaki her bir görev için, `observe_all_exceptions` yeniden oluşturulması gereken tüm özel durumları tetikler ve ardından bu özel durumu swýr.

[!code-cpp[concrt-eh-when_all#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_10.cpp)]

C++ ve XAML kullanan ve diske bir dosya kümesi yazan UWP uygulamasını göz önünde bulundurun. Aşağıdaki örnek, `when_all` `observe_all_exceptions` programın tüm özel durumları görmemesini sağlamak için ve kullanımını gösterir.

[!code-cpp[concrt-eh-when_all#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_11.cpp)]

##### <a name="to-run-this-example"></a>Bu örneği çalıştırmak için

1. MainPage. xaml dosyasında bir denetim ekleyin `Button` .

[!code-xml[concrt-eh-when_all#3](../../parallel/concrt/codesnippet/xaml/task-parallelism-concurrency-runtime_12.xaml)]

1. MainPage. xaml. h içinde, bu iletme bildirimlerini **`private`** `MainPage` sınıf bildiriminin bölümüne ekleyin.

[!code-cpp[concrt-eh-when_all#4](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_13.h)]

1. MainPage. xaml. cpp içinde `Button_Click` olay işleyicisini uygulayın.

[!code-cpp[concrt-eh-when_all#5](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_14.cpp)]

1. MainPage. xaml. cpp içinde, `WriteFilesAsync` örnekte gösterildiği gibi uygulayın.

> [!TIP]
> `when_all`, sonucu olarak bir oluşturan engelleyici olmayan bir işlevdir `task` . [Task:: wait](reference/task-class.md#wait)komutundan farklı olarak, bu IşLEVI ASTA (Application STA) Iş parçacığında UWP uygulamasında çağırmak güvenlidir.

### <a name="the-when_any-function"></a><a name="when-any"></a>When_any Işlevi

`when_any`İşlevi, bir görev kümesindeki ilk görev tamamlandığında tamamlanan bir görev oluşturur. Bu işlev, tamamlanan görevin sonucunu ve küme içindeki bu görevin dizinini içeren bir [std::p Air](../../standard-library/pair-structure.md) nesnesi döndürür.

`when_any`İşlevi aşağıdaki senaryolarda özellikle yararlıdır:

- Yedekli işlemler. Birçok şekilde gerçekleştirilen bir algoritma veya işlem düşünün. `when_any`İlk olarak sona erme işlemini seçmek için işlevini kullanabilir ve ardından kalan işlemleri iptal edebilirsiniz.

- Dönüşümlü işlemler. Her birinin tamamlaması gereken birden çok işlem başlatabilir ve `when_any` her işlem tamamlandığında sonuçları işlemek için işlevini kullanabilirsiniz. Bir işlem tamamlandıktan sonra bir veya daha fazla ek görev başlatabilirsiniz.

- Daraltılmış işlemler. `when_any`İşlevini, eşzamanlı işlemlerin sayısını sınırlayarak önceki senaryoyu genişletmek için kullanabilirsiniz.

- Süresi dolan işlemler. `when_any`İşlevini bir veya daha fazla görev ve belirli bir zamandan sonra sona erbir görev arasında seçim yapmak için kullanabilirsiniz.

' De olduğu gibi `when_all` , `when_any` bir görev kümesi ilk kez tamamlandığında eylemi gerçekleştirmek için gereken bir devamlılık kullanılması yaygındır. Aşağıdaki temel örnek, `when_any` diğer üç görevin ilki tamamlandığında tamamlanan bir görev oluşturmak için kullanır.

[!code-cpp[concrt-select-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_15.cpp)]

Bu örnekte, `task<pair<int, size_t>>` görev tabanlı devamlılık oluşturmak için de belirtebilirsiniz.

> [!NOTE]
> İle olduğu gibi `when_all` , geçirdiğiniz görevlerin `when_any` hepsi aynı türü döndürmelidir.

Ayrıca, `||` Aşağıdaki örnekte gösterildiği gibi, bir görev kümesindeki ilk görev tamamlandığında tamamlanan bir görev oluşturmak için söz dizimini kullanabilirsiniz.

`auto t = t1 || t2; // same as when_any`

> [!TIP]
> ' De olduğu gibi `when_all` , `when_any` engellenmeyen ve Asta Iş parçacığında UWP uygulamasında çağırmak güvenlidir.

## <a name="delayed-task-execution"></a><a name="delayed-tasks"></a>Gecikmeli görev yürütme

Bazen bir koşul karşılanana kadar bir görevin yürütülmesini geciktirmesi ya da bir dış olaya yanıt olarak bir görev başlatmanız gerekir. Örneğin, zaman uyumsuz programlamada, bir g/ç tamamlama olayına yanıt olarak bir görevi başlatmanız gerekebilir.

Bunu yapmanın iki yolu bir devamlılık ya da görevin çalışma işlevindeki bir olay üzerinde bekleme kullanmaktır. Ancak, bu tekniklerin birini kullanmanın mümkün olmadığı durumlar vardır. Örneğin, bir devamlılık oluşturmak için öncül görevin olması gerekir. Ancak, öncül göreviniz yoksa, bir *görev tamamlama olayı* oluşturabilir ve daha sonra bu tamamlanma olayını, kullanılabilir olduğunda öncül göreve zincirleyebilirsiniz. Ayrıca, bir bekleme görevi bir iş parçacığını de engellediği için, zaman uyumsuz bir işlem tamamlandığında iş parçacığı boşaltmaya ve böylece bir iş parçacığının serbest bırakıldığı bir işi gerçekleştirmek için görev tamamlama olayları kullanabilirsiniz.

[Concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) sınıfı, bu tür görevlerin oluşumunu basitleştirmeye yardımcı olur. Sınıfı gibi `task` , tür parametresi, `T` görev tarafından üretilen sonucun türüdür. **`void`** Görevin bir değer döndürmezse bu tür olabilir. `T`**`const`** değiştirici kullanılamıyor. Genellikle, bir `task_completion_event` nesne bir iş parçacığına veya göreve, bu değerin değeri kullanılabilir olduğunda onu işaret edecek şekilde sağlanır. Aynı zamanda, bir veya daha fazla görev bu olayın dinleyicileri olarak ayarlanır. Olay ayarlandığında, dinleyici görevleri tamamlanır ve devamlılıkları çalıştırılmak üzere zamanlanır.

`task_completion_event`Bir gecikmeden sonra tamamlanan bir görevi uygulamak için kullanan bir örnek için, bkz. [nasıl yapılır: bir gecikmeden sonra tamamlanan bir görev oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md).

## <a name="task-groups"></a><a name="task-groups"></a>Görev grupları

*Görev grubu bir görev* koleksiyonunu düzenler. Görev grupları, görevleri bir iş hırsızlığı kuyruğuna gönderir. Zamanlayıcı bu kuyruktaki görevleri kaldırır ve kullanılabilir bilgi işlem kaynaklarında yürütür. Görev grubuna görevler ekledikten sonra, tüm görevlerin bitmesini bekleyebilir veya henüz başlatılmamış görevleri iptal edebilirsiniz.

PPL, görev gruplarını temsil etmek için [concurrency:: task_group](reference/task-group-class.md) ve [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıflarını ve bu gruplarda çalışan görevleri temsil etmek için [concurrency:: task_handle](../../parallel/concrt/reference/task-handle-class.md) sınıfını kullanır. `task_handle`Sınıfı, işi gerçekleştiren kodu kapsüller. Sınıfı gibi `task` , iş işlevi bir Lambda işlevi, işlev işaretçisi veya işlev nesnesi biçiminde gelir. Genellikle `task_handle` nesnelerle doğrudan çalışmanız gerekmez. Bunun yerine, çalışma işlevlerini bir görev grubuna geçirirsiniz ve görev grubu nesneleri oluşturur ve yönetir `task_handle` .

PPL, görev gruplarını şu iki kategoriye böler: *yapılandırılmamış görev grupları* ve *yapılandırılmış görev grupları*. PPL, `task_group` yapılandırılmamış görev gruplarını temsil etmek için sınıfını ve `structured_task_group` yapılandırılmış görev gruplarını temsil etmek için sınıfını kullanır.

> [!IMPORTANT]
> PPL Ayrıca, paralel olarak bir dizi görevi yürütmek için sınıfını kullanan [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritmasını tanımlar `structured_task_group` . `parallel_invoke`Algoritmanın daha kısa bir sözdizimi olduğundan, bunu yaparken sınıfı yerine kullanmanızı öneririz `structured_task_group` . [Paralel algoritmaların](../../parallel/concrt/parallel-algorithms.md) konu başlığı `parallel_invoke` daha ayrıntılı olarak açıklanmıştır.

`parallel_invoke`Aynı anda yürütmek istediğiniz birkaç bağımsız görev olduğunda kullanın ve devam etmeden önce tüm görevlerin bitmesini beklemeniz gerekir. Bu teknik genellikle çatal olarak adlandırılır ve paralellik *birleştirir* . `task_group`Aynı anda yürütmek istediğiniz birkaç bağımsız göreviniz olduğunda, ancak görevlerin daha sonra bitmesini beklemek istiyorsanız kullanın. Örneğin, bir nesnesine görev ekleyebilir `task_group` ve görevlerin başka bir işlev veya başka bir iş parçacığından bitmesini bekleyebilirsiniz.

Görev grupları, iptal kavramını destekler. İptal işlemi, genel işlemi iptal etmek istediğiniz tüm etkin görevlere işaret etmenize olanak sağlar. İptal etme işlemi, henüz başlatılmayan görevleri de engeller. İptal hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

Çalışma zamanı ayrıca bir görevden özel durum oluşturmanız ve ilişkili görev grubunun bitmesini beklerseniz bu özel durumu işleyebilmenizi sağlayan bir özel durum işleme modeli sağlar. Bu özel durum işleme modeli hakkında daha fazla bilgi için bkz. [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="comparing-task_group-to-structured_task_group"></a><a name="comparing-groups"></a>Task_group structured_task_group karşılaştırma

Sınıfı yerine veya kullanmanız önerilir, `task_group` `parallel_invoke` Örneğin, `structured_task_group` `structured_task_group` değişken sayıda görevi gerçekleştiren veya iptal için destek gerektiren bir paralel algoritma yazdığınızda kullanmak istediğiniz durumlar vardır. Bu bölümde ve sınıfları arasındaki farklar açıklanmaktadır `task_group` `structured_task_group` .

`task_group`Sınıf, iş parçacığı güvenlidir. Bu nedenle, `task_group` birden fazla iş parçacığından bir nesneye görev ekleyebilir ve `task_group` birden fazla iş parçacığından bir nesneyi bekleyebilir veya iptal edebilirsiniz. Bir nesnenin oluşturulması ve yok `structured_task_group` edilmesi aynı sözcük temelli kapsamda gerçekleşmelidir. Ayrıca, bir nesne üzerindeki tüm işlemler `structured_task_group` aynı iş parçacığında gerçekleşmelidir. Bu kuralın özel durumu [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) ve [concurrency:: structured_task_group:: is_canceling](reference/structured-task-group-class.md#is_canceling) yöntemleridir. Bir alt görev, üst görev grubunu iptal etmek veya herhangi bir zamanda iptal işlemini denetlemek için bu yöntemleri çağırabilir.

`task_group` [Concurrency:: task_group:: wait](reference/task-group-class.md#wait) veya [concurrency:: task_group:: run_and_wait](reference/task-group-class.md#run_and_wait) metodunu çağırdıktan sonra bir nesne üzerinde ek görevler çalıştırabilirsiniz. Buna karşılık, `structured_task_group` [concurrency:: structured_task_group:: wait](reference/structured-task-group-class.md#wait) veya [concurrency:: structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait) yöntemlerini çağırdıktan sonra bir nesne üzerinde ek görevler çalıştırırsanız, davranış tanımsızdır.

`structured_task_group`Sınıf iş parçacıkları arasında eşitlenmediği için, sınıftan daha az yürütme yükü vardır `task_group` . Bu nedenle, sorununuz birden çok iş parçacığından iş zamanlamanızı gerektirmez ve `parallel_invoke` algoritmayı kullanamazsınız, `structured_task_group` sınıf daha iyi çalışan kod yazmanıza yardımcı olabilir.

Bir `structured_task_group` nesneyi başka bir nesne içinde kullanırsanız `structured_task_group` , iç nesne bitmelidir ve dış nesne bitmeden önce yok edilir. `task_group`Sınıf, dış Grup tamamlanmadan önce iç içe geçmiş görev gruplarının bitmesini gerektirmez.

Yapılandırılmamış görev grupları ve yapılandırılmış görev grupları, görev işleyicileri ile farklı yollarla çalışır. Çalışma işlevlerini doğrudan bir `task_group` nesneye geçirebilirsiniz; `task_group` nesne sizin için görev tanıtıcısını oluşturur ve yönetir. `structured_task_group`Sınıfı `task_handle` her bir görev için bir nesneyi yönetmenizi gerektirir. Her `task_handle` nesnenin ilişkili nesnesinin kullanım ömrü boyunca geçerli kalması gerekir `structured_task_group` . Aşağıdaki temel örnekte gösterildiği gibi bir nesne oluşturmak için [concurrency:: make_task](reference/concurrency-namespace-functions.md#make_task) işlevini kullanın `task_handle` :

[!code-cpp[concrt-make-task-structure#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_16.cpp)]

Değişken sayıda görevi olan durumlarda görev tutamaçlarını yönetmek için, [_malloca](../../c-runtime-library/reference/malloca.md) veya std::[Vector](../../standard-library/vector-class.md)gibi bir kapsayıcı sınıfı gibi bir yığın ayırma yordamı kullanın.

Hem hem de `task_group` `structured_task_group` iptali destekler. İptal hakkında daha fazla bilgi için bkz. [PPL 'de iptal](cancellation-in-the-ppl.md).

## <a name="example"></a><a name="example"></a>Örneğinde

Aşağıdaki temel örnek, görev gruplarıyla çalışmayı gösterir. Bu örnek, `parallel_invoke` iki görevi eşzamanlı olarak gerçekleştirmek için algoritmasını kullanır. Her görev, bir nesnesine alt görevler ekler `task_group` . `task_group`Sınıfının birden çok görevin aynı anda buna görev eklemesine izin verdiğini unutmayın.

[!code-cpp[concrt-using-task-groups#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_17.cpp)]

Aşağıda bu örnek için örnek çıktı verilmiştir:

```Output
Message from task: Hello
Message from task: 3.14
Message from task: 42
```

`parallel_invoke`Algoritma görevleri eşzamanlı olarak çalıştırdığı için çıkış iletilerinin sırası değişebilir.

Algoritmanın nasıl kullanılacağını gösteren tüm örnekler için `parallel_invoke` bkz. [nasıl yapılır: paralel sıralama yordamı yazmak Için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) ve [nasıl yapılır: paralel Işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md). `task_group`Zaman uyumsuz Futures uygulamak için sınıfını kullanan tüm bir örnek için bkz. [izlenecek yol: Işlem, uygulama](../../parallel/concrt/walkthrough-implementing-futures.md).

## <a name="robust-programming"></a><a name="robust"></a>Güçlü programlama

Görevler, görev grupları ve paralel algoritmalar kullandığınızda iptal ve özel durum işlemenin rolünü anladığınızdan emin olun. Örneğin, bir paralel çalışma ağacında, iptal edilen bir görev, alt görevlerin çalışmasını engeller. Bu, alt görevlerden biri, uygulamanız için önemli bir işlem gerçekleştirdiğinde (örneğin, bir kaynağı boşaltma gibi) soruna neden olabilir. Ayrıca, bir alt görev bir özel durum oluşturursa, bu özel durum bir nesne yıkıcısı aracılığıyla yayılır ve uygulamanızda tanımsız davranışlara neden olabilir. Bu noktaları gösteren bir örnek için, paralel Desenler kitaplığı belgesindeki En Iyi Yöntemler içindeki [iptal ve özel durum Işlemenin nesne yok etme işlemini nasıl etkilediğini anlamak](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) için bölümüne bakın. PPL 'de iptal ve özel durum işleme modelleri hakkında daha fazla bilgi için bkz. [iptal](../../parallel/concrt/cancellation-in-the-ppl.md) ve [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: paralel sıralama yordamı yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|`parallel_invoke`Bitonic sıralama algoritmasının performansını artırmak için algoritmasının nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: paralel Işlemleri yürütmek için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Bir `parallel_invoke` paylaşılan veri kaynağı üzerinde birden çok işlemi gerçekleştiren bir programın performansını artırmak için algoritmasının nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: bir gecikmeden sonra tamamlanan bir görev oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|`task` `cancellation_token_source` `cancellation_token` `task_completion_event` Bir gecikmeden sonra tamamlanan bir görev oluşturmak için,,, ve sınıflarının nasıl kullanılacağını gösterir.|
|[İzlenecek yol: Futures uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Eşzamanlılık Çalışma Zamanı mevcut işlevselliğin, daha fazlasını yapan bir şekilde nasıl birleştirileceğini gösterir.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eşzamanlı uygulamalar geliştirmek için bir zorunlu programlama modeli sağlayan PPL 'yi açıklar.|

## <a name="reference"></a>Başvuru

[Task sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)

[task_completion_event sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)

[when_all Işlevi](reference/concurrency-namespace-functions.md#when_all)

[when_any Işlevi](reference/concurrency-namespace-functions.md#when_any)

[task_group sınıfı](reference/task-group-class.md)

[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)

[structured_task_group sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)
