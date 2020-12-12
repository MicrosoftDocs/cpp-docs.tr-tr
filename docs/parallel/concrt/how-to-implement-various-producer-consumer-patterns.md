---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: çeşitli Producer-Consumer desenleri uygulama'
title: 'Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
ms.openlocfilehash: 5742d3ba213997efc54aeca360c99fd11b0cf712
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209912"
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama

Bu konuda, uygulamanızda üretici tüketicisi deseninin nasıl uygulanacağı açıklanmaktadır. Bu düzende, *üretici* iletileri bir ileti bloğuna gönderir ve *Tüketici* bu bloktaki iletileri okur.

Konuda iki senaryo gösterilmektedir. İlk senaryoda, tüketici, üretici tarafından gönderilen her iletiyi almalıdır. İkinci senaryoda, tüketici verileri düzenli aralıklarla yoklar ve bu nedenle her iletiyi almak zorunda değildir.

Bu konudaki örneklerin her ikisi de aracıları, ileti blokları ve ileti geçirme işlevlerini kullanarak üreticiden tüketiciye ileti iletmektir. Üretici Aracısı, concurrency:: [ITarget](../../parallel/concrt/reference/itarget-class.md) nesnesine ileti yazmak için [concurrency:: Send](reference/concurrency-namespace-functions.md#send) işlevini kullanır. Tüketici Aracısı eşzamanlılık [:: ISource](../../parallel/concrt/reference/isource-class.md) nesnesinden iletileri okumak için [concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) işlevini kullanır. Her iki aracı da işlem sonunu koordine etmek için Sentinel değerini tutar.

Zaman uyumsuz aracılar hakkında daha fazla bilgi için bkz. [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md). İleti blokları ve ileti geçirme işlevleri hakkında daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md) ve [ileti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md).

## <a name="example-send-series-of-numbers-to-consumer-agent"></a>Örnek: tüketici aracısına numara serisi gönder

Bu örnekte, üretici Aracısı tüketici aracısına bir dizi numara gönderir. Tüketici bu sayıların her birini alır ve ortalamasını hesaplar. Uygulama, ortalamayı konsola yazar.

Bu örnek, üreticinin iletileri sıraya alma olanağı sağlamak için bir [eşzamanlılık:: unbounded_buffer](reference/unbounded-buffer-class.md) nesnesi kullanır. Sınıfı, ve ' nin `unbounded_buffer` `ITarget` `ISource` , üretici ve tüketicinin, paylaşılan bir arabelleğe gelen ve olmayan iletileri gönderebilmesi ve alabilmesi için uygular. `send`Ve `receive` işlevleri, verileri üretici 'dan tüketiciye yayın görevini koordine edin.

[!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
The average is 50.
```

## <a name="example-send-series-of-stock-quotes-to-consumer-agent"></a>Örnek: tüketici aracısına Stok fiyatları serisi gönder

Bu örnekte, üretici Aracısı tüketici aracısına bir dizi stok teklifi gönderir. Tüketici Aracısı, geçerli teklifi düzenli aralıklarla okur ve konsola yazdırır.

Bu örnek, bir öncekine benzer, ancak üreticinin tüketiciyle bir ileti paylaşmasını sağlamak için bir [eşzamanlılık:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) nesnesi kullanır. Önceki örnekte olduğu gibi, `overwrite_buffer` sınıfı, `ITarget` ve `ISource` üreticisi ve tüketicinin paylaşılan bir ileti arabelleği üzerinde işlem yapabilmesi için ve uygular.

[!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
Current quote is 24.44.
Current quote is 24.44.
Current quote is 24.65.
Current quote is 24.99.
Current quote is 23.76.
Current quote is 22.30.
Current quote is 25.89.
```

Bir nesneden farklı olarak `unbounded_buffer` , `receive` işlevi nesnesinden iletiyi kaldırmaz `overwrite_buffer` . Tüketici, bu iletinin üzerine yazmadan önce ileti arabelleğinden birden çok kez okursa, alıcı aynı iletiyi her seferinde edinir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `producer-consumer.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/EHsc Producer-Consumer. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Uyumsuz Aracılar Kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)<br/>
[Zaman uyumsuz Ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[İleti geçirme Işlevleri](../../parallel/concrt/message-passing-functions.md)
