---
title: 'Nasıl yapılır: eşzamanlılık çalışma zamanı kullanmak üzere döngü için bir OpenMP paralelini dönüştürme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5295a7e38ef511cd2703961ffe8fe6f22faa74ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407965"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak üzere Döngü için bir OpenMP paralelini Dönüştürme

Bu örnekte OpenMP kullanan temel bir döngü dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) ve [için](../../parallel/openmp/reference/for-openmp.md) eşzamanlılık çalışma zamanı kullanmak için yönergeleri [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritma.

## <a name="example"></a>Örnek

Bu örnek sayısı rastgele değerler dizisi olarak asal sayıları hesaplamak için hem OpenMP hem de eşzamanlılık çalışma zamanı'nı kullanır.

[!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using OpenMP...
found 107254 prime numbers.
Using the Concurrency Runtime...
found 107254 prime numbers.
```

`parallel_for` Algoritması ve OpenMP 3.0 izin dizin türünü işaretli bir integral türe veya bir işaretsiz tamsayı türü olmalıdır. `parallel_for` Algoritması da sağlar belirtilen aralık işaretli bir türe overflow değil. OpenMP sürümleri 2.0 ve 2.5 yalnızca imzalı tamsayı dizini türü için izin verir. OpenMP dizin aralığına da doğrulamaz.

Eşzamanlılık Çalışma zamanı kullanan bu örnek sürümünü de kullanan bir [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) yerine nesne [atomik](../../parallel/openmp/reference/atomic.md) gerek kalmadan, sayaç değeri artırmak için yönergesi Eşitleme.

Hakkında daha fazla bilgi için `parallel_for` ve diğer paralel algoritmalar için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md). Hakkında daha fazla bilgi için `combinable` sınıfı [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="example"></a>Örnek

Bu örnek Öncekine gerçekleştirileceği değiştirir bir [std::array](../../standard-library/array-class-stl.md) yerel bir dizi nesnesi yerine. Tamsayı dizini türleri yalnızca imzalı OpenMP sürümleri 2.0 ve 2.5 olanak tanımak için bir `parallel_for` yapısı, paralel bir C++ Standart Kitaplığı kapsayıcının öğelerine erişmek için yineleyiciler kullanamazsınız. Paralel Desen kitaplığı (PPL) sağlayan [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını paralel, yinelemeli bir kapsayıcıda C++ Standart Kitaplığı tarafından sağlanan gibi görevleri gerçekleştirir. Bölümleme aynı mantığı kullanır, `parallel_for` algoritması kullanır. `parallel_for_each` Algoritması, C++ Standart Kitaplığı benzer [std::for_each](../../standard-library/algorithm-functions.md#for_each) hariç algoritmasını `parallel_for_each` algoritması görevleri aynı anda yürütür.

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-count-primes.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc/OpenMP concrt-omp-count-primes.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)

