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
ms.openlocfilehash: f65521771db3eb0fe19dc863b1b49e9627fc60e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368582"
---
# <a name="task-parallelism-concurrency-runtime"></a>Görev Parallelliği (Eşzamanlılık Çalışma Zamanı)

Eşzamanlılık Çalışma Zamanı'nda *görev,* belirli bir işi gerçekleştiren ve genellikle diğer görevlere paralel çalışan bir çalışma birimidir. Görev, *görev grubuna*düzenlenen ek, daha ince taneli görevlere ayrılabilir.

Eşzamanlı kod yazarken görevleri kullanırsınız ve eşzamanlı işlem tamamlandıktan sonra bazı işlemin gerçekleşmesini istersiniz. Örneğin, bir görevi bir dosyadan eş senkronize olarak okumak ve sonra da bu belgede daha sonra açıklanan bir *devam görevi*olan başka bir görevi kullanarak verileri kullanılabilir hale geldikten sonra işleyebilirsiniz. Tersine, paralel çalışmayı daha küçük parçalara ayrıştırmak için görev gruplarını kullanabilirsiniz. Örneğin, kalan çalışmayı iki bölüme ayıran özyinelemeli bir algoritmanız olduğunu varsayalım. Görev gruplarını, bu bölümleri aynı anda çalıştırmak için kullanabilir ve ardından bölünmüş çalışmanın tamamlanmasını bekleyebilirsiniz.

> [!TIP]
> Aynı yordamı bir koleksiyonun her öğesine paralel olarak uygulamak istediğinizde, görev veya görev grubu yerine [eşzamanlılık::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)gibi paralel bir algoritma kullanın. Paralel algoritmalar hakkında daha fazla bilgi için [Paralel Algoritmalar'a](../../parallel/concrt/parallel-algorithms.md)bakın.

## <a name="key-points"></a>Önemli Noktalar

- Değişkenleri başvuru yla lambda ifadesine geçtiğiniz zaman, görev bitene kadar bu değişkenin ömrünün devam ettiğini garanti etmeniz gerekir.

- Eşzamanlı kod yazarken görevleri [(eşzamanlılık::görev](../../parallel/concrt/reference/task-class.md) sınıfı) kullanın. Görev sınıfı, Eşzamanlılık Çalışma Zamanı olarak değil, zamanlayıcısı olarak Windows ThreadPool'u kullanır.

- Paralel çalışmayı daha küçük parçalara ayırmak ve sonra bu küçük parçaların tamamlanmasını beklemek istediğinizde görev gruplarını [(eşzamanlılık::task_group](reference/task-group-class.md) sınıfı veya [eşzamanlılık::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması) kullanın.

- [Eşzamanlılık kullanın::görev::sonra](reference/task-class.md#then) devamı oluşturmak için yöntem. *Devamı,* başka bir görev tamamlandıktan sonra eş senkronize çalışan bir görevdir. Bir eşzamanlı çalışma zinciri oluşturmak için istediğiniz sayıda devamı bağlayabilirsiniz.

- Görev tabanlı bir devam, öncül görev tamamlandığında, öncül görev iptal edilebilse veya özel bir durum atsa bile yürütme için her zaman zamanlanır.

- [Eşzamanlılık kullanın::when_all](reference/concurrency-namespace-functions.md#when_all) görev kümesinin her üyesi tamamlandıktan sonra tamamlayan bir görev oluşturmak için. [Eşzamanlılık kullanın::when_any](reference/concurrency-namespace-functions.md#when_any) görev kümesinin bir üyesi tamamlandıktan sonra tamamlayan bir görev oluşturmak için.

- Görevler ve görev grupları Paralel Desenler Kitaplığı (PPL) iptal mekanizmasına katılabilir. Daha fazla bilgi için [PPL'de İptal'e](cancellation-in-the-ppl.md)bakın.

- Çalışma zamanının görevler ve görev grupları tarafından atılan özel durumları nasıl işleyeceğini öğrenmek için [bkz.](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

## <a name="in-this-document"></a>Bu Belgede

- [Lambda İfadeleri kullanma](#lambdas)

- [Görev Sınıfı](#task-class)

- [Devam Görevleri](#continuations)

- [Değer Tabanlı Ve Görev Tabanlı Devamlar](#value-versus-task)

- [Görevleri Oluşturma](#composing-tasks)

  - [when_all Fonksiyonu](#when-all)

  - [when_any Fonksiyonu](#when-any)

- [Gecikmiş Görev Yürütme](#delayed-tasks)

- [Görev Grupları](#task-groups)

- [task_group ile structured_task_group karşılaştırması](#comparing-groups)

- [Örnek](#example)

- [Güçlü Programlama](#robust)

## <a name="using-lambda-expressions"></a><a name="lambdas"></a>Lambda İfadelerini Kullanma

Kısa öz sözdizimi nedeniyle lambda ifadeleri, görevler ve görev grupları tarafından gerçekleştirilen çalışmayı tanımlamanın yaygın bir yoludur. Aşağıda bazı kullanım ipuçları verilmiştir:

- Görevler genellikle arka plan iş parçacıklarında çalıştığıiçin, lambda ifadelerinde değişkenleri yakaladığınızda nesne yaşam süresine dikkat edin. Bir değişkeni değere göre yakaladığınızda, bu değişkenin bir kopyası lambda gövdesinde yapılır. Referansla yakaladığınızda, bir kopyasını yapılmaz. Bu nedenle, başvuru yla yakaladığınız herhangi bir değişkenin ömrünün, onu kullanan görevden daha uzun ömürlü olduğundan emin olun.

- Bir göreve lambda ifadesini geçtiğinde, başvuru ile yığına ayrılan değişkenleri yakalamayın.

- Lambda ifadelerinde yakaladığınız değişkenler hakkında açık olun, böylece değere göre ne yakaladığınızı referansa göre tanımlayabilirsiniz. Bu nedenle lambda ifadeleri için `[=]` seçenekleri `[&]` kullanmamanızı öneririz.

Ortak bir desen, devam zincirindeki bir görevin bir değişkene atadığı ve başka bir görevin bu değişkeni okumasıdır. Her devam görevi değişkenin farklı bir kopyasını tutacağı için değere göre yakalayamaabilirsiniz. Yığına ayrılan değişkenler için, değişken artık geçerli olmayabilir, çünkü referans tarafından da yakalayamaabilirsiniz.

Bu sorunu çözmek için, değişkeni sarmak ve akıllı işaretçiyi değere göre geçirmek için [std:shared_ptr](../../standard-library/shared-ptr-class.md)gibi akıllı bir işaretçi kullanın. Bu şekilde, temel nesne atanabilir ve okunabilir ve onu kullanan görevlerdaha uzun yaşayacak. Değişken bir işaretçi veya bir Windows Runtime nesnesine başvuru sayılan tutamacı ()`^`olsa bile bu tekniği kullanın. Basit bir örnek verelim:

[!code-cpp[concrt-lambda-task-lifetime#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_1.cpp)]

lambda ifadeleri hakkında daha fazla bilgi için [Lambda İfadeleri'ne](../../cpp/lambda-expressions-in-cpp.md)bakın.

## <a name="the-task-class"></a><a name="task-class"></a>Görev Sınıfı

[Eşzamanlılık::görev](../../parallel/concrt/reference/task-class.md) sınıfını, görevleri bağımlı işlemler kümesine oluşturmak için kullanabilirsiniz. Bu kompozisyon modeli *devamı*kavramı tarafından desteklenir. Devamı, önceki veya *öncül*görev tamamlandığında kodun yürütülmesini sağlar. Öncül görevin sonucu, bir veya daha fazla devam görevine giriş olarak geçirilir. Öncül bir görev tamamlandığında, üzerinde bekleyen tüm devam görevleri yürütme için zamanlanır. Her devam görevi, öncül görevin sonucunun bir kopyasını alır. Buna karşılık, bu devam görevleri de diğer devamlar için öncül görevler olabilir, bu nedenle görevler zinciri oluşturma. Devamlar, aralarında belirli bağımlılıklar olan rasgele uzunlukta görev zincirleri oluşturmanıza yardımcı olur. Buna ek olarak, bir görev görev başlamadan önce veya çalışırken işbirliği nezdinde iptale katılabilir. Bu iptal modeli hakkında daha fazla bilgi için [PPL'deki İptal'e](cancellation-in-the-ppl.md)bakın.

`task`şablon sınıfıdır. Tür parametresi, `T` görev tarafından üretilen sonucun türüdür. Görev bir `void` değer döndürmezse, bu tür olabilir. `T``const` değiştiriciyi kullanamaz.

Bir görev oluşturduğunuzda, görev gövdesini gerçekleştiren bir *iş işlevi* sağlarsınız. Bu çalışma işlevi bir lambda işlevi, işlev işaretçisi veya işlev nesnesi şeklinde gelir. Bir görevin sonucu almadan tamamlanmasını beklemek için [eşzamanlılığı arayın::görev::bekleme](reference/task-class.md#wait) yöntemi. Yöntem `task::wait` [eşzamanlılık döndürür::görevin](reference/concurrency-namespace-enums.md#task_group_status) tamamlanıp tamamlanmadığını veya iptal edilip edilmediğini açıklayan task_status değeri. Görevin sonucunu almak için [eşzamanlılığı arayın::görev::get](reference/task-class.md#get) metodu. Bu yöntem, görevin tamamlanmasını beklemeyi çağırır `task::wait` ve bu nedenle sonuç kullanılabilir olana kadar geçerli iş parçacığının yürütülmesini engeller.

Aşağıdaki örnek, bir görevin nasıl oluşturulup sonucunu bekleyeceğini ve değerini nasıl gösterini gösterir. Bu dokümantasyondaki örnekler lambda işlevlerini kullanır, çünkü daha kısa bir sözdizimi sağlarlar. Ancak, görevleri kullandığınızda işlev işaretçileri ve işlev nesneleri de kullanabilirsiniz.

[!code-cpp[concrt-basic-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_2.cpp)]

[Eşzamanlılık::create_task](reference/concurrency-namespace-functions.md#create_task) işlevini kullandığınızda, türü bildirmek `auto` yerine anahtar sözcüğü kullanabilirsiniz. Örneğin, kimlik matrisini oluşturan ve yazdıran bu kodu göz önünde bulundurun:

[!code-cpp[concrt-create-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_3.cpp)]

Eşdeğer işlemi `create_task` oluşturmak için işlevi kullanabilirsiniz.

[!code-cpp[concrt-create-task#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_4.cpp)]

Bir görevin yürütülmesi sırasında bir özel durum atılırsa, çalışma zamanı, `task::get` sonraki `task::wait`çağrıda veya görev tabanlı bir devama özel olarak bu özel durumu mareşaller. Görev özel durum işleme mekanizması hakkında daha fazla bilgi için [bkz.](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

`task` [Eşzamanlılık:::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), iptal, [bkz.](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) (Sınıf `task_completion_event` daha sonra bu belgede açıklanmıştır.)

> [!TIP]
> UWP uygulamalarındaki görevlere özgü ayrıntıları öğrenmek için [C++'da Asynchronous programlama](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) ve [UWP Uygulamaları için C++'da Eşzamanlı İşlemler Oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)konusuna bakın.

## <a name="continuation-tasks"></a><a name="continuations"></a>Devam Görevleri

Eşsenkronize programlamada, bir eşzamanlı işlemin tamamlanması, ikinci bir işlemi çağırmak ve ona veri aktarmak çok yaygındır. Geleneksel olarak, bu geri arama yöntemleri kullanılarak yapılır. Eşzamanlılık Çalışma Zamanı'nda, aynı işlevsellik *devam görevleri*tarafından sağlanır. Bir devam görevi (aynı zamanda bir devamı olarak da bilinir) öncül olarak bilinen başka *antecedent*bir görev tarafından çağrılan bir eşzamanlı görevdir, öncül tamamlandığında. Devamı kullanarak şunları yapabilirsiniz:

- Verileri öncülden devama aktarın.

- Devamın çağrıldığı veya çağrılmadığının kesin koşullarını belirtin.

- Başlamadan veya çalışırken işbirliği içinde devam etme iptal edin.

- Devamı nasıl zamanlanması gerektiği hakkında ipuçları sağlayın. (Bu yalnızca Evrensel Windows Platformu (UWP) uygulamaları için geçerlidir. Daha fazla bilgi için bkz: [UWP Uygulamaları için C++'da Eşzamanlı İşlemler Oluşturma](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).)

- Aynı öncülden birden çok devamı çağırın.

- Birden çok öncülden biri tamamlandığında bir devamı çağırın.

- Zincir herhangi bir uzunlukta birbiri ardına devam eder.

- Öncül tarafından atılan özel durumları işlemek için bir devam kullanın.

Bu özellikler, ilk görev tamamlandığında bir veya daha fazla görevi yürütmenizi sağlar. Örneğin, ilk görev diskten okursonra bir dosyasıkıştırır bir devamı oluşturabilirsiniz.

Aşağıdaki örnek, eşzamanlılık kullanmak için öncekibir [değiştirir::görev::sonra](reference/task-class.md#then) yöntem kullanılabilir olduğunda öncül görevin değerini yazdıran bir devamı zamanlamak için.

[!code-cpp[concrt-basic-continuation#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_5.cpp)]

Görevleri istediğiniz uzunlukta zincirleyebilir ve yuvalayabilirsiniz. Bir görevin birden çok devamı da olabilir. Aşağıdaki örnek, önceki görevin değerini üç kat artan temel bir devam zincirini göstermektedir.

[!code-cpp[concrt-continuation-chain#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_6.cpp)]

Devamı da başka bir görev döndürebilir. İptal yoksa, bu görev sonraki devamdan önce yürütülür. Bu teknik *asynchronous açma*olarak bilinir. Eşzamanlı açma, arka planda ek iş gerçekleştirmek istediğinizde yararlıdır, ancak geçerli görevin geçerli iş parçacığının engellenmesini istemez. (Bu, devamı nın UI iş parçacığı üzerinde çalıştırılabildiği UWP uygulamalarında yaygındır). Aşağıdaki örnekte üç görev gösterilmektedir. İlk görev, devam görevinden önce çalıştırılabilen başka bir görevi döndürür.

[!code-cpp[concrt-async-unwrapping#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_7.cpp)]

> [!IMPORTANT]
> Görevin devamı tür `N`iç içe bir görev döndürdüğünde , `N`ortaya `task<N>`çıkan görev türü vardır , değil , ve iç içe görev tamamlandığında tamamlar. Başka bir deyişle, devamı iç içe görevin unwrapping gerçekleştirir.

## <a name="value-based-versus-task-based-continuations"></a><a name="value-versus-task"></a>Değer Tabanlı Ve Görev Tabanlı Devamlar

İade `task` türü olan `T`bir nesne göz önüne alındığında, türü `T` veya devam görevleri `task<T>` için bir değer sağlayabilir. Türü `T` alan bir *devam, değer tabanlı devamı*olarak bilinir. Öncül görev hatasız tamamlandığında ve iptal edilmediğinde, değer tabanlı bir devamı yürütme için zamanlanır. Parametresi olarak `task<T>` türü alan bir *devam, görev tabanlı devamı*olarak bilinir. Görev tabanlı bir devam, öncül görev tamamlandığında, öncül görev iptal edilebilse veya özel bir durum atsa bile yürütme için her zaman zamanlanır. Daha sonra `task::get` öncül görevin sonucunu almak için arayabilirsiniz. Öncül görev iptal edildiyse, `task::get` [eşzamanlılık atar::task_canceled](../../parallel/concrt/reference/task-canceled-class.md). Öncül görev bir özel durum `task::get` attıysa, bu özel durumu yeniden atar. Görev tabanlı devamı, öncül görevi iptal edildiğinde iptal edilmiş olarak işaretlenmez.

## <a name="composing-tasks"></a><a name="composing-tasks"></a>Görevleri Oluşturma

Bu bölümde [eşzamanlılık açıklanır::when_all](reference/concurrency-namespace-functions.md#when_all) ve [eşzamanlılık::when_any](reference/concurrency-namespace-functions.md#when_all) işlevleri, ortak desenleri uygulamak için birden çok görev oluşturmanıza yardımcı olabilir.

### <a name="the-when_all-function"></a><a name="when-all"></a>when_all Fonksiyonu

İşlev, `when_all` bir dizi görev tamamlandıktan sonra tamamlanan bir görev üretir. Bu işlev bir std döndürür:: kümedeki her görevin sonucunu içeren[vektör](../../standard-library/vector-class.md) nesnesi. Aşağıdaki temel örnek, diğer üç görevin tamamlanmasını temsil eden bir görev oluşturmak için kullanır. `when_all`

[!code-cpp[concrt-join-tasks#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_8.cpp)]

> [!NOTE]
> Geçtiğiniz görevler tek `when_all` düze olmalıdır. Başka bir deyişle, hepsi aynı türü döndürmelidir.

Sözdizimini, `&&` aşağıdaki örnekte gösterildiği gibi, bir dizi görev tamamlandıktan sonra tamamlayan bir görev oluşturmak için de kullanabilirsiniz.

`auto t = t1 && t2; // same as when_all`

Bir dizi görev bittikten `when_all` sonra bir eylemi gerçekleştirmek için bir devamı birlikte kullanmak yaygındır. Aşağıdaki örnek, her biri bir `int` sonuç üreten üç görevin toplamını yazdırmak için öncekini değiştirir.

[!code-cpp[concrt-join-tasks#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_9.cpp)]

Bu örnekte, görev `task<vector<int>>` tabanlı bir devamı oluşturmak için de belirtebilirsiniz.

Bir görev kümesindeki herhangi bir görev iptal edilirse `when_all` veya bir özel durum atarsa, hemen tamamlar ve kalan görevlerin tamamlanmasını beklemez. Bir özel durum atılırsa, çalışan zaman, `task::get` `task::wait` `when_all` geri dönen görev nesnesini ararken veya görev nesnesini ararken özel durumu yeniden atar. Birden fazla görev atılırsa, çalışma zamanı bunlardan birini seçer. Bu nedenle, tüm görevler tamamlandıktan sonra tüm özel durumları gözlemlediğinizi emin olun; işlenmemiş bir görev özel durumu uygulamanın sonlandırılmasına neden olur.

Aşağıda, programınızın tüm özel durumları gözlemlediklerinden emin olmak için kullanabileceğiniz bir yardımcı program işlevi verebilirsiniz. Sağlanan aralıktaki her görev `observe_all_exceptions` için, yeniden atılması durumunda ki herhangi bir özel durumu tetikler ve sonra bu özel durumu yutar.

[!code-cpp[concrt-eh-when_all#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_10.cpp)]

C++ ve XAML kullanan ve diske bir dosya kümesi yazan bir UWP uygulaması düşünün. Aşağıdaki örnek, programın `when_all` tüm `observe_all_exceptions` özel durumları nasıl kullanacağıve gözlerden emin olunmasını gösterir.

[!code-cpp[concrt-eh-when_all#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_11.cpp)]

##### <a name="to-run-this-example"></a>Bu örneği çalıştırmak için

1. MainPage.xaml'da bir `Button` denetim ekleyin.

[!code-xml[concrt-eh-when_all#3](../../parallel/concrt/codesnippet/xaml/task-parallelism-concurrency-runtime_12.xaml)]

1. MainPage.xaml.h'de, bu iletme `private` bildirimlerini `MainPage` sınıf bildirimibölümüne ekleyin.

[!code-cpp[concrt-eh-when_all#4](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_13.h)]

1. MainPage.xaml.cpp'de olay `Button_Click` işleyicisini uygulayın.

[!code-cpp[concrt-eh-when_all#5](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_14.cpp)]

1. MainPage.xaml.cpp'de `WriteFilesAsync` örnekte gösterildiği gibi uygulayın.

> [!TIP]
> `when_all`sonucu olarak bir üreten olmayan `task` bir engelleme işlevidir. [Görev aksine::bekleyin](reference/task-class.md#wait), ASTA (Application STA) iş parçacığı üzerinde bir UWP uygulamasında bu işlevi aramak için güvenlidir.

### <a name="the-when_any-function"></a><a name="when-any"></a>when_any Fonksiyonu

İşlev, `when_any` görev kümesindeki ilk görev tamamlandığında tamamlayan bir görev üretir. Bu işlev, tamamlanan görevin sonucunu ve kümedeki bu görevin dizinini içeren bir [std::pair](../../standard-library/pair-structure.md) nesnesi döndürür.

İşlev `when_any` özellikle aşağıdaki senaryolarda yararlıdır:

- Yedekli işlemler. Birçok şekilde gerçekleştirilen bir algoritma veya işlem düşünün. `when_any` Önce işi bitiren işlemi seçmek ve sonra kalan işlemleri iptal etmek için işlevi kullanabilirsiniz.

- Dönüşümlü işlemler. Tüm bitirmek ve her işlem sona `when_any` ererken sonuçları işlemek için işlevi kullanmak gereken birden çok işlem başlatabilirsiniz. Bir işlem tamamlandıktan sonra bir veya daha fazla ek görev başlatabilirsiniz.

- Daraltılmış işlemler. Eşzamanlı işlem `when_any` sayısını sınırlayarak önceki senaryoyu genişletmek için işlevi kullanabilirsiniz.

- Süresi dolan işlemler. `when_any` Bir veya daha fazla görev ve belirli bir süre sonra sona eren bir görev arasında seçim yapmak için işlevi kullanabilirsiniz.

Olduğu `when_all`gibi, bir görev kümesinin `when_any` ilki bittiğinde eylem gerçekleştirmesi gereken bir devamı kullanmak yaygındır. Aşağıdaki temel örnek, diğer üç görevden ilki tamamlandığında tamamlayan bir görev oluşturmak için kullanır. `when_any`

[!code-cpp[concrt-select-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_15.cpp)]

Bu örnekte, görev `task<pair<int, size_t>>` tabanlı bir devamı oluşturmak için de belirtebilirsiniz.

> [!NOTE]
> Olduğu `when_all`gibi, geçtiğiniz görevlerin tümü aynı türü `when_any` döndürmelidir.

Sözdizimini, `||` aşağıdaki örnekte gösterildiği gibi, bir görev kümesindeki ilk görev tamamlandıktan sonra tamamlayan bir görev oluşturmak için de kullanabilirsiniz.

`auto t = t1 || t2; // same as when_any`

> [!TIP]
> Olduğu `when_all`gibi, `when_any` engelleme değil ve ASTA iş parçacığı üzerinde bir UWP uygulaması aramak için güvenlidir.

## <a name="delayed-task-execution"></a><a name="delayed-tasks"></a>Gecikmiş Görev Yürütme

Bazen bir koşul karşılanına kadar görevin yürütülmesini geciktirmek veya harici bir olaya yanıt olarak bir görevi başlatmak gerekir. Örneğin, eşzamanlı programlamada, Bir G/Ç tamamlama olayına yanıt olarak bir görevi başlatmanız gerekebilir.

Bunu gerçekleştirmenin iki yolu, bir devamı kullanmak veya bir görevi başlatmak ve görevin çalışma işlevi içindeki bir olayı beklemektir. Ancak, bu tekniklerden birini kullanmak mümkün değildir durumlar vardır. Örneğin, bir devamı oluşturmak için öncül bir görev olmalıdır. Ancak, öncül görev yoksa, bir *görev tamamlama olayı* oluşturabilir ve daha sonra kullanılabilir olduğunda bu tamamlama olayını öncül göreve zincirleyebilirsiniz. Buna ek olarak, bir bekleme görevi de bir iş parçacığı engeller çünkü, bir eşsenkronize işlemi tamamlandığında iş gerçekleştirmek için görev tamamlama olayları kullanabilirsiniz ve bu nedenle bir iş parçacığı serbest.

[Eşzamanlılık::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) sınıfı bu tür görev bileşimini basitleştirmeye yardımcı olur. `task` Sınıf gibi, tür parametresi `T` görev tarafından üretilen sonucun türüdür. Görev bir `void` değer döndürmezse, bu tür olabilir. `T``const` değiştiriciyi kullanamaz. Genellikle, bir `task_completion_event` nesne, değeri kullanılabilir olduğunda sinyal verecek bir iş parçacığı na veya göreve sağlanır. Aynı zamanda, bir veya daha fazla görev bu olayın dinleyicisi olarak ayarlanır. Olay ayarlandığında, dinleyici görevleri tamamlanır ve devamları çalışacak şekilde zamanlanır.

Bir gecikmeden `task_completion_event` sonra tamamlanan bir görevi uygulamak için kullanan [bir](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)örnek için bkz.

## <a name="task-groups"></a><a name="task-groups"></a>Görev Grupları

Görev *grubu* bir görev koleksiyonu düzenler. Görev grupları görevleri iş çalma kuyruğuna iter. Zamanlayıcı görevleri bu kuyruktan kaldırır ve bunları kullanılabilir bilgi işlem kaynaklarında yürütür. Görev grubuna görev ekledikten sonra, henüz başlamamış tüm görevlerin tamamlanmasını veya iptal etmesini bekleyebilirsiniz.

PPL [eşzamanlılık kullanır::task_group](reference/task-group-class.md) ve [eşzamanlılık::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) sınıfları görev gruplarını temsil etmek ve [eşzamanlılık::bu](../../parallel/concrt/reference/task-handle-class.md) gruplarda çalışan görevleri temsil etmek için task_handle sınıf. Sınıf, `task_handle` işi gerçekleştiren kodu kapsüller. `task` Sınıf gibi, iş işlevi bir lambda işlevi, işlev işaretçisi veya işlev nesnesi şeklinde gelir. Genellikle nesnelerle `task_handle` doğrudan çalışmanız gerekmez. Bunun yerine, çalışma işlevlerini bir görev grubuna geçirirsiniz ve `task_handle` görev grubu nesneleri oluşturur ve yönetir.

PPL görev gruplarını bu iki kategoriye ayırır: *yapılandırılmamış görev grupları* ve *yapılandırılmış görev grupları.* PPL, yapılandırılan görev gruplarını temsil `structured_task_group` etmek için `task_group` sınıfı ve yapılandırılmış görev gruplarını temsil etmek için sınıfı kullanır.

> [!IMPORTANT]
> PPL ayrıca [eşzamanlılık tanımlar::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) algoritması, `structured_task_group` paralel bir görev kümesi yürütmek için sınıf kullanır. Algoritmadaha `parallel_invoke` kısa bir sözdizimine sahip olduğundan, bunu `structured_task_group` sınıf yerine kullanabildiğiniz de kullanmanızı öneririz. Konu [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md) daha ayrıntılı olarak açıklar. `parallel_invoke`

Aynı `parallel_invoke` anda yürütmek istediğiniz birkaç bağımsız göreviniz varsa ve devam etmeden önce tüm görevlerin tamamlanmasını beklemeniz gerekir. Bu teknik genellikle çatal olarak adlandırılır ve paralellik *katılmak.* Aynı `task_group` anda yürütmek istediğiniz birkaç bağımsız göreviniz olduğunda, ancak görevlerin daha sonra bitmesini beklemek istediğinizde kullanın. Örneğin, bir nesneye görevler `task_group` ekleyebilir ve görevlerin başka bir işlevde veya başka bir iş parçacığında tamamlanmasını bekleyebilirsiniz.

Görev grupları iptal kavramını destekler. İptal işlemi, genel işlemi iptal etmek istediğiniz tüm etkin görevlere sinyal vermenizi sağlar. İptal işlemi, henüz başlamamış görevlerin başlatılmasını da engeller. İptal hakkında daha fazla bilgi için [PPL'deki İptal'e](cancellation-in-the-ppl.md)bakın.

Çalışma süresi, bir görevden özel durum atmanızı ve ilişkili görev grubunun tamamlanmasını beklerken bu özel durumu işlemenizi sağlayan bir özel durum işleme modeli de sağlar. Bu özel durum işleme modeli hakkında daha fazla bilgi için [bkz.](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

## <a name="comparing-task_group-to-structured_task_group"></a><a name="comparing-groups"></a>task_group ile structured_task_group karşılaştırması

Sınıf yerine `task_group` veya `parallel_invoke` kullanmanızı önersek de, örneğin değişken sayıda görev gerçekleştiren veya iptal için destek gerektiren paralel bir algoritma yazdığınızda kullanmak `structured_task_group`istediğiniz durumlar vardır. `structured_task_group` Bu bölümde sınıflar `task_group` ve `structured_task_group` sınıflar arasındaki farklar açıklanmaktadır.

Sınıf `task_group` iş parçacığı için güvenlidir. Bu nedenle, birden `task_group` çok iş parçacığı bir nesneye `task_group` görevler ekleyebilirsiniz ve beklemek veya birden çok iş parçacığı bir nesne iptal. Bir `structured_task_group` nesnenin yapısı ve imhası aynı sözlü kapsamda gerçekleşmelidir. Ayrıca, bir `structured_task_group` nesne üzerindeki tüm işlemler aynı iş parçacığı üzerinde oluşmalıdır. Bu kuralın istisnası [eşzamanlılıktır::structured_task_group::İptal](reference/structured-task-group-class.md#cancel) ve [eşzamanlılık::structured_task_group::is_canceling](reference/structured-task-group-class.md#is_canceling) yöntemleri. Bir alt görev, üst görev grubunu iptal etmek veya herhangi bir zamanda iptal olup olmadığını denetlemek için bu yöntemleri arayabilir.

Eşzamanlılığı aradıktan sonra `task_group` nesne üzerinde ek görevler çalıştırabilirsiniz::task_group::bekleyin veya [eşzamanlılık::task_group::run_and_wait](reference/task-group-class.md#run_and_wait) yöntemi. [concurrency::task_group::wait](reference/task-group-class.md#wait) Tam tersine, eşzamanlılığı aradıktan `structured_task_group` sonra bir nesne üzerinde ek görevler çalıştırırsanız::structured_task_group::bekleyin veya [eşzamanlılık::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait) yöntemleri, davranış tanımsız. [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait)

`structured_task_group` Sınıf iş parçacıkları arasında eşitleme olmadığından, sınıftan daha `task_group` az yürütme yükü vardır. Bu nedenle, sorununuzun birden çok iş parçacığı çalışma zamanlama gerektirmez `parallel_invoke` ve `structured_task_group` algoritmayı kullanamazsınız, sınıf daha iyi performans kodu yazmanıza yardımcı olabilir.

Başka bir `structured_task_group` `structured_task_group` nesne içinde bir nesne kullanıyorsanız, iç nesne bitirmek ve dış nesne bitmeden önce yok edilmelidir. Sınıfın `task_group` iç içe olan görev gruplarının dış grup bitmeden önce tamamlanmasını gerektirmez.

Yapılandırılmamış görev grupları ve yapılandırılmış görev grupları görev tutamaçlarıyla farklı şekillerde çalışır. Çalışma işlevlerini doğrudan bir `task_group` nesneye geçirebilirsiniz; `task_group` nesne sizin için görev kolu oluşturacak ve yönetecek. Sınıf, `structured_task_group` her görev `task_handle` için bir nesneyi yönetmenizi gerektirir. Her `task_handle` nesne, ilişkili `structured_task_group` nesnenin ömrü boyunca geçerli kalmalıdır. Aşağıdaki temel örnekte gösterildiği gibi, `task_handle` bir nesne oluşturmak için [eşzamanlılık::make_task](reference/concurrency-namespace-functions.md#make_task) işlevini kullanın:

[!code-cpp[concrt-make-task-structure#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_16.cpp)]

Değişken sayıda görevin olduğu durumlar için görev işleyicilerini yönetmek için, [_malloca](../../c-runtime-library/reference/malloca.md) veya std::[vektör](../../standard-library/vector-class.md)gibi bir kapsayıcı sınıfı gibi yığın ayırma yordamı kullanın.

Her `task_group` `structured_task_group` ikisi de ve destek iptali. İptal hakkında daha fazla bilgi için [PPL'deki İptal'e](cancellation-in-the-ppl.md)bakın.

## <a name="example"></a><a name="example"></a>Örnek

Aşağıdaki temel örnek, görev gruplarıyla nasıl çalışılabildiğini gösterir. Bu örnek, `parallel_invoke` aynı anda iki görevi gerçekleştirmek için algoritmayı kullanır. Her görev bir `task_group` nesneye alt görevler ekler. Sınıfın, `task_group` birden çok görevin aynı anda görevler eklemesine izin verdiğini unutmayın.

[!code-cpp[concrt-using-task-groups#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_17.cpp)]

Bu örnek için örnek çıktı aşağıdakigibidir:

```Output
Message from task: Hello
Message from task: 3.14
Message from task: 42
```

`parallel_invoke` Algoritma görevleri aynı anda çalıştırdığından, çıktı iletilerinin sırası değişebilir.

Algoritmanın nasıl kullanılacağını `parallel_invoke` gösteren tam örnekler için [bkz: Paralel Sıralama Yordamı Yazmak için parallel_invoke ve](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) Paralel İşlemleri Yürütmek için parallel_invoke [kullanma.](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md) Asynchronous futures `task_group` uygulamak için sınıfı kullanan tam bir örnek [için](../../parallel/concrt/walkthrough-implementing-futures.md)bkz.

## <a name="robust-programming"></a><a name="robust"></a>Sağlam Programlama

Görevleri, görev gruplarını ve paralel algoritmaları kullandığınızda iptal ve özel durum işlemenin rolünü anladığınızdan emin olun. Örneğin, paralel çalışma ağacında, iptal edilen bir görev alt görevlerin çalışmasını engeller. Alt görevlerden biri, uygulamanız için önemli olan bir kaynak serbest liği gibi bir işlem gerçekleştirirse, bu sorunlara neden olabilir. Ayrıca, bir alt görev bir özel durum atarsa, bu özel durum bir nesne yıkıcı aracılığıyla çoğalabilir ve uygulamanızda tanımlanmamış davranışlara neden olabilir. Bu noktaları gösteren bir örnek için, Paralel Desenler Kitaplığı belgesindeki En İyi Uygulamalar'da [İptal ve Özel Durum İşleme'nin Nesne Yok Oluşu](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) bölümünü nasıl etkilediğini anlayın bölümüne bakın. PPL'deki iptal ve özel durum işleme modelleri hakkında daha fazla bilgi için [Iptal](../../parallel/concrt/cancellation-in-the-ppl.md) ve [Özel Durum İşleme'ye](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)bakın.

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|Bitonik sıralama `parallel_invoke` algoritmasının performansını artırmak için algoritmanın nasıl kullanılacağını gösterir.|
|[Nasıl Kullanılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanın](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|Paylaşılan bir veri `parallel_invoke` kaynağında birden çok işlem gerçekleştiren bir programın performansını artırmak için algoritmanın nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: Bir Gecikmeden Sonra Tamamlanan bir Görev Oluşturma](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|`task`Bir gecikmeden sonra `cancellation_token_source` `cancellation_token`tamamlayan `task_completion_event` bir görev oluşturmak için , , ve sınıfların nasıl kullanılacağını gösterir.|
|[İzlenecek Yol: Vadeli İşlemleri Uygulama](../../parallel/concrt/walkthrough-implementing-futures.md)|Eşzamanlılık Çalışma Süresi'ndeki varolan işlevlerin daha fazlasını yapan bir şeyle nasıl birleştirilen gösterir.|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Eşzamanlı uygulamalar geliştirmek için zorunlu bir programlama modeli sağlayan PPL açıklar.|

## <a name="reference"></a>Başvuru

[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)

[task_completion_event Sınıfı](../../parallel/concrt/reference/task-completion-event-class.md)

[when_all Fonksiyonu](reference/concurrency-namespace-functions.md#when_all)

[when_any Fonksiyonu](reference/concurrency-namespace-functions.md#when_any)

[task_group Sınıfı](reference/task-group-class.md)

[parallel_invoke Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_invoke)

[structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)
