---
description: 'Daha fazla bilgi edinin: nasıl yapılır: verimliliği artırmak için paralel kapsayıcılar kullanma'
title: 'Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
ms.openlocfilehash: 6e416da7b1cdcbe1a9b3073569cf4dda6434ceea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341561"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma

Bu konu, paralel kapsayıcıları kullanarak paralel olarak verileri nasıl depolamak ve verilere erişmek için nasıl kullanılacağını gösterir.

Örnek kod, ana ve Carmichael numaralarının kümesini paralel olarak hesaplar. Ardından, her Carmichael numarası için, kod bu sayının asal etmenlerini hesaplar.

## <a name="example-determine-if-an-input-value-is-a-prime-number"></a>Örnek: bir giriş değerinin asal sayı olup olmadığını belirleme

Aşağıdaki örnek, `is_prime` bir giriş değerinin asal sayı olup olmadığını belirleyen işlevini ve `is_carmichael` giriş değerinin bir Carmichael numarası olup olmadığını belirleyen işlevi gösterir.

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example-compute-prime-and-carmichael-numbers"></a>Örnek: Ana ve Carmichael numaralarını hesaplama

Aşağıdaki örnek, `is_prime` ve işlevlerini kullanarak `is_carmichael` asal ve Carmichael numaralarının kümelerini hesaplar. Örnek, her kümeyi paralel olarak hesaplamak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) ve [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmalarını kullanır. Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Bu örnek, daha sonra bir iş kuyruğu olarak bu nesneyi kullanacağı için bir [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) nesnesi kullanır. Daha sonra Asal faktörleri bulmak için bu küme içinde yinelendirilebileceğinden, bir [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) nesnesini, asal sayılar kümesini tutmak için kullanır.

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example-find-all-prime-factors-of-a-given-value"></a>Örnek: belirli bir değere ait tüm Asal faktörleri bul

Aşağıdaki örnek, `prime_factors_of` belirtilen değerin tüm asal faktörlerini bulmak için deneme bölümünü kullanan işlevini gösterir.

Bu işlev, asal sayıların toplanması yoluyla yinelemek için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını kullanır. `concurrent_vector`Nesnesi paralel döngünün sonuca aynı anda ana faktörleri eklemesini sağlar.

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example-processes-each-element-in-the-queue-of-carmichael-numbers"></a>Örnek: Carmichael numaraları sırasındaki her öğeyi Işler

Bu örnek, `prime_factors_of` ana etmenlerini hesaplamak için işlevini çağırarak Carmichael sayıları kuyruğundaki her öğeyi işler. Bu işi paralel olarak gerçekleştirmek için bir görev grubu kullanır. Görev grupları hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Bu örnekte, bu sayının dörtten fazla asal faktörü varsa, her bir Carmichael numarası için asal faktörleri yazdırılır.

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example-finished-parallel-container-code-sample"></a>Örnek: biten paralel kapsayıcı kodu örneği

Aşağıdaki kod, Carmichael sayılarının asal çarpanlarını hesaplamak için paralel kapsayıcılar kullanan tüm örneği gösterir.

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `carmichael-primes.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Carmichael-Primes. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[concurrent_vector sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[concurrent_queue sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[parallel_for Işlevi](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[task_group sınıfı](reference/task-group-class.md)
