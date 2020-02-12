---
title: 'Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
ms.openlocfilehash: cd120d1fbe0f73ed0974efda5a1aa643a1afde9d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143005"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma

Bu konu, paralel kapsayıcıları kullanarak paralel olarak verileri nasıl depolamak ve verilere erişmek için nasıl kullanılacağını gösterir.

Örnek kod, ana ve Carmichael numaralarının kümesini paralel olarak hesaplar. Ardından, her Carmichael numarası için, kod bu sayının asal etmenlerini hesaplar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir giriş değerinin asal sayı olup olmadığını belirleyen `is_prime` işlevini ve giriş değerinin bir Carmichael numarası olup olmadığını belirleyen `is_carmichael` işlevini gösterir.

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, `is_prime` ve `is_carmichael` işlevlerini kullanarak asal ve Carmichael numaralarının kümelerini hesaplar. Örnek, her kümeyi paralel olarak hesaplamak için [eşzamanlılık::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) ve [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmalarını kullanır. Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Bu örnek, daha sonra bir iş kuyruğu olarak bu nesneyi kullanacağı için bir [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) nesnesi kullanır. Daha sonra Asal faktörleri bulmak için bu küme içinde yinelendirilebileceğinden, bir [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) nesnesini, asal sayılar kümesini tutmak için kullanır.

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnek, verilen değerin tüm asal faktörlerini bulmak için deneme bölümünü kullanan `prime_factors_of` işlevini gösterir.

Bu işlev, asal sayıların toplanması yoluyla yinelemek için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını kullanır. `concurrent_vector` nesnesi, paralel döngünün sonuca aynı anda ana faktörleri eklemesini sağlar.

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example"></a>Örnek

Bu örnek, ana etmenlerini hesaplamak için `prime_factors_of` işlevini çağırarak Carmichael sayıları kuyruğundaki her öğeyi işler. Bu işi paralel olarak gerçekleştirmek için bir görev grubu kullanır. Görev grupları hakkında daha fazla bilgi için bkz. [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Bu örnekte, bu sayının dörtten fazla asal faktörü varsa, her bir Carmichael numarası için asal faktörleri yazdırılır.

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki kod, Carmichael sayılarının asal çarpanlarını hesaplamak için paralel kapsayıcılar kullanan tüm örneği gösterir.

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

Bu örnek, aşağıdaki örnek çıktıyı üretir.

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `carmichael-primes.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Carmichael-Primes. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[concurrent_vector Sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[concurrent_queue Sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[parallel_invoke Işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[parallel_for Işlevi](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[task_group Sınıfı](reference/task-group-class.md)
