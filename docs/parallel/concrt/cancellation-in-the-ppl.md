---
title: Ppl'de iptal | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel algorithms, canceling [Concurrency Runtime]
- canceling parallel algorithms [Concurrency Runtime]
- parallel tasks, canceling [Concurrency Runtime]
- cancellation in the PPL
- parallel work trees [Concurrency Runtime]
- canceling parallel tasks [Concurrency Runtime]
ms.assetid: baaef417-b2f9-470e-b8bd-9ed890725b35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17babc058ef3e1851da686e9a8c5bf17cefbc2fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427010"
---
# <a name="cancellation-in-the-ppl"></a>PPL'de İptal

Bu belge, paralel Desen kitaplığı (PPL), paralel işi iptal etmek nasıl ve ne zaman paralel işi iptal edildi belirleme iptal rolünü açıklar.

> [!NOTE]
>  Çalışma zamanı özel durum işleme iptal uygulamak için kullanır. Catch değildir veya kodunuzda bu özel durumları işleme. Ayrıca, görevleriniz için işlev gövdeleri içinde özel durum-güvenli kod yazma öneririz. Örneği için kullanabileceğiniz *olduğu kaynak alımı başlatma* (RAII) deseni, bir görev gövdesinde bir özel durum oluştuğunda kaynaklar düzgün şekilde işlendiğinden emin olmak için. İptal edilebilen bir görevi kaynak temizlemek için RAII deseni kullanan tam bir örnek için bkz [izlenecek yol: bir kullanıcı arabirimi iş parçacığı kaldırma çalışma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md).

## <a name="key-points"></a>Önemli Noktalar

- İptali ortaktır ve yanıt iptali için görev ile iptal isteklerini koduyla arasında koordinasyon içerir.

- Mümkün olduğunda, işi iptal etmek için İptal belirteçlerini kullanın. [Concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) sınıfı tanımlayan bir iptal belirteci.

- İptal belirteçleri kullandığınızda, kullanın [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) iptal işlemini başlatmak için yöntem ve [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) yanıt işlevi İptali. Kullanım [is_canceled](reference/cancellation-token-class.md#is_canceled) başka bir görev iptal isteğinde olup olmadığını denetlemek için yöntem.

- İptal hemen gerçekleşmez. Bir görevi veya görev grubunu iptal ederseniz yeni iş başlatılmadı olsa da, etkin çalışma denetleyin ve iptal için yanıt.

- Değer tabanlı devamlılık, öncül görev iptal belirtecini devralır. Bir görev tabanlı devamlılık hiç öncül görevinin belirtecini devralır.

- Kullanım [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) metodu bir oluşturucu veya alan işlev çağırdığınızda bir `cancellation_token` nesne, ancak işlemi edilebilen olmasını istemiyorsanız. Ayrıca, bir iptal belirteci için geçirmezseniz [concurrency::task](../../parallel/concrt/reference/task-class.md) Oluşturucusu veya [concurrency::create_task](reference/concurrency-namespace-functions.md#create_task) işlevi, bu görev değil edilebilen.

##  <a name="top"></a> Bu belgede

- [Paralel çalışma ağaçları](#trees)

- [Paralel görevleri iptal etme](#tasks)

    - [Paralel işi iptal etmek için bir iptal belirteci kullanma](#tokens)

    - [Yöntemi paralel işi iptal etmek için İptal'i kullanma](#cancel)

    - [Paralel işi iptal etmek için özel durumlar kullanma](#exceptions)

- [Paralel algoritmaları iptal etme](#algorithms)

- [İptalin kullanılmayacağı zaman](#when)

##  <a name="trees"></a> Paralel çalışma ağaçları

PPL, hassas görevler ve hesaplamalar yönetmek için görevler ve görev grupları kullanır. Görev grupları forma iç içe yerleştirebilirsiniz *ağaçları* paralel iş. Paralel iş ağacında aşağıdaki çizimde gösterilmektedir. Bu çizimde, `tg1` ve `tg2` görev grupları; temsil eder `t1`, `t2`, `t3`, `t4`, ve `t5` görev grupları gerçekleştiren iş temsil eder.

![Paralel iş ağacında](../../parallel/concrt/media/parallelwork_trees.png "parallelwork_trees")

Aşağıdaki örnek çizimde ağacı oluşturmak için gereken kod gösterilir. Bu örnekte, `tg1` ve `tg2` olan [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnelerini; `t1`, `t2`, `t3`, `t4`, ve `t5` olan [concurrency::task_handle](../../parallel/concrt/reference/task-handle-class.md) nesneleri.

[!code-cpp[concrt-task-tree#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_1.cpp)]

Ayrıca [concurrency::task_group](reference/task-group-class.md) benzer bir iş ağacı oluşturmak için sınıf. [Concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı, ayrıca iş ağacının kavramını destekler. Ancak, bir `task` bir bağımlılık ağacı ağacıdır. İçinde bir `task` ağacında, gelecekteki works tamamlandıktan sonra geçerli çalışma. Bir görev grubu ağacında, iç iş dış iş önce tamamlanır. Görevler ve görev grupları arasındaki farklar hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

[[Üst](#top)]

##  <a name="tasks"></a> Paralel görevleri iptal etme

Paralel işi iptal etmek için birden çok yolu vardır. Tercih edilen yol, bir iptal belirteci kullanmaktır. Görev grupları da desteği [concurrency::task_group::cancel](reference/task-group-class.md#cancel) yöntemi ve [CONCURRENCY::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) yöntemi. Son özel durum bir görev iş işlevin gövdesinde yöntemdir. Seçtiğiniz yöntem ne olursa olsun, iptal hemen gerçekleşmez anlayın. Bir görevi veya görev grubunu iptal ederseniz yeni iş başlatılmadı olsa da, etkin çalışma denetleyin ve iptal için yanıt.

Paralel görevleri iptal etme daha fazla örnek için bkz [izlenecek yol: görevleri kullanarak bağlanma ve XML HTTP isteklerini](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md), [nasıl yapılır: paralel bir döngüden kullanım İptalden sona](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md), ve [nasıl yapılır: kullanın Özel durum paralel bir döngüden kurtulmak için işlemeyi](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).

###  <a name="tokens"></a> Paralel işi iptal etmek için bir iptal belirteci kullanma

`task`, `task_group`, Ve `structured_task_group` sınıfları iptal belirteçlerini kullanımıyla iptal etmeyi destekler. PPL tanımlar [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md) ve [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) bu amaç için sınıflar. İşi iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı için bu belirteci abone yeni iş başlamıyor. Zaten etkin olan iş kullanabileceğiniz [is_canceled](../../parallel/concrt/reference/cancellation-token-class.md#is_canceled) iptal belirtecini izlemek ve mümkün olduğunda durdurmak için üye işlevi.

İptal işlemini başlatmak için çağrı [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) yöntemi. Bu şekilde iptal yanıt verin:

- İçin `task` nesneleri kullanan [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) işlevi. `cancel_current_task` Geçerli görev ve tüm alt değer tabanlı devamlılık iptal eder. (İptal iptal etmez *belirteci* görev veya devamlılıkları ile ilişkili.)

- Görev grupları ve paralel algoritmalar için [concurrency::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) iptal algılayın ve bu işlevi döndüğünde görevin gövdesinden olabildiğince çabuk döndürmek için işlevi `true`. (Çağırmayın `cancel_current_task` bir görev grubundan.)

Aşağıdaki örnek, görev iptali için ilk temel düzeni gösterir. Görevin gövdesini bazen bir döngü içinde iptalleri denetler.

[!code-cpp[concrt-task-basic-cancellation#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_2.cpp)]

`cancel_current_task` İşlev oluşturur; bu nedenle açıkça geçerli döngü ya da işlev dönüş gerekmez.

> [!TIP]

>  Alternatif olarak, çağırabilirsiniz [concurrency::interruption_point](reference/concurrency-namespace-functions.md#interruption_point) yerine işlev `cancel_current_task`.

Çağrılacak önemlidir `cancel_current_task` ne zaman yanıt iptali için çünkü görev iptal edildi durumuna geçer. Çağırmak yerine erken dönüş yaparsa `cancel_current_task`işlemi tamamlanmış duruma geçer ve herhangi bir değer tabanlı devamlılık çalıştırılır.

> [!CAUTION]
>  Hiçbir zaman throw `task_canceled` kodunuzdan. Çağrı `cancel_current_task` yerine.

Bir görev iptal edildi durumunda sona erdiğinde [CONCURRENCY::Task:: get](reference/task-class.md#get) yöntem [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md). (Buna karşılık, [CONCURRENCY::Task:: wait](reference/task-class.md#wait) döndürür [task_status::canceled](reference/concurrency-namespace-enums.md#task_group_status) ve oluşturmaz.) Aşağıdaki örnek, bir görev tabanlı devamlılık için bu davranış gösterir. Hatta öncül görev iptal edildiğinde görev tabanlı devamlılık her zaman çağrılır.

[!code-cpp[concrt-task-canceled#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_3.cpp)]

Bunlar açık bir belirteç ile oluşturulan sürece değer tabanlı devamlılık, öncül görevinin belirtecini devralır. çünkü bile öncül görevin hala Yürütülüyor iken devamlılıklar hemen iptal edildi durumuna geçilmesidir. Bu nedenle, tarafından öncül görev iptal işleminden sonra oluşturulan tüm özel durum için devamlılık görevleri dağıtılmadı. Her zaman iptal öncül görevin durumunu geçersiz kılar. Aşağıdaki örnek, önceki benzer, ancak bir değer tabanlı devamlılık için davranış gösterir.

[!code-cpp[concrt-task-canceled#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_4.cpp)]

> [!CAUTION]

>  Bir iptal belirteci için geçirmezseniz `task` Oluşturucusu veya [concurrency::create_task](reference/concurrency-namespace-functions.md#create_task) işlevi, bu görev değil edilebilen. Ayrıca, tüm iç içe geçmiş görevler (diğer bir deyişle, başka bir görev gövdesinde oluşturulan görevler) oluşturucusuna aynı iptal belirtecini geçmesi gereken tüm görevleri aynı anda iptal etmek için.

Bir iptal belirteci iptal edildiğinde rasgele kodu çalıştırmak isteyebilirsiniz. Örneğin, kullanıcı seçerse bir **iptal** düğmesi kullanıcı başka bir işlemi başlayana kadar işlemi iptal etmek için kullanıcı arabiriminde, bu düğmeyi devre dışı bırakılamadı. Aşağıdaki örnek nasıl kullanılacağını gösterir [CONCURRENCY::cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) bir iptal belirteci iptal edildiğinde, çalışan bir geri çağırma işlevini kaydetmek için yöntemi.

[!code-cpp[concrt-task-cancellation-callback#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_5.cpp)]

Belge [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) değeri ve görev tabanlı devamlılık arasındaki farkı açıklar. Belirtmezseniz, bir `cancellation_token` nesne için bir devamlılık görevi, devamlılık öncül görevi iptal belirteci aşağıdaki yollarla devralır:

- Değer tabanlı devamlılık her zaman, öncül görevin iptal belirtecini devralır.

- Bir görev tabanlı devamlılık, öncül görevin iptal belirtecini hiçbir zaman devralır. Bir görev tabanlı devamlılık iptal edilebilir hale getirmek için tek yolu bir iptal belirteci açıkça geçirmektir.

Bu davranışların bir hatalı göreviyle (diğer bir deyişle, bir özel durum oluşturan) etkilenmez. Bu durumda, bir değer tabanlı devamlılık iptal edildi; bir görev tabanlı devamlılık iptal edilmedi.

> [!CAUTION]
>  Başka bir görev (diğer bir deyişle, iç içe bir görevdir) oluşturulan bir görev üst görevin iptal belirtecini devralmaz. Yalnızca bir değer tabanlı devamlılık, öncül görev iptal belirtecini devralır.

> [!TIP]

>  Kullanım [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) bir oluşturucu veya alan işlev çağırdığınızda yöntemi bir `cancellation_token` nesne ve işlem edilebilen olmasını istemiyorsanız.

Ayrıca bir iptal belirteci oluşturucusuna sağlayabilir bir `task_group` veya `structured_task_group` nesne. Bu önemli bir yönüdür alt görev grupları bu iptal belirteci Devral ' dir. Bu kavramı kullanarak gösteren bir örnek için [concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) işlevi çağırmak için çalıştırılacak `parallel_for`, bkz: [paralel algoritmaları iptal etme](#algorithms) daha sonra bu Belge.

[[Üst](#top)]

#### <a name="cancellation-tokens-and-task-composition"></a>İptal Belirteçleri ve Görev Oluşturma

[Concurrency::when_all](reference/concurrency-namespace-functions.md#when_all) ve [concurrency::when_any](reference/concurrency-namespace-functions.md#when_all) işlevleri, genel desenleri uygulamak için birden çok görevi oluşturan yardımcı olabilir. Bu bölümde, bu işlevler iptal belirteçleri ile nasıl çalıştığı açıklanmaktadır.

Bir iptal belirteci ya da sağladığınız ne zaman `when_all` ve `when_any` işlevi yalnızca bu iptal belirteci iptal edildiğinde ya da katılımcıdan biri görevleri iptal edilmiş duruma biter ya da bir özel durum oluşturur iptal işlev.

`when_all` İşlevi, ona bir iptal belirteci belirtmediğinizde, genel işlem ölçeklemesini her görevin iptal belirtecini devralır. Öğesinden döndürülen görev `when_all` bu belirteçlerden birini iptal edilir ve en az bir katılımcı görevleri henüz başlamamış ya da çalıştığından iptal edildi. Benzer bir davranış görevlerinden birini ve bir özel durum - öğesinden döndürülen görev oluşturduğunda gerçekleşir `when_all` hemen o özel durumu ile iptal edildi.

Öğesinden döndürülen görevin iptal belirtecini çalışma zamanının seçtiği `when_any` , görev tamamlandığında işlev. Katılımcı görevleri hiçbiri tamamlanmış durumda tamamlamak ve bir veya daha fazla görevleri bir özel durum oluşturursa, oluşturdu görevlerinden birini ve tamamlanması seçilir `when_any` ve kendi belirteç son görevin belirteciyle seçilir. Birden fazla görev tamamlanmış tamamlanırsa durumunda, öğesinden döndürülen görev `when_any` görevi tamamlanmış durumda sonlandırır. Görev, böylece belirteci tamamlama zaman değil iptal tamamlanan bir görev seçmek çalışma zamanı çalıştığında döndürülen `when_any` sonraki bir noktada yürütülen diğer görevleri tamamlayabilir olsa bile hemen iptal edilmedi.

[[Üst](#top)]

###  <a name="cancel"></a> Yöntemi paralel işi iptal etmek için İptal'i kullanma

[Concurrency::task_group::cancel](reference/task-group-class.md#cancel) ve [CONCURRENCY::structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) yöntemleri görev grubunu iptal edilmiş duruma ayarlayın. Çağırdıktan sonra `cancel`, görev grubunun gelecekteki görevleri başlamaz. `cancel` Yöntemleri birden çok alt görev tarafından çağrılabilir. İptal edilen bir görev neden [CONCURRENCY::task_group:: wait](reference/task-group-class.md#wait) ve [CONCURRENCY::structured_task_group](reference/structured-task-group-class.md#wait) döndürülecek yöntemleri [concurrency::canceled](reference/concurrency-namespace-enums.md#task_group_status).

Görev grubunu iptal edilirse, her alt görev çağrılarından zamanına tetikleyebilirsiniz bir *kesinti noktası*, throw ve catch etkin görevleri iptal etmek için bir iç özel durum türü için çalışma zamanı neden olur. Eşzamanlılık Çalışma zamanı, belirli bir kesinti noktaları tanımlamıyor; çalışma zamanı herhangi bir çağrıda oluşabilir. Çalışma zamanı iptal gerçekleştirmek için oluşturduğu özel durum işlemesi gerekir. Bu nedenle, bir görev gövdesinde Bilinmeyen özel durum işleyemez.

Bir alt görevi zaman alıcı bir işlem gerçekleştirir ve çalışma zamanına çağırmaz, bunu düzenli olarak iptalleri denetlemek ve zamanında çıkmak gerekir. Aşağıdaki örnek zaman iş iptal edildi belirlemenin bir yolunu gösterir. Görev `t4` hatayla karşılaştığında, üst görev grubunu iptal eder. Görev `t5` bazen çağırır `structured_task_group::is_canceling` iptalleri denetlemek için yöntemi. Üst görev grubunu iptal edilirse, görev `t5` bir ileti yazdırır ve çıkar.

[!code-cpp[concrt-task-tree#6](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_6.cpp)]

Bu örnekte her 100 iptal denetler<sup>th</sup> görev döngü yinelemesi. Miktarını, görevi gerçekleştiren iş ve görevler iptal için yanıt vermesi için gereken nasıl hızlı bir şekilde sıklığı ile iptalleri denetlemek bağlıdır.

Üst görev grubu nesnesine erişimi yoksa, çağrı [concurrency::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) üst görev grubunu iptal olup olmadığını belirlemek için işlevi.

`cancel` Yöntemi yalnızca alt görevler etkiler. Örneğin, görev grubunu iptal ederseniz `tg1` paralel iş ağacında çizimde, tüm görevler ağacında (`t1`, `t2`, `t3`, `t4`, ve `t5`) etkilenir. İç içe geçmiş görev grubunu iptal ederseniz `tg2`, yalnızca görevlerin `t4` ve `t5` etkilenir.

Çağırdığınızda `cancel` yöntemi, tüm alt görev grupları da iptal edilir. Ancak, iptal, paralel iş ağacında görev grubunun herhangi bir üst öğeye etkilemez. Aşağıdaki örnekler paralel iş ağacında çizim oluşturarak gösterir.

Bu örneklerin ilk görev bir iş işlevi oluşturur `t4`, bir alt görev grubunun olduğu `tg2`. İş işlevi işlevini çağırır `work` döngü içinde. Tüm çağırırsanız `work` başarısız olursa, görev, üst görev grubunu iptal eder. Bu görev grubu neden `tg2` iptal edildi durumunda olacaktır ancak girmek için görev grubunu iptal etmez `tg1`.

[!code-cpp[concrt-task-tree#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_7.cpp)]

Bu ikinci örnekte birinci benzer görev grubu görevi iptal `tg1`. Bu, tüm görevler ağacında etkiler (`t1`, `t2`, `t3`, `t4`, ve `t5`).

[!code-cpp[concrt-task-tree#3](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_8.cpp)]

`structured_task_group` Sınıf iş parçacığı açısından güvenli değildir. Bu nedenle, kendi üst öğesi bir yöntemi çağıran bir alt görev `structured_task_group` nesne belirtilmeyen bir davranış üretir. Bu kuralın istisnaları `structured_task_group::cancel` ve [CONCURRENCY::structured_task_group:: is_canceling](reference/structured-task-group-class.md#is_canceling) yöntemleri. Bir alt görev üst görev grubunu iptal etmek ve iptali denetlemek için bu yöntemleri çağırabilir.

> [!CAUTION]
>  Bir alt öğesi olarak çalıştırılan bir görev grubu tarafından gerçekleştirilen işi iptal etmek için bir iptal belirteci kullanabilirsiniz, ancak bir `task` nesne kullanamazsınız `task_group::cancel` veya `structured_task_group::cancel` iptal için yöntemleri `task` bir görev grubunda Çalıştır nesneleri.

[[Üst](#top)]

###  <a name="exceptions"></a> Paralel işi iptal etmek için özel durumlar kullanma

İptal belirteçleri kullanımını ve `cancel` yöntemi özel durum işleme bir paralel iş ağacında iptal etme sırasında daha verimlidir. İptal belirteçleri ve `cancel` yöntemi, yukarıdan aşağıya doğru bir şekilde bir görevi ve alt görev iptal. Buna karşılık, özel durum işleme bir aşağıdan yukarıya şekilde çalışır ve özel durum yukarı yayar gibi her bir alt görev grubu bağımsız olarak iptal etmeniz gerekir. Konu [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md) özel durumları eşzamanlılık çalışma zamanı hataları iletişim kurmak için nasıl kullandığını açıklar. Ancak, tüm özel durumlar bir hata gösterir. Örneğin, bir arama algoritması sonucu bulduğunda, ilişkili görev iptal. Ancak, daha önce belirtildiği gibi özel durum işleme kullanmaktan daha az verimlidir `cancel` paralel işi iptal etmek için yöntemi.

> [!CAUTION]
>  Yalnızca gerekli olduğunda, paralel işi iptal etmek için özel durumlar kullanmanızı öneririz. İptal belirteçleri ve görev grubu `cancel` yöntemlerdir daha verimli ve hata potansiyeli daha az.

Bir görev grubuna geçirdiğiniz bir iş işlevinin gövdesi bir özel durum throw, çalışma zamanı bu özel durum depolar ve görev grubunun tamamlanmasını bekler bağlam özel durumu sürekliliğe devreder. Olduğu gibi `cancel` yöntemi, çalışma zamanı henüz başlamamış ve yeni görevler kabul etmiyor herhangi bir görevi atar.

Bu görev dışında ikincisi bu üçüncü örnek benzer `t4` görev grubunu iptal etmek için bir özel durum oluşturur `tg2`. Bu örnekte bir `try` - `catch` blok iptalleri denetlemek için görev grubunun `tg2` kendi alt görevlerin tamamlanmasını bekler. İlk örnekteki gibi bu görev grubunun neden `tg2` iptal edildi durumunda olacaktır ancak girmek için görev grubunu iptal etmez `tg1`.

[!code-cpp[concrt-task-tree#4](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_9.cpp)]

Dördüncü Bu örnek, tüm iş ağacında iptal etmek için özel durum işleme kullanır. Örnek özel durumu yakalar grubu ne zaman görev `tg1` alt görevleri yerine ne zaman bitmesini bekler görev grubu `tg2` kendi alt görevlerin tamamlanmasını bekler. İkinci örnekteki gibi bu görevlerin her ikisinde ağacında neden `tg1` ve `tg2`, iptal edilmiş duruma girin.

[!code-cpp[concrt-task-tree#5](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_10.cpp)]

Çünkü `task_group::wait` ve `structured_task_group::wait` yöntemleri throw alt görev özel durum oluşturduğunda, dönüş değeri bunları almazsınız.

[[Üst](#top)]

##  <a name="algorithms"></a> Paralel algoritmaları iptal etme

Paralel algoritmalar ppl'de, örneğin, `parallel_for`, görev grupları oluşturun. Bu nedenle, bir paralel algoritma iptal etmek için birçok aynı teknikleri kullanabilirsiniz.

Aşağıdaki örnekler, paralel algoritma iptal etmek için çeşitli yollar gösterir.

Aşağıdaki örnekte `run_with_cancellation_token` işlevi çağırmak için `parallel_for` algoritması. `run_with_cancellation_token` İşlevi bir iptal belirteci bağımsız değişken olarak alır ve sağlanan çalışma işlevi zaman uyumlu olarak çağırır. Paralel algoritmalar görevleri yerleşik olduğundan, bunlar üst görevin iptal belirtecini devralır. Bu nedenle, `parallel_for` iptal için yanıt verebilir.

[!code-cpp[concrt-cancel-parallel-for#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_11.cpp)]

Aşağıdaki örnekte [CONCURRENCY::structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait) çağrılacak yöntem `parallel_for` algoritması. `structured_task_group::run_and_wait` Yöntemi sağlanan görevin tamamlanmasını bekler. `structured_task_group` Nesnesi görev iptal etmek iş işlevi sağlar.

[!code-cpp[concrt-task-tree#7](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_12.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
The task group status is: canceled.
```

Aşağıdaki örnek, iptal etmek için özel durum işleme kullanan bir `parallel_for` döngü. Çalışma zamanı özel durumu çağıran bağlamını sürekliliğe devreder.

[!code-cpp[concrt-task-tree#9](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_13.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Caught 50
```

Aşağıdaki örnek, iptali koordine etmek için bir Boole bayrağı kullanır. bir `parallel_for` döngü. Bu örnekte kullanmaz çünkü her görev çalıştırır `cancel` genel dizi görevi iptal etmek için yöntemi veya özel durum işleme. Bu nedenle, bu teknik, iptal mekanizması daha fazla hesaplama ek yüküne sahip olabilir.

[!code-cpp[concrt-task-tree#8](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_14.cpp)]

Her iptal yöntemi diğer avantajları vardır. Belirli ihtiyaçlarınıza uygun yöntemi seçin.

[[Üst](#top)]

##  <a name="when"></a> İptalin kullanılmayacağı zaman

İlgili görevlerin bir grubun her üyesi zamanında çıkabilirsiniz iptal kullanımını uygundur. Bununla birlikte, burada iptal uygulamanız için uygun olmayabilir bazı senaryolar vardır. Görev iptali ortaktır olduğundan herhangi bir görev engellenirse gibi genel dizi görevi iptal. Görev grubunu iptal edilirse Örneğin, bir görev henüz başlamadı, ancak başka bir etkin görev kaldırır, onu başlatılmaz. Bu, uygulamanızda gerçekleşecek şekilde kilitlenmeye neden olabilir. Burada iptal kullanımını uygun olmayabilir, ikinci bir örneği bir görev iptal edildi, ancak alt öğesi bir kaynağı serbest bırakmak gibi önemli bir işlem gerçekleştirir andır. Genel görev kümesini, üst görev iptal edildiğinde iptal edilir çünkü bu işlem yürütmez. Bu noktaya gösteren bir örnek için bkz: [anlayın nasıl iptal ve özel durum işleme etkileyen nesne yok etme](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) paralel desenler kitaplığı konusundaki en iyi uygulamalar bölümünde.

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|Paralel arama algoritması uygulamak için İptal kullanmayı gösterir.|
|[Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Nasıl kullanılacağını gösterir `task_group` temel ağaç yapısı için bir arama algoritması yazma sınıfı.|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Çalışma zamanının görev grupları, Basit görevler ve zaman uyumsuz aracılar tarafından oluşturulan özel durumları nasıl işlediğini ve uygulamalarınızda özel durumları yanıt verecek şekilde nasıl açıklar.|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Görevler, görev grupları nasıl ilişkili olduğunu ve yapılandırılmamış ve yapılandırılmış görevler uygulamalarınızda nasıl kullanabileceğinizi açıklar.|
|[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)|Eşzamanlı koleksiyon veri çalışma gerçekleştirme paralel algoritmalar açıklar|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Paralel Desen kitaplığı genel bir bakış sağlar.|

## <a name="reference"></a>Başvuru

[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)

[cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)

[cancellation_token Sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)

[task_group sınıfı](reference/task-group-class.md)

[structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)

[parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)

