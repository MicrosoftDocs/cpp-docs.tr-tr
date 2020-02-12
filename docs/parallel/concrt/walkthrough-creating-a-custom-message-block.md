---
title: 'İzlenecek Yol: Özel bir İleti Bloğu Oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: a29ed382d67b91443bd13e029af2a37c42ee834d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142823"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>İzlenecek Yol: Özel bir İleti Bloğu Oluşturma

Bu belgede, gelen iletileri önceliğe göre sipariş eden bir özel ileti bloğu türünün nasıl oluşturulacağı açıklanmaktadır.

Yerleşik ileti bloğu türleri çok çeşitli işlevler sağlamasına karşın, kendi ileti bloğu türünü oluşturabilir ve uygulamanızın gereksinimlerini karşılayacak şekilde özelleştirebilirsiniz. Zaman uyumsuz aracılar Kitaplığı tarafından sunulan yerleşik ileti bloğu türlerinin bir açıklaması için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="prerequisites"></a>Prerequisites

Bu yönergeyi başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

## <a name="top"></a>Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Özel bir Ileti bloğu tasarlama](#design)

- [Priority_buffer sınıfını tanımlama](#class)

- [Tüm örnek](#complete)

## <a name="design"></a>Özel bir Ileti bloğu tasarlama

İleti blokları ileti gönderme ve alma Yasası 'na katılır. İleti gönderen bir ileti bloğu, *kaynak bloğu*olarak bilinir. İletileri alan bir ileti bloğu *hedef blok*olarak bilinir. Her ikisinin de ileti gönderdiği ve aldığı bir ileti bloğu, bir *yayıcı bloğu*olarak bilinir. Aracılar Kitaplığı, kaynak bloklarını temsil etmek için [concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) soyut sınıfını ve hedef blokları temsil etmek için [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) soyut sınıfını kullanır. Kaynak olarak davranan ileti bloğu türleri `ISource`türetilir; hedef olarak davranan ileti bloğu türleri `ITarget`türetilir.

İleti bloğu türünü doğrudan `ISource` ve `ITarget`türetilebilseniz de, aracılar Kitaplığı, tüm ileti bloğu türleri için ortak olan işlevlerin çoğunu gerçekleştiren üç temel sınıfı tanımlar, örneğin, hataları işleme ve ileti bloklarını eşzamanlılık açısından güvenli bir şekilde birbirine bağlama. [Concurrency:: source_block](../../parallel/concrt/reference/source-block-class.md) sınıfı `ISource` türetilir ve diğer bloklara iletiler gönderir. [Concurrency:: target_block](../../parallel/concrt/reference/target-block-class.md) sınıfı `ITarget` türetilir ve diğer bloklardan ileti alır. [Eşzamanlılık::p ropagator_block](../../parallel/concrt/reference/propagator-block-class.md) sınıfı `ISource` ve `ITarget` türetilir ve diğer bloklara ileti gönderir ve diğer bloklardan ileti alır. İleti bloizin davranışına odaklanabilmeniz için altyapı ayrıntılarını işlemek üzere bu üç temel sınıfı kullanmanızı öneririz.

`source_block`, `target_block`ve `propagator_block` sınıfları, kaynak ve hedef blokları ile iletilerin nasıl işlendiğini yöneten bir tür üzerinde bağlantıları veya bağlantıları yöneten bir tür üzerinde parametreli şablonlardır. Aracılar Kitaplığı, bağlantı yönetimi gerçekleştiren iki türü tanımlar, [concurrency:: single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) ve [concurrency:: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). `single_link_registry` sınıfı, bir ileti bloğunun bir kaynağa veya bir hedefe bağlanmasını sağlar. `multi_link_registry` sınıfı, bir ileti bloğunun birden fazla kaynağa veya birden çok hedefe bağlanmasını sağlar. Aracılar Kitaplığı ileti yönetimi gerçekleştiren bir sınıfı tanımlar, [concurrency:: ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). `ordered_message_processor` sınıfı ileti bloklarının iletileri aldığı sırada işlemesini sağlar.

İleti bloklarının kaynak ve hedefleriyle nasıl ilişkili olduğunu daha iyi anlamak için aşağıdaki örneği göz önünde bulundurun. Bu örnek, [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıfının bildirimini gösterir.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer` sınıfı `propagator_block`türetilir ve bu nedenle hem kaynak blok hem de hedef blok olarak davranır. `_Input` türündeki iletileri kabul eder ve `_Output`türünde iletiler gönderir. `transformer` sınıfı herhangi bir hedef blok için bağlantı Yöneticisi olarak `single_link_registry` ve herhangi bir kaynak bloğu için bağlantı Yöneticisi olarak `multi_link_registry` belirtir. Bu nedenle, bir `transformer` nesnesi en fazla bir hedefe ve sınırsız sayıda kaynağa sahip olabilir.

`source_block` türetilen bir sınıf altı Yöntem gerçekleştirmelidir: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message)ve [resume_propagation](reference/source-block-class.md#resume_propagation). `target_block` türetilen bir sınıf [propagate_message](reference/propagator-block-class.md#propagate_message) yöntemini uygulamalıdır ve isteğe bağlı olarak [send_message](reference/propagator-block-class.md#send_message) metodunu uygulayabilir. `propagator_block` türetmek, hem `source_block` hem de `target_block`türetmede işlevsel olarak eşdeğerdir.

`propagate_to_any_targets` yöntemi, tüm gelen iletileri zaman uyumsuz olarak veya zaman uyumlu olarak işlemek ve giden iletileri yaymak için çalışma zamanı tarafından çağırılır. `accept_message` yöntemi, iletileri kabul etmek için hedef bloklar tarafından çağırılır. `unbounded_buffer`gibi birçok ileti bloğu türü, yalnızca iletiyi alacak olan ilk hedefe gönderir. Bu nedenle, iletinin sahipliğini hedefe aktarır. [Eşzamanlılık:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)gibi diğer ileti bloğu türleri, hedef bloklarından her birine iletiler sunar. Bu nedenle `overwrite_buffer`, her bir hedefi için iletinin bir kopyasını oluşturur.

`reserve_message`, `consume_message`, `release_message`ve `resume_propagation` yöntemleri ileti bloklarının ileti rezervasyonuna katılmasını sağlar. Hedef blokları bir ileti sunulduklarında ve daha sonra kullanmak üzere iletiyi ayırmak zorunda olduğunda `reserve_message` yöntemini çağırır. Hedef blok bir iletiyi ayırdıktan sonra, bu iletiyi kullanmak için `consume_message` yöntemi veya ayırmayı iptal etmek için `release_message` metodunu çağırabilir. `accept_message` yönteminde olduğu gibi, `consume_message` uygulanması iletinin sahipliğini aktarabilir ya da iletinin bir kopyasını döndürebilir. Bir hedef blok, ayrılmış bir iletiyi kullandıktan veya serbest bırakdıktan sonra, çalışma zamanı `resume_propagation` yöntemini çağırır. Genellikle, bu yöntem kuyruktaki bir sonraki iletiden başlayarak ileti yaymayı devam ettirir.

Çalışma zamanı, bir iletiyi başka bir bloktan geçerli bir bloğa zaman uyumsuz olarak aktarmak için `propagate_message` yöntemini çağırır. `send_message` yöntemi, zaman uyumsuz olarak değil, iletiyi hedef bloklara göndermesi dışında `propagate_message`benzer. `send_message` varsayılan uygulama tüm gelen iletileri reddeder. İleti, hedef bloğuyla ilişkili isteğe bağlı filtre işlevini geçemezse, çalışma zamanı bu yöntemlerden birini çağırmaz. İleti filtreleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

[[Üst](#top)]

## <a name="class"></a>Priority_buffer sınıfını tanımlama

`priority_buffer` sınıfı, gelen iletileri önce önceliğe, ardından iletilerin alındığı sıraya göre sipariş eden özel bir ileti bloğu türüdür. `priority_buffer` sınıfı, bir ileti kuyruğu tutan ve hem kaynak hem de hedef ileti bloğu olarak davrandığı ve hem birden fazla kaynağa hem de birden çok hedefe sahip olabileceğinden [eşzamanlılık:: unbounded_buffer](reference/unbounded-buffer-class.md) sınıfına benzer. Ancak, `unbounded_buffer` ileti yaymayı yalnızca kaynaklarından iletileri aldığı sıraya göre dayandırır.

`priority_buffer` sınıfı, `PriorityType` ve `Type` öğeleri içeren std::[Tuple](../../standard-library/tuple-class.md) türündeki iletileri alır. `PriorityType`, her iletinin önceliğini tutan tür anlamına gelir; `Type`, iletinin veri bölümüne başvurur. `priority_buffer` sınıfı, `Type`türünde iletiler gönderir. `priority_buffer` sınıfı iki ileti sırasını da yönetir: gelen iletiler için [std::p riority_queue](../../standard-library/priority-queue-class.md) nesnesi ve giden iletiler için std::[Queue](../../standard-library/queue-class.md) nesnesi. İletileri önceliğe göre sıralamak, bir `priority_buffer` nesnesi aynı anda birden çok ileti aldığında veya müşteriler tarafından herhangi bir ileti okunmadan birden çok ileti aldığında yararlıdır.

`propagator_block` ' den türetilen bir sınıfın uygulanması gereken yedi yönteme ek olarak, `priority_buffer` sınıfı da `link_target_notification` ve `send_message` yöntemlerini geçersiz kılar. `priority_buffer` sınıfı ayrıca iki genel yardımcı yöntem, `enqueue` ve `dequeue`ve bir özel yardımcı yöntemi olan `propagate_priority_order`tanımlar.

Aşağıdaki yordamda `priority_buffer` sınıfının nasıl uygulanacağı açıklanmaktadır.

#### <a name="to-define-the-priority_buffer-class"></a>Priority_buffer sınıfını tanımlamak için

1. Bir C++ üst bilgi dosyası oluşturun ve `priority_buffer.h`adlandırın. Alternatif olarak, projenizin bir parçası olan mevcut bir üst bilgi dosyasını kullanabilirsiniz.

1. `priority_buffer.h`, aşağıdaki kodu ekleyin.

[!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. `std` ad alanında, concurrency::[Message](../../parallel/concrt/reference/message-class.md) nesnelerinde işlem gören [std:: less](../../standard-library/less-struct.md) ve [std:: daha](../../standard-library/greater-struct.md) fazlasını tanımlayın.

[!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   `priority_buffer` sınıfı, `message` nesneleri bir `priority_queue` nesnesinde depolar. Bu tür Uzmanlıklar, öncelik sırasının iletileri önceliklerine göre sıralamalarını sağlar. Öncelik `tuple` nesnesinin ilk öğesidir.

1. `concurrencyex` ad alanında `priority_buffer` sınıfını bildirin.

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   `priority_buffer` sınıfı `propagator_block`türetilir. Bu nedenle, hem ileti gönderebilir hem de alabilir. `priority_buffer` sınıfı, `Type`türünde ileti alan birden çok hedefe sahip olabilir. Ayrıca, `tuple<PriorityType, Type>`türünde iletiler gönderen birden fazla kaynağa da sahip olabilir.

1. `priority_buffer` sınıfının `private` bölümünde aşağıdaki üye değişkenlerini ekleyin.

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   `priority_queue` nesnesi gelen iletileri barındırır; `queue` nesnesi giden iletileri barındırır. Bir `priority_buffer` nesnesi aynı anda birden fazla ileti alabilir; `critical_section` nesnesi, giriş iletilerinin kuyruğuna erişimi eşitler.

1. `private` bölümünde, kopya oluşturucusunu ve atama işlecini tanımlayın. Bu, `priority_queue` nesnelerinin atanabilir olmasını engeller.

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. `public` bölümünde, birçok ileti bloğu türü için ortak olan oluşturucuları tanımlayın. Yıkıcıyı da tanımlayın.

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. `public` bölümünde, `enqueue` ve `dequeue`yöntemlerini tanımlayın. Bu yardımcı yöntemler, `priority_buffer` nesnesinden ileti göndermek ve almak için alternatif bir yol sağlar.

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. `protected` bölümünde `propagate_to_any_targets` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   `propagate_to_any_targets` yöntemi, giriş sırasının önündeki iletiyi çıkış kuyruğuna aktarır ve çıkış kuyruğundaki tüm iletileri yayar.

10. `protected` bölümünde `accept_message` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Bir hedef blok `accept_message` yöntemini çağırdığında, `priority_buffer` sınıfı iletinin sahipliğini onu kabul eden ilk hedef bloğa aktarır. (`unbounded_buffer`davranışına benzer.)

11. `protected` bölümünde `reserve_message` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   `priority_buffer` sınıfı, bir hedef bloğunun, belirtilen ileti tanımlayıcısı kuyruğun önünde olan iletinin tanımlayıcısıyla eşleştiğinde bir ileti ayırmasını sağlar. Diğer bir deyişle, `priority_buffer` nesnesi henüz ek bir ileti almamışsa ve henüz geçerli olanı yaymadıysa, bir hedef iletiyi ayırabilir.

12. `protected` bölümünde `consume_message` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Bir hedef blok, ayrılan iletinin sahipliğini aktarmak için `consume_message` çağırır.

13. `protected` bölümünde `release_message` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Bir hedef blok, bir iletiye ayırmasını iptal etmek için `release_message` çağırır.

14. `protected` bölümünde `resume_propagation` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   Çalışma zamanı, bir hedef bloğundan sonra `resume_propagation` çağırır ve ayrılmış bir iletiyi serbest bırakır. Bu yöntem, çıkış sırasındaki tüm iletileri yayar.

15. `protected` bölümünde `link_target_notification` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor` üye değişkeni, `source_block`temel sınıf tarafından tanımlanır. Bu üye değişkeni, varsa, çıkış sırasının önündeki iletiye bir rezervasyon tutan hedef bloğuna işaret eder. Çalışma zamanı, `priority_buffer` nesnesine yeni bir hedef bağlandığında `link_target_notification` çağırır. Bu yöntem, bir hedef rezervasyon tutmsa çıkış kuyruğundaki tüm iletileri yayar.

16. `private` bölümünde `propagate_priority_order` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Bu yöntem, çıkış sırasından tüm iletileri yayar. Kuyruktaki her ileti, hedef bloklarından biri iletiyi kabul edene kadar her hedef bloğa sunulur. `priority_buffer` sınıfı giden iletilerin sırasını korur. Bu nedenle, bu yöntem hedef bloklara başka bir ileti girmeden önce, çıkış sırasındaki ilk ileti bir hedef blok tarafından kabul alınmalıdır.

17. `protected` bölümünde `propagate_message` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   `propagate_message` yöntemi, `priority_buffer` sınıfının bir ileti alıcısı veya hedef olarak çalışmasını sağlar. Bu yöntem, sağlanan kaynak bloğunun sunduğu iletiyi alır ve bu iletiyi öncelik kuyruğuna ekler. `propagate_message` yöntemi, tüm çıkış iletilerini zaman uyumsuz olarak hedef bloklara gönderir.

   [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevini çağırdığınızda veya ileti bloğu diğer ileti bloklarına bağlandığında, çalışma zamanı bu yöntemi çağırır.

18. `protected` bölümünde `send_message` yöntemini tanımlayın.

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   `send_message` yöntemi `propagate_message`benzerdir. Bununla birlikte, çıkış iletilerini zaman uyumsuz yerine eşzamanlı olarak gönderir.

   Çalışma zamanı, zaman uyumlu gönderme işlemi sırasında [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini çağırdığınızda olduğu gibi bu yöntemi çağırır.

`priority_buffer` sınıfı, çoğu ileti bloğu türünde tipik olan Oluşturucu aşırı yüklerini içerir. Bazı Oluşturucu aşırı yüklemeleri [eşzamanlılık:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [eşzamanlılık:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesneleri alır, bu da ileti bloğunun belirli bir görev zamanlayıcısı tarafından yönetilmesini sağlar. Diğer Oluşturucu aşırı yüklemeleri bir filtre işlevi alır. Filtre işlevleri, ileti bloklarının yük temelinde bir iletiyi kabul etmesini veya reddetmesini sağlar. İleti filtreleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md). Task zamanlayıcılar hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

`priority_buffer` sınıfı iletileri önceliğe göre ve ardından iletilerin alındığı sıraya göre sipariş ettiğinden, bu sınıf zaman uyumsuz olarak ileti aldığında yararlı olur, örneğin, [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevini çağırdığınızda veya ileti bloğu diğer ileti bloklarına bağlandığında.

[[Üst](#top)]

## <a name="complete"></a>Tüm örnek

Aşağıdaki örnek `priority_buffer` sınıfının tamamının tanımını gösterir.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

Aşağıdaki örnek eşzamanlı olarak bir dizi `asend` ve [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlemi `priority_buffer` nesnesi üzerinde gerçekleştirir.

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

`priority_buffer` sınıfı, iletileri önce önceliğe, sonra iletileri aldığı sıraya göre sıralar. Bu örnekte, sıranın önüne doğru daha fazla sayısal önceliğe sahip iletiler eklenir.

[[Üst](#top)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `priority_buffer` sınıfının tanımını `priority_buffer.cpp` adlı bir dosyadaki `priority_buffer.h` ve test programı olarak yapıştırın ve sonra Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

**CL. exe/EHsc priority_buffer. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
