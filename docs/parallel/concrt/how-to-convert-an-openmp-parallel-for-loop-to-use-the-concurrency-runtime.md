---
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak üzere Döngü için bir OpenMP paralelini Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
ms.openlocfilehash: 2d96ba23582368fe72e61003823826a6f3ab807a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141760"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak üzere Döngü için bir OpenMP paralelini Dönüştürme

Bu örnek, Eşzamanlılık Çalışma Zamanı [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanmak için OpenMP [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) [ve yönergeleri kullanan](../../parallel/openmp/reference/for-openmp.md) temel bir döngünün nasıl dönüştürüleceğini gösterir.

## <a name="example---prime-count"></a>Örnek-asal sayı

Bu örnek, bir rastgele değerler dizisindeki asal sayıların sayısını hesaplamak için hem OpenMP hem de Eşzamanlılık Çalışma Zamanı kullanır.

[!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using OpenMP...
found 107254 prime numbers.
Using the Concurrency Runtime...
found 107254 prime numbers.
```

`parallel_for` algoritması ve OpenMP 3,0, Dizin türünün imzalı bir integral türü veya işaretsiz integral türü olmasını sağlar. `parallel_for` algoritması, belirtilen aralığın imzalı bir tür üzerinde taşma olmadığından da emin olur. OpenMP sürümleri 2,0 ve 2,5 yalnızca imzalı integral Dizin türlerine izin verir. OpenMP, Dizin aralığını da doğrulamaz.

Eşzamanlılık Çalışma Zamanı kullanan Bu örnek, sayaç değerini eşitlemeye gerek kalmadan artırmak için [atomik](../../parallel/openmp/reference/atomic.md) yönergesinin yerine bir [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) nesnesi de kullanır.

`parallel_for` ve diğer paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md). `combinable` sınıfı hakkında daha fazla bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="example---use-stdarray"></a>Örnek-std:: Array kullanın

Bu örnek, bir öncekini yerel dizi yerine [std:: Array](../../standard-library/array-class-stl.md) nesnesine göre hareket etmek için bir önceki öğenin konumunu değiştirir. OpenMP sürümleri 2,0 ve 2,5, yalnızca bir `parallel_for` yapısında işaretli integral Dizin türlerine izin vereceğinden, bir C++ standart kitaplık kapsayıcısının öğelerine paralel olarak erişmek için yineleyiciler kullanamazsınız. Paralel Desenler kitaplığı (PPL), görevleri C++ standart kitaplık tarafından sağlananlar gibi yinelemeli bir kapsayıcıda paralel olarak gerçekleştiren [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını sağlar. `parallel_for` algoritmasının kullandığı bölümleme mantığını kullanır. `parallel_for_each` algoritması C++ standart kitaplık [std:: for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasına benzer, ancak `parallel_for_each` algoritması görevleri eşzamanlı olarak yürütür.

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `concrt-omp-count-primes.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc/OpenMP concrt-omp-Count-Primes. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)
