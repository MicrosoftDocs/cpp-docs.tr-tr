---
title: 'Nasıl yapılır: İleti Bloğu Filtresini Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
ms.openlocfilehash: ac58ef2240d2ea6ba34b334106c08595e70b02e8
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008635"
---
# <a name="how-to-use-a-message-block-filter"></a>Nasıl yapılır: İleti Bloğu Filtresini Kullanma

Bu belgede, zaman uyumsuz bir ileti bloğunun, bu iletinin yükünün temelinde bir iletiyi kabul etmesi veya reddetmesi için bir filtre işlevinin nasıl kullanılacağı gösterilmektedir.

[Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency:: Call](../../parallel/concrt/reference/call-class.md)veya [concurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md)gibi bir ileti bloğu nesnesi oluşturduğunuzda, ileti bloğunun bir iletiyi kabul ettiğini veya reddettiğini belirleyen bir *filtre işlevi* sağlayabilirsiniz. Filtre işlevi, ileti bloğunun yalnızca belirli değerleri almasını güvence altına almak için kullanışlı bir yoldur.

*Veri akışı ağlarına*ileti blokları bağlamanıza olanak sağladığından filtre işlevleri önemlidir. Bir veri akışı ağında, ileti blokları yalnızca belirli ölçütlere uyan iletileri işleyerek veri akışını denetler. Bunu, veri akışının koşullu deyimler, döngüler vb. gibi denetim yapıları kullanılarak düzenlenen denetim akışı modeliyle karşılaştırın.

Bu belge bir ileti filtresinin nasıl kullanılacağına ilişkin temel bir örnek sağlar. İleti filtrelerini ve ileti bloklarını bağlamak için veri akışı modelini kullanan ek örnekler için bkz. [Izlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) ve [izlenecek yol: Image-Processing ağ oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

## <a name="example-count_primes-function"></a>Örnek: count_primes işlevi

`count_primes`Gelen iletileri filtrelemez bir ileti bloğunun temel kullanımını gösteren aşağıdaki işlevi göz önünde bulundurun. İleti bloğu bir [std:: vector](../../standard-library/vector-class.md) nesnesine asal sayılar ekler. `count_primes`İşlevi ileti bloğuna birkaç sayı gönderir, ileti bloğundan çıkış değerlerini alır ve konsola ana olan bu sayıları yazdırır.

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

`transformer`Nesne tüm giriş değerlerini işler; ancak, yalnızca asal değerleri gerektirir. İleti göndericisinin yalnızca asal sayılar göndermesi için uygulama yazılabilse de ileti alıcısının gereksinimleri her zaman bilinmez.

## <a name="example-count_primes_filter-function"></a>Örnek: count_primes_filter işlevi

Aşağıdaki işlev, `count_primes_filter` işleviyle aynı görevi gerçekleştirir `count_primes` . Ancak, `transformer` Bu sürümdeki nesne yalnızca asal olan değerleri kabul etmek için bir filtre işlevi kullanır. Eylemi gerçekleştiren işlev yalnızca asal sayılar alır; Bu nedenle, işlevi çağırmak zorunda değildir `is_prime` .

`transformer`Nesne yalnızca asal sayılar aldığından, `transformer` nesnenin kendisi asal sayıları alabilir. Diğer bir deyişle `transformer` Bu örnekteki nesne, nesneye asal sayılar eklemek için gerekli değildir `vector` .

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

`transformer`Nesne artık yalnızca asal olan değerleri işler. Önceki örnekte, `transformer` nesne tüm iletileri işler. Bu nedenle, önceki örnek, gönderdiği ileti sayısını aynı sayıda almalıdır. Bu örnek, nesnesinden kaç ileti alınacağını anlamak için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevinin sonucunu kullanır `transformer` . `send`İşlevi, ileti **`true`** arabelleği iletiyi kabul ettiğinde ve ileti **`false`** arabelleği iletiyi reddettiğinde döndürür. Bu nedenle, ileti arabelleğinin iletiyi kaç kez kabul ettiğini asal sayı sayısıyla eşleştirir.

## <a name="example-finished-message-block-filter-code-sample"></a>Örnek: tamamlanan ileti bloğu filtre kodu örneği

Aşağıdaki kod, tüm örneği göstermektedir. Örnek hem işlevini hem de `count_primes` `count_primes_filter` işlevini çağırır.

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `primes-filter.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc primes-filter. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Filtre işlevi bir Lambda işlevi, işlev işaretçisi veya işlev nesnesi olabilir. Her filtre işlevi aşağıdaki biçimlerden birini alır:

```Output
bool (T)
bool (T const &)
```

Verilerin gereksiz şekilde kopyalanmasını engellemek için, değere göre aktarılan bir toplama türü olduğunda ikinci formu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[İzlenecek yol: veri akışı Aracısı oluşturma](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[İzlenecek yol: Image-Processing ağ oluşturma](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[Transformatör sınıfı](../../parallel/concrt/reference/transformer-class.md)
