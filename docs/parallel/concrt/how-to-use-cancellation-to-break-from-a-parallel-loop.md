---
title: 'Nasıl yapılır: İptal paralel bir döngüden kurtulmak için'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 08f33a75bc5c5391333a2d9368d4ed6563e117c2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299575"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Nasıl yapılır: İptal paralel bir döngüden kurtulmak için

Bu örnek, iptal temel paralel arama algoritması uygulamak için nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dizideki bir öğe için aranacak iptal kullanır. `parallel_find_any` İşlevini kullanan [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması ve [concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) belirtilen değeri içeren konumu için aranacak işlev. Paralel bir döngüden değeri bulduğunda, çağrı [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) metodu gelecek işi iptal etmek için.

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

[Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması eşzamanlı olarak görev yapar. Bu nedenle, bu işlemleri önceden belirlenmiş bir sırada gerçekleştirmez. Dizi birden fazla değer içeriyorsa, sonuç kendi konumları herhangi biri olabilir.

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-array-search.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel-diziyi-search.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[PPL'de İptal](cancellation-in-the-ppl.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[cancellation_token_source Sınıfı](../../parallel/concrt/reference/cancellation-token-source-class.md)
