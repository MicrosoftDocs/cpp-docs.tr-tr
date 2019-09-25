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
ms.openlocfilehash: 3a7f9c5720c4bd6a43a1a95f9bc19680ba0a9c1e
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "69631719"
---
# <a name="cancellation-in-the-ppl"></a>PPL'de İptal

Bu belgede, paralel Desenler kitaplığı 'nda (PPL) iptal etme rolü, paralel çalışmayı iptal etme ve paralel çalışmanın ne zaman iptal edildiğini belirleme açıklanmaktadır.

> [!NOTE]
>  Çalışma zamanı, iptali uygulamak için özel durum işlemeyi kullanır. Kodunuzda bu özel durumları yakalamayın veya işleyin. Ayrıca, görevleriniz için işlev gövdelerinde özel durum güvenli kod yazmanızı öneririz. Örneğin, bir görevin gövdesinde bir özel durum oluştuğunda kaynakların doğru işlenmesini sağlamak için *kaynak alımı başlatma* (rampa) modelini kullanabilirsiniz. İptal edilebilen bir görevde bir kaynağı temizlemek için, esii deseninin kullanıldığı tüm bir örnek için bkz [. İzlenecek yol: Kullanıcı arabirimi Iş parçacığından](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)iş kaldırma.

## <a name="key-points"></a>Önemli Noktalar

- İptali birlikte çalışır ve iptali isteyen kod ve iptal 'e yanıt veren görev arasında eşgüdüm içerir.

- Mümkün olduğunda, çalışmayı iptal etmek için iptal belirteçlerini kullanın. [Concurrency:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) sınıfı bir iptal belirteci tanımlar.

- İptal belirteçlerini kullandığınızda, iptali başlatmak için [concurrency:: cancellation_token_source:: Cancel](reference/cancellation-token-source-class.md#cancel) metodunu ve iptal 'e yanıt vermek için [concurrency:: cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) işlevini kullanın. Başka bir görevin iptal isteyip olmadığını denetlemek için [concurrency:: cancellation_token:: is_canceled](reference/cancellation-token-class.md#is_canceled) metodunu kullanın.

- İptal hemen gerçekleşmez. Bir görev veya görev grubu iptal edilirse, yeni iş başlatılmamış olsa da, etkin çalışmanın iptali denetlemesi ve iptali yanıt vermesi gerekir.

- Değer tabanlı devamlılık, öncül görevinin iptal belirtecini devralır. Görev tabanlı devamlılık hiçbir şekilde öncül görevinin belirtecini devralmasıdır.

- Bir`cancellation_token` nesne alan bir Oluşturucu veya işlevi çağırdığınızda ancak işlemin iptal edilebilir olmasını istemediğiniz durumlarda [concurrency:: cancellation_token:: None](reference/cancellation-token-class.md#none) metodunu kullanın. Ayrıca, [concurrency:: Task](../../parallel/concrt/reference/task-class.md) oluşturucusuna veya [concurrency:: create_task](reference/concurrency-namespace-functions.md#create_task) işlevine bir iptal belirteci geçirmezseniz, bu görev iptal edilemez.

##  <a name="top"></a>Bu belgede

- [Paralel Iş ağaçları](#trees)

- [Paralel görevleri iptal etme](#tasks)

    - [Paralel Işi Iptal etmek için Iptal belirteci kullanma](#tokens)

    - [Paralel Işi Iptal etmek için Cancel metodunu kullanma](#cancel)

    - [Paralel Işi Iptal etmek için özel durumlar kullanma](#exceptions)

- [Paralel algoritmaları iptal etme](#algorithms)

- [Iptal etme ne zaman kullanılmaz](#when)

##  <a name="trees"></a>Paralel Iş ağaçları

PPL, ayrıntılı görevleri ve hesaplamaları yönetmek için görevler ve görev grupları kullanır. Paralel çalışmanın *ağaçlarını* oluşturmak için görev gruplarını iç içe geçirebilirsiniz. Aşağıdaki çizimde bir paralel çalışma ağacı gösterilmektedir. Bu çizimde `tg1` ve `tg2` görev gruplarını temsil eder; `t1` ,,,`t5` ve görev gruplarının gerçekleştirdiği işi temsil eder. `t2` `t3` `t4`

![Paralel çalışma ağacı](../../parallel/concrt/media/parallelwork_trees.png "Paralel çalışma ağacı")

Aşağıdaki örnek, resimde ağaç oluşturmak için gereken kodu gösterir. Bu örnekte `tg1` ve `tg2` [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Objects; `t1` ,`t2`,, ve`t5` , [concurrency:: task_handle](../../parallel/concrt/reference/task-handle-class.md) nesneleri. `t3` `t4`

[!code-cpp[concrt-task-tree#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_1.cpp)]

Ayrıca, benzer bir iş ağacı oluşturmak için [concurrency:: task_group](reference/task-group-class.md) sınıfını da kullanabilirsiniz. [Concurrency:: Task](../../parallel/concrt/reference/task-class.md) sınıfı ayrıca bir iş ağacı kavramını destekler. Ancak, `task` ağaç bir bağımlılık ağacıdır. Bir `task` ağaçta, gelecekteki işler geçerli iş sonrasında tamamlanır. Bir görev grubu ağacında, iç iş, dış çalışmadan önce tamamlanır. Görevler ve görev grupları arasındaki farklılıklar hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

[[Üst](#top)]

##  <a name="tasks"></a>Paralel görevleri iptal etme

Paralel çalışmayı iptal etmenin birden çok yolu vardır. Tercih edilen yol, bir iptal belirteci kullanmaktır. Görev grupları ayrıca [concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) yöntemini ve [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) metodunu destekler. Son yöntem, bir görev çalışma işlevinin gövdesinde özel durum oluşturmak için kullanılır. Hangi yöntemi seçerseniz seçin, iptal işleminin hemen gerçekleşmediğinden emin olun. Bir görev veya görev grubu iptal edilirse, yeni iş başlatılmamış olsa da, etkin çalışmanın iptali denetlemesi ve iptali yanıt vermesi gerekir.

Paralel görevleri iptal eden daha fazla örnek için bkz [. İzlenecek yol: Görevleri ve XML http isteklerini](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)kullanarak bağlanma, [nasıl yapılır: Bir paralel döngüden](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)bölmek için iptal 'i kullanın ve [şunları yapın: Paralel bir döngüden](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)ayırmak Için özel durum işlemeyi kullanın.

###  <a name="tokens"></a>Paralel Işi Iptal etmek için Iptal belirteci kullanma

`task`, Vesınıfları`structured_task_group` iptal belirteçleri kullanılarak iptali destekler. `task_group` PPL, bu amaçla [concurrency:: cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md) ve [concurrency:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) sınıflarını tanımlar. İşi iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı bu belirtece abone olan yeni çalışmayı başlatmaz. Zaten etkin olan iş, iptal belirtecini izlemek ve mümkün olduğunda durdurmak için [is_canceled](../../parallel/concrt/reference/cancellation-token-class.md#is_canceled) üye işlevini kullanabilir.

İptali başlatmak için [concurrency:: cancellation_token_source:: Cancel](reference/cancellation-token-source-class.md#cancel) metodunu çağırın. İptal 'e şu yollarla yanıt verebilirsiniz:

- Nesneler `task` için [concurrency:: cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) işlevini kullanın. `cancel_current_task`geçerli görevi ve değer tabanlı devamlılıklarını iptal eder. (Görevle veya Devamlılıklarla ilişkili iptal *belirtecini* iptal etmez.)

- Görev grupları ve paralel algoritmalar için [concurrency:: is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) işlevini kullanarak iptali algılar ve bu işlev **true**değerini döndürdüğünde görev gövdesinden mümkün olan en kısa sürede geri döndürün. (Bir görev grubundan `cancel_current_task` çağırmayın.)

Aşağıdaki örnek, görev iptalinin ilk temel modelini gösterir. Görev gövdesi zaman zaman bir döngü içinde iptali denetler.

[!code-cpp[concrt-task-basic-cancellation#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_2.cpp)]

`cancel_current_task` İşlev atar; bu nedenle, geçerli döngüden veya işlevden açıkça geri dönebilmeniz gerekmez.

> [!TIP]
> Alternatif olarak, yerine `cancel_current_task` [concurrency:: interruption_point](reference/concurrency-namespace-functions.md#interruption_point) işlevini çağırabilirsiniz.

Görevi iptal edildi durumuna geçirdiğine yanıt verme sırasında çağrı `cancel_current_task` yapmak önemlidir. Çağırmak `cancel_current_task`yerine erken geri dönerseniz, işlem tamamlanmış durumuna geçiş yapar ve değer tabanlı devamlılıklar çalıştırılır.

> [!CAUTION]
> Kodunuzda hiçbir `task_canceled` şekilde throw. Bunun `cancel_current_task` yerine çağırın.

Bir görev iptal edildi durumunda sona erdiğinde [concurrency:: task:: Get](reference/task-class.md#get) yöntemi [concurrency:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md)oluşturur. (Buna karşılık, [concurrency:: task:: wait](reference/task-class.md#wait) , [task_status:: iptal edildi](reference/concurrency-namespace-enums.md#task_group_status) ve throw.) Aşağıdaki örnek, görev tabanlı devamlılık için bu davranışı gösterir. Öncül görev iptal edildiğinde bile, görev tabanlı devamlılık her zaman çağrılır.

[!code-cpp[concrt-task-canceled#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_3.cpp)]

Değer tabanlı devamlılıklar, açık bir belirteçle oluşturulmadığı takdirde, öncül görevinin belirtecini devraldığı için, öncül görevi hala yürütüldüğü zaman bile devamlılıklar, iptal edilmiş durumu hemen girer. Bu nedenle, iptalden sonra öncül görev tarafından oluşturulan tüm özel durumlar devamlılık görevlerine yayılmaz. İptal etme her zaman öncül görevin durumunu geçersiz kılar. Aşağıdaki örnek öncekine benzer, ancak değer tabanlı devamlılık davranışını gösterir.

[!code-cpp[concrt-task-canceled#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_4.cpp)]

> [!CAUTION]
> `task` Oluşturucuya veya [concurrency:: create_task](reference/concurrency-namespace-functions.md#create_task) işlevine bir iptal belirteci geçirmezseniz, bu görev iptal edilemez. Ayrıca, tüm görevleri eşzamanlı olarak iptal etmek için aynı iptal belirtecini iç içe geçmiş görevlerin (diğer bir deyişle, başka bir görevin gövdesinde oluşturulan görevler) oluşturucusuna geçirmeniz gerekir.

İptal belirteci iptal edildiğinde rastgele kod çalıştırmak isteyebilirsiniz. Örneğin, Kullanıcı arabiriminde işlemi iptal etmek için bir **iptal** düğmesi seçerse, Kullanıcı başka bir işlem başlatana kadar bu düğmeyi devre dışı bırakabilirsiniz. Aşağıdaki örnek, bir iptal belirteci iptal edildiğinde çalışan bir geri çağırma işlevini kaydetmek için [concurrency:: cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) yönteminin nasıl kullanılacağını gösterir.

[!code-cpp[concrt-task-cancellation-callback#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_5.cpp)]

[Paralellik belge görevi](../../parallel/concrt/task-parallelism-concurrency-runtime.md) , değer tabanlı ve görev tabanlı devamlılıklar arasındaki farkı açıklamaktadır. Bir devamlılık görevine bir `cancellation_token` nesne sağlamazsanız, devamlılık aşağıdaki yollarla iptal belirtecini öncül görevden devralır:

- Değer tabanlı devamlılık her zaman öncül görevin iptal belirtecini devralır.

- Görev tabanlı devamlılık, öncül görevin iptal belirtecini hiçbir şekilde devralmaz. Görev tabanlı devamlılık iptali yapmanın tek yolu, açıkça bir iptal belirteci geçirmektir.

Bu davranışlar, hatalı bir görevden etkilenmez (yani, bir özel durum oluşturur). Bu durumda, değer tabanlı devamlılık iptal edilir; görev tabanlı devamlılık iptal edilmez.

> [!CAUTION]
> Başka bir görevde (diğer bir deyişle, iç içe geçmiş bir görevde) oluşturulan bir görev, üst görevin iptal belirtecini içermez. Yalnızca bir değer tabanlı devamlılık, öncül görevinin iptal belirtecini devralır.

> [!TIP]
> Bir`cancellation_token` nesne alan bir Oluşturucu veya işlev çağırdığınızda ve işlemin iptal edilebilir olmasını istemiyorsanız [concurrency:: cancellation_token:: None](reference/cancellation-token-class.md#none) metodunu kullanın.

Bir `task_group` veya`structured_task_group` nesnesinin oluşturucusuna bir iptal belirteci de sağlayabilirsiniz. Bunun önemli bir yönü, alt görev gruplarının bu iptal belirtecini devraldığı bir yönüdür. Çağırmak`parallel_for`üzere çalıştırmak için [concurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) işlevini kullanarak bu kavramı gösteren bir örnek için, bkz. bu belgede daha sonra [paralel algoritmaları iptal etme](#algorithms) .

[[Üst](#top)]

#### <a name="cancellation-tokens-and-task-composition"></a>İptal Belirteçleri ve Görev Oluşturma

[Concurrency:: when_all](reference/concurrency-namespace-functions.md#when_all) ve [concurrency:: when_any](reference/concurrency-namespace-functions.md#when_all) işlevleri, ortak desenleri uygulamak için birden fazla görev oluşturmanıza yardımcı olabilir. Bu bölümde, bu işlevlerin iptal belirteçleriyle nasıl çalıştığı açıklanmaktadır.

`when_all` Ve`when_any` işlevine bir iptal belirteci sağladığınızda, bu işlev yalnızca iptal belirteci iptal edildiğinde veya katılımcı görevlerden biri iptal edilmiş bir durumda sona erdiğinde veya bir özel durum oluşturduğunda iptal edilir.

`when_all` İşlevi, kendisine bir iptal belirteci sağlamadığınızda, genel işlemi oluşturan her görevden iptal belirtecini devralır. Bu belirteçlerden herhangi biri iptal `when_all` edildiğinde ve katılımcı görevlerden en az biri henüz başlamamışsa veya çalışmıyorsa, öğesinden döndürülen görev iptal edilir. Görevlerden biri bir özel durum oluşturduğunda benzer bir davranış oluşur; öğesinden `when_all` döndürülen görev bu özel durumla hemen iptal edilir.

Çalışma zamanı, görev tamamlandığında `when_any` işlevinden döndürülen görevin iptal belirtecini seçer. Katılımcı görevlerinin hiçbiri tamamlanmış durumda bitmiyorsa ve bir veya daha fazla görev bir özel durum oluşturursa, bir veya daha fazla görev bir özel durum oluşturursa, ' ın tamamlanması `when_any` için seçilen görevlerden biri ve son görevin belirteci olarak seçilir. Tamamlandı durumunda birden fazla görev tamamlanırsa, `when_any` görevden döndürülen görev tamamlandı durumunda sona erer. Çalışma zamanı, başka yürütülen görevlerin daha sonraki bir noktada tamamlanmasına rağmen, ' den `when_any` döndürülen görevin hemen iptal edilmemesi adına, belirteci tamamlanma sırasında iptal edilmemiş tamamlanmış bir görevi seçmeyi dener.

[[Üst](#top)]

###  <a name="cancel"></a>Paralel Işi Iptal etmek için Cancel metodunu kullanma

[Concurrency:: task_group:: Cancel](reference/task-group-class.md#cancel) ve [concurrency:: structured_task_group:: Cancel](reference/structured-task-group-class.md#cancel) yöntemleri bir görev grubunu iptal edildi durumuna ayarlar. ' İ çağırdığınızda `cancel`, görev grubu gelecekteki görevleri başlatmaz. `cancel` Yöntemler birden çok alt görev tarafından çağrılabilir. İptal edilen bir görev [eşzamanlılık:: task_group:: wait](reference/task-group-class.md#wait) ve [concurrency:: structured_task_group:: wait](reference/structured-task-group-class.md#wait) yöntemlerinin [eşzamanlılık:: iptal](reference/concurrency-namespace-enums.md#task_group_status)döndürmesini sağlar.

Bir görev grubu iptal edilirse, her bir alt görevden çalışma zamanına yapılan çağrılar bir *kesinti noktası*tetikleyip, çalışma zamanının etkin görevleri iptal etmek için bir iç özel durum türü oluşturmasına ve yakalamasına neden olur. Eşzamanlılık Çalışma Zamanı, belirli kesinti noktaları tanımlamaz; çalışma zamanına herhangi bir çağrıda meydana gelebilir. Çalışma zamanının iptali gerçekleştirmek için oluşturduğu özel durumları işlemesi gerekir. Bu nedenle, bir görevin gövdesinde bilinmeyen özel durumları işlemez.

Bir alt görev zaman alan bir işlem gerçekleştirir ve çalışma zamanına çağırmaz, düzenli aralıklarla iptali ve çıkış zamanında kontrol etmelidir. Aşağıdaki örnek, işin ne zaman iptal edildiğini belirlemenin bir yolunu gösterir. Görev `t4` , bir hatayla karşılaştığında üst görev grubunu iptal eder. Görev `t5` bazen iptali denetlemek `structured_task_group::is_canceling` için yöntemini çağırır. Üst görev grubu iptal edilirse, görev `t5` bir ileti yazdırır ve çıkar.

[!code-cpp[concrt-task-tree#6](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_6.cpp)]

Bu örnek, görev döngüsünün<sup>her 100.</sup> yinelemesinde iptal olup olmadığını denetler. İptali için kontrol ettiğiniz sıklık, göreviniz için gereken çalışma miktarına ve iptal etmek için görevlerin ne kadar hızlı bir şekilde yanıt vereceğini bağlıdır.

Üst görev grubu nesnesine erişiminiz yoksa, üst görev grubunun iptal edilip edilmeyeceğini öğrenmek için [concurrency:: is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) işlevini çağırın.

`cancel` Yöntemi yalnızca alt görevleri etkiler. Örneğin, paralel çalışma `tg1` ağacının çizimdeki görev grubunu iptal ederseniz, ağaçtaki (`t1`, `t2`, `t3` `t4`,, ve `t5`) tüm görevler etkilenir. İç içe geçmiş görev grubunu `tg2`iptal ederseniz, yalnızca görevler `t4` ve `t5` bundan etkilenir.

`cancel` Yöntemini çağırdığınızda tüm alt görev grupları da iptal edilir. Ancak, iptal etme, bir paralel çalışma ağacındaki görev grubunun herhangi bir üst öğesini etkilemez. Aşağıdaki örneklerde, paralel çalışma ağacı çizimi üzerinde derleme yaparak bu gösterilmektedir.

Bu örneklerin ilki görev grubunun `t4` `tg2`bir alt öğesi olan görev için bir çalışma işlevi oluşturur. Work işlevi bir döngüsünde işlevi `work` çağırır. Herhangi bir çağrı `work` başarısız olursa, görev üst görev grubunu iptal eder. Bu durum görev grubunun `tg2` iptal edildi durumuna girmesine neden olur, ancak görev grubunu `tg1`iptal etmez.

[!code-cpp[concrt-task-tree#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_7.cpp)]

Bu ikinci örnek, görevin görev grubunu `tg1`iptal etmek dışında birinci örneğe benzer. Bu, ağaçtaki tüm görevleri etkiler (`t1` `t3`, `t2` `t4`,,, ve `t5`).

[!code-cpp[concrt-task-tree#3](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_8.cpp)]

Sınıf `structured_task_group` , iş parçacığı açısından güvenli değildir. Bu nedenle, kendi üst `structured_task_group` nesnesine ait bir yöntemi çağıran bir alt görev belirtilmemiş bir davranış üretir. Bu kuralın özel durumları `structured_task_group::cancel` ve [concurrency:: structured_task_group:: is_canceling](reference/structured-task-group-class.md#is_canceling) metotlardır. Bir alt görev, üst görev grubunu iptal etmek ve iptali denetlemek için bu yöntemleri çağırabilir.

> [!CAUTION]
>  Bir `task` nesnenin alt öğesi olarak çalışan bir görev grubu tarafından gerçekleştirilen işleri iptal etmek için bir iptal belirteci kullanabilseniz de, bir görev grubunda çalışan nesneleri iptal `task` etmek için `task_group::cancel` veya `structured_task_group::cancel` yöntemlerini kullanamazsınız.

[[Üst](#top)]

###  <a name="exceptions"></a>Paralel Işi Iptal etmek için özel durumlar kullanma

İptal belirteçlerinin ve `cancel` yönteminin kullanımı, paralel bir iş ağacını iptal edilirken özel durum işleme göre daha etkilidir. İptal belirteçleri ve `cancel` yöntemi bir görevi ve alt görevleri yukarıdan aşağı doğru bir şekilde iptal eder. Buna karşılık, özel durum işleme bir alt şekilde çalışır ve özel durum yukarı doğru yayıldıklarından her bir alt görev grubunu bağımsız olarak iptal etmelidir. Konu [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md) , eşzamanlılık çalışma zamanı hataları iletmek için özel durumları nasıl kullandığını açıklar. Ancak, tüm özel durumlar bir hata göstermez. Örneğin, bir arama algoritması, sonucu bulduğunda onunla ilişkili görevini iptal edebilir. Ancak, daha önce belirtildiği gibi, özel durum işleme paralel çalışmayı iptal etmek `cancel` için yöntemini kullanmaktan daha az verimlidir.

> [!CAUTION]
>  Yalnızca gerektiğinde paralel çalışmayı iptal etmek için özel durumlar kullanmanızı öneririz. İptal belirteçleri ve görev grubu `cancel` yöntemleri daha etkilidir ve hata açısından daha az açıktır.

Bir görev grubuna geçirdiğiniz iş işlevinin gövdesinde bir özel durum oluşturduğunuzda, çalışma zamanı bu özel durumu depolar ve görev grubunun bitmesini bekleyen bağlamda özel durumu oluşturur. `cancel` Yönteminde olduğu gibi, çalışma zamanı henüz başlatılmamış tüm görevleri atar ve yeni görevleri kabul etmez.

Bu üçüncü örnek ikincisine benzer, bu görev `t4` , görev grubunu `tg2`iptal etmek için bir özel durum oluşturur. Bu örnek, görev `try` grubu - `catch` altgörevlerininbitmesinibekliyorsaiptalidenetlemekiçin`tg2` bir blok kullanır. İlk örnekte olduğu gibi, bu durum görev grubunun `tg2` iptal edilme durumuna girmesine neden olur, ancak görev grubunu `tg1`iptal etmez.

[!code-cpp[concrt-task-tree#4](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_9.cpp)]

Bu dördüncü örnek, tüm iş ağacını iptal etmek için özel durum işlemeyi kullanır. Örnek, görev grubu onun alt görevlerini `tg1` `tg2` beklediği zaman yerine, alt görevlerinin tamamlanmasını bekliyorsa özel durumu yakalar. İkinci örnekte olduğu gibi, bu, ağaçta `tg1` her iki görev grubuna da neden olur ve `tg2`iptal edildi durumuna girer.

[!code-cpp[concrt-task-tree#5](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_10.cpp)]

`task_group::wait` Ve`structured_task_group::wait` yöntemleri bir alt görev bir özel durum oluşturduğunda, bunlardan bir dönüş değeri almazsınız.

[[Üst](#top)]

##  <a name="algorithms"></a>Paralel algoritmaları iptal etme

PPL içindeki paralel algoritmalar, örneğin `parallel_for`, görev grupları üzerinde derleyin. Bu nedenle, bir paralel algoritmayı iptal etmek için aynı tekniklerin birçoğunu kullanabilirsiniz.

Aşağıdaki örneklerde bir paralel algoritmayı iptal etmenin birkaç yolu gösterilmektedir.

Aşağıdaki örnek, `parallel_for` algoritmasını çağırmak `run_with_cancellation_token` için işlevini kullanır. `run_with_cancellation_token` İşlevi bir iptal belirtecini bağımsız değişken olarak alır ve belirtilen iş işlevini zaman uyumlu olarak çağırır. Paralel algoritmalar görevler üzerine oluşturulduğundan, üst görevin iptal belirtecini alırlar. Bu nedenle `parallel_for` , iptal 'e yanıt verebilir.

[!code-cpp[concrt-cancel-parallel-for#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_11.cpp)]

Aşağıdaki örnek, `parallel_for` algoritmayı çağırmak için [concurrency:: structured_task_group:: run_and_wait](reference/structured-task-group-class.md#run_and_wait) yöntemini kullanır. Yöntemi `structured_task_group::run_and_wait` , belirtilen görevin bitmesini bekler. `structured_task_group` Nesnesi, çalışma işlevinin görevi iptal etmesini sağlar.

[!code-cpp[concrt-task-tree#7](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_12.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
The task group status is: canceled.
```

Aşağıdaki örnek, bir `parallel_for` döngüyü iptal etmek için özel durum işlemeyi kullanır. Çalışma zamanı, çağıran bağlamın özel durumunu sıraladığında.

[!code-cpp[concrt-task-tree#9](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_13.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Caught 50
```

Aşağıdaki örnek, bir `parallel_for` döngüsünde iptali koordine etmek için Boolean bayrağını kullanır. Her görev çalışır, çünkü bu örnek, `cancel` genel görev kümesini iptal etmek için yöntemini veya özel durum işlemeyi kullanmaz. Bu nedenle, bu teknik bir iptal mekanizmasından daha fazla hesaplama ek yüküne sahip olabilir.

[!code-cpp[concrt-task-tree#8](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_14.cpp)]

Her bir iptal yönteminin avantajları vardır. Özel gereksinimlerinize uyan yöntemi seçin.

[[Üst](#top)]

##  <a name="when"></a>Iptal etme ne zaman kullanılmaz

Bir ilgili görev grubunun her bir üyesi zamanında çıkış yaparken, iptal etme kullanımı uygundur. Ancak, iptal etme uygulamanız için uygun olmayan bazı senaryolar vardır. Örneğin, Görev iptali birlikte çalışırken, tek bir görev engellenirse genel görev kümesi iptal edilmez. Örneğin, bir görev henüz başlatılmamışsa, ancak başka bir etkin görevi engelliyorsa, görev grubu iptal edilirse başlatılmaz. Bu, uygulamanızda kilitlenmenin oluşmasına neden olabilir. İptal işleminin kullanıldığı ikinci bir örnek, bir görev iptal edildiğinde, ancak alt görevi bir kaynağı boşaltma gibi önemli bir işlem gerçekleştirdiğinde. Üst görev iptal edildiğinde, genel görev kümesi iptal edildiğinden, bu işlem yürütülmez. Bu noktayı gösteren bir örnek için, paralel Desenler kitaplığı konusunun En Iyi uygulamalarında [iptal ve özel durum Işlemenin nesne yok etme işlemini nasıl etkilediğini anlama](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) bölümüne bakın.

[[Üst](#top)]

## <a name="related-topics"></a>İlgili Konular

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: Paralel Döngüden Kurtulmak için İptal Kullanma](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|Bir paralel arama algoritmasını uygulamak için iptalin nasıl kullanılacağını gösterir.|
|[Nasıl yapılır: Paralel Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|`task_group` Sınıfının temel ağaç yapısına yönelik arama algoritması yazmak için nasıl kullanılacağını gösterir.|
|[Özel Durum İşleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Çalışma zamanının görev grupları, hafif görevler ve zaman uyumsuz aracılar tarafından oluşturulan özel durumları nasıl işlediğini ve uygulamalarınızda özel durumlara nasıl yanıt verileceğini açıklar.|
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Görevlerin görev gruplarıyla ilişkilerini ve uygulamalarınızda yapılandırılmamış ve yapılandırılmış görevleri nasıl kullanabileceğinizi açıklar.|
|[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)|Veri koleksiyonlarında eşzamanlı olarak iş gerçekleştiren paralel algoritmaları açıklar|
|[Paralel Desen Kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Paralel Desenler kitaplığına genel bakış sağlar.|

## <a name="reference"></a>Başvuru

[task Sınıfı (Eşzamanlılık Çalışma Zamanı)](../../parallel/concrt/reference/task-class.md)

[cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)

[cancellation_token Sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)

[task_group Sınıfı](reference/task-group-class.md)

[structured_task_group Sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)

[parallel_for Işlevi](reference/concurrency-namespace-functions.md#parallel_for)
