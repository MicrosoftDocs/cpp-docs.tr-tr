---
title: 'Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 2a19c2874ce331be2d4f5840f61cabf7bca9abf6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612751"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için İptal

Bu örnek, iptal temel paralel arama algoritması uygulamak için nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dizideki bir öğe için aranacak iptal kullanır. `parallel_find_any` İşlevini kullanan [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması ve [concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) belirtilen değeri içeren konumu için aranacak işlev. Paralel bir döngüden değeri bulduğunda, çağrı [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) metodu gelecek işi iptal etmek için.

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

[Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması eşzamanlı olarak görev yapar. Bu nedenle, bu işlemleri önceden belirlenmiş bir sırada gerçekleştirmez. Dizi birden fazla değer içeriyorsa, sonuç kendi konumları herhangi biri olabilir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-array-search.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel-diziyi-search.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)
