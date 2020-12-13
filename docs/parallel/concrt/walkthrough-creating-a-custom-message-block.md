---
description: 'Daha fazla bilgi edinin: Izlenecek yol: özel bir Ileti bloğu oluşturma'
title: 'İzlenecek Yol: Özel bir İleti Bloğu Oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: 2347284c4541ef52579a2179c6387b435b1d382f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163853"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>İzlenecek Yol: Özel bir İleti Bloğu Oluşturma

Bu belgede, gelen iletileri önceliğe göre sipariş eden bir özel ileti bloğu türünün nasıl oluşturulacağı açıklanmaktadır.

Yerleşik ileti bloğu türleri çok çeşitli işlevler sağlamasına karşın, kendi ileti bloğu türünü oluşturabilir ve uygulamanızın gereksinimlerini karşılayacak şekilde özelleştirebilirsiniz. Zaman uyumsuz aracılar Kitaplığı tarafından sunulan yerleşik ileti bloğu türlerinin bir açıklaması için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi başlamadan önce aşağıdaki belgeleri okuyun:

- [Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu izlenecek yol aşağıdaki bölümleri içerir:

- [Özel bir Ileti bloğu tasarlama](#design)

- [Priority_buffer sınıfını tanımlama](#class)

- [Tam Örnek](#complete)

## <a name="designing-a-custom-message-block"></a><a name="design"></a> Özel bir Ileti bloğu tasarlama

İleti blokları ileti gönderme ve alma Yasası 'na katılır. İleti gönderen bir ileti bloğu, *kaynak bloğu* olarak bilinir. İletileri alan bir ileti bloğu *hedef blok* olarak bilinir. Her ikisinin de ileti gönderdiği ve aldığı bir ileti bloğu, bir *yayıcı bloğu* olarak bilinir. Aracılar Kitaplığı, kaynak bloklarını temsil etmek için [concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) soyut sınıfını ve hedef blokları temsil etmek için [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) soyut sınıfını kullanır. Kaynak olarak davranan ileti bloğu türleri ' den türetilir `ISource` ; hedef olarak davranan ileti bloğu türleri öğesinden türetilir `ITarget` .

İleti bloğu türünü doğrudan ve ' den türetebilirsiniz, `ISource` ancak `ITarget` aracılar Kitaplığı, tüm ileti bloğu türleri için ortak olan işlevlerin çoğunu gerçekleştiren üç temel sınıfı tanımlar, örneğin, hataları işleme ve ileti bloklarını eşzamanlılık açısından güvenli bir şekilde bağlama. [Concurrency:: source_block](../../parallel/concrt/reference/source-block-class.md) sınıfı, öğesinden türetilir `ISource` ve diğer bloklara ileti gönderir. [Concurrency:: target_block](../../parallel/concrt/reference/target-block-class.md) sınıfı, öğesinden türetilir `ITarget` ve diğer bloklardan ileti alır. [Eşzamanlılık::p ropagator_block](../../parallel/concrt/reference/propagator-block-class.md) sınıfı, `ISource` ve `ITarget` diğer bloklara ileti gönderir ve diğer bloklardan ileti alır. İleti bloizin davranışına odaklanabilmeniz için altyapı ayrıntılarını işlemek üzere bu üç temel sınıfı kullanmanızı öneririz.

`source_block`, `target_block` Ve sınıfları, `propagator_block` bağlantıları ya da kaynak ve hedef blokları ile iletilerin nasıl işlendiğini yöneten bir tür üzerinde bağlantı veya bağlantıları yöneten bir tür üzerinde parametreli şablonlardır. Aracılar Kitaplığı, bağlantı yönetimi gerçekleştiren iki türü tanımlar, [concurrency:: single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) ve [concurrency:: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). Sınıfı, bir `single_link_registry` ileti bloğunun bir kaynağa veya bir hedefe bağlanmasını sağlar. `multi_link_registry`Sınıfı, bir ileti bloğunun birden fazla kaynağa veya birden çok hedefe bağlanmasını sağlar. Aracılar Kitaplığı ileti yönetimi gerçekleştiren bir sınıfı tanımlar, [concurrency:: ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). `ordered_message_processor`Sınıfı ileti bloklarının iletileri aldığı sırada işlemesini sağlar.

İleti bloklarının kaynak ve hedefleriyle nasıl ilişkili olduğunu daha iyi anlamak için aşağıdaki örneği göz önünde bulundurun. Bu örnek, [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md) sınıfının bildirimini gösterir.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer`Sınıfı öğesinden türetilir `propagator_block` ve bu nedenle hem kaynak blok hem de hedef blok olarak davranır. Bu, türündeki iletileri kabul eder `_Input` ve türündeki iletileri gönderir `_Output` . `transformer`Sınıfı herhangi bir `single_link_registry` hedef blok için bağlantı Yöneticisi olarak ve `multi_link_registry` herhangi bir kaynak bloğu için bağlantı Yöneticisi olarak belirtir. Bu nedenle, bir `transformer` nesne en fazla bir hedefe ve sınırsız sayıda kaynağa sahip olabilir.

Öğesinden türetilen bir sınıf `source_block` altı Yöntem gerçekleştirmelidir: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message)ve [resume_propagation](reference/source-block-class.md#resume_propagation). Öğesinden türetilen bir sınıf `target_block` [propagate_message](reference/propagator-block-class.md#propagate_message) yöntemini uygulamalıdır ve isteğe bağlı olarak [send_message](reference/propagator-block-class.md#send_message) metodunu uygulayabilir. Öğesinden türeten `propagator_block` , her ikisi ve ' den türetmede işlevsel olarak eşdeğerdir `source_block` `target_block` .

`propagate_to_any_targets`Yöntemi, tüm gelen iletileri zaman uyumsuz veya zaman uyumlu olarak işlemek ve giden iletileri yaymak için çalışma zamanı tarafından çağırılır. `accept_message`Yöntemi, iletileri kabul etmek için hedef bloklar tarafından çağırılır. Gibi birçok ileti bloğu türü `unbounded_buffer` , yalnızca iletiyi alacak ilk hedefe gönderir. Bu nedenle, iletinin sahipliğini hedefe aktarır. [Eşzamanlılık:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)gibi diğer ileti bloğu türleri, hedef bloklarından her birine iletiler sunar. Bu nedenle, `overwrite_buffer` her bir hedefin her biri için iletinin bir kopyasını oluşturur.

`reserve_message`,, `consume_message` `release_message` Ve yöntemlerinde ileti `resume_propagation` bloklarının ileti rezervasyonuna katılmasını sağlar. Hedef blokları, `reserve_message` bir ileti sunulduklarında ve daha sonra kullanılmak üzere iletiyi ayırmak zorunda olduğunda yöntemini çağırır. Hedef blok bir iletiyi ayırdıktan sonra, `consume_message` Bu iletiyi kullanmak için yöntemini veya `release_message` ayırmayı iptal etmek için yöntemini çağırabilir. Yönteminde olduğu gibi `accept_message` , uygulamasının uygulanması `consume_message` iletinin sahipliğini aktarabilir ya da iletinin bir kopyasını döndürebilir. Bir hedef blok, ayrılmış bir iletiyi kullandıktan veya serbest bırakdıktan sonra, çalışma zamanı `resume_propagation` yöntemini çağırır. Genellikle, bu yöntem kuyruktaki bir sonraki iletiden başlayarak ileti yaymayı devam ettirir.

Çalışma zamanı, bir `propagate_message` iletiyi başka bir bloktan güncel bir iletiyi zaman uyumsuz olarak aktarmak için yöntemini çağırır. `send_message`Yöntemi, `propagate_message` zaman uyumsuz yerine eşzamanlı olarak, iletiyi hedef bloklara gönderecek şekilde benzerdir. Varsayılan uygulama `send_message` tüm gelen iletileri reddeder. İleti, hedef bloğuyla ilişkili isteğe bağlı filtre işlevini geçemezse, çalışma zamanı bu yöntemlerden birini çağırmaz. İleti filtreleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).

[[Üst](#top)]

## <a name="defining-the-priority_buffer-class"></a><a name="class"></a> Priority_buffer sınıfını tanımlama

`priority_buffer`Sınıfı, gelen iletileri önce önceliğe, ardından iletilerin alındığı sıraya göre sipariş eden özel bir ileti bloğu türüdür. `priority_buffer`Sınıf, bir ileti kuyruğu tutan ve hem kaynak hem de hedef ileti bloğu olarak davrandığı ve hem birden çok kaynağa hem de birden çok hedefe sahip olabileceğinden [eşzamanlılık:: unbounded_buffer](reference/unbounded-buffer-class.md) sınıfına benzer. Ancak, `unbounded_buffer` ileti yaymayı yalnızca kaynaklarından iletileri aldığı sırada dayandırır.

`priority_buffer`Sınıfı, ve öğelerini içeren std::[Tuple](../../standard-library/tuple-class.md) türündeki iletileri alır `PriorityType` `Type` . `PriorityType` her iletinin önceliğini tutan türü belirtir; `Type` iletinin veri bölümünü gösterir. `priority_buffer`Sınıfı, türünde iletiler gönderir `Type` . `priority_buffer`Sınıfı iki ileti kuyruğunu da yönetir: gelen iletiler için [std::p riority_queue](../../standard-library/priority-queue-class.md) nesnesi ve giden iletiler için std::[Queue](../../standard-library/queue-class.md) nesnesi. İletileri önceliğe göre sıralamak, bir `priority_buffer` nesne aynı anda birden çok ileti aldığında veya müşteriler tarafından herhangi bir ileti okunmadan birden çok ileti aldığında yararlıdır.

Sınıfından türetilen bir sınıfın de uygulanması gereken yedi yönteme ek olarak, `propagator_block` `priority_buffer` sınıfı ve yöntemlerini de geçersiz kılar `link_target_notification` `send_message` . `priority_buffer`Sınıfı ayrıca iki ortak yardımcı yöntemi `enqueue` ve ve `dequeue` özel bir yardımcı yöntemini tanımlar `propagate_priority_order` .

Aşağıdaki yordamda sınıfının nasıl uygulanacağı açıklanmaktadır `priority_buffer` .

#### <a name="to-define-the-priority_buffer-class"></a>Priority_buffer sınıfını tanımlamak için

1. Bir C++ üst bilgi dosyası oluşturun ve adlandırın `priority_buffer.h` . Alternatif olarak, projenizin bir parçası olan mevcut bir üst bilgi dosyasını kullanabilirsiniz.

1. İçinde `priority_buffer.h` , aşağıdaki kodu ekleyin.

    [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. `std`Ad alanında, concurrency::[Message](../../parallel/concrt/reference/message-class.md) nesnelerinde işlem gören [std:: less](../../standard-library/less-struct.md) ve [std:: daha](../../standard-library/greater-struct.md) fazlasını tanımlayın.

    [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   `priority_buffer`Sınıf `message` nesneleri bir nesne içinde depolar `priority_queue` . Bu tür Uzmanlıklar, öncelik sırasının iletileri önceliklerine göre sıralamalarını sağlar. Öncelik, nesnenin ilk öğesidir `tuple` .

1. `concurrencyex`Ad alanında, `priority_buffer` sınıfını bildirin.

    [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   `priority_buffer`Sınıfı öğesinden türetilir `propagator_block` . Bu nedenle, hem ileti gönderebilir hem de alabilir. `priority_buffer`Sınıfı, türünde ileti alan birden çok hedefe sahip olabilir `Type` . Ayrıca, türünde ileti gönderen birden fazla kaynak olabilir `tuple<PriorityType, Type>` .

1. **`private`** `priority_buffer` Sınıfının bölümünde aşağıdaki üye değişkenlerini ekleyin.

    [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   `priority_queue`Nesne gelen iletileri barındırır; `queue` nesne giden iletileri barındırır. Bir `priority_buffer` nesne birden fazla iletiyi aynı anda alabilir; `critical_section` nesne, giriş iletilerinin kuyruğuna erişimi eşitler.

1. **`private`** Bölümünde, kopya oluşturucusunu ve atama işlecini tanımlayın. Bu, `priority_queue` nesnelerin atanabilir olmasını engeller.

    [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. **`public`** Bölümünde, birçok ileti bloğu türü için ortak olan oluşturucuları tanımlayın. Yıkıcıyı da tanımlayın.

    [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. **`public`** Bölümünde, ve yöntemlerini tanımlayın `enqueue` `dequeue` . Bu yardımcı yöntemler, bir nesneden ileti göndermek ve iletileri almak için alternatif bir yol sağlar `priority_buffer` .

    [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

1. **`protected`** Bölümünde `propagate_to_any_targets` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   `propagate_to_any_targets`Yöntemi, giriş sırasının önündeki iletiyi çıkış kuyruğuna aktarır ve çıkış kuyruğundaki tüm iletileri yayar.

1. **`protected`** Bölümünde `accept_message` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Bir hedef blok `accept_message` yöntemini çağırdığında, `priority_buffer` sınıfı iletiyi kabul eden ilk hedef bloğa iletinin sahipliğini aktarır. (Bunun davranışına benzer `unbounded_buffer` .)

1. **`protected`** Bölümünde `reserve_message` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   `priority_buffer`Sınıfı, bir hedef bloğunun, belirtilen ileti tanımlayıcısı kuyruğun önünde olan iletinin tanımlayıcısıyla eşleştiğinde bir ileti ayırmasını sağlar. Diğer bir deyişle, `priority_buffer` nesne henüz ek bir ileti almamışsa ve henüz geçerli olanı yayılmadıysa bir hedef iletiyi ayırabilir.

1. **`protected`** Bölümünde `consume_message` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Bir hedef blok `consume_message` , ayrılan iletinin sahipliğini aktarmak için çağırır.

1. **`protected`** Bölümünde `release_message` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Bir hedef blok `release_message` , bir iletiye ayırmasını iptal etmek için çağırır.

1. **`protected`** Bölümünde `resume_propagation` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   `resume_propagation`Bir hedef bloğundan sonra çalışma zamanı çağrıları, ayrılmış bir ileti kullanır veya serbest bırakır. Bu yöntem, çıkış sırasındaki tüm iletileri yayar.

1. **`protected`** Bölümünde `link_target_notification` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor`Üye değişkeni, taban sınıfı tarafından tanımlanır `source_block` . Bu üye değişkeni, varsa, çıkış sırasının önündeki iletiye bir rezervasyon tutan hedef bloğuna işaret eder. Çalışma zamanı, `link_target_notification` nesnesine yeni bir hedef bağlandığında çağrılır `priority_buffer` . Bu yöntem, bir hedef rezervasyon tutmsa çıkış kuyruğundaki tüm iletileri yayar.

1. **`private`** Bölümünde `propagate_priority_order` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Bu yöntem, çıkış sırasından tüm iletileri yayar. Kuyruktaki her ileti, hedef bloklarından biri iletiyi kabul edene kadar her hedef bloğa sunulur. `priority_buffer`Sınıfı giden iletilerin sırasını korur. Bu nedenle, bu yöntem hedef bloklara başka bir ileti girmeden önce, çıkış sırasındaki ilk ileti bir hedef blok tarafından kabul alınmalıdır.

1. **`protected`** Bölümünde `propagate_message` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   `propagate_message`Yöntemi, `priority_buffer` sınıfın bir ileti alıcısı veya hedefi olarak davranmasını sağlar. Bu yöntem, sağlanan kaynak bloğunun sunduğu iletiyi alır ve bu iletiyi öncelik kuyruğuna ekler. `propagate_message`Yöntemi daha sonra zaman uyumsuz olarak tüm çıkış iletilerini hedef bloklara gönderir.

   [Concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevini çağırdığınızda veya ileti bloğu diğer ileti bloklarına bağlandığında, çalışma zamanı bu yöntemi çağırır.

1. **`protected`** Bölümünde `send_message` yöntemini tanımlayın.

    [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   `send_message`Yöntemi benzerdir `propagate_message` . Bununla birlikte, çıkış iletilerini zaman uyumsuz yerine eşzamanlı olarak gönderir.

   Çalışma zamanı, zaman uyumlu gönderme işlemi sırasında [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini çağırdığınızda olduğu gibi bu yöntemi çağırır.

`priority_buffer`Sınıfı, çoğu ileti bloğu türünde tipik olan Oluşturucu aşırı yüklerini içerir. Bazı Oluşturucu aşırı yüklemeleri [eşzamanlılık:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [eşzamanlılık:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) nesneleri alır, bu da ileti bloğunun belirli bir görev zamanlayıcısı tarafından yönetilmesini sağlar. Diğer Oluşturucu aşırı yüklemeleri bir filtre işlevi alır. Filtre işlevleri, ileti bloklarının yük temelinde bir iletiyi kabul etmesini veya reddetmesini sağlar. İleti filtreleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md). Task zamanlayıcılar hakkında daha fazla bilgi için bkz. [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).

`priority_buffer`Sınıfı iletileri önceliğe göre ve ardından iletilerin alındığı sıraya göre sipariş ettiğinden, bu sınıf, iletileri zaman uyumsuz aldığında, örneğin [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) işlevini çağırdığınızda veya ileti bloğu diğer ileti bloklarına bağlandığında yararlı olur.

[[Üst](#top)]

## <a name="the-complete-example"></a><a name="complete"></a> Tüm örnek

Aşağıdaki örnek, sınıfının tamamının tanımını gösterir `priority_buffer` .

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

Aşağıdaki örnek, `asend` bir nesne üzerinde bir dizi ve [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlemi eşzamanlı olarak gerçekleştirir `priority_buffer` .

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

`priority_buffer`Sınıfı, iletileri önce önceliğe, sonra iletileri aldığı sıraya göre sıralar. Bu örnekte, sıranın önüne doğru daha fazla sayısal önceliğe sahip iletiler eklenir.

[[Üst](#top)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın ya da sınıf tanımını adlı bir `priority_buffer` `priority_buffer.h` dosyadaki ve test programı adlı bir dosyaya yapıştırın `priority_buffer.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/EHsc priority_buffer. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı Izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)
