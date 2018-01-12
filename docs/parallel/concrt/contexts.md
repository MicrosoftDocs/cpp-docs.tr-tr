---
title: "Bağlamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01ec145de3c41aeb30bdd308794d9f8d90a3f3e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="contexts"></a>Bağlamlar

Bu belge eşzamanlılık çalışma zamanı bağlamlarda rolü açıklanmaktadır. Bir zamanlayıcı bağlı bir iş parçacığı olarak bilinen bir *yürütme bağlamı*, veya yalnızca *bağlamı*. [Concurrency::wait](reference/concurrency-namespace-functions.md#wait) işlevi ve eşzamanlılık::[bağlam sınıfı](../../parallel/concrt/reference/context-class.md) bağlamları davranışını denetlemek etkinleştirin. Kullanım `wait` belirli bir süre boyunca geçerli bağlamı askıya almak için işlevi. Kullanım `Context` sınıfı zaman bağlamları engellemek, engellemesini kaldırmak ve verim ya da geçerli bağlamı oversubscribe istediğinizde hakkında daha fazla denetime ihtiyacınız olduğunda.  
  
> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, uygulamanızda oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ince ayar yardımcı olduğundan, ile başlamanızı öneririz [paralel Desen kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Eşzamanlılık Çalışma zamanı için yeni.  
  
## <a name="the-wait-function"></a>Wait işlevi  

 [Concurrency::wait](reference/concurrency-namespace-functions.md#wait) işlevi işbirliği ile belirtilen milisaniye sayısı için geçerli bağlam yürütülmesi verir. Çalışma zamanı verim zaman diğer görevleri gerçekleştirmek için kullanır. Belirtilen süre dolduktan sonra çalışma zamanı yürütme bağlamı reschedules. Bu nedenle, `wait` işlevi için sağlanan değer daha uzun geçerli bağlam askıya `milliseconds` parametresi.  
  
 0 (sıfır) geçirmesi `milliseconds` parametresi, diğer etkin içerikler işlerini yapmak için Fırsat verilen kadar geçerli bağlamı askıya almak çalışma zamanı neden olur. Bu, tüm diğer etkin görevleri göreve verim sağlar.  
  
### <a name="example"></a>Örnek  
 Kullanan bir örnek `wait` geçerli bağlamı elde etmek üzere işlev ve bu nedenle diğer bağlamlarda çalıştırmak için bkz: izin [nasıl yapılır: kullanım zamanlama grupları, etkisi sipariş yürütme için](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="the-context-class"></a>Bağlam sınıfı  
 Eşzamanlılık::[bağlam sınıfı](../../parallel/concrt/reference/context-class.md) bir yürütme bağlamı için programlama bir Özet sağlar ve iki önemli özellikler sunar: işlevinizde engellemek, engellemesini kaldırmak ve geçerli bağlamı verim olanağı ve yeteneği Geçerli bağlam oversubscribe.  
  
### <a name="cooperative-blocking"></a>İşbirlikçi engelleme  
 `Context` Sınıfı engellemek ya da geçerli yürütme bağlamı verim olanak sağlar. Bir kaynak kullanılabilir olmadığından geçerli bağlamı devam edemiyor engelleme veya sağlayan yararlıdır.  
  

 [Concurrency::Context::Block](reference/context-class.md#block) yöntemi geçerli bağlamı engeller. Çalışma zamanı diğer görevleri gerçekleştirebilmeleri için engellenen bir bağlam işlem kaynaklarını verir. [Concurrency::Context::Unblock](reference/context-class.md#unblock) yöntemi engellenen bağlam engelini kaldırır. `Context::Unblock` Yöntemi çağrılır, çağrılan olandan farklı bir bağlamından `Context::Block`. Çalışma zamanı oluşturur [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) kendisini engellemesini kaldırmak bir bağlam çalışırsa.  
  
 İşbirliği ile engellemek ve bir bağlam engellemesini kaldırmak için genellikle çağrısı [concurrency::Context::CurrentContext](reference/context-class.md#currentcontext) bir işaretçi almak için `Context` sonucu kaydetme geçerli iş parçacığı ile ilişkili nesne. Ardından çağıran `Context::Block` geçerli bağlamı engellemek için yöntem. Daha sonra arama `Context::Unblock` engellenen bağlam engellemesini kaldırmak için ayrı bir içeriğinden.  
  
 Her çifti yapılan çağrıların eşleşmelidir `Context::Block` ve `Context::Unblock`. Çalışma zamanı oluşturur [concurrency::context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) zaman `Context::Block` veya `Context::Unblock` yöntemi çağrıldığında art arda başka bir yöntem için eşleşen bir çağrı olmadan. Ancak, çağrı gerekmez `Context::Block` çağırmadan önce `Context::Unblock`. Örneğin, bir içerik çağırırsa `Context::Unblock` başka bir bağlam çağrıları önce `Context::Block` aynı içerik için bu bağlam engeli kalır.  
  
 [Concurrency::Context::Yield](reference/context-class.md#yield) yöntemi, böylece çalışma zamanı diğer görevleri gerçekleştirmek ve yürütme bağlamı yeniden zamanla yürütme verir. Çağırdığınızda `Context::Block` yöntemi, çalışma zamanının içeriği yeniden değil.  

  
#### <a name="example"></a>Örnek  
 Kullanan bir örnek `Context::Block`, `Context::Unblock`, ve `Context::Yield` işbirlikçi semafor sınıfı uygulamaya yönelik yöntemleri bkz [nasıl yapılır: bir Cooperative semafor uygulamak için bağlam sınıfını kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).  
  
##### <a name="oversubscription"></a>Aşırı abonelik  
 Kullanılabilir donanım iş parçacıkları olduğundan varsayılan Zamanlayıcı iş parçacığı aynı sayıda oluşturur. Kullanabileceğiniz *aşırı abonelik* belirli donanım iş parçacığı için ek iş parçacığı oluşturulamadı.  
  
 Pkı'ya yoğun işlemleri için ek yükü getirir çünkü aşırı abonelik genellikle ölçeklenmez. Ancak, gecikme süresi yüksek miktarda görevler için örneğin, disk veya bir ağ bağlantısından veri okuma aşırı abonelik bazı uygulamaları genel verimliliğini artırabilir.  
  
> [!NOTE]
>  Eşzamanlılık Çalışma zamanı tarafından oluşturulan bir iş aşırı abonelik etkinleştirin. (Ana iş parçacığı dahil) çalışma zamanı tarafından oluşturulmayan akıştan çağrıldığında aşırı abonelik bir etkisi yoktur.  
  
 Aşırı abonelik geçerli bağlamda etkinleştirmek için arama [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) yöntemiyle `_BeginOversubscription` parametre kümesine `true`. Eşzamanlılık Çalışma zamanı tarafından oluşturulan bir iş parçacığında aşırı abonelik etkinleştirdiğinizde, bir ek iş parçacığı oluşturmak çalışma zamanı neden olur. Aşırı abonelik bitiş gerektiren tüm görevleri sonra çağrısı `Context::Oversubscribe` ile `_BeginOversubscription` parametre kümesine `false`.  

  
 Aşırı abonelik birden çok kez geçerli bağlamdan etkinleştirebilirsiniz, ancak, onu etkinleştirmeniz aynı sayısı devre dışı bırakmalısınız. Aşırı abonelik Ayrıca iç içe olabilir; diğer bir deyişle, aşırı talep kullanan başka bir görev tarafından oluşturulan bir görev Ayrıca kendi bağlamı fazlasına abone olabilirsiniz. Ancak, aynı bağlamın, yalnızca en dıştaki çağrısı için iç içe geçmiş bir görevi ve kendi üst aitse `Context::Oversubscribe` ek bir iş parçacığı oluşturulmasına neden olur.  
  
> [!NOTE]
>  Çalışma zamanı oluşturur [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) etkinleştirmeden önce aşırı abonelik devre dışı bırakılırsa.  
  
###### <a name="example"></a>Örnek  
 Bir ağ bağlantısından veri okuyarak neden gecikmeyi dengelemek için aşırı talep kullanan bir örnek için bkz: [nasıl yapılır: kullanım aşırı abonelik uzaklığı gecikme](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Nasıl yapılır: yürütme sırasını etkilemek için zamanlama grupları kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)   
 [Nasıl yapılır: bağlam sınıfını işbirlikçi semafor uygulamak için kullanın](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

