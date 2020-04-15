---
title: PPL'de İptal
ms.date: 11/19/2018
helpviewer_keywords:
- parallel algorithms, canceling [Concurrency Runtime]
- canceling parallel algorithms [Concurrency Runtime]
- parallel tasks, canceling [Concurrency Runtime]
- cancellation in the PPL
- parallel work trees [Concurrency Runtime]
- canceling parallel tasks [Concurrency Runtime]
ms.assetid: baaef417-b2f9-470e-b8bd-9ed890725b35
ms.openlocfilehash: 27c0ea3cfcf62060800c1c0b034dde7de6357250
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368502"
---
# <a name="cancellation-in-the-ppl"></a>PPL'de İptal

Bu belge, Paralel Desenler Kitaplığı'nda (PPL) iptal rolünü, paralel çalışmanın nasıl iptal edilebildiğini ve paralel çalışmanın ne zaman iptal edildiğini nasıl belirleyeceklerini açıklar.

> [!NOTE]
> Çalışma süresi, iptali uygulamak için özel durum işlemeyi kullanır. Kodunuzda bu özel durumları yakalamayın veya işlemeyin. Ayrıca, görevleriniz için işlev gövdelerine özel durum güvenli kodu yazmanızı öneririz. Örneğin, bir özel durum görevin gövdesine atıldığında kaynakların doğru şekilde işlendiğinden emin olmak için *Kaynak Edinme Başlatma* (RAII) deseni kullanabilirsiniz. İptal edilebilir bir görevde bir kaynağı temizlemek için RAII deseni kullanan tam [bir](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)örnek için bkz.

## <a name="key-points"></a>Önemli Noktalar

- İptal, işbirliği ne kadar dır ve iptal talebinde olan kod ile iptale yanıt veren görev arasındaki koordinasyonu içerir.

- Mümkün olduğunda, işi iptal etmek için iptal belirteçlerini kullanın. [Eşzamanlılık::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) sınıfı bir iptal belirteci tanımlar.

- İptal belirteçlerini kullandığınızda, iptal işlemini başlatmak için [eşzamanlılık::cancellation_token_source::iptal](reference/cancellation-token-source-class.md#cancel) yöntemini ve [eşzamanlılığı kullanın::iptale](reference/concurrency-namespace-functions.md#cancel_current_task) yanıt vermek için cancel_current_task işlevi. [Eşzamanlılık kullanın::cancellation_token:::başka](reference/cancellation-token-class.md#is_canceled) bir görevin iptal istemip talep etmediğini kontrol etmek için is_canceled yöntemi.

- İptal hemen gerçekleşmez. Bir görev veya görev grubu iptal edilirse yeni çalışma başlatılmasa da, etkin çalışma iptali denetlemeli ve yanıt vermelidir.

- Değer tabanlı bir devamı, öncül görevinin iptal belirteci devralır. Görev tabanlı bir devam, hiçbir zaman öncül görevinin belirteci devralmaz.

- Eşpara [birimini kullanın::cancellation_token::bir](reference/cancellation-token-class.md#none) `cancellation_token` nesne alan bir oluşturucu veya işlev ibaresini aradığınızda yok yöntemini kullanın, ancak işlemin iptal edilebilmesini istemezsiniz. Ayrıca, eşzamanlılık için bir iptal belirteci [geçirmiyorsanız::görev](../../parallel/concrt/reference/task-class.md) oluşturucu veya [eşzamanlılık::create_task](reference/concurrency-namespace-functions.md#create_task) işlevi, bu görev iptal edilemez.

## <a name="in-this-document"></a><a name="top"></a>Bu Belgede

- [Paralel Çalışma Ağaçları](#trees)

- [Paralel Görevleri İptal Etme](#tasks)

  - [Paralel Çalışmayı İptal Etmek Için İptal Belirteci Kullanma](#tokens)

  - [Paralel Çalışmayı İptal Etmek Için İptal Yöntemini Kullanma](#cancel)

  - [Paralel Çalışmayı İptal Etmek İçin Özel Durumlar Kullanma](#exceptions)

- [Paralel Algoritmaları İptal Etme](#algorithms)

- [İptal Ne Zaman Kullanılmaz?](#when)

## <a name="parallel-work-trees"></a><a name="trees"></a>Paralel Çalışma Ağaçları

PPL, ince taneli görevleri ve hesaplamaları yönetmek için görevleri ve görev gruplarını kullanır. Paralel çalışma *ağaçları* oluşturmak için görev gruplarını yuvalayabilirsiniz. Aşağıdaki resimde paralel bir çalışma ağacı gösterilmektedir. Bu resimde `tg1` ve `tg2` görev gruplarını temsil; `t1`, `t2` `t3`, `t4`, `t5` , ve görev gruplarının gerçekleştirdiği çalışmayı temsil.

![Paralel çalışma ağacı](../../parallel/concrt/media/parallelwork_trees.png "Paralel çalışma ağacı")

Aşağıdaki örnek, resimde ağacı oluşturmak için gereken kodu gösterir. Bu örnekte `tg1` `tg2` ve [eşzamanlılık vardır::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesneleri; `t1`, `t2` `t3`, `t4`, `t5` , ve [eşzamanlılık vardır::task_handle](../../parallel/concrt/reference/task-handle-class.md) nesneleri.

[!code-cpp[concrt-task-tree#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_1.cpp)]

[Eşzamanlılık::task_group](reference/task-group-class.md) sınıfı nda benzer bir çalışma ağacı oluşturmak için de kullanabilirsiniz. [Eşzamanlılık::görev](../../parallel/concrt/reference/task-class.md) sınıfı da bir iş ağacı kavramını destekler. Ancak, `task` bir ağaç bir bağımlılık ağacıdır. Bir `task` ağaçta, gelecekteki işler geçerli çalışmadan sonra tamamlar. Görev grubu ağacında, iç çalışma dış çalışmadan önce tamamlar. Görevler ve görev grupları arasındaki farklar hakkında daha fazla bilgi için Görev [Paralelliği'ne](../../parallel/concrt/task-parallelism-concurrency-runtime.md)bakın.

[[Üst](#top)]

## <a name="canceling-parallel-tasks"></a><a name="tasks"></a>Paralel Görevleri İptal Etme

Paralel çalışmayı iptal etmenin birden çok yolu vardır. Tercih edilen yol bir iptal belirteci kullanmaktır. Görev grupları eşzamanlılığı da [destekler::task_group::cancel](reference/task-group-class.md#cancel) metodu ve [eşzamanlılık::structured_task_group::iptal](reference/structured-task-group-class.md#cancel) yöntemi. Son yol, görev çalışması işlevinin gövdesine bir özel durum atmaktır. Hangi yöntemi seçerseniz seçin, iptalin hemen gerçekleşmediğini anlayın. Bir görev veya görev grubu iptal edilirse yeni çalışma başlatılmasa da, etkin çalışma iptali denetlemeli ve yanıt vermelidir.

Paralel görevleri iptal eden diğer örnekler için [Bkz. Walkthrough: Görevleri Kullanma ve XML HTTP İstekleri](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)Bağlama , [Paralel Döngüden Kopmak Için İptali Kullanma](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)ve [Paralel Döngüden Kopmak Için İstisna İşlemini Kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).

### <a name="using-a-cancellation-token-to-cancel-parallel-work"></a><a name="tokens"></a>Paralel Çalışmayı İptal Etmek Için İptal Belirteci Kullanma

`task_group`İptal `task` `structured_task_group` belirteçleri aracılığıyla iptali destekler. PPL [eşzamanlılık tanımlar::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md) ve [eşzamanlılık::bu](../../parallel/concrt/reference/cancellation-token-class.md) amaç için cancellation_token sınıfları. İşi iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı bu belirteci abone yeni çalışma başlatmaz. Zaten etkin olan çalışma, iptal belirteci izlemek ve ne zaman durdurmak için [is_canceled](../../parallel/concrt/reference/cancellation-token-class.md#is_canceled) üye işlevini kullanabilirsiniz.

İptal başlatmak için [eşzamanlılığı arayın::cancellation_token_source::iptal](reference/cancellation-token-source-class.md#cancel) yöntemi. İptal işlemine şu şekilde yanıt verirsiniz:

- Nesneler `task` için [eşzamanlılık işlevini kullanın::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) işlevi. `cancel_current_task`geçerli görevi ve değer tabanlı devamlarından herhangi birini iptal eder. (Görevle veya devamıyla ilişkili iptal *belirteci* iptal etmez.)

- Görev grupları ve paralel algoritmalar için [eşzamanlılık::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) işlevini kullanarak iptali algılar ve bu işlev **doğru**döndüğünde görev gövdesinden mümkün olan en kısa sürede geri döner. (Görev grubundan aramayın.) `cancel_current_task`

Aşağıdaki örnek, görev iptali için ilk temel deseni gösterir. Görev gövdesi bazen bir döngü içinde iptal idenetler.

[!code-cpp[concrt-task-basic-cancellation#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_2.cpp)]

Fonksiyon `cancel_current_task` atar; bu nedenle, geçerli döngü veya işlevden açıkça dönmeniz gerekmez.

> [!TIP]
> Alternatif olarak, [eşzamanlılık çağırabilirsiniz::interruption_point](reference/concurrency-namespace-functions.md#interruption_point) işlevi `cancel_current_task`yerine .

İptal yanıtı verirken aramak `cancel_current_task` önemlidir, çünkü görevi iptal edilen duruma aktarıyor. Aramak `cancel_current_task`yerine erken dönerseniz, işlem tamamlanan duruma geçiş eder ve değer tabanlı devamlar çalıştırılır.

> [!CAUTION]
> Asla `task_canceled` kodundan atma. Onun `cancel_current_task` yerine ara.

Bir görev iptal edilen durumda sona erdiğinde, [eşzamanlılık::görev::get](reference/task-class.md#get) metodu [eşzamanlılık atar::task_canceled](../../parallel/concrt/reference/task-canceled-class.md). (Tersine, [eşzamanlılık::görev::bekleme](reference/task-class.md#wait) [task_status::iptal edildi](reference/concurrency-namespace-enums.md#task_group_status) ve atmaz.) Aşağıdaki örnek, görev tabanlı bir devamı için bu davranışı göstermektedir. Görev tabanlı devam, öncül görev iptal edilebilse bile her zaman çağrılır.

[!code-cpp[concrt-task-canceled#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_3.cpp)]

Değer tabanlı devamlar, açık bir belirteçle oluşturulmadığı sürece, öncül görevin belirteci olarak devraldığından, sekans görevi hala yürütülse bile devamlar hemen iptal edilen duruma girer. Bu nedenle, iptalden sonra öncül görev tarafından atılan herhangi bir özel durum devam görevlerine yayılmaz. İptal her zaman öncül görevin durumunu geçersiz kılar. Aşağıdaki örnek öncekine benzer, ancak değer tabanlı bir devamı için davranışı göstermektedir.

[!code-cpp[concrt-task-canceled#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_4.cpp)]

> [!CAUTION]
> `task` Bir iptal belirtecinin oluşturucuya veya [eşzamanlılık::create_task](reference/concurrency-namespace-functions.md#create_task) işlevine geçemezseniz, bu görev iptal edilemez. Ayrıca, tüm görevleri aynı anda iptal etmek için iç içe geçen görevlerin (diğer bir deyişle, başka bir görevin gövdesinde oluşturulan görevler) oluşturucuya aynı iptal belirteci aktarmanız gerekir.

İptal jetonu iptal edildiğinde rasgele kod çalıştırmak isteyebilirsiniz. Örneğin, kullanıcınız işlemi iptal etmek için kullanıcı arabiriminde bir **İptal** düğmesi seçerse, kullanıcı başka bir işlem başlatana kadar bu düğmeyi devre dışı kabilirsiniz. Aşağıdaki örnek, bir iptal jetonu iptal edildiğinde çalışan bir geri arama işlevini kaydetmek için [eşzamanlılık::cancellation_token::register_callback](reference/cancellation-token-class.md#register_callback) yöntemini gösterir.

[!code-cpp[concrt-task-cancellation-callback#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_5.cpp)]

Görev [Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) belgesi, değer tabanlı ve görev tabanlı devamlar arasındaki farkı açıklar. Bir devam görevine `cancellation_token` nesne sağlamazsanız, devamı aşağıdaki yollarla öncül görevden iptal belirteci devralır:

- Değer tabanlı bir devamı her zaman öncül görevin iptal belirteci devralır.

- Görev tabanlı bir devamı, öncül görevin iptal belirteci asla devralmaz. Görev tabanlı bir devamı iptal edilebilir hale getirmenin tek yolu, bir iptal jetonunu açıkça geçirmektir.

Bu davranışlar hatalı bir görevden etkilenmez (diğer bir şekilde, özel durum atan bir görev). Bu durumda, değer tabanlı devamı iptal edilir; görev tabanlı devamı iptal edilmez.

> [!CAUTION]
> Başka bir görevde oluşturulan bir görev (başka bir deyişle, iç içe geçen bir görev) üst görevin iptal jetonunu devralmaz. Yalnızca değer tabanlı bir devamı, öncül görevinin iptal belirteci devralır.

> [!TIP]
> Eşpara [birimini kullanın::cancellation_token::nesne](reference/cancellation-token-class.md#none) alan `cancellation_token` bir oluşturucu veya işlev ibaresini yaptığınızda ve işlemin iptal edilebilmesini istemediğiniz zaman yok yöntemi.

Bir `task_group` veya `structured_task_group` nesnenin oluşturucusuna bir iptal belirteci de sağlayabilirsiniz. Bunun önemli bir yönü, alt görev gruplarının bu iptal belirteci devralmasTır. Eşzamanlılık kullanarak bu kavramı gösteren bir örnek [için::aramak](reference/concurrency-namespace-functions.md#run_with_cancellation_token) `parallel_for`için çalıştırmak için run_with_cancellation_token işlevi , bu belgede daha sonra [Paralel Algoritmaları İptal](#algorithms) bakınız.

[[Üst](#top)]

#### <a name="cancellation-tokens-and-task-composition"></a>İptal Belirteçleri ve Görev Oluşturma

[Eşzamanlılık::when_all](reference/concurrency-namespace-functions.md#when_all) ve [eşzamanlılık::when_any](reference/concurrency-namespace-functions.md#when_all) işlevleri ortak desenleri uygulamak için birden çok görev oluşturmanıza yardımcı olabilir. Bu bölümde, bu işlevlerin iptal belirteçleriyle nasıl çalıştığı açıklanmaktadır.

Bu işlev, işlevin veya `when_all` `when_any` işlevin iptal inemi verdiğinizde, bu işlev yalnızca iptal jetonu iptal edildiğinde veya katılımcı görevlerinden biri iptal edilmiş durumda sona erdiğinde veya bir özel durum attığında iptal eder.

İşlev, `when_all` bir iptal belirteci sağlamadığınızda, genel işlemi oluşturan her görevden iptal jetonu devralır. Bu belirteçlerden `when_all` herhangi biri iptal edildiğinde ve katılımcı görevlerden en az biri henüz başlatılmadı veya çalışmaya başladığında iade edilen görev iptal edilir. Benzer bir davranış, görevlerden biri özel durum attığında da oluşur `when_all` - iade edilen görev bu özel durumla birlikte hemen iptal edilir.

Çalışma zamanı, görev tamamlandığında işlevden `when_any` döndürülen görevin iptal jetonunu seçer. Katılımcı görevlerden hiçbiri tamamlanmış bir durumda bitirmezse ve görevlerden biri veya daha fazlası özel durum atmazsa, atılan görevlerden biri tamamlamak için seçilir `when_any` ve belirteci son görevin belirteci olarak seçilir. Tamamlanan durumda birden fazla görev biterse, görevden `when_any` döndürülen görev tamamlanmış durumda sona erer. Çalışma zamanı, diğer yürütme görevleri daha sonraki bir noktada tamamlansa bile, iade `when_any` edilen görevin hemen iptal edilememesi için belirteci tamamlanma anında iptal edilmeyen tamamlanmış bir görev seçmeye çalışır.

[[Üst](#top)]

### <a name="using-the-cancel-method-to-cancel-parallel-work"></a><a name="cancel"></a>Paralel Çalışmayı İptal Etmek Için İptal Yöntemini Kullanma

[Eşzamanlılık::task_group::İptal](reference/task-group-class.md#cancel) ve [eşzamanlılık::structured_task_group::iptal](reference/structured-task-group-class.md#cancel) yöntemleri bir görev grubunu iptal durumuna ayarlar. Siz aradıktan `cancel`sonra, görev grubu gelecekteki görevleri başlatmaz. Yöntemler `cancel` birden çok alt görev tarafından çağrılabilir. İptal edilen bir görev eşzamanlılık neden [olur::task_group::bekleyin](reference/task-group-class.md#wait) ve [eşzamanlılık::structured_task_group::eşzamanlılık](reference/structured-task-group-class.md#wait) döndürmek için bekleme [yöntemleri::iptal .](reference/concurrency-namespace-enums.md#task_group_status)

Bir görev grubu iptal edilirse, her alt görevden çalışma süresine yapılan çağrılar, çalışma zamanının etkin görevleri iptal etmek için bir iç özel durum türü atmasını ve yakalamasına neden olan bir *kesinti noktası*tetikleyebilir. Eşzamanlı çalışma süresi belirli kesinti noktalarını tanımlamaz; çalışma zamanı için herhangi bir arama oluşabilir. Çalışma süresi, iptal gerçekleştirmek için attığı özel durumları işlemelidir. Bu nedenle, bir görevin gövdesinde bilinmeyen özel durumları işlemeyin.

Bir alt görev zaman alan bir işlem gerçekleştiriyorsa ve çalışma süresine çağrılmazsa, düzenli olarak iptal ve çıkış için zamanında kontrol etmelidir. Aşağıdaki örnek, çalışmanın ne zaman iptal edildiğini belirlemenin bir yolunu gösterir. Görev, `t4` bir hatayla karşılaştığında üst görev grubunu iptal eder. Görev `t5` bazen iptal `structured_task_group::is_canceling` için kontrol etmek için metodu çağrısır. Üst görev grubu iptal edilirse, `t5` görev bir ileti yazdırır ve çıkar.

[!code-cpp[concrt-task-tree#6](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_6.cpp)]

Bu örnek, görev döngüsünün her<sup>100</sup> yinelemesinde iptal edilmeyi denetler. İptal için denetleme sıklığı, görevin izinverdiği çalışma miktarına ve iptale yanıt vermek için görevlerin ne kadar hızlı olması gerektiğine bağlıdır.

Ana görev grubu nesnesine erişiminiz yoksa, ana görev grubunun iptal edilip edilemeyeceğini belirlemek için [eşzamanlılık::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) işlevini arayın.

Yöntem `cancel` yalnızca alt görevleri etkiler. Örneğin, paralel çalışma ağacının `tg1` çizimindeki görev grubunu iptal ederseniz, ağaçtaki `t3`tüm `t4`görevler `t5`(,`t1` `t2`, , , ve) etkilenir. İç içe olan görev grubunu `tg2`iptal `t4` ederseniz, yalnızca görevler ve `t5` etkilenir.

`cancel` Yöntemi aradığınızda, tüm alt görev grupları da iptal edilir. Ancak, iptal, paralel bir çalışma ağacında görev grubunun ebeveynlerini etkilemez. Aşağıdaki örnekler, paralel iş ağacı illüstrasyonu üzerine inşa ederek bunu göstermektedir.

Bu örneklerden ilki, görev grubunun `t4` `tg2`bir alt parçası olan görev için bir çalışma işlevi oluşturur. İş işlevi bir `work` döngü içinde işlevi çağırır. Herhangi bir `work` çağrı başarısız olursa, görev üst görev grubunu iptal eder. Bu, görev `tg2` grubunun iptal edilen durumu girmesine neden olur, ancak görev grubunu `tg1`iptal etmez.

[!code-cpp[concrt-task-tree#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_7.cpp)]

Bu ikinci örnek, görevin görev grubunu `tg1`iptal ettiği dışında ilkine benzer. Bu, ağaçtaki tüm`t1`görevleri `t2` `t3`etkiler `t4`( `t5`, , , , ve ).

[!code-cpp[concrt-task-tree#3](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_8.cpp)]

Sınıf `structured_task_group` iş parçacığı güvenli değildir. Bu nedenle, üst `structured_task_group` nesnesinin yöntemini çağıran bir alt görev belirtilmeyen davranış üretir. Bu kuralın `structured_task_group::cancel` istisnaları ve [eşzamanlılık::structured_task_group::is_canceling](reference/structured-task-group-class.md#is_canceling) yöntemleridir. A child task can call these methods to cancel the parent task group and check for cancellation.

> [!CAUTION]
> `task` Nesnenin alt bölümü olarak çalışan bir görev grubu tarafından gerçekleştirilen işi iptal etmek için iptal `task_group::cancel` jetonu kullanabilseniz de, görev grubunda çalışan nesneleri iptal `structured_task_group::cancel` `task` etmek için yöntemleri kullanamazsınız.

[[Üst](#top)]

### <a name="using-exceptions-to-cancel-parallel-work"></a><a name="exceptions"></a>Paralel Çalışmayı İptal Etmek İçin Özel Durumlar Kullanma

İptal belirteçlerinin ve `cancel` yöntemin kullanımı, paralel bir iş ağacını iptal etmede özel durum işlemeden daha verimlidir. İptal belirteçleri `cancel` ve yöntem, bir görevi ve alt görevleri yukarıdan aşağıya iptal eder. Tersine, özel durum işleme aşağıdan yukarıya doğru çalışır ve özel durum yukarı yayılır gibi bağımsız olarak her alt görev grubu iptal etmelidir. Konu [Özel Durum İşleması,](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md) Eşzamanlılık Çalışma Zamanı'nın hataları iletmek için özel durumları nasıl kullandığını açıklar. Ancak, tüm özel durumlar bir hata göstermez. Örneğin, bir arama algoritması sonucu bulduğunda ilişkili görevini iptal edebilir. Ancak, daha önce de belirtildiği gibi, özel `cancel` durum işleme paralel çalışmayı iptal etmek için yöntemi kullanmaktan daha az verimlidir.

> [!CAUTION]
> Yalnızca gerektiğinde paralel çalışmayı iptal etmek için özel durumlar kullanmanızı öneririz. İptal belirteçleri ve `cancel` görev grubu yöntemleri daha verimli ve hataya daha az yatkındır.

Bir görev grubuna geçtiğiniz bir iş işlevinin gövdesine bir özel durum attığınızda, çalışma zamanı bu özel durumu depolar ve özel durumu görev grubunun tamamlanmasını bekleyen içeriğe aktarAr. Yöntemde `cancel` olduğu gibi, çalışma zamanı henüz başlatılmayan tüm görevleri atar ve yeni görevleri kabul etmez.

Bu üçüncü örnek, bu görevin `t4` görev grubunu `tg2`iptal etmek için bir özel durum atması dışında ikincisini andırır. Bu örnek, `try` - `catch` görev grubu `tg2` alt görevlerinin tamamlanmasını beklerken iptali denetlemek için bir blok kullanır. İlk örnekte olduğu gibi, `tg2` bu görev grubunun iptal edilen durumu girmesine `tg1`neden olur, ancak görev grubunu iptal etmez.

[!code-cpp[concrt-task-tree#4](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_9.cpp)]

Bu dördüncü örnek, tüm çalışma ağacını iptal etmek için özel durum işleme kullanır. Örnek, görev grubu `tg1` alt görevlerini `tg2` beklediğinde yerine alt görevlerinin tamamlanmasını beklerken özel durumu yakalar. İkinci örnekte olduğu gibi, bu ağaçtaki `tg1` `tg2`her iki görev grubuna ve iptal edilen duruma girmeye neden olur.

[!code-cpp[concrt-task-tree#5](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_10.cpp)]

Bir `task_group::wait` alt `structured_task_group::wait` görev bir özel durum attığında ve yöntemler attığından, onlardan bir iade değeri almazsınız.

[[Üst](#top)]

## <a name="canceling-parallel-algorithms"></a><a name="algorithms"></a>Paralel Algoritmaları İptal Etme

PpL paralel algoritmalar, örneğin, `parallel_for`görev grupları üzerine inşa. Bu nedenle, paralel bir algoritmayı iptal etmek için aynı tekniklerin çoğunu kullanabilirsiniz.

Aşağıdaki örnekler, paralel bir algoritmayı iptal etmenin çeşitli yollarını göstermektedir.

Aşağıdaki örnek, `run_with_cancellation_token` `parallel_for` algoritmayı çağırmak için işlevi kullanır. İşlev `run_with_cancellation_token` bir bağımsız değişken olarak bir iptal belirteci alır ve sağlanan iş işlevini eşzamanlı olarak çağırır. Paralel algoritmalar görevler üzerine oluşturulduğundan, üst görevin iptal jetonunu devralır. Bu `parallel_for` nedenle, iptal yanıt verebilir.

[!code-cpp[concrt-cancel-parallel-for#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_11.cpp)]

Aşağıdaki örnekte [eşzamanlılık kullanır::structured_task_group::algoritmayı](reference/structured-task-group-class.md#run_and_wait) `parallel_for` çağırmak için run_and_wait yöntemi. Yöntem, `structured_task_group::run_and_wait` sağlanan görevin tamamlanmasını bekler. Nesne, `structured_task_group` iş işlevinin görevi iptal etmesini sağlar.

[!code-cpp[concrt-task-tree#7](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_12.cpp)]

Bu örnek, aşağıdaki çıktıyı üretir.

```Output
The task group status is: canceled.
```

Aşağıdaki örnekte, bir `parallel_for` döngüyü iptal etmek için özel durum işleme kullanır. Çalışma zamanı, çağrı bağlamına özel durumu mareşaller.

[!code-cpp[concrt-task-tree#9](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_13.cpp)]

Bu örnek, aşağıdaki çıktıyı üretir.

```Output
Caught 50
```

Aşağıdaki örnekte, bir `parallel_for` döngüde iptali koordine etmek için Boolean bayrağı kullanır. Bu örnek, genel görev kümesini `cancel` iptal etmek için yöntem veya özel durum işleme yi kullanmadığından, her görev çalışır. Bu nedenle, bu teknik bir iptal mekanizması daha fazla hesaplama yükü olabilir.

[!code-cpp[concrt-task-tree#8](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_14.cpp)]

Her iptal yönteminin diğerlerine göre avantajları vardır. Özel gereksinimlerinize uygun yöntemi seçin.

[[Üst](#top)]

## <a name="when-not-to-use-cancellation"></a><a name="when"></a>İptal Ne Zaman Kullanılmaz?

İptal kullanımı, ilgili görevler grubunun her üyesi zamanında çıkabiliyorsa uygundur. Ancak, iptalin başvurunuz için uygun olmadığı bazı senaryolar vardır. Örneğin, görev iptali işbirliği olduğundan, tek bir görev engellenirse, genel görev kümesi iptal etmez. Örneğin, bir görev henüz başlatılmamışsa, ancak başka bir etkin görevin engelini kılırsa, görev grubu iptal edilirse başlamaz. Bu, uygulamanızda kilitlenme oluşmasına neden olabilir. İptal kullanımının uygun olmadığı ikinci bir örnek, bir görevin iptal edilmesidir, ancak alt görevi kaynağı serbest duruma alma gibi önemli bir işlem gerçekleştirir. Ana görev iptal edildiğinde genel görev kümesi iptal edildiğinden, bu işlem yürütülmez. Bu noktayı gösteren bir örnek için, Paralel Desenler Kitaplığı konusundaki En İyi Uygulamalar'da [İptal ve Özel Durum İşleme'nin Nesne Yok Oluşu](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) bölümünü nasıl etkilediğini anlayın bölümüne bakın.

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|Paralel arama algoritması uygulamak için iptalin nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Temel bir ağaç `task_group` yapısı için arama algoritması yazmak için sınıfın nasıl kullanılacağını gösterir.|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Çalışma zamanının görev grupları, hafif görevler ve eşzamanlı aracılar tarafından atılan özel durumları nasıl işleyeceğini ve uygulamalarınızdaki özel durumlara nasıl yanıt verilebildiğini açıklar.|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Görevlerin görev gruplarıyla nasıl ilişkili olduğunu ve uygulamalarınızda yapılandırılmamış ve yapılandırılmış görevleri nasıl kullanabileceğinizi açıklar.|
|[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)|Veri koleksiyonları üzerinde aynı anda çalışma gerçekleştiren paralel algoritmaları açıklar|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Paralel Desenler Kitaplığı'na genel bir bakış sağlar.|

## <a name="reference"></a>Başvuru

[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)

[cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)

[cancellation_token Sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)

[task_group Sınıfı](reference/task-group-class.md)

[structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)

[parallel_for Fonksiyonu](reference/concurrency-namespace-functions.md#parallel_for)
