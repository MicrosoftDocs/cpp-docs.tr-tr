---
title: 'Nasıl yapılır: İleti Bloğu Filtresini Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
ms.openlocfilehash: 074d3989ce48b0b6d69206e3f83c374a2ec65c93
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142811"
---
# <a name="how-to-use-a-message-block-filter"></a>Nasıl yapılır: İleti Bloğu Filtresini Kullanma

Bu belgede, zaman uyumsuz bir ileti bloğunun, bu iletinin yükünün temelinde bir iletiyi kabul etmesi veya reddetmesi için bir filtre işlevinin nasıl kullanılacağı gösterilmektedir.

[Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency:: Call](../../parallel/concrt/reference/call-class.md)veya [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md)gibi bir ileti bloğu nesnesi oluşturduğunuzda, ileti bloğunun bir iletiyi kabul ettiğini veya reddettiğini belirleyen bir *filtre işlevi* sağlayabilirsiniz. Filtre işlevi, ileti bloğunun yalnızca belirli değerleri almasını güvence altına almak için kullanışlı bir yoldur.

*Veri akışı ağlarına*ileti blokları bağlamanıza olanak sağladığından filtre işlevleri önemlidir. Bir veri akışı ağında, ileti blokları yalnızca belirli ölçütlere uyan iletileri işleyerek veri akışını denetler. Bunu, veri akışının koşullu deyimler, döngüler vb. gibi denetim yapıları kullanılarak düzenlenen denetim akışı modeliyle karşılaştırın.

Bu belge bir ileti filtresinin nasıl kullanılacağına ilişkin temel bir örnek sağlar. İleti filtrelerini ve ileti bloklarını bağlamak için veri akışı modelini kullanan ek örnekler için bkz. [Izlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) ve [Izlenecek yol: görüntü işleme ağı](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)oluşturma.

## <a name="example"></a>Örnek

Gelen iletileri filtreleyebilen bir ileti bloğunun temel kullanımını gösteren `count_primes`, aşağıdaki işlevi göz önünde bulundurun. İleti bloğu bir [std:: vector](../../standard-library/vector-class.md) nesnesine asal sayılar ekler. `count_primes` işlevi ileti bloğuna birkaç sayı gönderir, ileti bloğundan çıkış değerlerini alır ve konsola ana bu sayıları yazdırır.

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

`transformer` nesnesi tüm giriş değerlerini işler; Ancak, yalnızca asal olan değerleri gerektirir. İleti göndericisinin yalnızca asal sayılar göndermesi için uygulama yazılabilse de ileti alıcısının gereksinimleri her zaman bilinmez.

## <a name="example"></a>Örnek

Aşağıdaki işlev `count_primes_filter`, `count_primes` işleviyle aynı görevi gerçekleştirir. Ancak, bu sürümdeki `transformer` nesnesi yalnızca asal olan değerleri kabul etmek için bir filtre işlevi kullanır. Eylemi gerçekleştiren işlev yalnızca asal sayılar alır; Bu nedenle, `is_prime` işlevini çağırmak zorunda değildir.

`transformer` nesnesi yalnızca asal sayılar aldığından, `transformer` nesnenin kendisi asal sayıları alabilir. Diğer bir deyişle, bu örnekteki `transformer` nesnesi, `vector` nesnesine asal sayılar eklemek için gerekli değildir.

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

`transformer` nesnesi artık yalnızca asal olan değerleri işler. Önceki örnekte `transformer` nesne tüm iletileri işler. Bu nedenle, önceki örnek, gönderdiği ileti sayısını aynı sayıda almalıdır. Bu örnek, `transformer` nesnesinden kaç ileti alınacağını öğrenmek için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevinin sonucunu kullanır. `send` işlevi, ileti arabelleği iletiyi kabul ettiğinde **true** , ileti arabelleği iletiyi reddettiğinde **false** döndürür. Bu nedenle, ileti arabelleğinin iletiyi kaç kez kabul ettiğini asal sayı sayısıyla eşleştirir.

## <a name="example"></a>Örnek

Aşağıdaki kod, tüm örneği göstermektedir. Örnek hem `count_primes` işlevini hem de `count_primes_filter` işlevini çağırır.

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `primes-filter.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc primes-filter. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Filtre işlevi bir Lambda işlevi, işlev işaretçisi veya işlev nesnesi olabilir. Her filtre işlevi aşağıdaki biçimlerden birini alır:

```Output
bool (T)
bool (T const &)
```

Verilerin gereksiz şekilde kopyalanmasını engellemek için, değere göre aktarılan bir toplama türü olduğunda ikinci formu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[İzlenecek Yol: Veri Akışı Aracısı Oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[İzlenecek yol: Görüntü İşleme Ağı Oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[transformer Sınıfı](../../parallel/concrt/reference/transformer-class.md)
