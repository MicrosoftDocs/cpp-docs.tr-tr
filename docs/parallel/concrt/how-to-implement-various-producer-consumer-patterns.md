---
title: "Nasıl yapılır: çeşitli üretici-tüketici desenlerini uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4daf7005eabee7f6cf74144c08c8d8d8aabef232
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>Nasıl yapılır: Çeşitli Üretici-Tüketici Desenlerini Uygulama
Bu konu, uygulamanızı üretici-tüketici düzeni uygulama açıklar. Bu modelde *üretici* ileti bloğu iletileri gönderir ve *tüketici* bu bloğundan iletileri okur.  
  
 Konu iki senaryo gösterir. İlk senaryoda, üretici tarafından gönderilen her ileti tüketici alması gerekir. İkinci senaryoda Tüketici verileri düzenli aralıklarla yoklar ve bu nedenle her ileti almak mevcut değil.  
  
 Bu konudaki her iki örnekleri üretici iletilerden tüketici iletmek için aracıları, ileti blokları ve ileti geçirme işlevleri kullanın. Üretici Aracısı'nı kullanan [concurrency::send](reference/concurrency-namespace-functions.md#send) iletileri yazmak için işlevi bir [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) nesnesi. Tüketici Aracısı'nı kullanan [concurrency::receive](reference/concurrency-namespace-functions.md#receive) gelen iletileri okumak için işlev bir [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) nesnesi. Her iki aracıları işleme sonuna koordine etmek için bir sentinel değer tutun.  
  
 Zaman uyumsuz aracılar hakkında daha fazla bilgi için bkz: [zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md). İleti blokları ve ileti geçirme işlevleri hakkında daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md) ve [ileti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md).  
  
## <a name="example"></a>Örnek  
 Bu örnekte, üretici aracı bir dizi numarası tüketici aracıya gönderir. Tüketici her bu sayının alır ve kendi ortalama hesaplar. Uygulama ortalama konsola yazar.  
  
 Bu örnekte bir [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) kuyruk iletileri üretici etkinleştirmek için nesne. `unbounded_buffer` Uygulayan sınıf `ITarget` ve `ISource` böylece üretici ve tüketici gönderebilir ve paylaşılan bir arabellek gelen ve giden iletiler alabilirsiniz. `send` Ve `receive` işlevleri koordine üretici verileri tüketici yayılıyor görevi.  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
The average is 50.  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte, üretici aracı hisse senedi fiyatları bir dizi tüketici aracıya gönderir. Tüketici aracı, düzenli aralıklarla geçerli teklif okur ve konsola yazdırır.  
  
 Bu örnek önceki bir benzer kullandığı bir [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) bir ileti tüketicisi ile paylaşmak üretici etkinleştirmek için nesne. Önceki örnekte olduğu gibi `overwrite_buffer` uygulayan sınıf `ITarget` ve `ISource` böylece üretici ve tüketici paylaşılan ileti arabellek üzerinde çalışabilir.  
  
 [!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir.  
  
```Output  
Current quote is 24.44.  
Current quote is 24.44.  
Current quote is 24.65.  
Current quote is 24.99.  
Current quote is 23.76.  
Current quote is 22.30.  
Current quote is 25.89.  
```  
  
 Aksine ile bir `unbounded_buffer` nesnesi `receive` işlevi iletiden kaldırmaz `overwrite_buffer` nesnesi. Tüketici üretici ileti üzerine yazar önce birden fazla kez ileti arabelleğinden yazıyorsa, alıcının her zaman aynı iletiyi alır.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `producer-consumer.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc üretici-consumer.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Zaman uyumsuz aracılar kitaplığı](../../parallel/concrt/asynchronous-agents-library.md)   
 [Zaman uyumsuz aracılar](../../parallel/concrt/asynchronous-agents.md)   
 [Zaman uyumsuz ileti blokları](../../parallel/concrt/asynchronous-message-blocks.md)   
 [İleti geçirme işlevleri](../../parallel/concrt/message-passing-functions.md)
