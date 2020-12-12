---
description: 'Daha fazla bilgi edinin: zaman uyumsuz aracılar kitaplığındaki En Iyi uygulamalar'
title: Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler
ms.date: 11/04/2016
helpviewer_keywords:
- best practices, Asynchronous Agents Library
- Asynchronous Agents Library, best practices
- Asynchronous Agents Library, practices to avoid
- practices to avoid, Asynchronous Agents Library
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
ms.openlocfilehash: 5468d5c7a0ddb3a0a87d0675dfb3f19385ccc8b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205726"
---
# <a name="best-practices-in-the-asynchronous-agents-library"></a>Zaman Uyumsuz Aracılar Kitaplığı'ndaki En İyi Yöntemler

Bu belgede, zaman uyumsuz aracılar Kitaplığı 'nın nasıl etkili bir şekilde kullanılacağı açıklanmaktadır. Aracılar Kitaplığı, oyuncu tabanlı bir programlama modeli ve kaba veri akışı ve ardışık düzen görevleri için işlem içi ileti geçişini yükseltir.

Aracılar Kitaplığı hakkında daha fazla bilgi için bkz. [zaman uyumsuz aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md).

## <a name="sections"></a><a name="top"></a> Başlıklı

Bu belgede aşağıdaki bölümler yer alır:

- [Durumu yalıtmak için aracıları kullanma](#isolation)

- [Bir veri kanalındaki Ileti sayısını sınırlamak için bir daraltma mekanizması kullanın](#throttling)

- [Veri ardışık düzeninde Fine-Grained Iş gerçekleştirme](#fine-grained)

- [Büyük Ileti yüklerini değere göre geçirmeyin](#large-payloads)

- [Sahiplik tanımsız olduğunda bir veri Ağında shared_ptr kullanın](#ownership)

## <a name="use-agents-to-isolate-state"></a><a name="isolation"></a> Durumu yalıtmak için aracıları kullanma

Aracılar Kitaplığı, yalıtılmış bileşenleri zaman uyumsuz bir ileti geçirme mekanizması aracılığıyla bağlamanıza izin vererek paylaşılan durum için alternatifler sağlar. Zaman uyumsuz aracılar, iç durumlarını diğer bileşenlerden yalıtmak için en etkilidir. Durumu yalıtarak, birden çok bileşen genellikle paylaşılan verilere göre hareket etmez. Durum yalıtımı, paylaşılan bellek çekişmesini azalttığından uygulamanızın ölçeğini değiştirebilir. Durum yalıtımı, Ayrıca, bileşenlerin paylaşılan verilere erişimi eşitlemesine sahip olmadığı için kilitlenme ve yarış durumlarının olasılığını azaltır.

Genellikle aracı **`private`** sınıfının veya bölümlerinde veri üyelerini tutarak **`protected`** ve durum değişikliklerini iletmek için ileti arabelleklerini kullanarak bir aracıdaki durumu yalıtabilirsiniz. Aşağıdaki örnek, `basic_agent` [concurrency:: Agent](../../parallel/concrt/reference/agent-class.md)öğesinden türetilen sınıfı gösterir. `basic_agent`Sınıfı, dış bileşenlerle iletişim kurmak için iki ileti arabelleği kullanır. Bir ileti arabelleği gelen iletileri barındırır; diğer ileti arabelleği giden iletileri tutar.

[!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_1.cpp)]

Aracıları tanımlama ve kullanma hakkında tüm örnekler için bkz. [Izlenecek yol: Agent-Based uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) ve [Izlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md).

[[Üst](#top)]

## <a name="use-a-throttling-mechanism-to-limit-the-number-of-messages-in-a-data-pipeline"></a><a name="throttling"></a> Bir veri kanalındaki Ileti sayısını sınırlamak için bir daraltma mekanizması kullanın

[Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md)gibi birçok ileti arabelleği türü sınırsız sayıda ileti tutabilir. Bir ileti üreticisi, tüketiciden bu iletileri işleyebileceğinden daha hızlı bir şekilde bir veri ardışık düzenine ileti gönderdiğinde, uygulama düşük bellekli veya bellek dışı bir durum girebilir. Bir veri ardışık düzeninde eşzamanlı olarak etkin olan ileti sayısını sınırlamak için bir bir azaltma mekanizması (örneğin, bir semafor) kullanabilirsiniz.

Aşağıdaki temel örnek, bir veri işlem hattındaki ileti sayısını sınırlamak için bir semaforun nasıl kullanılacağını göstermektedir. Veri ardışık düzeni, en az 100 milisaniye alan bir işlemin benzetimini yapmak için [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) işlevini kullanır. Gönderen, tüketicinin bu iletileri işleyebileceğinden daha hızlı iletiler ürettiğinden, bu örnek, `semaphore` Uygulamanın etkin ileti sayısını sınırlamasına olanak tanımak için sınıfını tanımlar.

[!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_2.cpp)]

`semaphore`Nesnesi, işlem hattını aynı anda en fazla iki iletiyi işleyecek şekilde sınırlandırır.

Bu örnekteki üretici, tüketiciye görece birkaç ileti gönderir. Bu nedenle, bu örnekte olası düşük bellek veya bellek yetersiz durumu gösterilmektedir. Ancak, bir veri işlem hattı görece yüksek sayıda ileti içerdiğinde bu mekanizma yararlı olur.

Bu örnekte kullanılan semafor sınıfının nasıl oluşturulacağı hakkında daha fazla bilgi için bkz. [nasıl yapılır: bağlam sınıfını kullanarak bir Cooperative semaforu uygulama](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md).

[[Üst](#top)]

## <a name="do-not-perform-fine-grained-work-in-a-data-pipeline"></a><a name="fine-grained"></a> Veri ardışık düzeninde Fine-Grained Iş gerçekleştirme

Aracılar Kitaplığı, bir veri işlem hattı tarafından gerçekleştirilen iş oldukça kaba oldukça yararlıdır. Örneğin, bir uygulama bileşeni bir dosya veya ağ bağlantısından verileri okuyabilir ve bazen bu verileri başka bir bileşene gönderebilir. Aracılar kitaplığının iletileri yaymak için kullandığı protokol, ileti geçirme mekanizmasının [paralel Desenler kitaplığı](../../parallel/concrt/parallel-patterns-library-ppl.md) (ppl) tarafından sunulan görev paralel yapılarına daha fazla yüke neden olur. Bu nedenle, bir veri işlem hattı tarafından gerçekleştirilen çalışmanın bu ek yükü kaydırmak için yeterince uzun olduğundan emin olun.

Bir veri işlem hattı, görevleri kaba olduğunda en etkili olsa da, veri işlem hattının her bir aşaması, daha ayrıntılı iş gerçekleştirmek için görev grupları ve paralel algoritmalar gibi PPL yapılarını kullanabilir. Her bir işleme aşamasında hassas paralellik kullanan kaba bir veri ağı örneği için bkz. [Izlenecek yol: Image-Processing ağ oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

[[Üst](#top)]

## <a name="do-not-pass-large-message-payloads-by-value"></a><a name="large-payloads"></a> Büyük Ileti yüklerini değere göre geçirmeyin

Bazı durumlarda, çalışma zamanı bir ileti arabelleğinden başka bir ileti arabelleğine geçen her iletinin bir kopyasını oluşturur. Örneğin, [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) sınıfı, her birinin hedeflediği her bir iletinin bir kopyasını sunar. Çalışma zamanı ayrıca bir ileti arabelleğinden ileti yazmak ve iletileri okumak için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) ve [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) gibi ileti geçirme işlevlerini kullandığınızda ileti verilerinin bir kopyasını oluşturur. Bu mekanizma, paylaşılan verilere eş zamanlı yazma riskini ortadan kaldırmaya yardımcı olmakla birlikte, ileti yükü nispeten büyükse zayıf bellek performansına neden olabilir.

Büyük bir yüküne sahip iletileri geçirdiğinizde bellek performansını artırmak için işaretçiler veya başvurular kullanabilirsiniz. Aşağıdaki örnek, aynı ileti türüne işaretçiler geçirmek için büyük iletileri değere göre geçirmeyi karşılaştırır. Örnek iki aracı türü tanımlar `producer` ve `consumer` nesneler üzerinde işlem görür `message_data` . Örnek, üretici tarafından tüketiciye bir kaç nesne göndermek için gereken süreyi, `message_data` üretici aracısının tüketicilere nesnelere çeşitli işaretçiler gönderebilmesi için gereken zamana göre karşılaştırır `message_data` .

[!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_3.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

```Output
Using message_data...
took 437ms.
Using message_data*...
took 47ms.
```

İşaretçiler kullanan sürüm, çalışma zamanının `message_data` üretici tarafından tüketiciye aktardığı her nesnenin tam bir kopyasını oluşturmak için gereken bir tam kopyasını ortadan kaldırdığı için daha iyi gerçekleştirir.

[[Üst](#top)]

## <a name="use-shared_ptr-in-a-data-network-when-ownership-is-undefined"></a><a name="ownership"></a> Sahiplik tanımsız olduğunda bir veri Ağında shared_ptr kullanın

İleti geçirme işlem hattı veya ağ aracılığıyla işaretçiye göre ileti gönderdiğinizde, genellikle ağın önündeki her bir ileti için belleği ayırır ve ağın sonunda bu belleği boşaltın. Bu mekanizma sıklıkla iyi çalışsa da, zor olan veya kullanılması mümkün olmayan durumlar vardır. Örneğin, veri ağının birden çok bitiş düğümü içerdiği durumu göz önünde bulundurun. Bu durumda, iletilerin belleği boşaltmak için açık bir konum yoktur.

Bu sorunu çözmek için, örneğin, [std:: shared_ptr](../../standard-library/shared-ptr-class.md), bir işaretçinin birden çok bileşene ait olmasını sağlayan bir mekanizma kullanabilirsiniz. `shared_ptr`Bir kaynağa sahip olan son nesne yok edildiğinde, kaynak de serbest bırakılır.

Aşağıdaki örnek, `shared_ptr` birden çok ileti arabelleği arasında işaretçi değerlerinin paylaşılması için nasıl kullanılacağını gösterir. Örnek, [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) nesnesini üç [concurrency:: Call](../../parallel/concrt/reference/call-class.md) nesnesine bağlar. `overwrite_buffer`Sınıfı, hedeflerine her birine iletiler sunar. Veri ağının sonundaki verilerin birden fazla sahibi olduğundan, bu örnek, `shared_ptr` her bir `call` nesnenin iletilerin sahipliğini paylaşmasını sağlamak için kullanır.

[!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_4.cpp)]

Bu örnek aşağıdaki örnek çıktıyı üretir:

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

## <a name="see-also"></a>Ayrıca bkz.

[En Iyi Eşzamanlılık Çalışma Zamanı uygulamalar](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[İzlenecek yol: Agent-Based uygulama oluşturma](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br/>
[İzlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[İzlenecek yol: Image-Processing ağ oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Paralel Desenler kitaplığındaki en iyi uygulamalar](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[Eşzamanlılık Çalışma Zamanı genel En Iyi Yöntemler](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)
