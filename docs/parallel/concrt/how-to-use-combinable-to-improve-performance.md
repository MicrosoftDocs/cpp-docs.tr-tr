---
title: 'Nasıl yapılır: performansı arttırmak için combinable kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22425ac212ee2bfb52354044b1a6193b6a9cd11a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432094"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Nasıl yapılır: Performansı arttırmak için combinable Kullanma

Bu örnek nasıl kullanılacağını gösterir [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sayıların toplamını hesaplamak için sınıf bir [std::array](../../standard-library/array-class-stl.md) asal olan nesne. `combinable` Sınıfı paylaşılan durum ortadan kaldırarak performansı artırır.

> [!TIP]
>  Bazı durumlarda, paralel eşleme ([concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) ve azaltma ([eşzamanlılık:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) üzerinden performans artışı sağlayabilir `combinable`. Kullanan harita ve bu örnek olarak aynı sonuçlar için işlemleri azaltma bir örnek için bkz [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="example"></a>Örnek

Aşağıdaki örnekte [std::accumulate](../../standard-library/numeric-functions.md#accumulate) asal olan bir dizideki öğelerin toplamını hesaplamak için işlevi. Bu örnekte, `a` olduğu bir `array` nesne ve `is_prime` işlevi, giriş değeri asal olup olmadığını belirler.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, önceki örnekte paralel hale getirmek için naïve yol gösterir. Bu örnekte [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) dizi paralel işlemeye algoritması ve [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) nesnesi erişimi eşitlemek için `prime_sum` değişkeni . Bu örnekte, her iş parçacığı kullanılabilir hale gelmesi paylaşılan kaynak için beklemeniz gerekir çünkü ölçeklenmez.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte bir `combinable` önceki örnek performansını artırmak için nesne. Bu örnek, eşitleme nesneleri ihtiyacını ortadan kaldırır; çünkü ölçeklendirir `combinable` bağımsız olarak, görev gerçekleştirmek her bir iş parçacığı nesnesi sağlar.

A `combinable` nesnesi genellikle iki adımda kullanılır. İlk olarak, paralel olarak iş gerçekleştirerek ayrıntılı hesaplamaları bir dizi oluşturur. Ardından, birleştirebilir (veya azaltmak) nihai sonucu içine hesaplamalar. Bu örnekte [concurrency::combinable::local](reference/combinable-class.md#local) yerel toplamı bir başvuru almak için yöntemi. Ardından kullanır [concurrency::combinable::combine](reference/combinable-class.md#combine) yöntemi ve bir [std::plus](../../standard-library/plus-struct.md) yerel hesaplamalar nihai sonucu halinde birleştirmek için nesne.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki tam bir örnek seri olarak ve paralel asal sayıları iki toplamını hesaplar. Örnek, her iki hesaplamalar gerçekleştirmek için gerekli olan zamanı konsola yazdırır.

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

Aşağıdaki örnek çıktıda dört işlemciye sahip bir bilgisayar içindir.

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-sum-of-primes.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel-toplam-ın-primes.cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Kullanan harita ve işlemleri aynı sonuçları üretmek için azaltma bir örnek için bkz [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)<br/>
[critical_section Sınıfı](../../parallel/concrt/reference/critical-section-class.md)
