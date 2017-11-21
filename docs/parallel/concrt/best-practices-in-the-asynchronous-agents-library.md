---
title: "En iyi uygulamalar zaman uyumsuz aracılar Kitaplığı'nda | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- best practices, Asynchronous Agents Library
- Asynchronous Agents Library, best practices
- Asynchronous Agents Library, practices to avoid
- practices to avoid, Asynchronous Agents Library
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 15e4b6aca6d9f00806a37a04ffb7c93008125b6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="best-practices-in-the-asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler
Bu belge, zaman uyumsuz aracılar kitaplığı etkili kullanımını sağlamak açıklar. Aracılar Kitaplığı aktör tabanlı programlama modeli ve görevleri ardışık düzen ve parçalı veri akışı için geçirme işlemi iletisi yükseltir.  
  
 Aracılar Kitaplığı hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).  
  
##  <a name="top"></a>Bölümler  
 Bu belgede aşağıdaki bölümler yer alır:  
  
- [Ayırma durumu için aracıları kullanma](#isolation)  
  
- [Veri ardışık düzeninde ileti sayısını sınırlamak için azaltma mekanizmasını kullanın](#throttling)  
  
- [Hassas iş veri ardışık düzeninde gerçekleştirme](#fine-grained)  
  
- [Büyük ileti yükü değer geçmeyin](#large-payloads)  
  
- [Shared_ptr bir veri ağ zaman sahipliği olduğu tanımsız içinde kullanma](#ownership)  
  
##  <a name="isolation"></a>Ayırma durumu için aracıları kullanma  
 Aracılar Kitaplığı, zaman uyumsuz bir ileti geçirme mekanizma aracılığıyla yalıtılmış bileşenleri bağlanmanıza izin vererek paylaşılan durum alternatifleri sağlar. İç durumlarına diğer bileşenler'den ayrı tuttuğunuzda zaman uyumsuz aracılar en etkili. Durum yalıtarak birden çok bileşen genellikle paylaşılan veri üzerinde herhangi bir işlem yapmayacak. Durum yalıtım paylaşılan bellek üzerinde Çekişme azalttığı ölçeklendirmek uygulamanızı etkinleştirebilirsiniz. Bileşenleri Paylaşılan verilere erişimi eşitlemeye sahip olmadığınızdan durum yalıtım ayrıca kilitlenme ve yarış koşullar olasılığını azaltır.  
  
 Genellikle veri üyeleri tutarak bir aracı durumda yalıtmak `private` veya `protected` Aracısı sınıfının ve durum değişikliklerini iletişim kurmak için ileti arabelleklerinin kullanarak bölümler. Aşağıdaki örnekte gösterildiği `basic_agent` türeyen sınıf [concurrency::agent](../../parallel/concrt/reference/agent-class.md). `basic_agent` Sınıfı dış bileşenleriyle iletişim kurmak için iki ileti arabelleklerinin kullanır. Bir ileti arabelleği gelen iletileri tutan; bir ileti arabelleği giden iletiler tutar.  
  
 [!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_1.cpp)]  
  
 Tanımlama ve aracıları kullanma konusunda tam örnekler için bkz: [izlenecek yol: aracı temelli uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) ve [izlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md).  
  
 [[Üst](#top)]  
  
##  <a name="throttling"></a>Veri ardışık düzeninde ileti sayısını sınırlamak için azaltma mekanizmasını kullanın  
 Birçok ileti arabelleği türleri gibi [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), iletileri sınırsız sayıda tutabilir. İleti üreticisi iletileri için veri ardışık tüketici bu iletiler işleyebileceğinden daha hızlı gönderdiğinde, uygulama düşük bellek veya bellek yetersiz durumunu girebilirsiniz. Örneğin, bir semafor azaltma bir mekanizma veri ardışık düzeninde aynı anda etkin olan iletilerin sayısını sınırlamak için kullanabilirsiniz.  
  
 Aşağıdaki temel örnek semafor veri ardışık düzeninde ileti sayısını sınırlamak için nasıl kullanılacağını gösterir. Veri kanalı kullanır [concurrency::wait](reference/concurrency-namespace-functions.md#wait) en az 100 milisaniyede alan bir işlem benzetimini yapmak için işlevi. Gönderenin iletileri tüketici bu iletileri işleyebileceğinden daha hızlı oluşturduğundan, bu örnek tanımlar `semaphore` etkin ileti sayısını sınırlamak uygulama etkinleştirmek için sınıf.  
  
 [!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_2.cpp)]  
  
 `semaphore` Nesnesi aynı anda en fazla iki iletileri işlemek için ardışık düzen sınırlar.  
  
 Bu örnekte üretici tüketiciye nispeten az iletileri gönderir. Bu nedenle, bu örnek bir olası düşük bellek veya bellek yetersiz koşul gösterilmemiştir. Ancak, veri ardışık iletilerin görece yüksek sayıda içerdiğinde bu düzenek yararlıdır.  
  
 Bu örnekte kullanılan semafor sınıfı oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Cooperative semafor uygulamak için bağlam sınıfını kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).  
  
 [[Üst](#top)]  
  
##  <a name="fine-grained"></a>Hassas iş veri ardışık düzeninde gerçekleştirme  
 Veri ardışık düzen tarafından gerçekleştirilen işi oldukça parçalı Aracılar Kitaplığı en yararlı olur. Örneğin, bir uygulama bileşeni bir dosya veya bir ağ bağlantısı veri okumak ve bazen bu verileri başka bir bileşen Gönder. Aracılar Kitaplığı iletilerini dağıtmak için kullandığı protokolü tarafından sağlanan görev paralel yapıları'den daha çok yüke sahip ileti geçirme mekanizması neden [paralel Desen kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Bu nedenle, bir veri ardışık düzen tarafından gerçekleştirilen iş bu yükünü dengelemek yeterince uzun olduğundan emin olun.  
  
 Görevleri parçalı olduğunda bir veri ardışık en etkili olsa da, her veri ardışık düzen aşaması PPL yapıları görev grupları ve paralel algoritmalar gibi daha hassas iş gerçekleştirmek için kullanabilirsiniz. Her işleme aşamada hassas paralellik kullanan parçalı verileri ağ bir örnek için bkz: [izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 [[Üst](#top)]  
  
##  <a name="large-payloads"></a>Büyük ileti yükü değer geçmeyin  

 Bazı durumlarda, çalışma zamanı başka bir ileti arabelleğe bir ileti arabelleğinden geçirmeden her iletinin bir kopyasını oluşturur. Örneğin, [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı her hedeflerine aldığı her iletinin bir kopyasını sunar. İleti geçirme işlevleri gibi kullandığınızda çalışma zamanı ileti verilerin bir kopyasını da oluşturur. [concurrency::send](reference/concurrency-namespace-functions.md#send) ve [concurrency::receive](reference/concurrency-namespace-functions.md#receive) iletileri yazmak ve bir iletiden iletileri okumak için arabellek. Bu mekanizma eşzamanlı olarak paylaşılan veri yazma riski ortadan kaldırmanıza yardımcı olmakla birlikte, ileti yükü nispeten daha büyük olduğunda zayıf bellek performansı yol açabilir.  
  
 İşaretçileri kullanabilir veya iletileri geçirdiğinizde bellek performansını artırmak için büyük bir yük başvurmuş. Aşağıdaki örnek, aynı ileti türü işaretçileri geçirme için değere göre geçirme büyük iletileri karşılaştırır. Bu örnek iki aracı türlerini tanımlar `producer` ve `consumer`, üzerinde hareket `message_data` nesneleri. Örnek üretici birkaç göndermek gereken süreyi karşılaştırır `message_data` birkaç işaretçiler göndermek üretici aracısı için gereken süreyi tüketiciye nesnelere `message_data` tüketici nesnelere.  
  
 [!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_3.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
Using message_data...  
took 437ms.  
Using message_data*...  
took 47ms.  
```  
  
 Tam bir kopyasını oluşturmak çalışma zamanı gereksinimini attığından işaretçileri kullanan sürüm daha iyi gerçekleştirir her `message_data` tüketiciye üreticiden geçirir nesnesi.  
  
 [[Üst](#top)]  
  
##  <a name="ownership"></a>Shared_ptr bir veri ağ zaman sahipliği olduğu tanımsız içinde kullanma  
 Bir ileti geçirme ardışık düzen veya ağ üzerinden işaretçisi ileti gönderirken genellikle ağ ön her ileti için bellek tahsis ve ağ ucunda belleğin boş. Bu mekanizma sık iyi çalışmasına rağmen zor veya kullanmak mümkün olduğu durumlar vardır. Örneğin, veri ağı birden çok uç düğümleri içeren bir durum düşünün. Bu durumda, iletiler için belleği boşaltmak için açık konum yok.  
  
 Bu sorunu çözmek için bir mekanizma, örneğin, kullanabilirsiniz [std::shared_ptr](../../standard-library/shared-ptr-class.md), birden çok bileşenleri tarafından sahibi bir işaretçi sağlar. Zaman en son `shared_ptr` bir kaynağın sahibi nesne yok, kaynak de serbest bırakılır.  
  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `shared_ptr` işaretçi değerler birden çok ileti arabelleklerinin arasında paylaşmak için. Örnek bağlayan bir [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) üç nesnesine [concurrency::call](../../parallel/concrt/reference/call-class.md) nesneleri. `overwrite_buffer` Sınıfı her hedeflerine iletileri sunar. Veri ağ ucunda verilerin birden çok sahipleri olduğundan, bu örnekte `shared_ptr` her etkinleştirmek için `call` iletileri sahipliğini paylaşmak için nesne.  
  
 [!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_4.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir:  
  
```Output  
Creating resource 42...  
receiver1: received resource 42  
Creating resource 64...  
receiver2: received resource 42  
receiver1: received resource 64  
Destroying resource 42...  
receiver2: received resource 64  
Destroying resource 64...  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Çalışma zamanı en iyi uygulamalar](../../parallel/concrt/concurrency-runtime-best-practices.md)   
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [İzlenecek yol: aracı temelli uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)   
 [İzlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [İzlenecek yol: bir görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Paralel desen Kitaplığı'ndaki en iyi yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)   
 [Eşzamanlılık Çalışma zamanındaki genel en iyi yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

