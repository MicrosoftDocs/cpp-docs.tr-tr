---
title: 'İzlenecek yol: özel bir ileti bloğu oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa70cf40851815ff92f01405d47015afd2e3e444
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694683"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>İzlenecek Yol: Özel bir İleti Bloğu Oluşturma
Bu belge, gelen iletileri önceliğe göre sıralar özel ileti blok türü oluşturmayı açıklar.  
  
 Yerleşik ileti bloğu türleri işlevsellik aralığını wide sunmasına karşın, kendi ileti blok türü oluşturma ve uygulamanızın gereksinimlerini karşılayacak şekilde özelleştirin. Zaman uyumsuz aracılar kitaplığı tarafından sağlanan yerleşik ileti bloğu türleri açıklaması için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuza başlamadan önce aşağıdaki belgeleri okuyun:  
  
- [Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)  
  
##  <a name="top"></a> Bölümler  
 Bu kılavuz aşağıdaki bölümleri içerir:  
  
- [Özel bir ileti bloğu tasarlama](#design)  
  
- [Sınıf priority_buffer tanımlama](#class)  
  
- [Tam bir örnek](#complete)  
  
##  <a name="design"></a> Özel bir ileti bloğu tasarlama  
 İleti blokları ileti gönderme ve alma işlemi içinde katılın. İletiler gönderen bir ileti bloğu olarak bilinen bir *kaynak blok*. İletileri alan bir ileti bloğu olarak bilinen bir *hedef blok*. Hem ileti alıp gönderen bir ileti bloğu olarak bilinen bir *yayılması blok*. Aracılar Kitaplığı soyut sınıf kullanan [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) kaynak blokları ve soyut sınıf temsil etmek için [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) hedef blokları temsil etmek için. İleti bloğu türleri bu act kaynakları türetin gibi `ISource`; ileti bloğu türleri bu act hedefleri türetin gibi `ITarget`.  
  
 İleti bloğu türünüzü doğrudan türetilemeyeceğini rağmen `ISource` ve `ITarget`, aracılar kitaplığı hataları işleme Örneğin, tüm ileti bloğu türleri için ortak olan işlevlerinin çoğunu gerçekleştirmek üç temel sınıf tanımlar ve ileti blokları, bir eşzamanlılık güvenli şekilde birbirine bağlama. [Concurrency::source_block](../../parallel/concrt/reference/source-block-class.md) sınıfı türer `ISource` ve diğer bloklarına iletileri gönderir. [Concurrency::target_block](../../parallel/concrt/reference/target-block-class.md) sınıfı türer `ITarget` ve diğer bloklarından iletilerini alır. [Concurrency::propagator_block](../../parallel/concrt/reference/propagator-block-class.md) sınıfı türer `ISource` ve `ITarget` ve gönderdiği iletileri diğer blokları ve diğer bloklarından iletileri alır. İleti bloğu davranışını odaklanabilmeniz altyapı ayrıntıları işlemek için bu üç temel sınıfları kullanmanızı öneririz.  
  
 `source_block`, `target_block`, Ve `propagator_block` sınıflardır bağlantıları yönetir ve bağlantıları bir türü, kaynak ve hedef blokları arasındaki ve iletilerin nasıl işleneceği yöneten bir türü üzerinde parametreli şablonları. Bağlantı yönetimi gerçekleştirmek iki tür Aracılar Kitaplığı tanımlar [concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) ve [concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md). `single_link_registry` Sınıfı bir kaynak veya bir hedef bağlantı kurulacak bir ileti bloğu sağlar. `multi_link_registry` Sınıfı bir ileti bloğu birden çok kaynak ya da birden çok hedef bağlanmasını sağlar. Aracılar Kitaplığı ileti Yönetimi gerçekleştiren bir sınıfı tanımlar [concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md). `ordered_message_processor` Sınıfı içinde aldığı bunları sırayla iletileri işlemek ileti blokları sağlar.  
  
 İleti blokları kendi kaynaklarını ve hedefleri nasıl ilişkili olduğunu daha iyi anlamak için aşağıdaki örneği göz önünde bulundurun. Bu örnek bildirimi gösterir [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) sınıfı.  
  
 [!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]  
  
 `transformer` Sınıfı türer `propagator_block`ve bu nedenle hem kaynak bloğu ve bir hedef blok olarak görev yapar. Türden iletileri kabul `_Input` ve türden iletileri gönderir `_Output`. `transformer` Sınıfını belirtir `single_link_registry` herhangi bir hedef bloğu için Bağlantı Yöneticisi olarak ve `multi_link_registry` herhangi bir kaynak bloğu için Bağlantı Yöneticisi olarak. Bu nedenle, bir `transformer` nesnesi olabilir bir hedef ve kaynakları sınırsız sayıda.  
  

 Öğesinden türeyen bir sınıf `source_block` altı yöntemleri uygulamanız gerekir: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets), [accept_message](reference/source-block-class.md#accept_message), [reserve_message](reference/source-block-class.md#reserve_message), [ consume_message](reference/source-block-class.md#consume_message), [release_message](reference/source-block-class.md#release_message), ve [resume_propagation](reference/source-block-class.md#resume_propagation). Öğesinden türeyen bir sınıf `target_block` uygulamalıdır [propagate_message](reference/propagator-block-class.md#propagate_message) yöntemi ve isteğe bağlı olarak uygulayabileceğiniz [send_message](reference/propagator-block-class.md#send_message) yöntemi. Türetme `propagator_block` hem de türetme işlevsel olarak eşdeğerdir `source_block` ve `target_block`.  


  
 `propagate_to_any_targets` Yöntemi zaman uyumsuz veya zaman uyumlu olarak tüm gelen iletileri işlemek ve giden tüm iletileri yayılması için çalışma zamanı tarafından çağrılır. `accept_message` Yöntemi, iletileri kabul etmek için hedef blok tarafından çağrılır. Çoğu gibi blok türleri, ileti `unbounded_buffer`, onu alacağı yalnızca ilk hedefine iletileri göndermek. Bu nedenle, ileti sahipliğini hedef aktarır. Diğer ileti bloğu türleri, aşağıdaki gibi [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), her bir hedef blokları iletileri sunar. Bu nedenle, `overwrite_buffer` her hedeflerine iletinin bir kopyasını oluşturur.  
  
 `reserve_message`, `consume_message`, `release_message`, Ve `resume_propagation` yöntemleri cinsinden ileti ayırma katılmayı ileti blokları sağlar. Hedef engeller çağrısı `reserve_message` bir ileti sunulur ve ileti sonraki kullanımlar için ayrılacak varsa yöntemi. Bir ileti hedef blok ayırır sonra çağırabilirsiniz `consume_message` ileti kullanmak için yöntemi veya `release_message` ayırması iptal etmek için yöntem. İle `accept_message` yöntemi, uygulanması `consume_message` ileti sahipliğini aktarma veya iletinin bir kopyasını döndürür. Hedef blok kullanır veya ayrılmış bir ileti yayımlar sonra runtime çağırır `resume_propagation` yöntemi. Genellikle, bu yöntem sırasındaki sonraki ileti başlayarak ileti yayma devam eder.  
  
 Çalışma zamanı çağrıları `propagate_message` bir ileti başka bir bloğundan geçerli bir zaman uyumsuz olarak aktarması yöntemi. `send_message` Yöntemi benzer `propagate_message`, zaman uyumlu olarak, zaman uyumsuz olarak yerine, ileti hedef blokları gönderir dışında. Varsayılan uygulaması `send_message` gelen tüm iletilerin reddeder. İleti hedef blok ile ilişkili isteğe bağlı filtre işlevi geçemezse çalışma zamanı bu yöntemlerin her ikisi çağırmaz. İleti filtreleri hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 [[Üst](#top)]  
  
##  <a name="class"></a> Sınıf priority_buffer tanımlama  
 `priority_buffer` Sınıftır gelen iletileri önceliğine göre ve iletileri alınan sıraya göre ilk siparişleri özel ileti blok türü. `priority_buffer` Sınıfı benzer [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) iletileri kuyruğunu tutan çünkü sınıf ve ayrıca hem kaynak hem de hedef ileti bloğu olarak davranır ve birden çok kaynağı ve birden çok olabilir çünkü hedefler. Ancak, `unbounded_buffer` tabanları yayma yalnızca içinde aldığı iletileri kendi kaynaklardan sipariş iletisi.  
  
 `priority_buffer` Sınıf türü iletileri alır std::[tanımlama grubu](../../standard-library/tuple-class.md) içeren `PriorityType` ve `Type` öğeleri. `PriorityType` her iletinin önceliğini tutan bir türe başvurur; `Type` iletisinin veri bölümünü başvuruyor. `priority_buffer` Sınıfı türden iletileri gönderir `Type`. `priority_buffer` Sınıfı da iki ileti kuyrukları yönetir: bir [std::priority_queue](../../standard-library/priority-queue-class.md) gelen iletiler için nesne ve bir std::[sıra](../../standard-library/queue-class.md) giden iletiler için nesne. İletileri öncelik sırasına göre sıralama yararlı bir `priority_buffer` nesne birden çok iletileri aynı anda alır veya ne zaman aldığı birden fazla ileti herhangi bir ileti tüketiciler tarafından okumadan önce.  
  
 Yedi yöntemleri yanı sıra bir sınıf, türeyen olduğunu `propagator_block` uygulamalıdır, `priority_buffer` sınıfı ayrıca geçersiz kılmaları `link_target_notification` ve `send_message` yöntemleri. `priority_buffer` Sınıfı ayrıca tanımlayan iki ortak yardımcı yöntemler `enqueue` ve `dequeue`ve bir özel yardımcı yöntemi `propagate_priority_order`.  
  
 Aşağıdaki yordamı uygulamak açıklar `priority_buffer` sınıfı.  
  
#### <a name="to-define-the-prioritybuffer-class"></a>Priority_buffer sınıfını tanımlamak için  
  
1.  C++ üstbilgi dosyası oluşturun ve adlandırın `priority_buffer.h`. Alternatif olarak, projenizin parçası olan mevcut bir üst bilgi dosyasını kullanabilirsiniz.  
  
2.  İçinde `priority_buffer.h`, aşağıdaki kodu ekleyin.  
  
 [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]  
  
3.  İçinde `std` ad alanı, özelleştirmeleri, tanımlamak [std::less](../../standard-library/less-struct.md) ve [std::greater](../../standard-library/greater-struct.md) eşzamanlılık üzerinde hareket::[ileti](../../parallel/concrt/reference/message-class.md) nesneleri.  
  
 [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]  
  
     `priority_buffer` Sınıf depoları `message` nesnelerini bir `priority_queue` nesnesi. Bu tür özelleştirmeleri iletileri kendi önceliğe göre sıralamak öncelikli kuyruğa etkinleştirin. İlk öğesi önceliktir `tuple` nesnesi.  
  
4.  İçinde `concurrencyex` ad alanı, bildirme `priority_buffer` sınıfı.  
  
 [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]  
  
     `priority_buffer` Sınıfı türer `propagator_block`. Bu nedenle, bu hem gönderebilir ve iletileri alabilirsiniz. `priority_buffer` Sınıf türü iletilerini birden çok hedef olabilir `Type`. Türden iletileri gönder birden çok kaynak sağlayabilirsiniz `tuple<PriorityType, Type>`.  
  
5.  İçinde `private` bölümünü `priority_buffer` sınıfında, aşağıdaki üye değişkenleri ekleyin.  
  
 [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]  
  
     `priority_queue` Nesnesi tutar gelen iletileri; `queue` nesnesi giden iletiler tutar. A `priority_buffer` nesne alabilir birden fazla ileti aynı anda; `critical_section` nesne giriş iletileri kuyruğunu erişimi eşitler.  
  
6.  İçinde `private` bölümünde, kopya oluşturucu ve atama işleci tanımlayın. Bu engeller `priority_queue` nesneleri atanabilir engeller.  
  
 [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]  
  
7.  İçinde `public` bölümünde, birçok ileti bloğu türleri için ortaktır oluşturucuları tanımlama. Aynı zamanda yıkıcı tanımlar.  
  
 [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]  
  
8.  İçinde `public` bölümünde, yöntemleri tanımlama `enqueue` ve `dequeue`. Bu yardımcı yöntemler ileti göndermek ve gelen iletileri almak için alternatif bir yol sağlayan bir `priority_buffer` nesnesi.  
  
 [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]  
  
9. İçinde `protected` bölümünde, tanımlamak `propagate_to_any_targets` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]  
  
     `propagate_to_any_targets` Yöntemi çıkış sırasının girdi sırasına önüne altındadır ve çıktı sıradaki tüm iletileri çıkışı yayar ileti aktarır.  
  
10. İçinde `protected` bölümünde, tanımlamak `accept_message` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]  
  
     Hedef blok çağırdığında `accept_message` yöntemi, `priority_buffer` sınıfı kabul ettiği ilk hedef blok ileti sahipliğini aktarır. (Bu davranışını benzer `unbounded_buffer`.)  
  
11. İçinde `protected` bölümünde, tanımlamak `reserve_message` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]  
  
     `priority_buffer` Sınıfı sağlanan ileti tanımlayıcısı sıranın önünü iletisi tanıtıcısı eşleştiğinde bir ileti ayırmak için bir hedef blok izin verir. Diğer bir deyişle, bir hedef ileti varsa ayırabilirsiniz `priority_buffer` nesne henüz bir ek iletisi almadığını ve henüz geçerli bir yayılmadan değil.  
  
12. İçinde `protected` bölümünde, tanımlamak `consume_message` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]  
  
     Hedef blok çağırır `consume_message` ayrılmış ileti sahipliğini aktarmak için.  
  
13. İçinde `protected` bölümünde, tanımlamak `release_message` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]  
  
     Hedef blok çağırır `release_message` bir iletiyi, ayırmasını iptal etmek için.  
  
14. İçinde `protected` bölümünde, tanımlamak `resume_propagation` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]  
  
     Çalışma zamanı çağrıları `resume_propagation` sonra hedef blok kullanır veya ayrılmış bir ileti yayımlar. Bu yöntem çıkış sırasının tüm iletilerinin çıkışı yayar.  
  
15. İçinde `protected` bölümünde, tanımlamak `link_target_notification` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]  
  
     `_M_pReservedFor` Üye değişkeni temel sınıfı tarafından tanımlanan `source_block`. Bu üye değişkeni varsa çıkış sırasının öne iletisi için bir ayırma bulunduran hedef blok için işaret eder. Çalışma zamanı çağrıları `link_target_notification` zaman yeni bir hedef bağlantılı `priority_buffer` nesnesi. Bu yöntem çıkış sırasının hiçbir hedef bir ayırma bulunduran durumunda olan tüm iletileri yayar.  
  
16. İçinde `private` bölümünde, tanımlamak `propagate_priority_order` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]  
  
     Bu yöntem, çıkış sırasının alınan tüm iletileri çıkışı yayar. Hedef blokları birini ileti kabul edene kadar her iletiyi her hedef blok sunulur. `priority_buffer` Sınıfı giden iletiler sırasını korur. Bu yöntem hedef blokları için başka bir ileti sunar önce bu nedenle, çıktı sıradaki ilk iletiyi hedef blok tarafından kabul edilmesi gerekir.  
  
17. İçinde `protected` bölümünde, tanımlamak `propagate_message` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]  
  
     `propagate_message` Yöntemi etkinleştirir `priority_buffer` bir ileti alıcısı olarak davranacak şekilde sınıf veya hedefleyin. Bu yöntem, sağlanan kaynak bloğu tarafından sunulan ve öncelik sıraya ileti ekler iletiyi alır. `propagate_message` Yöntemi ardından zaman uyumsuz olarak gönderir tüm çıktı hedef blokları iletileri.  
  

     Çağırdığınızda çalışma zamanı bu yöntemi çağırır [concurrency::asend](reference/concurrency-namespace-functions.md#asend) işlevi veya ileti bloğu diğer ileti blokları bağlandığında.  

  
18. İçinde `protected` bölümünde, tanımlamak `send_message` yöntemi.  
  
 [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]  
  
     `send_message` Yöntemi benzer `propagate_message`. Ancak çıktı iletileri zaman uyumlu olarak yerine zaman uyumsuz olarak gönderir.  
  

     Çalışma zamanı çağırdığınızda gibi ek olarak, eş zamanlı gönderme işlemi sırasında bu yöntemi çağırır [concurrency::send](reference/concurrency-namespace-functions.md#send) işlevi.  
  
 `priority_buffer` Sınıfı, birçok ileti bloğu türlerinde tipik Oluşturucusu aşırı içerir. Bazı Oluşturucusu overloads Al [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) veya [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) ileti bloğu belirli bir Görev Zamanlayıcı tarafından yönetilmek üzere etkinleştirme nesneleri. Diğer Oluşturucusu aşırı bir filtre işlevi alın. Filtre işlevleri kabul edin veya reddedin yük temel alınarak bir ileti ileti blokları etkinleştirin. İleti filtreleri hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md). Görev zamanlayıcılar hakkında daha fazla bilgi için bkz: [Görev Zamanlayıcı](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 Çünkü `priority_buffer` sınıfı iletileri öncelik sırasına göre sıralar ve çağırdığınızda, iletileri zaman uyumsuz olarak, örneğin, aldığında sonra iletilerin alındığını sıraya göre bu sınıf kullanışlıdır [concurrency::asend](reference/concurrency-namespace-functions.md#asend)işlevi veya ileti bloğu diğer ileti blokları bağlandığında.  
  
 [[Üst](#top)]  
  
##  <a name="complete"></a> Tam bir örnek  
 Aşağıdaki örnek eksiksiz tanımını gösterir `priority_buffer` sınıfı.  
  
 [!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]  
  
 Aşağıdaki örnek eşzamanlı olarak bir dizi gerçekleştirir `asend` ve [concurrency::receive](reference/concurrency-namespace-functions.md#receive) işlemleri bir `priority_buffer` nesnesi.  

  
 [!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir.  
  
```Output  
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36  
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24  
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12  
```  
  
 `priority_buffer` Öncelik ve sonra da hangi iletileri aldığı sıraya göre sınıfı iletileri ilk siparişleri. Bu örnekte, iletilerin büyük sayısal önceliğe sahip sıranın önünü eklenir.  
  
 [[Üst](#top)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya tanımını yapıştırın `priority_buffer` adlı bir dosyayı sınıfında `priority_buffer.h` ve adlı bir dosyayı test programında `priority_buffer.cpp` ve ardından Visual Studio'da aşağıdaki komutu çalıştırın Komut İstemi penceresi.  
  
 **cl.exe /EHsc priority_buffer.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı izlenecek yollar](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
