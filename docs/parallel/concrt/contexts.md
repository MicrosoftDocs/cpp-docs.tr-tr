---
title: Bağlamlar
ms.date: 11/04/2016
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
ms.openlocfilehash: 9eaf21a3d65ae891a48657de9d3e7aff78ce12b9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142183"
---
# <a name="contexts"></a>Bağlamlar

Bu belgede Eşzamanlılık Çalışma Zamanı bağlamların rolü açıklanmaktadır. Bir Scheduler 'a bağlı olan iş parçacığı, *yürütme bağlamı*veya yalnızca *bağlam*olarak bilinir. [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) işlevi ve concurrency::[Context sınıfı](../../parallel/concrt/reference/context-class.md) , bağlamların davranışını denetlemenize olanak tanır. Geçerli bağlamı belirli bir süre askıya almak için `wait` işlevini kullanın. Bağlamlar engellenme, engellemeyi kaldırma, ve yield işlemleri sırasında daha fazla denetime ihtiyacınız olduğunda veya geçerli bağlamın üzerine fazla abone olmak istediğinizde `Context` sınıfını kullanın.

> [!TIP]
> Eşzamanlılık Çalışma Zamanı varsayılan bir Zamanlayıcı sağlar ve bu nedenle uygulamanızda bir tane oluşturmanız gerekmez. Görev Zamanlayıcı uygulamalarınızın performansını hassas bir şekilde ayarlamanıza yardımcı olduğundan, Eşzamanlılık Çalışma Zamanı yeni başladıysanız [paralel Desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) ile başlamanız önerilir.

## <a name="the-wait-function"></a>Wait Işlevi

[Concurrency:: wait](reference/concurrency-namespace-functions.md#wait) işlevi birlikte çalışır, belirtilen milisaniye sayısı için geçerli bağlamın yürütülmesini verir. Çalışma zamanı, diğer görevleri gerçekleştirmek için yield süresini kullanır. Belirtilen süre geçtikten sonra, çalışma zamanı yürütme bağlamını müşteri sizinle randevusunu. Bu nedenle `wait` işlevi, `milliseconds` parametresi için belirtilen değerden daha uzun geçerli bağlamı askıya alabilir.

`milliseconds` parametresi için 0 (sıfır) geçirme işlemi, diğer tüm etkin bağlamlara iş gerçekleştirme fırsatı verilene kadar çalışma zamanının geçerli bağlamı askıya almasına neden olur. Bu, görevi diğer tüm etkin görevlere vermenizi sağlar.

### <a name="example"></a>Örnek

Geçerli bağlamı yürütmek için `wait` işlevini kullanan bir örnek için, diğer bağlamların çalışmasına izin vermek için bkz. [nasıl yapılır: zamanlama gruplarını kullanarak yürütme sırasını etkileme](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="the-context-class"></a>Bağlam sınıfı

Concurrency::[Context sınıfı](../../parallel/concrt/reference/context-class.md) , bir yürütme bağlamı için programlama soyutlaması sağlar ve iki önemli özellik sunar: geçerli bağlamı birlikte engellemeye, engellemeyi kaldırmaya ve ortaya almanıza ve geçerli bağlamın üzerine fazla abone olma imkanına sahiptir.

### <a name="cooperative-blocking"></a>Birlikte çalışmayan engelleme

`Context` sınıfı, geçerli yürütme bağlamını engellemenize veya yapmanızı sağlar. Bir kaynak kullanılamadığından, geçerli bağlam devam edemediği için engelleme veya işleme yararlı olur.

[Concurrency:: Context:: Block](reference/context-class.md#block) yöntemi geçerli bağlamı engeller. Engellenen bir bağlam, çalışma zamanının diğer görevleri gerçekleştirebilmesi için işlem kaynaklarını verir. [Concurrency:: Context::](reference/context-class.md#unblock) ununununlıı metodu engellenen bağlamı engeller. `Context::Unblock` yöntemi, `Context::Block`çağırılabilecek olandan farklı bir bağlamdan çağrılmalıdır. Çalışma zamanı, bir bağlam kendi engellemesini engellemeyi denediğinde [eşzamanlılık:: context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) oluşturur.

Bir bağlamı birlikte engellemek ve engelini kaldırmak için genellikle [concurrency:: Context:: CurrentContext](reference/context-class.md#currentcontext) ' i çağırıp geçerli iş parçacığıyla ilişkili `Context` nesnesine bir işaretçi alır ve sonucu kaydeder. Ardından, geçerli bağlamı engellemek için `Context::Block` yöntemini çağırın. Daha sonra, engellenen bağlamın engelini kaldırmak için ayrı bir bağlamdan `Context::Unblock` çağırın.

`Context::Block` ve `Context::Unblock`her bir çağrı çiftini eşleştirmelidir. Çalışma zamanı, `Context::Block` veya `Context::Unblock` yöntemi diğer yönteme eşleşen bir çağrı olmadan arka arkaya çağrıldığında [eşzamanlılık:: context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) oluşturur. Ancak, `Context::Unblock`çağırmadan önce `Context::Block` çağırmanız gerekmez. Örneğin, bir bağlam, aynı bağlam için başka bir bağlam `Context::Block` çağırmadan önce `Context::Unblock` çağırırsa, bu bağlam engellenmeye devam eder.

[Concurrency:: Context:: yield](reference/context-class.md#yield) yöntemi, çalışma zamanının diğer görevleri gerçekleştirebilmesi ve sonra yürütme bağlamını yeniden zamanlayabilmesi için yürütmeyi verir. `Context::Block` yöntemini çağırdığınızda, çalışma zamanı bağlamı yeniden zamanlamaz.

#### <a name="example"></a>Örnek

Bir işbirlikçi semafor sınıfı uygulamak için `Context::Block`, `Context::Unblock`ve `Context::Yield` yöntemlerini kullanan bir örnek için bkz. [nasıl yapılır: bağlam sınıfını kullanarak bir işbirlikçi semaforu uygulama](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).

##### <a name="oversubscription"></a>Aşırı abonelik

Varsayılan Zamanlayıcı, kullanılabilir donanım iş parçacıklarında aynı sayıda iş parçacığı oluşturur. *Fazla aboneliği* , belirli bir donanım iş parçacığı için ek iş parçacıkları oluşturmak üzere kullanabilirsiniz.

Yoğun şekilde yoğun işlemler için fazla abonelik genellikle ölçeklendirmez ve ek yük getirir. Ancak, büyük miktarda gecikme süresi olan görevler için, örneğin diskten veya bir ağ bağlantısından veri okurken, aşırı abonelik bazı uygulamaların genel verimliliğini artırır.

> [!NOTE]
> Fazla aboneliği yalnızca Eşzamanlılık Çalışma Zamanı tarafından oluşturulan bir iş parçacığından etkinleştirin. Fazla abonelik, çalışma zamanı tarafından oluşturulmamış bir iş parçacığından çağrıldığında etkisizdir (ana iş parçacığı dahil).

Geçerli bağlamda fazla aboneliği etkinleştirmek için, `_BeginOversubscription` parametresi **true**olarak ayarlanan [concurrency:: Context:: Oversubscribe](reference/context-class.md#oversubscribe) metodunu çağırın. Eşzamanlılık Çalışma Zamanı tarafından oluşturulan bir iş parçacığında fazla aboneliği etkinleştirdiğinizde, çalışma zamanının bir ek iş parçacığı oluşturmasına neden olur. Fazla abonelik gerektiren tüm görevler tamamlandıktan sonra, `_BeginOversubscription` parametresi **false**olarak ayarlanmış `Context::Oversubscribe` çağırın.

Mevcut bağlamdan fazla aboneliği birden çok kez etkinleştirebilirsiniz, ancak bunu etkinleştirdiğiniz sayıda devre dışı bırakmanız gerekir. Fazla abonelik de iç içe olabilir; diğer bir deyişle, aşırı abonelik kullanan başka bir görev tarafından oluşturulan bir görev, bağlamını de fazla abone olabilir. Ancak, iç içe geçmiş bir görev ve onun üst öğesi aynı içeriğe aitse, yalnızca `Context::Oversubscribe` en dıştaki çağrı ek bir iş parçacığı oluşturulmasına neden olur.

> [!NOTE]
> Çalışma zamanı, aşırı abonelik etkinleştirilmeden önce devre dışı bırakılmışsa [eşzamanlılık:: invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) oluşturur.

###### <a name="example"></a>Örnek

Bir ağ bağlantısından veri okurken oluşan gecikme süresini kaydırmak için aşırı abonelik kullanan bir örnek için bkz. [nasıl yapılır: gecikme gecikmesini anlamak Için aşırı abonelik kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)<br/>
[Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)
