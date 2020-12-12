---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bir OpenMP Parallel for döngüsünü Eşzamanlılık Çalışma Zamanı kullanmak için dönüştürme'
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak üzere Döngü için bir OpenMP paralelini Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
ms.openlocfilehash: 76164886b0b812b32a8b9263bb79d7ca1441f148
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209899"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak üzere Döngü için bir OpenMP paralelini Dönüştürme

Bu örnek, Eşzamanlılık Çalışma Zamanı [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını kullanmak için OpenMP [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) [ve yönergeleri kullanan](../openmp/reference/openmp-directives.md#for-openmp) temel bir döngünün nasıl dönüştürüleceğini gösterir.

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

`parallel_for`Algoritma ve OpenMP 3,0, Dizin türünün imzalı bir integral türü veya işaretsiz integral türü olmasını sağlar. `parallel_for`Algoritma Ayrıca belirtilen aralığın imzalı bir tür üzerinde taşma olmadığından emin olmanızı sağlar. OpenMP sürümleri 2,0 ve 2,5 yalnızca imzalı integral Dizin türlerine izin verir. OpenMP, Dizin aralığını da doğrulamaz.

Eşzamanlılık Çalışma Zamanı kullanan Bu örnek, sayaç değerini eşitlemeye gerek kalmadan artırmak için [atomik](../openmp/reference/openmp-directives.md#atomic) yönergesinin yerine bir [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) nesnesi de kullanır.

Ve diğer paralel algoritmalar hakkında daha fazla bilgi için `parallel_for` bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md). Sınıfı hakkında daha fazla bilgi için `combinable` bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="example---use-stdarray"></a>Örnek-std:: Array kullanın

Bu örnek, bir öncekini yerel dizi yerine [std:: Array](../../standard-library/array-class-stl.md) nesnesine göre hareket etmek için bir önceki öğenin konumunu değiştirir. OpenMP sürümleri 2,0 ve 2,5 yalnızca bir yapı içinde imzalanmış integral Dizin türlerine izin vereceğinden `parallel_for` , bir C++ standart kitaplık kapsayıcısının öğelerine paralel olarak erişmek için yineleyiciler kullanamazsınız. Paralel Desenler kitaplığı (PPL),, C++ standart kitaplığı tarafından sağlananlar gibi yinelemeli bir kapsayıcıda görevleri, paralel olarak gerçekleştiren [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını sağlar. Algoritmanın kullandığı bölümleme mantığını kullanır `parallel_for` . Algoritma, `parallel_for_each` görevleri eşzamanlı olarak yürütdüğünden, algoritma C++ Standart Kitaplığı [std:: for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasına benzer `parallel_for_each` .

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `concrt-omp-count-primes.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc/OpenMP concrt-omp-Count-Primes. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[Paralel Kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)
