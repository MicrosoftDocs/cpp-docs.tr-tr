---
description: 'Daha fazla bilgi edinin: nasıl yapılır: eşleme gerçekleştirme ve Işlemleri paralel olarak azaltma'
title: 'Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
ms.openlocfilehash: f35c9bf4df5a79cf9568bc286ff628e2f9fd45c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209847"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma

Bu örnek, dosyalardaki sözcüklerin tekrarlarının sayısını saymak için [eşzamanlılık::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [eşzamanlılık::p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmalarının ve [concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) sınıfının nasıl kullanılacağını gösterir.

*Eşleme* işlemi, dizideki her değere bir işlev uygular. Bir *azaltma* işlemi bir dizinin öğelerini tek bir değer olarak birleştirir. C++ Standart Kitaplığı [std:: Transform](../../standard-library/algorithm-functions.md#transform) ve [std:: birikme](../../standard-library/numeric-functions.md#accumulate) işlevlerini kullanarak harita gerçekleştirir ve işlemleri azaltabilirsiniz. Ancak, birçok soruna ilişkin performansı artırmak için, `parallel_transform` algoritmayı kullanarak eşleme işlemini paralel olarak ve `parallel_reduce` azaltma işlemini paralel olarak gerçekleştirmek için algoritmayı kullanabilirsiniz. Bazı durumlarda, `concurrent_unordered_map` eşlemeyi ve tek bir işlemde küçültme işlemini gerçekleştirmek için kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, dosyalardaki sözcüklerin tekrarlamalarını sayar. Bu, iki dosyanın içeriğini göstermek için [std:: vector](../../standard-library/vector-class.md) öğesini kullanır. Eşleme işlemi her vektörde her bir sözcüğün tekrarlamalarını hesaplar. Azaltma işlemi her iki vektörde sözcük sayısını birikir.

[!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `parallel-map-reduce.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Parallel-Map-Reduce. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Bu örnekte, `concurrent_unordered_map` eşlemeyi gerçekleştirmek ve tek bir işlemde azaltmak için concurrent_unordered_map. h içinde tanımlanan sınıfını kullanabilirsiniz.

[!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]

Genellikle yalnızca OUTER veya Inner döngüsünü paralel hale getirmek. Oldukça az dosyanız varsa ve her dosya birçok kelime içeriyorsa, iç döngüyü paralel hale getirmek. Görece çok sayıda dosyanız varsa ve her dosya birkaç kelime içeriyorsa dış döngüyü paralel hale getirmek.

## <a name="see-also"></a>Ayrıca bkz.

[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_transform Işlevi](reference/concurrency-namespace-functions.md#parallel_transform)<br/>
[parallel_reduce Işlevi](reference/concurrency-namespace-functions.md#parallel_reduce)<br/>
[concurrent_unordered_map sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
