---
title: 'Nasıl yapılır: Çeşitli üretici-tüketici desenlerini uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
ms.openlocfilehash: 113518e97b6715384b5e7b84b0d0eab63dfcfcc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411363"
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>Nasıl yapılır: Çeşitli üretici-tüketici desenlerini uygulama

Bu konu, uygulamanıza üretici-tüketici düzeni açıklar. Bu modelde *üretici* iletiler gönderen bir ileti bloğu ve *tüketici* bu iletileri okuduğu.

Bu konuda, iki senaryo gösterilir. İlk senaryoda tüketici üretici gönderen her iletiyi alması gerekir. İkinci senaryoda Tüketici verileri düzenli aralıklarla yoklar ve bu nedenle her iletiyi alması gerekmez.

Örneklerin her ikisi de bu konuda, tüketiciye üretici gelen ileti aktarmaya aracıları ve ileti blokları ileti geçirme işlevleri'ni kullanın. Üretici Aracısı'nı kullanan [concurrency::send](reference/concurrency-namespace-functions.md#send) ileti yazmak için işlevi bir [CONCURRENCY::ıtarget](../../parallel/concrt/reference/itarget-class.md) nesne. Tüketici Aracısı'nı kullanan [concurrency::receive](reference/concurrency-namespace-functions.md#receive) gelen iletileri okumak için işlev bir [CONCURRENCY::ısource](../../parallel/concrt/reference/isource-class.md) nesne. Her iki aracı işleme sonuna koordine etmek için bir sentinel değeri tutun.

Zaman uyumsuz aracılar hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md). İleti blokları ve ileti geçirme işlevleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md) ve [ileti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md).

## <a name="example"></a>Örnek

Bu örnekte, üretici aracı, bir dizi numarası tüketici aracıya gönderir. Tüketici bu numaraların her alır ve bunların ortalamasını hesaplar. Uygulama, ortalama konsola yazar.

Bu örnekte bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) kuyruk iletileri için üretici etkinleştirmek için nesne. `unbounded_buffer` Sınıfının Implements `ITarget` ve `ISource` böylece üretici ve tüketici gönderebilir ve paylaşılan bir arabellek gelen ve giden iletileri alabilirsiniz. `send` Ve `receive` işlevleri üretici verilerden tüketici Yayma görevi koordine edin.

[!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
The average is 50.
```

## <a name="example"></a>Örnek

Bu örnekte, üretici aracı hisse senedi fiyatlarını bir dizi tüketici aracıya gönderir. Tüketici aracı, düzenli aralıklarla geçerli teklif okur ile konsola yazdırır.

Bu örnek Öncekine benzer kullandığı bir [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) üretici ile tüketici bir ileti paylaşmak etkinleştirmek için nesne. Önceki örnekte olduğu gibi `overwrite_buffer` sınıfının Implements `ITarget` ve `ISource` üretici ve tüketici bir paylaşılan ileti arabelleği üzerinde işlem yapabilmesi.

[!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]

Bu örnek, aşağıdaki örnek çıktısı üretir.

```Output
Current quote is 24.44.
Current quote is 24.44.
Current quote is 24.65.
Current quote is 24.99.
Current quote is 23.76.
Current quote is 22.30.
Current quote is 25.89.
```

Farklı olarak ile bir `unbounded_buffer` nesnesi `receive` işlevi iletiden kaldırmaz `overwrite_buffer` nesne. Tüketici ileti arabellekteki ileti üretici üzerine yazılmadan önce birden fazla kez okuyorsa, alıcının her zaman aynı iletiyi alır.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `producer-consumer.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc üretici-consumer.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman Uyumsuz Aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Zaman Uyumsuz İleti Blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti Geçirme İşlevleri](../../parallel/concrt/message-passing-functions.md)
