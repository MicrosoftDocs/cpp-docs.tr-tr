---
title: 'Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
ms.openlocfilehash: 599e46c05a91a1f2ea6e317fe024d3c98a78977f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141704"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma

Bu örnek, dosyalardaki sözcüklerin tekrarlarının sayısını saymak için [eşzamanlılık::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [eşzamanlılık::p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmalarının ve [concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) sınıfının nasıl kullanılacağını gösterir.

*Eşleme* işlemi, dizideki her değere bir işlev uygular. Bir *azaltma* işlemi bir dizinin öğelerini tek bir değer olarak birleştirir. C++ Standart Kitaplığı [std:: Transform](../../standard-library/algorithm-functions.md#transform) ve [std:: birikme](../../standard-library/numeric-functions.md#accumulate) işlevlerini kullanarak harita gerçekleştirir ve işlemleri azaltabilirsiniz. Ancak, birçok sorun için performansı artırmak amacıyla, eşleme işlemini paralel olarak gerçekleştirmek için `parallel_transform` algoritmasını ve azaltma işlemini paralel olarak gerçekleştirmek için `parallel_reduce` algoritmasını kullanabilirsiniz. Bazı durumlarda, eşlemeyi gerçekleştirmek ve tek bir işlemde azaltmak için `concurrent_unordered_map` kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, dosyalardaki sözcüklerin tekrarlamalarını sayar. Bu, iki dosyanın içeriğini göstermek için [std:: vector](../../standard-library/vector-class.md) öğesini kullanır. Eşleme işlemi her vektörde her bir sözcüğün tekrarlamalarını hesaplar. Azaltma işlemi her iki vektörde sözcük sayısını birikir.

[!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `parallel-map-reduce.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Parallel-Map-Reduce. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bu örnekte, eşlemeyi gerçekleştirmek ve tek bir işlemde azaltmak için, concurrent_unordered_map. h içinde tanımlanan `concurrent_unordered_map` sınıfını kullanabilirsiniz.

[!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]

Genellikle yalnızca OUTER veya Inner döngüsünü paralel hale getirmek. Oldukça az dosyanız varsa ve her dosya birçok kelime içeriyorsa, iç döngüyü paralel hale getirmek. Görece çok sayıda dosyanız varsa ve her dosya birkaç kelime içeriyorsa dış döngüyü paralel hale getirmek.

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_transform Işlevi](reference/concurrency-namespace-functions.md#parallel_transform)<br/>
[parallel_reduce Işlevi](reference/concurrency-namespace-functions.md#parallel_reduce)<br/>
[concurrent_unordered_map Sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
