---
title: 'Nasıl yapılır: Eşleme gerçekleştirme ve işlemleri paralel olarak azaltma'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
ms.openlocfilehash: ba3ffb5cdae7dcc6f108f005fab33f9a1fee6a6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412715"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Nasıl yapılır: Eşleme gerçekleştirme ve işlemleri paralel olarak azaltma

Bu örnek nasıl kullanılacağını gösterir [concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmaları ve [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)dosyalarında bir kelimelerin oluşumları için sınıf.

A *harita* işlemi, bir dizideki her bir değeri bir işlev uygular. A *azaltmak* işlemi bir dizisinin bir değer halinde birleştirir. C++ Standart Kitaplığı kullanabilirsiniz [std::transform](../../standard-library/algorithm-functions.md#transform) ve [std::accumulate](../../standard-library/numeric-functions.md#accumulate) eşleme gerçekleştirme ve işlemleri azaltmak için işlevleri. Ancak, birçok sorun için performansı artırmak için kullanabileceğiniz `parallel_transform` paralel olarak harita işlemi gerçekleştirmek için algoritma ve `parallel_reduce` paralel olarak azaltma işlemi gerçekleştirmek için algoritma. Bazı durumlarda, kullandığınız `concurrent_unordered_map` eşleme ve azaltma tek bir işlemde gerçekleştirmek için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, oluşum dosyalarında bir kelimelerin sayar. Kullandığı [std::vector](../../standard-library/vector-class.md) iki dosya içeriğini temsil etmek için. Harita işlemi her vektör her bir sözcüğün oluşumlarını hesaplar. Küçültme işlemi her iki vektör sözcük sayıları toplanır.

[!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-map-reduce.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel-map-reduce.cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bu örnekte, kullandığınız `concurrent_unordered_map` sınıfı — concurrent_unordered_map.h—to içinde tanımlandığı eşleme gerçekleştirme ve tek bir işlemde azaltın.

[!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]

Genellikle, yalnızca dış veya iç döngü paralel hale getirmek. İç döngü paralel hale nispeten daha az sayıda dosya varsa ve her dosya pek çok sözcük içerir. Dış döngü paralel hale oldukça fazla dosya varsa ve her dosya birkaç sözcük içerir.

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_transform işlevi](reference/concurrency-namespace-functions.md#parallel_transform)<br/>
[parallel_reduce işlevi](reference/concurrency-namespace-functions.md#parallel_reduce)<br/>
[concurrent_unordered_map Sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
