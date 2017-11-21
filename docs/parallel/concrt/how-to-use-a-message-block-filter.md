---
title: "Nasıl yapılır: ileti bloğu filtresini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 48649931d20d344e724bd0d3ae7c64a43caa9549
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-a-message-block-filter"></a>Nasıl yapılır: İleti Bloğu Filtresini Kullanma
Bu belge, kabul etme veya reddetme ileti yükünü temel alınarak bir ileti için bir zaman uyumsuz ileti bloğu etkinleştirmek için bir filtre işlevi kullanmak gösterilmiştir.  
  
 Oluştururken bir ileti bloğu nesne gibi bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::call](../../parallel/concrt/reference/call-class.md), veya bir [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md), bir sağlayabilir*filtre işlevi* ileti bloğu kabul ediyor veya bir ileti reddeder olup olmadığını belirler. Filter işlevi bir ileti bloğu yalnızca belirli değerlerin aldığını güvence altına almak için kullanışlı bir yoludur.  
  
 Bunlar ileti blokları forma bağlanmanıza imkan sağlamak için filtre işlevleri önemli *veri akışı ağları*. Bir veri akışı ağında ileti blokları belirli ölçütlere uyan iletileri işleyerek veri akışını denetler. Bu veri akışını denetim yapıları koşullu deyimler, döngüler, gibi kullanarak burada düzenlenen akış denetimi modeli karşılaştırma vb. kullanın.  
  
 Bu belgede bir ileti filtresi kullanımıyla ilgili temel bir örnek sağlar. İleti blokları bağlanmak için ileti filtreleri ve veri akışı modelini kullanan ek örnekler için bkz: [izlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) ve [izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md) .  
  
## <a name="example"></a>Örnek  
 Aşağıdaki işlevi göz önünde bulundurun `count_primes`, gelen iletileri Filtrele olmayan bir ileti bloğu'nın temel kullanımını gösterir. İleti bloğu asal sayılar ekler bir [std::vector](../../standard-library/vector-class.md) nesnesi. `count_primes` İşlevi birkaç numaralarını ileti bloğu gönderir, ileti bloğundan çıkış değerleri alır ve konsola asal bu sayılar yazdırır.  
  
 [!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]  
  
 `transformer` Nesnesini tüm giriş değerlerini işler; ancak, asal olan değerleri gerektirir. Uygulama iletiyi gönderenin yalnızca asal sayılar gönderir böylece yazılmış olsa da, ileti alıcısı gereksinimlerini her zaman bilinen olamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki işlevi `count_primes_filter`, aynı görevi gerçekleştirir `count_primes` işlevi. Ancak, `transformer` nesne bu sürümde asal olan değerleri kabul etmek için bir filtre işlevi kullanır. Bir eylem gerçekleştiren işlevi yalnızca asal sayılar alır; Bu nedenle, çağrılacak yok `is_prime` işlevi.  
  
 Çünkü `transformer` nesnesini alır yalnızca asal sayılar `transformer` nesnenin kendisini asal sayılar basılı tutun. Diğer bir deyişle, `transformer` nesne bu örnekte asal sayılar eklemek için gerekli değildir `vector` nesnesi.  
  
 [!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]  
  
 `transformer` Nesnesini şimdi asal olan değerleri işler. Önceki örnekte, `transformer` nesnesini tüm iletileri işler. Bu nedenle, önceki örnekte, gönderdiği iletileri aynı sayıda alması gerekir. Bu örnek sonucu kullanır [concurrency::send](reference/concurrency-namespace-functions.md#send) almak için kaç tane iletileri belirlemek için işlevi `transformer` nesnesi. `send` İşlev döndürür `true` ileti arabelleği iletiyi ne zaman kabul eder ve `false` zaman ileti arabelleği ileti reddeder. Bu nedenle, ileti arabelleği ileti kabul sayısı asal sayılar sayısı ile eşleşir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, tam bir örnek gösterilir. Örnek her ikisi de çağırır `count_primes` işlevi ve `count_primes_filter` işlevi.  
  
 [!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `primes-filter.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc primes-filter.cpp**  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Filter işlevi lambda işlevi, bir işlev işaretçisi veya işlev nesnesi olabilir. Her filtre işlevi aşağıdaki biçimlerden birini alır:  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 Gereksiz verilerin kopyalanmasını ortadan kaldırmak için değeri tarafından aktarılan toplam bir tür olduğunda ikinci formu kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [İzlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [İzlenecek yol: bir görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Transformer sınıfı](../../parallel/concrt/reference/transformer-class.md)
