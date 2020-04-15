---
title: 'İzlenecek Yol: Özel bir İleti Bloğu Oluşturma'
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: 3386994dce68812cf3ed0852a24d8910cb903acf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368566"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>İzlenecek Yol: Özel bir İleti Bloğu Oluşturma

Bu belge, gelen iletileri önceliğe göre sipariş eden özel bir ileti bloğu türü nasıl oluşturulacak açıklanır.

Yerleşik ileti bloğu türleri geniş bir işlevsellik yelpazesi sağlasa da, kendi ileti bloğu türünüzü oluşturabilir ve uygulamanızın gereksinimlerini karşılayacak şekilde özelleştirebilirsiniz. Asynchronous Agents Kitaplığı tarafından sağlanan yerleşik ileti bloğu türlerinin açıklaması için, [Asynchronous İleti Blokları'na](../../parallel/concrt/asynchronous-message-blocks.md)bakın.

## <a name="prerequisites"></a>Ön koşullar

Bu izbiyi başlatmadan önce aşağıdaki belgeleri okuyun:

- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)

- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)

## <a name="sections"></a><a name="top"></a>Bölüm

Bu izksiyon aşağıdaki bölümleri içerir:

- [Özel İleti Bloğu Tasarlama](#design)

- [priority_buffer Sınıfının Tanımlanması](#class)

- [Tam Örnek](#complete)

## <a name="designing-a-custom-message-block"></a><a name="design"></a>Özel İleti Bloğu Tasarlama

İleti blokları ileti gönderme ve alma eylemine katılır. İleti gönderen ileti bloğu *kaynak bloğu*olarak bilinir. İletileri alan ileti bloğu hedef *bloğu*olarak bilinir. İletileri gönderen ve alan ileti bloğu, *yayılma alanı bloğu*olarak bilinir. Aracılar Kitaplığı, kaynak blokları ve soyut sınıf eşzamanlılığını temsil etmek için soyut sınıf [eşzamanlılığını](../../parallel/concrt/reference/isource-class.md) [kullanır::Hedef](../../parallel/concrt/reference/itarget-class.md) blokları temsil etmek için IHedef. Kaynak olarak hareket eden ileti `ISource`bloğu türleri; hedef olarak hareket eden ileti `ITarget`bloğu türleri.

İleti bloğu türünüzü doğrudan türetebiliyor olsanız da `ISource` ve `ITarget`Aracılar Kitaplığı, tüm ileti bloğu türlerinde yaygın olan işlevlerin çoğunu gerçekleştiren üç temel sınıf tanımlar, örneğin hataları işleme ve ileti bloklarını eşzamanlılık açısından güvenli bir şekilde birbirine bağlama. [Eşzamanlılık::source_block](../../parallel/concrt/reference/source-block-class.md) sınıfı türetilmiştir `ISource` ve diğer bloklara ileti gönderir. [Eşzamanlılık::target_block](../../parallel/concrt/reference/target-block-class.md) sınıfı diğer bloklardan `ITarget` iletiler alır ve alır. [Eşzamanlılık::propagator_block](../../parallel/concrt/reference/propagator-block-class.md) sınıfı türetilmiştir `ISource` `ITarget` ve diğer bloklara iletigönderir ve diğer bloklardan iletiler alır. İleti bloğunuzun davranışına odaklanabilmeniz için altyapı ayrıntılarını işlemek için bu üç temel sınıfı kullanmanızı öneririz.

, `source_block` `target_block`ve `propagator_block` sınıflar, kaynak ve hedef bloklar arasında ve iletilerin nasıl işlenirken yöneten bir tür arasında bağlantıları veya bağlantıları yöneten bir türüzerinde parametreli şablonlardır. Aracılar Kitaplığı bağlantı yönetimi, eşzamanlılık gerçekleştiren iki tür [tanımlar::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) ve [eşzamanlılık::multi_link_registry.](../../parallel/concrt/reference/multi-link-registry-class.md) Sınıf, `single_link_registry` ileti bloğunun bir kaynağa veya tek bir hedefe bağlanmasını sağlar. Sınıf, `multi_link_registry` ileti bloğunun birden çok kaynağa veya birden çok hedefe bağlanmasını sağlar. Aracılar Kitaplığı ileti yönetimi, eşzamanlılık gerçekleştiren bir sınıf [tanımlar::ordered_message_processor.](../../parallel/concrt/reference/ordered-message-processor-class.md) Sınıf, `ordered_message_processor` ileti bloklarının iletileri aldığı sırada işlemesini sağlar.

İleti bloklarının kaynakları ve hedefleri ile nasıl ilişkili olduğunu daha iyi anlamak için aşağıdaki örneği göz önünde bulundurun. Bu örnek, eşzamanlılık bildirimini [gösterir::transformatör](../../parallel/concrt/reference/transformer-class.md) sınıfı.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

Sınıf, `transformer` `propagator_block`ve bu nedenle hem kaynak blok ve bir hedef blok olarak hareket türetilmiştir. Tür iletilerini kabul `_Input` eder ve türünden `_Output`iletiler gönderir. Sınıf, `transformer` herhangi `single_link_registry` bir hedef blok için bağlantı `multi_link_registry` yöneticisi ve kaynak blokları için bağlantı yöneticisi olarak belirtir. Bu nedenle, bir `transformer` nesnenin en fazla bir hedefi ve sınırsız sayıda kaynağı olabilir.

[Propagate_to_any_targets,](reference/source-block-class.md#propagate_to_any_targets) [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message), ve [resume_propagation:](reference/source-block-class.md#resume_propagation)türeyen bir sınıf altı yöntem uygulamak `source_block` gerekir. Bu türleyen `target_block` bir sınıf [propagate_message](reference/propagator-block-class.md#propagate_message) yöntemini uygulamalı ve isteğe bağlı olarak [send_message](reference/propagator-block-class.md#send_message) yöntemini uygulayabilir. Türetilmesi `propagator_block` işlevsel olarak her ikisinden `source_block` de `target_block`türemeye eşdeğerdir ve .

Yöntem, `propagate_to_any_targets` gelen iletileri eşit olarak veya eşzamanlı olarak işlemek ve giden iletileri yaymak için çalışma zamanı tarafından çağrılır. Yöntem, `accept_message` iletileri kabul etmek için hedef bloklar tarafından çağrılır. Birçok ileti bloğu türleri, örneğin, `unbounded_buffer`yalnızca onu alacak ilk hedefe ileti gönderir. Bu nedenle, iletinin sahipliğini hedefe aktarıyor. [Eşzamanlılık::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)gibi diğer ileti bloğu türleri, hedef bloklarının her birine ileti ler sunar. Bu `overwrite_buffer` nedenle, her hedefleri için iletinin bir kopyasını oluşturur.

Mesaj `reserve_message` `consume_message` `release_message`bloklarının ileti rezervasyonuna katılmasını `resume_propagation` sağlar. Hedef bloklar, bir ileti sunulduklarında `reserve_message` yöntemi çağırır ve iletiyi daha sonra kullanmak üzere ayırmak zorunda kalırken. Hedef blok bir ileti ayırdıktan sonra, bu `consume_message` iletiyi `release_message` kullanma yöntemini veya rezervasyonu iptal etme yöntemini arayabilir. `accept_message` Yöntemde olduğu gibi, `consume_message` uygulama iletinin sahipliğini aktarabilir veya iletinin bir kopyasını döndürebilir. Hedef blok, ayrılmış bir iletiyi tükettikten veya `resume_propagation` serbest bıraktıktan sonra, çalışma zamanı yöntemi çağırır. Genellikle, bu yöntem, kuyruktaki sonraki iletiyle başlayarak ileti yayılımı devam eder.

Çalışma zamanı, `propagate_message` yöntemi, bir iletiyi başka bir bloktan geçerli olana eşit olarak aktarmak için çağırır. Yöntem `send_message` benzer `propagate_message`, eşzamanlı olarak yerine eşzamanlı olarak, hedef bloklara ileti gönderir dışında. Varsayılan uygulama `send_message` gelen tüm iletileri reddeder. İleti hedef blokla ilişkili isteğe bağlı filtre işlevini geçmiyorsa, çalışma süresi bu yöntemlerden ikisini de aramaz. İleti filtreleri hakkında daha fazla bilgi [için, Bkz.](../../parallel/concrt/asynchronous-message-blocks.md)

[[Üst](#top)]

## <a name="defining-the-priority_buffer-class"></a><a name="class"></a>priority_buffer Sınıfının Tanımlanması

Sınıf, `priority_buffer` gelen iletileri önce önce önce önce, sonra iletilerin alındığı sıraya göre sıralayan özel bir ileti bloğu türüdür. Sınıf `priority_buffer` [eşzamanlılık benzer::unbounded_buffer](reference/unbounded-buffer-class.md) sınıfı, çünkü bir ileti sırası tutar ve aynı zamanda hem bir kaynak ve hedef ileti bloğu olarak davranır ve hem birden çok kaynak ve birden çok hedef olabilir. Ancak, `unbounded_buffer` ileti yayılımını yalnızca kaynaklarından ileti leri aldığı sıraya temel alır.

Sınıf `priority_buffer` std türü iletileri alır:: içeren `PriorityType` `Type` [tuple](../../standard-library/tuple-class.md) ve öğeleri. `PriorityType`her iletinin önceliğini tutan türü ifade eder; `Type` iletinin veri bölümüne başvurur. Sınıf `priority_buffer` türünden `Type`iletiler gönderir. Sınıf `priority_buffer` ayrıca iki ileti sırasını da yönetir: gelen iletiler için [std::priority_queue](../../standard-library/priority-queue-class.md) nesnesi ve std:: giden iletiler için[sıra](../../standard-library/queue-class.md) nesnesi. İletileri öncelik sıralı sıralama, `priority_buffer` bir nesne aynı anda birden çok ileti aldığında veya herhangi bir ileti tüketiciler tarafından okunmadan önce birden çok ileti aldığında yararlıdır.

Bir `propagator_block` sınıfın uygulaması gereken yedi yönteme `priority_buffer` ek olarak, sınıf da bu `link_target_notification` `send_message` ve yöntemleri geçersiz kılar. Sınıf `priority_buffer` ayrıca iki ortak yardımcı yöntemi `enqueue` `dequeue`ve özel bir yardımcı `propagate_priority_order`yöntemi tanımlar.

Aşağıdaki yordam, `priority_buffer` sınıfın nasıl uygulanacağını açıklar.

#### <a name="to-define-the-priority_buffer-class"></a>Priority_buffer sınıfını tanımlamak için

1. C++ üstbilgi dosyası oluşturun `priority_buffer.h`ve adlandırın. Alternatif olarak, projenizin bir parçası olan varolan bir üstbilgi dosyası kullanabilirsiniz.

1. In `priority_buffer.h`, aşağıdaki kodu ekleyin.

    [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. `std` Ad alanında, [std::less](../../standard-library/less-struct.md) ve [std::büyük](../../standard-library/greater-struct.md) bu eşzamanlılık hareket uzmanlıkları tanımlayın::[ileti](../../parallel/concrt/reference/message-class.md) nesneleri.

    [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   Sınıf `priority_buffer` nesneleri `message` bir `priority_queue` nesnede depolar. Bu tür uzmanlıklar, öncelik sırasının iletileri önceliklerine göre sıralamasını sağlar. Öncelik `tuple` nesnenin ilk öğesidir.

1. `concurrencyex` Ad alanında sınıfı bildirin. `priority_buffer`

    [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   Sınıf `priority_buffer` `propagator_block`türetilmiştir. Bu nedenle, hem gönderebilir hem de ileti alabilir. Sınıfın, `priority_buffer` tür `Type`iletileri alan birden çok hedefi olabilir. Ayrıca, tür `tuple<PriorityType, Type>`iletileri göndermek birden çok kaynak olabilir.

1. Sınıfın `private` bölümüne `priority_buffer` aşağıdaki üye değişkenleri ekleyin.

    [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   Nesne `priority_queue` gelen iletileri tutar; `queue` nesne giden iletileri tutar. Bir `priority_buffer` nesne aynı anda birden çok ileti alabilir; `critical_section` nesne giriş iletileri sırasına erişimi eşitler.

1. `private` Bölümde, kopya oluşturucuyu ve atama işlecini tanımlayın. Bu, `priority_queue` nesnelerin atayabilmesini önler.

    [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. `public` Bölümde, birçok ileti bloğu türüne ortak olan oluşturucuları tanımlayın. Ayrıca yıkıcı tanımlayın.

    [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. `public` Bölümde, yöntemleri `enqueue` tanımlamak ve `dequeue`. Bu yardımcı yöntemleri, bir nesneye ileti göndermek ve bir `priority_buffer` nesneden ileti almak için alternatif bir yol sağlar.

    [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

1. `protected` Bölümde, yöntemi tanımlayın. `propagate_to_any_targets`

    [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   Yöntem, `propagate_to_any_targets` giriş sırasının önündeki iletiyi çıkış kuyruğuna aktarıyor ve çıkış kuyruğundaki tüm iletileri dışarı yayıyor.

1. `protected` Bölümde, yöntemi tanımlayın. `accept_message`

    [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   Hedef blok `accept_message` yöntemi aradığında, `priority_buffer` sınıf iletinin sahipliğini kabul eden ilk hedef bloğuna aktarAr. (Bu davranış benzer `unbounded_buffer`.)

1. `protected` Bölümde, yöntemi tanımlayın. `reserve_message`

    [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   Sınıf, `priority_buffer` sağlanan ileti tanımlayıcısı sıranın önündeki iletinin tanımlayıcısıyla eşleştiğinde bir ileti ayırmasına izin verir. Başka bir deyişle, `priority_buffer` nesne henüz ek bir ileti almamışsa ve henüz geçerli iletiyi yaymamışsa, hedef iletiyi rezerve edebilir.

1. `protected` Bölümde, yöntemi tanımlayın. `consume_message`

    [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   Hedef blok, `consume_message` ayırdığı iletinin sahipliğini aktarmak için çağrıda bulunur.

1. `protected` Bölümde, yöntemi tanımlayın. `release_message`

    [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   Hedef blok, `release_message` bir iletiye olan rezervasyonunu iptal etmek için çağrı da bulunur.

1. `protected` Bölümde, yöntemi tanımlayın. `resume_propagation`

    [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   Hedef bloğunun `resume_propagation` tükettiği veya ayrılmış bir ileti saserbest bırakmaları sonrasında çalışma zamanı çağrıları. Bu yöntem, çıkış kuyruğundaki tüm iletileri dışarı yayılmaktadır.

1. `protected` Bölümde, yöntemi tanımlayın. `link_target_notification`

    [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor` Üye değişken taban sınıf tarafından `source_block`tanımlanır. Bu üye değişkeni, çıktı sırasının önündeki iletiye rezervasyon tutan hedef bloğuna işaret eder. Yeni bir `link_target_notification` hedef `priority_buffer` nesneye bağlandığında çalışma zamanı çağırır. Bu yöntem, hiçbir hedef bir rezervasyon tutuyorsa çıktı kuyruğunda olan iletileri dışarı yayıltMaktadır.

1. `private` Bölümde, yöntemi tanımlayın. `propagate_priority_order`

    [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   Bu yöntem, çıkış kuyruğundan tüm iletileri dışarı yayıltıyor. Hedef bloklardan biri iletiyi kabul edene kadar kuyruktaki her ileti her hedef bloğa sunulur. Sınıf `priority_buffer` giden iletilerin sırasını korur. Bu nedenle, bu yöntem hedef bloklara başka bir ileti göndermeden önce çıktı kuyruğundaki ilk iletinin bir hedef bloğu tarafından kabul edilmesi gerekir.

1. `protected` Bölümde, yöntemi tanımlayın. `propagate_message`

    [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   Yöntem, `propagate_message` sınıfın `priority_buffer` ileti alıcısı veya hedef olarak hareket etmesini sağlar. Bu yöntem, sağlanan kaynak bloğu tarafından sunulan iletiyi alır ve bu iletiyi öncelik sırasına ekler. Yöntem `propagate_message` daha sonra eşzamanlı olarak tüm çıkış iletilerini hedef bloklara gönderir.

   Çalışma zamanı, [eşzamanlılık::asend](reference/concurrency-namespace-functions.md#asend) işlevini veya ileti bloğu diğer ileti bloklarına bağlandığında bu yöntemi çağırır.

1. `protected` Bölümde, yöntemi tanımlayın. `send_message`

    [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   Yöntem `send_message` benzer `propagate_message`. Ancak, çıktı iletilerini eşzamanlı olarak yerine eşzamanlı olarak gönderir.

   Çalışma zamanı, [eşzamanlılık::gönder](reference/concurrency-namespace-functions.md#send) işlevini çağırdığınızda olduğu gibi eşzamanlı gönderme işlemi sırasında bu yöntemi çağırır.

Sınıf, `priority_buffer` birçok ileti bloğu türünde tipik olan yapı oluşturucu aşırı yükler içerir. Bazı kurucu aşırı yükler [eşzamanlılık alır::Zamanlayıcı](../../parallel/concrt/reference/scheduler-class.md) veya [eşzamanlılık::Zamangrubu](../../parallel/concrt/reference/schedulegroup-class.md) nesneleri, ileti bloğunun belirli bir görev zamanlayıcısı tarafından yönetilmesini sağlar. Diğer yapıcı aşırı yükler bir filtre işlevi alır. Filtre işlevleri ileti bloklarının bir iletiyi yüküne göre kabul etmesini veya reddetmesini sağlar. İleti filtreleri hakkında daha fazla bilgi [için, Bkz.](../../parallel/concrt/asynchronous-message-blocks.md) Görev zamanlayıcıları hakkında daha fazla bilgi için [Görev Zamanlayıcısı'na](../../parallel/concrt/task-scheduler-concurrency-runtime.md)bakın.

`priority_buffer` Sınıf iletileri önceliğe ve daha sonra iletilerin alındığı sıraya göre sıraladığı için, bu sınıf iletileri eşzamanlı olarak aldığında, örneğin [eşzamanlılık::asend](reference/concurrency-namespace-functions.md#asend) işlevini veya ileti bloğu diğer ileti bloklarına bağlandığında çok yararlıdır.

[[Üst](#top)]

## <a name="the-complete-example"></a><a name="complete"></a>Tam Örnek

Aşağıdaki örnek, sınıfın tam `priority_buffer` tanımını gösterir.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

Aşağıdaki örnek aynı anda `asend` bir dizi ve [eşzamanlılık gerçekleştirir::bir](reference/concurrency-namespace-functions.md#receive) `priority_buffer` nesne üzerinde işlemleri al.

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

Sınıf `priority_buffer` iletileri önce önceönce, sonra iletileri aldığı sıraya göre sıralar. Bu örnekte, daha fazla sayısal önceliğe sahip iletiler sıranın önüne eklenir.

[[Üst](#top)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve Visual Studio projesine yapıştırın veya `priority_buffer` sınıfın tanımını adlandırılmış `priority_buffer.h` bir dosyaya ve test `priority_buffer.cpp` programını adlandırılmış bir dosyaya yapıştırın ve ardından aşağıdaki komutu Visual Studio Komut İstemi penceresinde çalıştırın.

**cl.exe /EHsc priority_buffer.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Çalışma Zamanı İzlenecek Yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
