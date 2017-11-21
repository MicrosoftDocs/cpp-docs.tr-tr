---
title: PPL'de iptal | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel algorithms, canceling [Concurrency Runtime]
- canceling parallel algorithms [Concurrency Runtime]
- parallel tasks, canceling [Concurrency Runtime]
- cancellation in the PPL
- parallel work trees [Concurrency Runtime]
- canceling parallel tasks [Concurrency Runtime]
ms.assetid: baaef417-b2f9-470e-b8bd-9ed890725b35
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 90edebe8e57e6720ad1cb7a83b59f478532c16c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cancellation-in-the-ppl"></a>PPL'de İptal
Bu belge iptali paralel Desen kitaplığı (PPL), paralel iş iptal etme ve paralel iş zaman iptal belirleme rolünü açıklamaktadır.  
  
> [!NOTE]
>  Çalışma zamanı özel durum işleme iptal uygulamak için kullanır. Catch bulunamıyor veya bu özel durumları, kodunuzda işleme. Ayrıca, görevleriniz için işlevi gövdeleri özel durum güvenli kod yazma öneririz. Örneği için kullanabileceğiniz *kaynak edinme olan başlatma* görev gövdesinde bir özel durum oluştuğunda kaynakları doğru şekilde işlenir emin olmak için (RAII) deseni. Bir kaynak iptal edilebilen bir görev olarak temizlemek için RAII desen kullanan bir tam örnek için bkz: [izlenecek yol: bir kullanıcı arabirimi iş parçacığı kaldırma çalışma](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md).  
  
## <a name="key-points"></a>Önemli Noktalar  
  
-   İptal işbirlikçi ve yanıt iptali için görev iptal isteklerini kodu arasında eşgüdüme ilgilidir.  
  
-   Mümkün olduğunda, iş iptal etmek için İptal belirteçlerini kullanın. [Concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) sınıfı tanımlayan bir iptal belirteci.  
  

-   İptal belirteçleri kullanırken [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) iptal başlatmak için yöntem ve [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) yanıt verecek şekilde işlevi İptali. Kullanım [is_canceled](reference/cancellation-token-class.md#is_canceled) yöntemi başka bir görev iptal istedi olup olmadığını denetleyin.
  
-   İptal hemen gerçekleşmez. Bir görevi veya görev grubu iptal edilirse yeni iş başlamadı rağmen etkin çalışma denetleyin ve iptal için yanıt gerekir.  
  
-   Bir değer tabanlı devamlılık öncül görevini iptal belirteci devralır. Görev tabanlı bir devamlılık öncül görevini belirteci hiçbir zaman devralır.  
  
-   Kullanım [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) Oluşturucusu veya isteyen işlevi çağırdığınızda yöntemi bir `cancellation_token` nesne, ancak işlemi edilebilen olmasını istemiyorsanız. Ayrıca, bir iptal belirteci geçirmezseniz [concurrency::task](../../parallel/concrt/reference/task-class.md) Oluşturucusu veya [concurrency::create_task](reference/concurrency-namespace-functions.md#create_task) işlev, bu görev değil işlem iptal edilemez.  


  
##  <a name="top"></a>Bu belgede  
  
- [Paralel iş ağaçları](#trees)  
  
- [Paralel görevleri iptal etme](#tasks)  
  
    - [Paralel iş iptal etmek için bir iptal belirteci kullanma](#tokens)  
  
    - [Paralel iş iptal yönteme iptal kullanma](#cancel)  
  
    - [Paralel iş iptal etmek için özel durumlar kullanma](#exceptions)  
  
- [Paralel algoritmaları iptal etme](#algorithms)  
  
- [İptal kullanmamayı ne zaman](#when)  
  
##  <a name="trees"></a>Paralel iş ağaçları  
 PPL'de, hassas görevleri ve hesaplamalar yönetmek için görevler ve görev grupları kullanır. Görev grupları forma geçirebilmenize *ağaçları* paralel iş. Aşağıdaki çizimde bir paralel iş ağacı gösterir. Bu çizimde, `tg1` ve `tg2` görev grupları; temsil eder `t1`, `t2`, `t3`, `t4`, ve `t5` görev grupları gerçekleştirmek iş temsil eder.  
  
 ![Paralel çalışma ağacı](../../parallel/concrt/media/parallelwork_trees.png "parallelwork_trees")  
  
 Aşağıdaki örnek çizimde ağacı oluşturmak için gerekli kod gösterir. Bu örnekte, `tg1` ve `tg2` olan [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesneleri; `t1`, `t2`, `t3`, `t4`, ve `t5` olan [concurrency::task_handle](../../parallel/concrt/reference/task-handle-class.md) nesneleri.  
  
 [!code-cpp[concrt-task-tree#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_1.cpp)]  
  
 Aynı zamanda [concurrency::task_group](reference/task-group-class.md) benzer iş ağacı oluşturmak için sınıfı. [Concurrency::task](../../parallel/concrt/reference/task-class.md) sınıfı, ayrıca iş ağacının kavramını destekler. Ancak, bir `task` ağacıdır bağımlılığı ağacı. İçinde bir `task` ağacında, gelecekteki works tamamlandıktan sonra geçerli çalışma. Bir görev grubu ağacında, iç iş önce dış iş tamamlar. Görevler ve görev grupları arasındaki farklar hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 [[Üst](#top)]  
  
##  <a name="tasks"></a>Paralel görevleri iptal etme  

 Paralel iş iptal etmek için birden çok yolu vardır. Tercih edilen yol bir iptal belirteci kullanmaktır. Görev grupları da destek [concurrency::task_group::cancel](reference/task-group-class.md#cancel) yöntemi ve [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) yöntemi. Son bir görev iş işlev gövdesine bir özel durum yoludur. Seçtiğiniz yöntem olsun, iptal hemen gerçekleşmez anlayın. Bir görevi veya görev grubu iptal edilirse yeni iş başlamadı rağmen etkin çalışma denetleyin ve iptal için yanıt gerekir.  

  
 Paralel görevleri iptal etme daha fazla örnek için bkz: [izlenecek yol: bağlanma kullanarak görevleri ve XML HTTP isteklerini](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md), [nasıl yapılır: paralel bir döngüden gelen sonu için kullanım iptal](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md), ve [nasıl yapılır: kullanın Özel durum paralel bir döngüden kurtulmak için işleme](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md).  
  
###  <a name="tokens"></a>Paralel iş iptal etmek için bir iptal belirteci kullanma  
 `task`, `task_group`, Ve `structured_task_group` sınıfları iptal belirteçlerini kullanımı ile iptal destekler. PPL'de tanımlar [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md) ve [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md) bu amaç için sınıflar. İş iptal etmek için bir iptal belirteci kullandığınızda, çalışma zamanı bu belirtece abone yeni iş başlatılmaz. Zaten etkin olan iş [is_canceled] kullanabilirsiniz ((.. /.. / parallel/concrt/reference/cancellation-token-class.md#is_canceled) iptal belirteci izlemek ve mümkün olduğunda durdurmak için üye işlevi.  
  

 İptal başlatmak için çağrı [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) yöntemi. Aşağıdaki şekillerde iptal için yanıtlayın:  
  
-   İçin `task` nesneleri, kullanın [concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task) işlevi. `cancel_current_task`Geçerli görev ve onun değerine bağlı devamlılıklar hiçbirini iptal eder. (İptal iptal etmez *belirteci* görev veya kendi devamlılıklar ile ilişkili.)  
  
-   Görev grupları ve paralel algoritmalar için kullanmak [concurrency::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) iptal algılamak ve bu işlevi döndüğünde görev gövdesinden mümkün olan en kısa sürede dönmek için işlevi `true`. (Çağırmayın `cancel_current_task` bir görev grubundan.)  

  
 Aşağıdaki örnek ilk temel düzeni görev iptali için gösterir. Görev gövde bazen iptal döngü içinde olup olmadığını denetler.  
  
 [!code-cpp[concrt-task-basic-cancellation#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_2.cpp)]  
  
 `cancel_current_task` İşlev atar; bu nedenle, açıkça geçerli döngü veya işlev dönüş gerekmez.  
  
> [!TIP]

>  Alternatif olarak, çağırabilirsiniz [concurrency::interruption_point](reference/concurrency-namespace-functions.md#interruption_point) yerine işlev `cancel_current_task`.  
  
 Çağrı önemlidir `cancel_current_task` zaman yanıt iptali için iptal durumu görevi geçişleri için. Arama yerine erken dönerseniz `cancel_current_task`, işlemi tamamlanmış durumuna geçiş yapar ve herhangi bir değer tabanlı devamlılıklar çalıştırın.  
  
> [!CAUTION]
>  Hiçbir zaman throw `task_canceled` kodunuzdan. Çağrı `cancel_current_task` yerine.  
  
 Bir görevi iptal edilmiş durumda sona erdiğinde [CONCURRENCY::Task](reference/task-class.md#get) yöntemi atar [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md). (Buna karşılık, [concurrency::task::wait](reference/task-class.md#wait) döndürür [task_status::canceled](reference/concurrency-namespace-enums.md#task_group_status) ve throw değil.) Aşağıdaki örnek, görev tabanlı devam etmesi için bu davranış gösterilmektedir. Hatta öncül görev iptal edildiğinde görev tabanlı bir devamlılık her zaman çağrılır.  

  
 [!code-cpp[concrt-task-canceled#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_3.cpp)]  
  
 Bir açık belirteciyle oluşturuldukları sürece değeri tabanlı devamlılıklar öncül görevini belirteci devraldığı bile öncül görev hala yürütülürken zaman devamlılıklar hemen iptal edildi durumu girin. Bu nedenle, sonra iptal öncül görevi tarafından oluşturulan özel durumları devamlılık görevlerini dağıtılmaz. Her zaman iptal öncül görev durumu geçersiz kılar. Aşağıdaki örnek önceki benzer, ancak bir değer tabanlı devamlılık davranışı gösterir.  
  
 [!code-cpp[concrt-task-canceled#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_4.cpp)]  
  
> [!CAUTION]

>  Bir iptal belirteci geçirmezseniz `task` Oluşturucusu veya [concurrency::create_task](reference/concurrency-namespace-functions.md#create_task) işlev, bu görev değil işlem iptal edilemez. Ayrıca, tüm iç içe geçmiş görevleri (diğer bir deyişle, başka bir görev gövdesinde oluşturulan görevler) oluşturucuya aynı iptal belirtecini geçmesi gereken aynı anda tüm görevleri iptal etmek için.  
  
 Bir iptal belirteci iptal edildiğinde rastgele kod çalıştırmak isteyebilirsiniz. Örneğin, kullanıcı seçerse bir **iptal** düğmesi kullanıcı başka bir işlem başlatır kadar işlemi iptal etmek için kullanıcı arabiriminde, bu düğme devre dışı bırakılamadı. Aşağıdaki örnekte nasıl kullanılacağını gösterir [CONCURRENCY::cancellation_token:: register_callback](reference/cancellation-token-class.md#register_callback) bir iptal belirteci iptal edildiğinde çalıştırılan bir geri çağırma işlevini kaydetmek için yöntem.  

  
 [!code-cpp[concrt-task-cancellation-callback#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_5.cpp)]  
  
 Belge [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md) değeri ve görev tabanlı devamlılıklar arasındaki farkı açıklar. Belirtmezseniz, bir `cancellation_token` nesne devamlılık görevi için devamlılık aşağıdaki yollarla öncül görevden iptal belirteci devralır:  
  
-   Bir değer tabanlı devamlılık her zaman öncül görev iptal belirteci alır.  
  
-   Görev tabanlı bir devamlılık hiçbir zaman öncül görev iptal belirteci alır. Görev tabanlı bir devamlılık iptal edilebilen yapmak için tek yolu bir iptal belirteci açıkça geçirmektir.  
  
 Bu davranışların hatalı görev tarafından (diğer bir deyişle, bir özel durum oluşturur) etkilenmez. Bu durumda, bir değer tabanlı devamlılık iptal edildi; görev tabanlı bir devamlılık iptal değil.  
  
> [!CAUTION]
>  Başka bir görev (diğer bir deyişle, iç içe geçmiş bir görevi) oluşturulan bir görev iptal belirteci üst görevinin devralmaz. Yalnızca bir değer tabanlı devamlılık öncül görevini iptal belirtecini alır.  
  
> [!TIP]

>  Kullanım [concurrency::cancellation_token:: none](reference/cancellation-token-class.md#none) Oluşturucusu veya isteyen işlevi çağırdığınızda yöntemi bir `cancellation_token` nesne ve işleminin işlem iptal edilemez olmasını istemiyorsanız.  
  
 Bir iptal belirteci oluşturucusunun için de sağlayabilirsiniz bir `task_group` veya `structured_task_group` nesnesi. Bir önemli bu alt görev grupları bu iptal belirteci devral yönüdür. Bu kavram kullanarak gösteren bir örnek için [concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) işlevi çağırmak için çalıştırmak için `parallel_for`, bkz: [paralel algoritmaları iptal etme](#algorithms) daha sonra bu Belge.  
  
 [[Üst](#top)]  
  
#### <a name="cancellation-tokens-and-task-composition"></a>İptal Belirteçleri ve Görev Oluşturma  

 [Eşzamanlılık:: HYPERLINK "http://msdn.microsoft.com/library/system.threading.tasks.task.whenall (v=VS.110).aspx" when_all](reference/concurrency-namespace-functions.md#when_all) ve [concurrency::when_any](reference/concurrency-namespace-functions.md#when_all) işlevleri, oluşturmanıza yardımcı olabilir Ortak desenler uygulamak için birden çok görev. Bu bölümde, bu işlevler iptal belirteçleri ile nasıl çalıştığı açıklanmaktadır.  
  
 Ya da bir iptal belirteci sağladığınız zaman `when_all` ve `when_any` işlev işlevi yalnızca bu iptal belirteci iptal edildiğinde veya bir katılımcının görevleri iptal edilmiş durumda sona erer veya bir özel durum oluşturur, iptal.  
  
 `when_all` İşlevi ona bir iptal belirteci belirtmediğinizde oluşturur ve genel işlemi her görev iptal belirteci devralır. Sunucudan döndürülen görev `when_all` bu belirteçleri hiçbirini iptal edilir ve katılımcı görevleri en az biri henüz başlamamış veya çalışan iptal edilir. Görevlerden birini - sunucudan döndürülen görev aykırı bir benzer davranış `when_all` bu özel durumla hemen iptal edilir.  
  
 Çalışma zamanı sunucudan döndürülen görev için İptal belirtecini seçer `when_any` görev tamamlandığında işlev. Katılımcı görevleri hiçbiri tamamlanmış durumda son ve bir veya daha fazla görevleri bir özel durum oluşturur, belirtti görevlerden birini tamamlamak için seçilir `when_any` ve kendi token son görev için belirteç olarak seçilir. Birden fazla görev tamamlanacak tamamlanırsa durumunda, sunucudan döndürülen görev `when_any` görevi tamamlanmış durumda sonlandırır. Görev, böylece, belirteci tamamlama aynı anda değil iptal tamamlanmış bir görevi seçmek çalışma zamanı çalıştığında döndürülen `when_any` diğer yürütülen görevler sonraki bir noktada tamamlayabilir olsa bile hemen iptal edilmedi.  
  
 [[Üst](#top)]  
  
###  <a name="cancel"></a>Paralel iş iptal yönteme iptal kullanma  

 [Concurrency::task_group::cancel](reference/task-group-class.md#cancel) ve [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) yöntemlerini görev grubu iptal edilmiş durumuna ayarlayın. Çağırdıktan sonra `cancel`, görev grubu gelecekteki görevlerin başlatılmaz. `cancel` Yöntemleri birden çok alt görevler tarafından çağrılabilir. İptal edilen bir görev neden [concurrency::task_group::wait](reference/task-group-class.md#wait) ve [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait) dönmek için yöntemleri [concurrency::canceled](reference/concurrency-namespace-enums.md#task_group_status).  

  
 Bir görev grubu iptal ederseniz, her alt görev çağrılar çalışma zamanı tetikleyebilir bir *kesinti noktası*, throw ve catch etkin görevleri iptal etmek için bir iç özel durum türü çalışma zamanı neden olur. Eşzamanlılık Çalışma zamanı belirli kesinti noktaları tanımlamaz; çalışma zamanı için herhangi bir çağrıda oluşabilir. Çalışma zamanı iptal gerçekleştirmek için oluşturur özel durumları işleme gerekir. Bu nedenle, bir görev gövdesinde Bilinmeyen özel durum işleyemez.  
  
 Alt görevin uzun süren işlem gerçekleştirir ve çalışma zamanına çağırmaz, düzenli aralıklarla iptalleri denetlemek ve gerekir zamanında çıkın. Aşağıdaki örnek iş zaman iptal belirlemenin bir yolu gösterir. Görev `t4` bir hatayla karşılaştığında üst görev grubu iptal eder. Görev `t5` bazen çağırır `structured_task_group::is_canceling` iptalleri denetlemek için yöntem. Üst görev grubu iptal ederseniz, görev `t5` bir ileti yazdırır ve çıkar.  
  
 [!code-cpp[concrt-task-tree#6](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_6.cpp)]  
  
 Bu örnekte her 100 üzerinde iptal denetler<sup>th</sup> görev döngü. İptalleri denetlemek sıklığı, bir görev gerçekleştiren iş ve ne kadar hızlı iptali için yanıt görevler için gereksinim duyduğunuz miktarına bağlıdır.  
  
 Üst görev grup nesneye erişimi yoksa, çağrı [concurrency::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling) üst görev grubu iptal olup olmadığını belirlemek için işlev.  

  
 `cancel` Yöntemi yalnızca alt görevler etkiler. Örneğin, görev grubu iptal ederseniz `tg1` paralel iş ağaç çizimde, tüm görevler ağacında (`t1`, `t2`, `t3`, `t4`, ve `t5`) etkilenir. İç içe geçmiş görev grubu iptal ederseniz `tg2`, yalnızca görevleri `t4` ve `t5` etkilenir.  
  
 Çağırdığınızda `cancel` yöntemi, tüm alt görev grupları ayrıca iptal edilir. Ancak, iptal paralel iş ağacında görev grubunun herhangi bir üst etkilemez. Aşağıdaki örnekler bu paralel iş ağaç çizim oluşturarak gösterir.  
  
 Bu örneklerin görev için bir iş işlev oluşturur `t4`, görev grubunun bir alt öğesi olan `tg2`. İş işlevi işlevini çağırır `work` döngü. Herhangi bir için çağırırsanız `work` başarısız olursa, görev kendi üst görev grubu iptal eder. Bu görev grubu neden `tg2` iptal durumu, ancak girmek için görev grubu iptal etmez `tg1`.  
  
 [!code-cpp[concrt-task-tree#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_7.cpp)]  
  
 Bu ikinci örnek birincisini benzer görev grubu görevi iptal `tg1`. Bu, tüm görevler ağacında etkiler (`t1`, `t2`, `t3`, `t4`, ve `t5`).  
  
 [!code-cpp[concrt-task-tree#3](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_8.cpp)]  
  
 `structured_task_group` Sınıfı iş parçacığı açısından güvenli değil. Bu nedenle, kendi üst bir yöntemi çağırır alt görevin `structured_task_group` nesne belirtilmeyen davranışı üretir. Bu kural istisnaları `structured_task_group::cancel` ve [concurrency::structured_task_group::is_canceling](reference/structured-task-group-class.md#is_canceling) yöntemleri. Alt görevin üst görev grubu iptal etmek ve iptalleri denetlemek için bu yöntemleri çağırabilirsiniz.  

 
> [!CAUTION]
>  Bir alt öğesi olarak çalışan bir görev grubu tarafından gerçekleştirilen iş iptal etmek için bir iptal belirteci kullanabilirsiniz ancak bir `task` nesne kullanamazsınız `task_group::cancel` veya `structured_task_group::cancel` iptal etmek için yöntemleri `task` görev grupta çalışmasını nesneleri.  
  
 [[Üst](#top)]  
  
###  <a name="exceptions"></a>Paralel iş iptal etmek için özel durumlar kullanma  
 İptal belirteçleri kullanımını ve `cancel` yöntemi özel durum işleme paralel çalışma ağacı iptal etme sırasında daha verimlidir. İptal belirteçleri ve `cancel` cancel yöntemi bir görevi ve tüm alt görevler yukarıdan aşağıya doğru bir biçimde. Buna karşılık, özel durum işleme aşağıdan yukarıya biçimde çalışır ve özel durum yukarı yayar gibi her alt görev grubu bağımsız olarak iptal etmeniz gerekir. Konu [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md) özel durumlar eşzamanlılık çalışma zamanı hataları iletişim kurmak için nasıl kullandığını açıklar. Ancak, tüm özel durumlar bir hata gösterir. Örneğin, sonuç bulduğunda arama algoritması ilişkili görevi iptal etme. Ancak, daha önce belirtildiği gibi özel durum işleme kullanmaktan daha az verimlidir `cancel` paralel iş iptal etmek için yöntem.  
  
> [!CAUTION]
>  Paralel iş yalnızca gerekli olduğunda iptal etmek için özel durumlar kullanmanızı öneririz. İptal belirteçleri ve görev grubu `cancel` yöntemleri daha etkili ve hata potansiyeli daha az.  
  
 Bir görev grubuna geçirdiğiniz çalışma işlevini gövdesinde bir özel durum, çalışma zamanı bu özel durum depolar ve tamamlanması için görev grubu bekler bağlam özel durumu sıralar. İle `cancel` yöntemi, çalışma zamanı henüz başlatılmamış ve yeni görevler kabul etmiyorum herhangi bir görevi atar.  
  
 Bu görev dışında ikincisi bu üçüncü örneğe benzer `t4` görev grubu iptal etmek için bir özel durum oluşturur `tg2`. Bu örnekte bir `try` - `catch` iptalleri denetlemek için blok olduğunda görev grubu `tg2` onun alt görevleri tamamlamak bekler. İlk örnekteki gibi bu görev grubu neden `tg2` iptal durumu, ancak girmek için görev grubu iptal etmez `tg1`.  
  
 [!code-cpp[concrt-task-tree#4](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_9.cpp)]  
  
 Dördüncü Bu örnek, tüm iş ağaç iptal etmek için özel durum işleme kullanır. Özel durum örnek yakalar zaman Grup görev `tg1` onun alt görevleri yerine ne zaman tamamlanmasını bekler görev grup `tg2` onun alt görevleri için bekler. İkinci örnekteki gibi bu iki görevleri Grup ağacında neden `tg1` ve `tg2`, iptal edilen durumuna geçilmesidir.  
  
 [!code-cpp[concrt-task-tree#5](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_10.cpp)]  
  
 Çünkü `task_group::wait` ve `structured_task_group::wait` yöntemleri throw alt görevin bir özel durum oluşturduğunda, dönüş değeri kendilerinden aldığınız değil.  
  
 [[Üst](#top)]  
  
##  <a name="algorithms"></a>Paralel algoritmaları iptal etme  
 Paralel algoritmalar ppl'de, örneğin, `parallel_for`, görev grupları oluşturun. Bu nedenle, bir paralel algoritması iptal etmek için birçok aynı teknikleri kullanabilirsiniz.  
  
 Aşağıdaki örnekler bir paralel algoritması iptal etmek için çeşitli yollarını gösterir.  
  
 Aşağıdaki örnek kullanır `run_with_cancellation_token` çağrılacak işlevi `parallel_for` algoritması. `run_with_cancellation_token` İşlev iptal bağımsız değişken olarak belirteci alır ve zaman uyumlu olarak sağlanan çalışma işlevi çağırır. Paralel algoritmalar görevleri oluşturulur çünkü bunlar üst görevinin iptal belirteci alır. Bu nedenle, `parallel_for` iptali için yanıt verebilir.  
  
 [!code-cpp[concrt-cancel-parallel-for#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_11.cpp)]  
  

 Aşağıdaki örnek kullanır [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait) çağrılacak yöntem `parallel_for` algoritması. `structured_task_group::run_and_wait` Yöntemi sağlanan görevin tamamlanmasını bekler. `structured_task_group` Nesne görevi iptal etmek iş işlevi sağlar.  
  
 [!code-cpp[concrt-task-tree#7](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_12.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
The task group status is: canceled.  
```  
  
 Aşağıdaki örnek, iptal etmek için özel durum işleme kullanan bir `parallel_for` döngü. Çalışma zamanı çağıran bağlamını özel durumu sıralar.  
  
 [!code-cpp[concrt-task-tree#9](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_13.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Caught 50  
```  
  
 Aşağıdaki örnek, iptal koordine etmek için bir Boole bayrağı kullanır. bir `parallel_for` döngü. Bu örnek kullanmayan nedeniyle her görev çalışır `cancel` genel dizi görevi iptal etmek için yöntemi veya özel durum işleme. Bu nedenle, bu teknik hesaplama yükünü iptal mekanizması daha fazla olabilir.  
  
 [!code-cpp[concrt-task-tree#8](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_14.cpp)]  
  
 Her iptal yöntemin diğer avantajları vardır. Gereksinimlerinize en uygun yöntemi seçin.  
  
 [[Üst](#top)]  
  
##  <a name="when"></a>İptal kullanmamayı ne zaman  
 İptal kullanımını uygun olduğunda her ilgili görevlerin bir grubun üyesi zamanında çıkabilirsiniz. Ancak, burada iptal uygulamanız için uygun olmayabilir bazı senaryolar vardır. Görev iptali işbirlikçi olduğundan, herhangi bir görev engellendi, örneğin, genel dizi görevi iptal eder değil. Görev grubu iptal edilirse Örneğin, bir görev henüz başlamamış, ancak başka bir etkin görev engelini kaldırır, onu başlatılmaz. Bu kilitlenme uygulamanızda oluşmasına neden olabilir. Burada iptal kullanımını uygun olmayabilir, ikinci bir örnek, bir görevi iptal edilir, ancak kaynak boşaltma gibi önemli bir işlem, kendi alt görevi gerçekleştirir verilmiştir. Üst görev iptal ettiğinizde genel dizi görevi iptal olduğundan bu işlem çalıştırmaz. Bu noktayı gösterir bir örnek için bkz: [anlayın nasıl iptali ve özel durum işleme etkileyen nesne yok etme](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) paralel Desen kitaplığı konusunda en iyi yöntemler bölümündeki.  
  
 [[Üst](#top)]  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: paralel bir döngüden kurtulmak için İptal kullanın](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|İptal paralel arama algoritması uygulamak için nasıl kullanılacağını gösterir.|  
|[Nasıl yapılır: özel durum paralel bir döngüden kurtulmak için işleme kullanın](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|Nasıl kullanılacağını gösterir `task_group` temel ağaç yapısı için bir arama algoritması yazma sınıfı.|  
|[Özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|Çalışma zamanı görev grupları, Basit görevler ve zaman uyumsuz aracılar tarafından oluşturulan özel durumları nasıl işler ve nasıl özel durumlar uygulamalarınızda yanıt açıklar.|  
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Görevler için görev grupları nasıl ilişkili olduğunu ve yapılandırılmamış ve yapılandırılmış görevler uygulamalarınızı nasıl kullanabileceğiniz açıklanır.|  
|[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)|Eşzamanlı olarak veri koleksiyonlar üzerinde çalışmayı gerçekleştirmek paralel algoritmalar açıklar|  
|[Paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|Paralel Desen kitaplığı genel bir bakış sağlar.|  
  
## <a name="reference"></a>Başvuru  
 [task sınıfı (eşzamanlılık çalışma zamanı)](../../parallel/concrt/reference/task-class.md)  
  
 [cancellation_token_source sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)  
  
 [cancellation_token sınıfı](../../parallel/concrt/reference/cancellation-token-class.md)  
  
 [task_group sınıfı](reference/task-group-class.md)  
  
 [structured_task_group sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)  

 [parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)


