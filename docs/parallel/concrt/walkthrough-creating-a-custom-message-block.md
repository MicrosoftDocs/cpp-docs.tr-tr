---
title: 'İzlenecek Yol: Özel bir İleti Bloğu Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: de44a2d01364070318f4d800fc6316c628177178
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607135"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>İzlenecek Yol: Özel bir İleti Bloğu Oluşturma

Bu belge, gelen iletileri öncelik sırasına göre sıralayan bir özel ileti bloğu türünün nasıl oluşturulacağını açıklar.

Yerleşik ileti bloğu türleri geniş aralık işlevsellik sağlasa da, kendi ileti bloğu türünüzü oluşturabilir ve uygulamanızın gereksinimlerini karşılayacak şekilde özelleştirin. Zaman uyumsuz aracılar kitaplığı tarafından sağlanan yerleşik ileti bloğu türleri ile ilgili açıklama için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

##  <a name="top"></a> Bölümleri

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Özel bir ileti bloğu tasarlama](#design)

- [Priority_buffer sınıfını tanımlama](#class)

- [Tam örnek](#complete)

##  <a name="design"></a> Özel bir ileti bloğu tasarlama

İleti blokları ileti gönderme ve alma, işlemine katılır. İletiler gönderen bir ileti bloğu olarak bilinen bir *kaynak blok*. Olarak bilinen, iletileri alan bir ileti bloğu bir *hedef blok*. Olarak bilinen, iletileri alan ve gönderen bir ileti bloğu bir *Yayıcı blok*. Agents kitaplığı soyut sınıfını kullanır [CONCURRENCY::ısource](../../parallel/concrt/reference/isource-class.md) kaynak bloklar ve soyut sınıfını temsil eden [CONCURRENCY::ıtarget](../../parallel/concrt/reference/itarget-class.md) hedef bloklarını temsil etmek için. Kaynakları türetilmesi gibi davranan ileti bloğu türleri `ISource`; hedefleri türetilmesi gibi davranan ileti bloğu türleri `ITarget`.

İleti bloğu türünüzü doğrudan türetebilseniz `ISource` ve `ITarget`, Agents kitaplığı, hataları işleme gibi tüm ileti bloğu türleri için ortak olan işlevselliğinin gerçekleştirmeniz üç temel sınıf tanımlar ve ileti blokları, eşzamanlılık açısından güvenli bir şekilde birbirine bağlama. [Concurrency::source_block](../../parallel/concrt/reference/source-block-class.md) sınıf türetilir `ISource` ve diğer bloklara ileti gönderir. [Concurrency::target_block](../../parallel/concrt/reference/target-block-class.md) sınıf türetilir `ITarget` ve diğer bloklardan ileti alır. [Concurrency::propagator_block](../../parallel/concrt/reference/propagator-block-class.md) sınıf türetilir `ISource` ve `ITarget` ve ileti gönderip diğer bloklardan ve diğer bloklardan ileti alır. İleti bloğunuzun davranışı odaklanabilmeniz için altyapı ayrıntılarını işlemek için bu üç temel sınıfı kullanmanızı öneririz.

`source_block`, `target_block`, Ve `propagator_block` sınıfları, ilişkileri veya bağlantıları bir tür, kaynak ve hedef bloklar arasındaki ve mesajların nasıl işlendiğini yöneten bir türde Parametreleştirilen şablonlardır. Agents kitaplığı, bağlantı yönetimi gerçekleştiren iki tür tanımlar [concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) ve [concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). `single_link_registry` Sınıfı bir kaynak veya bir hedefe bağlanacak bir ileti bloğu sağlar. `multi_link_registry` Sınıfı, birden çok kaynak veya birden çok hedef için bağlantı kurulacak bir ileti bloğu sağlar. Agents kitaplığı, ileti Yönetimi gerçekleştiren bir sınıf tanımlar [concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). `ordered_message_processor` Sınıfı aldığı bunları sırayla iletileri işlemek ileti blokları sağlar.

İleti bloklarının, kaynakları ve hedefleriyle nasıl ilişkili olduğunu daha iyi anlamak için aşağıdaki örneği göz önünde bulundurun. Bu örnekte bildirimi gösterir [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfı.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer` Sınıf türetilir `propagator_block`ve bu nedenle hem kaynak bloğu ve bir hedef blok olarak görev yapar. Türü iletileri kabul `_Input` ve türden iletileri gönderen `_Output`. `transformer` Sınıfını belirtir `single_link_registry` herhangi bir hedef bloğu için Bağlantı Yöneticisi olarak ve `multi_link_registry` herhangi bir kaynak bloğu için Bağlantı Yöneticisi olarak. Bu nedenle, bir `transformer` nesne sahip bir hedef ve sınırsız sayıda kaynağa.

Türetilen bir sınıf `source_block` altı yöntem uygulaması gerekir: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [ consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message), ve [resume_propagation](reference/source-block-class.md#resume_propagation). Türetilen bir sınıf `target_block` uygulamalıdır [propagate_message](reference/propagator-block-class.md#propagate_message) yöntemi ve isteğe bağlı olarak uygulayabilirsiniz [send_message](reference/propagator-block-class.md#send_message) yöntemi. Öğesinden türetme `propagator_block` hem de türetme işlevsel olarak eşdeğerdir `source_block` ve `target_block`.

`propagate_to_any_targets` Yöntemi zaman uyumlu veya zaman uyumsuz olarak tüm gelen iletileri işlemek ve tüm mesajları yaymak için çalışma zamanı tarafından çağrılır. `accept_message` Yöntemi, ileti kabul etmek için hedef blokları tarafından çağrılır. Çoğu gibi bloğu türü, ileti `unbounded_buffer`, iletileri alan yalnızca ilk hedefe gönderir. Bu nedenle, mesajların sahipliğini hedefe aktarır. Diğer ileti blok türleri, aşağıdaki gibi [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), her biri kendi hedef bloklarından iletileri sunar. Bu nedenle, `overwrite_buffer` hedeflerinin her biri için mesajın bir kopyasını oluşturur.

`reserve_message`, `consume_message`, `release_message`, Ve `resume_propagation` yöntemlerini etkinleştirmek ileti blokları ileti rezervasyonlarına katılmalarını sağlar. Hedef blokları çağrı `reserve_message` bir ileti sunulduğunda ve daha sonra kullanmak için bir ileti ayırmak zorunda yöntemi. Bir hedef blok bir iletiyi ayırdıktan sonra çağırabilirsiniz `consume_message` iletiyi kullanmak için yöntemi veya `release_message` ayırmayı iptal etmek için yöntemi. Olduğu gibi `accept_message` yöntemi, uygulanması `consume_message` iletinin sahipliğini veya iletinin bir kopyasını döndürür. Çalışma zamanının bir hedef blok kullandıktan veya ayrılmış bir iletiyi bırakır sonra çağırır `resume_propagation` yöntemi. Genellikle, bu yöntem, sıradaki sonraki iletiye başlayarak ileti yaymaya devam eder.

Çalışma zamanı çağrıları `propagate_message` zaman uyumsuz olarak bir ileti başka bir engelden mevcut olana aktarmak için yöntemi. `send_message` Yöntemi benzer `propagate_message`dışında bu zaman uyumlu olarak, zaman uyumsuz olarak yerine, ileti hedef bloklara gönderir. Varsayılan uygulaması `send_message` gelen tüm iletileri reddeder. Çalışma zamanı, ileti hedef blok ile ilgili isteğe bağlı filtreleme işlevini geçmezse bu yöntemlerden hiç birini çağırmaz. İleti filtreleri hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

[[Üst](#top)]

##  <a name="class"></a> Priority_buffer sınıfını tanımlama

`priority_buffer` Gelen iletileri ilk olarak öncelik, ardından iletilerin alındığı sıraya göre sıralayan bir özel ileti bloğu türünün bir sınıftır. `priority_buffer` Sınıfına benzer [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) çünkü bir ileti kuyruğu tutar ve ayrıca hem kaynak hem de bir hedef mesaj engeli olarak görev yapar ve birden çok kaynaktan hem birden çok olabilir çünkü hedefler. Ancak, `unbounded_buffer` ileti yayılımını yalnızca aldığı iletileri kaynaktan sipariş.

`priority_buffer` Sınıf türündeki mesajları alır std::[demet](../../standard-library/tuple-class.md) içeren `PriorityType` ve `Type` öğeleri. `PriorityType` her iletinin önceliğini barındıran türü gösterir; `Type` iletinin veri bölümünü gösterir. `priority_buffer` Sınıfı türden iletileri gönderen `Type`. `priority_buffer` Sınıfı ayrıca iki ileti kuyruğu yönetir: bir [std::priority_queue](../../standard-library/priority-queue-class.md) gelen iletiler için nesne ve bir std::[kuyruk](../../standard-library/queue-class.md) giden iletiler için nesne. İletileri önceliğe göre düzenlemek yararlı bir `priority_buffer` aldığında birden çok ileti tüketiciler tarafından hiçbir ileti okunmadan önce ya da nesne birden çok ileti aynı anda alır.

Yedi yöntemin yanı sıra bir sınıf öğesinden türetilen `propagator_block` uygulamalıdır, `priority_buffer` sınıfı da geçersiz kılmalar `link_target_notification` ve `send_message` yöntemleri. `priority_buffer` Sınıfı ayrıca iki genel yardımcı yöntemi tanımlar `enqueue` ve `dequeue`ve özel bir yardımcı yöntemi, `propagate_priority_order`.

Aşağıdaki yordam nasıl uygulanacağını açıklar `priority_buffer` sınıfı.

#### <a name="to-define-the-prioritybuffer-class"></a>Priority_buffer sınıfını tanımlamak için

1. Bir C++ üstbilgi dosyası oluşturun ve adlandırın `priority_buffer.h`. Alternatif olarak, projenizin bir parçası olan var olan bir üstbilgi dosyasını kullanabilirsiniz.

1. İçinde `priority_buffer.h`, aşağıdaki kodu ekleyin.

[!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. İçinde `std` ad alanı, uzmanlıklarını tanımlayın [std::less](../../standard-library/less-struct.md) ve [Std::less](../../standard-library/greater-struct.md) eşzamanlılık üzerinde hareket::[ileti](../../parallel/concrt/reference/message-class.md) nesneleri.

[!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   `priority_buffer` Sınıfı depoları `message` nesneler bir `priority_queue` nesne. Bu tür uzmanlıklar, iletileri önceliklerine göre sıralamak öncelik sırası etkinleştirir. Öncelik ilk öğesidir `tuple` nesne.

1. İçinde `concurrencyex` ad alanı bildirimini `priority_buffer` sınıfı.

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   `priority_buffer` Sınıf türetilir `propagator_block`. Bu nedenle, hem gönderdikleri hem de ileti alma. `priority_buffer` Sınıf türü iletiler alan birden çok hedefe sahip `Type`. Türden iletileri gönderen birden çok kaynağı olabilir `tuple<PriorityType, Type>`.

1. İçinde `private` bölümünü `priority_buffer` sınıfında, aşağıdaki üye değişkenlerini ekleyin.

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   `priority_queue` Nesnesi gelen iletileri tutar; `queue` nesnesi giden iletileri tutar. A `priority_buffer` nesne birden çok ileti alabilir aynı anda; `critical_section` nesnesi giriş ileti kuyruğuna erişimi eşitler.

1. İçinde `private` bölümünde, kopya oluşturucu ve atama işlecini tanımlayın. Bu engeller `priority_queue` nesnelerinin atanabilir olmasını.

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. İçinde `public` bölümünde, çoğu ileti bloğu türlerinde ortak olan yapıcıları tanımlayın. Ayrıca yok ediciyi tanımlayın.

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. İçinde `public` bölümünde, definovat metody `enqueue` ve `dequeue`. İleti göndermek ve ileti almak için alternatif bir yolu bu yardımcı yöntemler sağlayan bir `priority_buffer` nesne.

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. İçinde `protected` bölümünde, tanımlama `propagate_to_any_targets` yöntemi.

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   `propagate_to_any_targets` Yöntemi çıkış kuyruğundaki tüm iletileri yayar ve çıkış kuyruğuna giriş kuyruğunun önünde olan iletiyi aktarır.

10. İçinde `protected` bölümünde, tanımlama `accept_message` yöntemi.

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Bir hedef blok çağırdığında `accept_message` yöntemi `priority_buffer` sınıfı, iletinin sahipliğini, onu kabul eden ilk hedef bloğa aktarır. (Bu davranışına benzer `unbounded_buffer`.)

11. İçinde `protected` bölümünde, tanımlama `reserve_message` yöntemi.

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   `priority_buffer` Sınıfı, ileti tanımlayıcısının kuyruğun önündeki iletinin tanımlayıcısı eşleştiğinde bir ileti ayırmak için bir hedef blok izin verir. Diğer bir deyişle, bir hedef iletiyi ayırabilir `priority_buffer` nesnesi henüz ek bir iletiyi almadıysa ve henüz geçerli birini yaymadıysa.

12. İçinde `protected` bölümünde, tanımlama `consume_message` yöntemi.

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Bir hedef blok çağırır `consume_message` ayrılmış olan iletinin sahipliğini aktarmak için.

13. İçinde `protected` bölümünde, tanımlama `release_message` yöntemi.

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Bir hedef blok çağırır `release_message` ileti rezervasyonu iptal etmek için.

14. İçinde `protected` bölümünde, tanımlama `resume_propagation` yöntemi.

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   Çalışma zamanı çağrıları `resume_propagation` sonra bir hedef blok kullandıktan veya ayrılmış bir ileti yayımlar. Bu yöntem, çıktı sırasındaki herhangi bir iletiyi yayar.

15. İçinde `protected` bölümünde, tanımlama `link_target_notification` yöntemi.

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor` Üye değişkeni taban sınıfı tarafından tanımlanan `source_block`. Bu üye değişkeni, varsa çıkış sırası önündeki iletiye bir ayırmaya bulunduran hedef bloğuna işaret eder. Çalışma zamanı çağrıları `link_target_notification` ne zaman yeni bir hedef bağlantılı `priority_buffer` nesne. Bu yöntem, hiçbir hedef bir rezervasyon tutmuyorsa, çıktı sırasındaki herhangi bir iletiyi yayar.

16. İçinde `private` bölümünde, tanımlama `propagate_priority_order` yöntemi.

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Bu yöntem, çıktı sırasındaki tüm iletileri yayar. Hedef bloklardan biri iletiyi kabul edene kadar sıradaki her ileti her hedef bloğa sunulur. `priority_buffer` Sınıfı giden iletilerin sırasını korur. Bu nedenle, bu yöntem hedef bloklarına başka bir ileti sunmadan önce çıkış sırasındaki ilk iletinin bir hedef bloğu tarafından kabul gerekir.

17. İçinde `protected` bölümünde, tanımlama `propagate_message` yöntemi.

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   `propagate_message` Yöntemi etkinleştirir `priority_buffer` ileti alıcısı görev yapacak sınıfı veya hedefleyin. Bu yöntem, bu iletiyi öncelik sırasına ekler ve sağlanan kaynak blokla sunulan iletiyi alır. `propagate_message` Yöntemi ardından zaman uyumsuz olarak gönderir tüm çıktı iletilerini hedef engellerine.

   Çağırdığınızda çalışma zamanı bu yöntemi çağırır [concurrency::asend](reference/concurrency-namespace-functions.md#asend) işlevi veya ileti bloğu diğer ileti bloklarına bağlandığında.

18. İçinde `protected` bölümünde, tanımlama `send_message` yöntemi.

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   `send_message` Yöntemi benzer `propagate_message`. Ancak zaman uyumlu olarak yerine zaman uyumsuz olarak çıktı iletilerini gönderir.

   Çalışma zamanı bu yöntemi çağırdığınızda gibi bir eş zamanlı gönderme işlemi sırasında çağırır. [concurrency::send](reference/concurrency-namespace-functions.md#send) işlevi.

`priority_buffer` Sınıfı, çok sayıda ileti engelleme türü için tipik olan oluşturucu aşırı yüklemeleri içerir. Bazı yapıcı yeniden yüklemeleri [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) ileti bloğunun belirli bir Görev Zamanlayıcı tarafından yönetilecek nesneleri. Diğer Oluşturucu tekrar yüklemeleri bir filtre işlevi alır. Filtre işlevleri ileti bloklarının kabul etme veya reddetme yük boyutuna göre bir ileti etkinleştirin. İleti filtreleri hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md). Görev planlayıcılar hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

Çünkü `priority_buffer` sınıfı iletileri önceliğe göre sıralar ve çağırdığınızda iletileri zaman uyumsuz olarak, örneğin, aldığında ardından iletilerin alındığı sıraya göre bu sınıf en kullanışlı sınıftır [concurrency::asend](reference/concurrency-namespace-functions.md#asend)işlevi veya ileti bloğu diğer ileti bloklarına bağlandığında.

[[Üst](#top)]

##  <a name="complete"></a> Tam örnek

Aşağıdaki örnek eksiksiz tanımını gösterir `priority_buffer` sınıfı.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

Aşağıdaki örnek aynı anda birçok gerçekleştirir `asend` ve [concurrency::receive](reference/concurrency-namespace-functions.md#receive) işlemleri bir `priority_buffer` nesne.

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

Bu örnek, aşağıdaki örnek çıktısı üretir.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

`priority_buffer` Önceliğe göre ve ardından aldığı iletileri sıraya göre sınıfı iletileri ilk sıralar. Bu örnekte, büyük sayısal önceliğe sahip iletiler sıranın önüne doğru eklenir.

[[Üst](#top)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya tanımını yapıştırın `priority_buffer` sınıf adında bir dosya içinde `priority_buffer.h` ve adlı dosyadaki test programına `priority_buffer.cpp` ve ardından Visual Studio'da aşağıdaki komutu çalıştırın Komut İstemi penceresi.

**cl.exe/ehsc priority_buffer.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
