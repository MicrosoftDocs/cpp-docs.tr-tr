---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: paralel bir döngüden ayırmak için Iptal kullanma'
title: 'Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 0d2817e3a2645cb01d652b7858176ffce6df73c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172524"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal

Bu örnek, bir temel paralel arama algoritmasını uygulamak için iptalin nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dizideki bir öğeyi aramak için iptali kullanır. `parallel_find_any`İşlevi, verilen değeri içeren konumu aramak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını ve [concurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) işlevini kullanır. Paralel döngü değeri bulduğunda, gelecekteki işleri iptal etmek için [concurrency:: cancellation_token_source:: Cancel](reference/cancellation-token-source-class.md#cancel) yöntemini çağırır.

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

[Eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması eşzamanlı olarak çalışır. Bu nedenle, işlemleri önceden belirlenmiş bir sırada gerçekleştirmez. Dizi değerin birden çok örneğini içeriyorsa sonuç, pozisyonlarından herhangi biri olabilir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `parallel-array-search.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Parallel-Array-Search. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for Işlevi](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[cancellation_token_source sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)
