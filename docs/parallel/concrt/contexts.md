---
title: Bağlamları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7be66658c9452fa97c1971ae6719dccb06dbd836
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378227"
---
# <a name="contexts"></a>Bağlamlar

Bu belge, eşzamanlılık çalışma zamanı bağlamları rolünü açıklar. Bir zamanlayıcı için bağlı bir iş parçacığı olarak da bilinen bir *yürütme bağlamı*, veya yalnızca *bağlam*. [Concurrency::wait](reference/concurrency-namespace-functions.md#wait) işlevi ve eşzamanlılık::[bağlamı sınıfının](../../parallel/concrt/reference/context-class.md) bağlamları davranışını denetlemesine olanak sağlar. Kullanım `wait` geçerli bağlam belirli bir süre boyunca askıya almak için işlev. Kullanım `Context` sınıfı, ne zaman bağlamları blok, engellemesini kaldırmak ve yield ya da geçerli bağlam oversubscribe istediğinizde hakkında daha fazla denetime ihtiyacınız olduğunda.

> [!TIP]
>  Eşzamanlılık Çalışma zamanı varsayılan Zamanlayıcı sağlar ve bu nedenle, bir uygulama oluşturmak için gerekli değildir. Görev Zamanlayıcısı'nı, uygulamalarınızın performansını ayarlamanıza yardımcı olduğundan, ile başlamanızı öneririz [paralel desenler kitaplığı (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) veya [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md) kullanıyorsanız Yeni eşzamanlılık çalışma zamanı.

## <a name="the-wait-function"></a>Wait işlevi

[Concurrency::wait](reference/concurrency-namespace-functions.md#wait) işlevi işbirliği içerisinde devamlılığı yürütme geçerli bağlam için belirtilen sayıda milisaniye verir. Çalışma zamanı yield diğer görevleri gerçekleştirmek için kullanır. Belirtilen süre geçtikten sonra çalışma zamanı yürütme bağlamı tarih değiştirdiğinde. Bu nedenle, `wait` işlevi için sağlanan değer'den uzun geçerli bağlam askıya `milliseconds` parametresi.

0 (sıfır) geçirmek için `milliseconds` parametresi, geçerli bağlam tüm etkin bağlamları çalışma gerçekleştirme fırsatı verilir kadar askıya almak çalışma zamanı neden olur. Bu, tüm etkin görevleri için bir görev yield sağlar.

### <a name="example"></a>Örnek

Kullanan bir örnek için `wait` geçerli bağlam elde etmek üzere işlev ve diğer bağlamlarda çalıştırmak bkz. Bu nedenle izin [nasıl yapılır: yürütme sırasını etkisi için zamanlama grupları kullanın](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="the-context-class"></a>Bağlam sınıfı

Eşzamanlılık::[bağlamı sınıfının](../../parallel/concrt/reference/context-class.md) yürütme içeriği için programlama bir Özet sağlar ve iki önemli özellikleri sunar: işbirliği içerisinde devamlılığı blok, engellemesini kaldırmak ve geçerli bağlam yield olanağı ve yeteneği Geçerli bağlam oversubscribe.

### <a name="cooperative-blocking"></a>Birlikte engelleme

`Context` Sınıfı, engelleme ya da geçerli yürütme bağlamı yield olanak tanır. Bir kaynak kullanılabilir olmadığından geçerli bağlam devam edemiyor engelleme ya da sonuçlanmıyor yararlı olur.

[Concurrency::Context::Block](reference/context-class.md#block) yöntemi geçerli bağlamı engeller. Çalışma zamanı diğer görevleri gerçekleştirebilmeleri için engellenen bir bağlam işlem kaynaklarını verir. [Concurrency::Context::Unblock](reference/context-class.md#unblock) yöntemi engellenen bağlam engellemesini kaldırır. `Context::Unblock` Yöntemi çağrıldığında, çağrılan olandan farklı bir bağlamdan `Context::Block`. Çalışma zamanı [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) kendisini engelini kaldırmak bir bağlam çalışırsa.

İşbirliği içerisinde devamlılığı engellemek ve bir bağlam engelini kaldırmak için genellikle çağırmanızı [concurrency::Context::CurrentContext](reference/context-class.md#currentcontext) işaretçisi alınacak `Context` sonucu Kaydet geçerli iş parçacığı ile ilişkili olan nesne. Ardından çağırın `Context::Block` geçerli bağlam engellemek için yöntemi. Daha sonra çağrı `Context::Unblock` engellenen bağlam engelini kaldırmak için ayrı bir bağlamı.

Her bir çifti yapılan çağrıların eşleşmelidir `Context::Block` ve `Context::Unblock`. Çalışma zamanı [concurrency::context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) olduğunda `Context::Block` veya `Context::Unblock` yöntemi çağrıldığında art arda olmadan eşleşen başka bir yöntem çağrısı. Ancak, çağrı gerekmez `Context::Block` çağırmadan önce `Context::Unblock`. Örneğin, bir bağlam çağırırsa `Context::Unblock` başka bir bağlam çağrıları önce `Context::Block` aynı içerik için bu bağlamı engeli kalır.

[Concurrency::Context::Yield](reference/context-class.md#yield) yöntemi yürütme çalışma zamanı, diğer görevleri gerçekleştirmek ve yürütme bağlamı randevularını yeniden zamanlayabilir verir. Çağırdığınızda `Context::Block` metodu, çalışma zamanı bağlamı yeniden değil.

#### <a name="example"></a>Örnek

Kullanan bir örnek için `Context::Block`, `Context::Unblock`, ve `Context::Yield` işbirlikçi semafor sınıfını uygulamak için bkz [nasıl yapılır: bağlam sınıfını Guyana semafor uygulamak için kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).

##### <a name="oversubscription"></a>Aşırı abonelik

Kullanılabilir donanım iş parçacıklarının olduğundan varsayılan Zamanlayıcı aynı sayıda iş parçacığı oluşturur. Kullanabileceğiniz *gecikmeyi* belirli donanım iş parçacığı için ek iş parçacığı oluşturmak için.

İşlem bakımından yoğun işlemleri için ek yük getirir çünkü gecikmeyi genellikle ölçeklenmez. Ancak, gecikme süresi yüksek miktarda olan görevler için örneğin, disk veya ağ bağlantısı kurulurken, verileri okuma gecikmeyi bazı uygulamaları genel verimliliğini artırabilir.

> [!NOTE]
>  Eşzamanlılık Çalışma zamanı tarafından oluşturulan bir iş parçacığından gecikmeyi etkinleştirin. (Ana iş parçacığı dahil) çalışma zamanı tarafından oluşturulmamış bir iş parçacığından çağrıldığında gecikmeyi bir etkisi yoktur.

Geçerli bağlamda gecikmeyi etkinleştirmek için çağrı [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) yöntemiyle `_BeginOversubscription` parametresini `true`. Eşzamanlılık Çalışma zamanı tarafından oluşturulan bir iş parçacığında gecikmeyi etkinleştirdiğinizde, ek bir iş parçacığı oluşturmak çalışma zamanı neden olur. Aşırı abonelik bitiş gerektiren tüm görevleri sonra çağırma `Context::Oversubscribe` ile `_BeginOversubscription` parametresini `false`.

Aşırı abonelik birden çok kez geçerli bağlamdan etkinleştirebilirsiniz, ancak, onu etkinleştirmeniz aynı sayıda devre dışı bırakmanız gerekir. Aşırı abonelik da yuvalanabilir; diğer bir deyişle, aşırı talep kullanan başka bir görev tarafından oluşturulan bir görev Ayrıca kendi bağlam fazladan abone atayabilir. Ancak, aynı içeriği, yalnızca en dıştaki çağrısı bir iç içe geçmiş görev ve üst aitse `Context::Oversubscribe` ek bir iş parçacığı oluşturulmasına neden olur.

> [!NOTE]
>  Çalışma zamanı [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) ise, etkinleştirmeden önce aşırı abonelik devre dışı.

###### <a name="example"></a>Örnek

Bir ağ bağlantısından veri okuyarak neden dengelemek için aşırı talep kullanan bir örnek için bkz: [nasıl yapılır: kullanım gecikmeyi uzaklığı gecikme](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Görev Zamanlayıcısı](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Nasıl yapılır: Yürütme Sırasını Etkilemek için Zamanlama Grupları Kullanma](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)<br/>
[Nasıl yapılır: Bağlam Sınıfını İşbirlikçi Semafor Uygulamak için Kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[Nasıl yapılır: Gecikmeyi Dengelemek için Aşırı Aboneliği Kullanma](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

