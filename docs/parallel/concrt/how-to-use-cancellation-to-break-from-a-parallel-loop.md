---
title: 'Nasıl yapılır: paralel bir döngüden kurtulmak için İptal kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1b5153c225c3bb3a67be4265cf8303da2121c2b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696298"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal
Bu örnek iptal temel paralel arama algoritması uygulamak için nasıl kullanılacağını gösterir.  
  
## <a name="example"></a>Örnek  

 Aşağıdaki örnek, bir dizi bir öğe için aranacak iptal kullanır. `parallel_find_any` İşlev kullandığı [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması ve [concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) için belirtilen değeri içeren konumu aramak için işlevi. Paralel döngü değeri bulduğunda, çağıran [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) gelecekteki iş iptal etmek için yöntem.  


  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  

 [Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması eşzamanlı olarak görev yapar. Bu nedenle, bu işlemlerin önceden belirlenmiş bir sırayla gerçekleştirmez. Dizi değeri birden çok örneği varsa, sonuç kendi konumları herhangi biri olabilir.  

  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-array-search.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel-dizi-search.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)   
 [cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)
