---
title: 'Nasıl yapılır: ileti bloğu filtresini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b16dee4d0a3c5a6d09c1fd19006c832be400d5a4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411085"
---
# <a name="how-to-use-a-message-block-filter"></a>Nasıl yapılır: İleti Bloğu Filtresini Kullanma

Bu belge, kabul etme veya reddetme söz konusu iletinin yükü boyutuna göre bir iletiyi için bir zaman uyumsuz ileti bloğu etkinleştirmek için bir filtre işlevi nasıl yapılacağı açıklanır.

Oluşturduğunuzda, bir ileti bloğu nesnesi gibi bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::call](../../parallel/concrt/reference/call-class.md), veya bir [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md), bir sağlayabilirsiniz.*filtre işlevi* ileti bloğu kabul eder ya da bir ileti reddeder olup olmadığını belirler. Bir filtre işlevi, bir ileti bloğu yalnızca belirli değerleri almasını sağlamak için kullanışlı bir yoldur.

Filtre işlevleri, bunlar için form ileti blokları bağlanmanıza imkan sağlamak için önemlidir *veri akışı ağları*. Bir veri akışı ağında, yalnızca belirli ölçütlere uyan iletileri işleyerek, veri akışını ileti blokları denetler. Bu veri akışını gibi koşullu deyimleri, döngüler, Denetim yapıları kullanarak burada düzenlenen denetim akışı modeli, karşılaştırma vb. kullanın.

Bu belge, bir ileti filtresi kullanmak nasıl basit bir örneği sağlar. İleti bloklarına bağlanma ileti filtreleri ve veri akışı modelini kullanan diğer örnekler için [izlenecek yol: bir veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) ve [izlenecek yol: görüntü işleme ağı oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md) .

## <a name="example"></a>Örnek

Aşağıdaki işlev göz önünde bulundurun `count_primes`, gelen iletileri filtrelemez bir ileti bloğu temel kullanımını göstermektedir. İleti bloğu asal sayıları ekler bir [std::vector](../../standard-library/vector-class.md) nesne. `count_primes` İşlevi birkaç sayı ileti bloğu gönderir, ileti bloğundan çıkış değerleri alır ve asal konsolunda bu numaraları yazdırır.

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

`transformer` Nesnesini işler tüm giriş değerlerini; ancak, asal olan değerleri gerektirir. Uygulama iletiyi gönderenin asal sayıları göndermesi yazılmış olsa da, ileti alıcısı gereksinimlerini her zaman bilinen olamaz.

## <a name="example"></a>Örnek

Aşağıdaki işlev `count_primes_filter`, aynı görevi gerçekleştirir `count_primes` işlevi. Ancak, `transformer` nesne bu sürümde asal olan değerleri kabul etmek için bir filtre işlevi kullanır. Bir eylem gerçekleştiren işlevi yalnızca asal sayıları alır. Bu nedenle, onu çağırmak yok `is_prime` işlevi.

Çünkü `transformer` nesnesi aldığında yalnızca asal sayıları `transformer` nesnenin kendisini asal sayıları tutabilir. Diğer bir deyişle, `transformer` nesne bu örnekte asal sayıları için gerekli değildir `vector` nesne.

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

`transformer` Nesne artık asal olan değerleri işler. Önceki örnekte, `transformer` nesnesini tüm iletileri işler. Bu nedenle, önceki örnekle aynı sayıda gönderdiği iletileri alması gerekir. Bu örnekte sonucunu [concurrency::send](reference/concurrency-namespace-functions.md#send) almak için kaç iletileri belirlemek için işlevi `transformer` nesne. `send` İşlevinin döndürdükleriyle `true` ileti arabelleği iletiyi ne zaman kabul eder ve `false` zaman ileti arabelleği ileti reddeder. Bu nedenle, ileti arabelleği iletiyi kabul kaç kez asal sayıları sayısı ile eşleşir.

## <a name="example"></a>Örnek

Aşağıdaki kod, tam bir örnek gösterir. Örnek her ikisi de çağırır `count_primes` işlevi ve `count_primes_filter` işlevi.

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `primes-filter.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc primes filter.cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bir filtre işlevi lambda işlevi, işlev işaretçisi veya işlev nesnesi olabilir. Her filtre işlevi aşağıdaki biçimlerden birini alır:

```Output
bool (T)
bool (T const &)
```

Gereksiz verilerin kopyalanmasını ortadan kaldırmak için değer tarafından gönderilen bir toplam değer türüne sahip olduğunda ikinci formu kullanın.

## <a name="see-also"></a>Ayrıca Bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[transformer Sınıfı](../../parallel/concrt/reference/transformer-class.md)
