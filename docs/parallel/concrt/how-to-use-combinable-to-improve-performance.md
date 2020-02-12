---
title: 'Nasıl yapılır: Performansı arttırmak için combinable Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
ms.openlocfilehash: db27a791b2b92102118606712db4cbd2920f9619
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142436"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Nasıl yapılır: Performansı arttırmak için combinable Kullanma

Bu örnek, bir [std:: Array](../../standard-library/array-class-stl.md) nesnesindeki sayıların toplamını hesaplamak için [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfının nasıl kullanılacağını gösterir. `combinable` sınıfı, paylaşılan durumu ortadan kaldırarak performansı geliştirir.

> [!TIP]
> Bazı durumlarda, paralel eşleme ([eşzamanlılık::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) ve azaltma ([concurrency:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)), `combinable`üzerinde performans iyileştirmeleri sağlayabilir. Eşleme kullanan bir örnek için, bu örnekle aynı sonuçları üretmek üzere işlemleri azaltır ve bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

## <a name="example---accumulate"></a>Örnek-biriktir

Aşağıdaki örnek, asal olan bir dizideki öğelerin toplamını hesaplamak için [std:: birikme](../../standard-library/numeric-functions.md#accumulate) işlevini kullanır. Bu örnekte, `a` bir `array` nesnesidir ve `is_prime` işlevi giriş değerinin asal olup olmadığını belirler.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example---parallel_for_each"></a>Örnek-parallel_for_each

Aşağıdaki örnek, önceki örneği paralel hale getirmek için Naïve bir yol gösterir. Bu örnek, `prime_sum` değişkenine erişimi eşitlenmek üzere diziyi paralel olarak işlemek için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını ve bir [eşzamanlılık:: critical_section](../../parallel/concrt/reference/critical-section-class.md) nesnesini kullanır. Bu örnek ölçeklenmez çünkü her iş parçacığının paylaşılan kaynağın kullanılabilir hale gelmesini beklemesi gerekir.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example---combinable"></a>Örnek-combinable

Aşağıdaki örnek, önceki örneğin performansını geliştirmek için bir `combinable` nesnesi kullanır. Bu örnek, eşitleme nesneleri gereksinimini ortadan kaldırır; `combinable` nesnesi, her iş parçacığının görevini bağımsız olarak gerçekleştirmesini sağladığından ölçeği ölçeklendirir.

`combinable` nesnesi genellikle iki adımda kullanılır. İlk olarak, işleri paralel olarak gerçekleştirerek ayrıntılı hesaplamalar üreten bir dizi hesaplama üretin. Sonra, hesaplamaları son bir sonuçla birleştirin (veya azaltın). Bu örnek, yerel toplamın başvurusunu almak için [concurrency:: combinable:: Local](reference/combinable-class.md#local) yöntemini kullanır. Ardından, yerel hesaplamaları nihai sonuçla birleştirmek için [concurrency:: combinable:: birleştirme](reference/combinable-class.md#combine) yöntemini ve [std::p lus](../../standard-library/plus-struct.md) nesnesini kullanır.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example---serial-and-parallel"></a>Örnek-seri ve paralel

Aşağıdaki tüm örnek, hem seri olarak hem de paralel olarak ana sayıların toplamını hesaplar. Örnek, her iki hesaplamaları gerçekleştirmek için gereken zamanı konsola yazdırır.

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

Aşağıdaki örnek çıktı, dört işlemcili bir bilgisayar içindir.

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `parallel-sum-of-primes.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Parallel-Sum-of-Primes. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Aynı sonuçları oluşturmak için eşleme ve işlemleri azaltma gibi bir örnek için bkz. [Parallel algoritma](../../parallel/concrt/parallel-algorithms.md).

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)<br/>
[critical_section Sınıfı](../../parallel/concrt/reference/critical-section-class.md)
