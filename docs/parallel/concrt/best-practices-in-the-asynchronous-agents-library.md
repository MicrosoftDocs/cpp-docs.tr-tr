---
title: En iyi uygulamalar zaman uyumsuz aracılar Kitaplığı'ndaki | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- best practices, Asynchronous Agents Library
- Asynchronous Agents Library, best practices
- Asynchronous Agents Library, practices to avoid
- practices to avoid, Asynchronous Agents Library
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e70b4004b24b04470e1fff280869887bbba74cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412749"
---
# <a name="best-practices-in-the-asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler

Bu belge, zaman uyumsuz aracılar kitaplığı etkili kullanımını sağlamak açıklar. Agents kitaplığı, bir aktör tabanlı programlama modeli ve işlem içi ileti geçirme için parçalı veri akışı ve ardışık düzen oluşturma görevleri yükseltir.

Agents Kitaplığı hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).

##  <a name="top"></a> Bölümleri

Bu belgede aşağıdaki bölümler yer alır:

- [Durumu ayırmak için aracılar kullanma](#isolation)

- [Veri ardışık düzeninde iletilerin sayısını sınırlamak için azaltmak için sınırlama mekanizması kullanma](#throttling)

- [Bir veri ardışık düzeninde ayrıntılı işler gerçekleştirmeyin](#fine-grained)

- [Büyük ileti yüklerini değere göre geçirmeyin](#large-payloads)

- [Shared_ptr bir veri ağ sahiplik tanımlanmadığında içinde kullanın](#ownership)

##  <a name="isolation"></a> Durumu ayırmak için aracılar kullanma

Agents kitaplığı, zaman uyumsuz bir ileti geçirme mekanizma aracılığıyla yalıtılmış bileşenleri bağlanmanıza izin vererek paylaşılan durum alternatifleri sağlar. Bunlar iç durumlarına diğer bileşenlerden ayırmak zaman zaman uyumsuz aracılar en etkili olur. Durum yalıtarak birden çok bileşen genellikle paylaşılan veriler üzerinde bir işlem yapmayacak. Uygulamanız paylaşılan bellek çekişmesini azaltır çünkü ölçeklendirmek durum yalıtım etkinleştirebilirsiniz. Paylaşılan verilere erişimi eşitleme bileşenleri olmadığı için durum yalıtım ayrıca kilitlenme ve yarış koşulları olasılığını azaltır.

Genellikle veri üyelerinde basılı tutarak bir aracı durumda yalıtmak `private` veya `protected` aracı sınıf ve durum değişikliklerini iletişim kurmak için mesaj arabellekleri kullanarak bölümler. Aşağıdaki örnekte gösterildiği `basic_agent` türetilen sınıf [concurrency::agent](../../parallel/concrt/reference/agent-class.md). `basic_agent` Sınıfı iki ileti arabelleklerinin dış bileşenler ile iletişim kurmak için kullanır. Bir ileti arabelleği gelen iletileri tutar; diğer ileti arabelleği giden iletileri tutar.

[!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_1.cpp)]

Tanımlamak ve aracıları kullanma hakkında tam örnekler için bkz. [izlenecek yol: aracı temelli uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) ve [izlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md).

[[Üst](#top)]

##  <a name="throttling"></a> Veri ardışık düzeninde iletilerin sayısını sınırlamak için azaltmak için sınırlama mekanizması kullanma

Çok sayıda ileti arabelleği türü gibi [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), sınırsız sayıda ileti içerebilir. Tüketici bu iletiler işleyebileceğinden daha hızlı bir veri işlem hattı için bir mesajın üreticisi ileti gönderen uygulama düşük bellek veya bellek yetersiz durumuna geçilmesidir. Semafor, örneğin, bir azaltma mekanizması, bir veri işlem hattında aynı anda etkin olan iletilerin sayısını sınırlamak için kullanabilirsiniz.

Aşağıdaki temel örnek, semafor veri ardışık düzeninde iletilerin sayısını sınırlamak için nasıl kullanılacağını gösterir. Veri işlem hattı kullandığı [concurrency::wait](reference/concurrency-namespace-functions.md#wait) en az 100 milisaniye işleminin benzetimini yapmak için işlevi. İletileri gönderen üretir, bu iletileri bir tüketici işleyebileceğinden daha hızlı olduğundan, bu örnek tanımlar `semaphore` sınıfı etkin ileti sayısını sınırlamak uygulamayı etkinleştirin.

[!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_2.cpp)]

`semaphore` Nesnesi aynı anda en fazla iki iletileri işlemek üzere işlem hattı sınırlar.

Bu örnekte üretici, tüketici nispeten daha az sayıda iletileri gönderir. Bu nedenle, bu örnekte, olası bir düşük bellek veya bellek yetersiz koşulu gösterilmemiştir. Ancak, bu mekanizma veri işlem hattı görece yüksek sayıda ileti içerdiğinde yararlıdır.

Bu örnekte kullanılan semafor sınıfı oluşturma hakkında daha fazla bilgi için bkz. [nasıl yapılır: bağlam sınıfını Guyana semafor uygulamak için kullanma](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).

[[Üst](#top)]

##  <a name="fine-grained"></a> Bir veri ardışık düzeninde ayrıntılı işler gerçekleştirmeyin

Agents kitaplığı, bir veri işlem hattı tarafından gerçekleştirilen işi oldukça parçalı en yararlı olur. Örneğin, bir uygulama bileşeni bir dosya ya da bir ağ bağlantısı verileri okumak ve bazen bu verileri başka bir bileşene gönderin. Aracılar Kitaplığı iletilerini dağıtmak için kullandığı protokolü tarafından sağlanan görev paralel yapılar değerinden daha fazla ek yük ileti geçirme mekanizması neden [paralel desenler Kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). Bu nedenle, bir veri işlem hattı tarafından gerçekleştirilen iş bu yükü dengelemek yeterince uzun olduğundan emin olun.

Görevleri parçalı olduğunda bir veri işlem hattı en etkili olsa da, veri işlem hattının her aşama daha hassas iş gerçekleştirmek için görev grupları ve paralel algoritmalar gibi PPL yapıları kullanabilirsiniz. Her işleme aşamasında hassas paralellik kullanan bir parçalı verileri ağ bir örnek için bkz [izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Üst](#top)]

##  <a name="large-payloads"></a> Büyük ileti yüklerini değere göre geçirmeyin

Bazı durumlarda, çalışma zamanı başka bir ileti arabelleği için bir ileti arabellek geçirir her iletinin bir kopyasını oluşturur. Örneğin, [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı hedeflerinin her biri için aldığı her iletinin bir kopyasını sunar. Çalışma zamanı, ileti geçirme işlevleri gibi kullandığınızda da ileti verilerin bir kopyasını oluşturur. [concurrency::send](reference/concurrency-namespace-functions.md#send) ve [concurrency::receive](reference/concurrency-namespace-functions.md#receive) nasıl yazılacağını ve iletiden iletileri okumak için arabellek. Bu mekanizma, eşzamanlı olarak Paylaşılan verilere yazma karşılaşma yardımcı olmakla birlikte, ileti yükü görece büyük olduğunda düşük bellek performansı neden olabilir.

İşaretçileri kullanabilir veya büyük bir yükü iletileri geçirdiğinizde bellek performansını artırmak için başvuruya sahip. Aşağıdaki örnek geçirme büyük iletiler aynı ileti türüne işaretçiler geçirme için değere göre karşılaştırır. Örnek, iki aracı türleri tanımlar `producer` ve `consumer`, ve `message_data` nesneleri. Örnek üretici birkaç göndermek gerekli zamanı karşılaştırır `message_data` üretici aracının birkaç işaretçileri göndermek gerekli olan zamanı tüketiciye nesnelere `message_data` tüketici nesneleri.

[!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_3.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

```Output
Using message_data...
took 437ms.
Using message_data*...
took 47ms.
```

Çalışma zamanının tam bir kopyasını oluşturma gereksinimini ortadan kaldırdığından işaretçileri kullanan sürümü daha iyi sonuç verdiğini her `message_data` nesnesini tüketiciye üreticiden geçirir.

[[Üst](#top)]

##  <a name="ownership"></a> Shared_ptr bir veri ağ sahiplik tanımlanmadığında içinde kullanın

Bir ileti geçirme ardışık düzen veya ağda işaretçiyle tarafından iletileri gönderdiğinizde, genellikle ağ önündeki her ileti için bellek ayrılamadı ve sonunda, ağ, bellek. Bu mekanizma sık iyi çalışır, ancak zor veya bunu kullanmak mümkün olduğu durumlar vardır. Örneğin, veri ağı birden çok uç düğümleri içeren bir durum düşünün. Bu durumda, iletileri için belleği boşaltmak için açık konum yoktur.

Bu sorunu çözmek için bir mekanizma, örneğin, kullanabileceğiniz [std::shared_ptr](../../standard-library/shared-ptr-class.md), birden çok bileşen tarafından ait olduğu bir işaretçi sağlar. Zaman en son `shared_ptr` bir kaynağa sahip nesnesi yok edildiğinde, kaynak da serbest bırakılır.

Aşağıdaki örnek nasıl kullanılacağını gösterir `shared_ptr` işaretçi değerleri arasında birden çok ileti arabelleklerinin paylaşmak için. Örnek bağlayan bir [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) üç nesne [concurrency::call](../../parallel/concrt/reference/call-class.md) nesneleri. `overwrite_buffer` Sınıfı iletileri hedeflerinin her biri için sunar. Birden fazla sahibe verilerin sonunda, veri ağı olduğundan, bu örnekte `shared_ptr` her etkinleştirmek için `call` iletileri sahipliğini paylaşmak için nesne.

[!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_4.cpp)]

Bu örnek, örnek aşağıdaki çıktıyı üretir:

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

[Eşzamanlılık Çalışma Zamanı En İyi Yöntemleri](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[İzlenecek Yol: Aracı Temelli Uygulama Oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br/>
[İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Paralel Desen Kitaplığı'ndaki En İyi Yöntemler](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[Eşzamanlılık Çalışma Zamanındaki Genel En İyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)

