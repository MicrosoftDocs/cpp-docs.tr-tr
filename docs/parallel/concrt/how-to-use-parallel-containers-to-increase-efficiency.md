---
title: 'Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
ms.openlocfilehash: a9c428ee54853fbd8106901434823e69b402eace
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439188"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma

Bu konuda, verimli bir şekilde depolamak ve paralel verilere erişmek için paralel kapsayıcılar kullanma gösterilmektedir.

Örnek kod asal ve paralel Carmichael sayı kümesini hesaplar. Ardından, her Carmichael numarası için kod ana Etkenler bu sayının hesaplar.

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `is_prime` giriş değeri asal sayı olup olmadığını belirleyen işlev ve `is_carmichael` işlevin giriş değeri bir Carmichael sayı olup olmadığını belirler.

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte `is_prime` ve `is_carmichael` asal ve Carmichael sayıları hesaplamak için işlevleri. Örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) ve [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmaları her işlem için paralel olarak ayarlayın. Paralel algoritmalar hakkında daha fazla bilgi için bkz. [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).

Bu örnekte bir [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) numaraları daha sonra iş sırası olarak o nesne kullanacağınız Carmichael kümesini tutacak nesne. Bunu kullanan bir [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) bunu daha sonra bu ana Etkenler bulmak için yineleme çünkü asal sayıları kümesini tutacak nesne.

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki örnekte gösterildiği `prime_factors_of` deneme bölme verilen değerin tüm ana Etkenler bulmak için kullandığı işlevi.

Bu işlev kullanır [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) asal sayıları toplulukta tekrarlama için algoritma. `concurrent_vector` Nesnesi eşzamanlı olarak ana Etkenler sonucu eklemek paralel bir döngüden sağlar.

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example"></a>Örnek

Bu örnekte çağırarak Carmichael sayı sıradaki her bir öğe işler `prime_factors_of` kendi ana Etkenler hesaplamak için işlevi. Görev grubu bu işi paralel olarak gerçekleştirmek için kullanır. Görev grupları hakkında daha fazla bilgi için bkz. [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Bu örnek, bu sayıyı dörtten fazla ana Etkenler varsa her Carmichael numarası için ana Etkenler yazdırır.

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example"></a>Örnek

Aşağıdaki kodu ana Etkenler Carmichael sayıların hesaplamak için paralel kapsayıcılar kullanan tam bir örnek gösterilmektedir.

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

Bu örnek, aşağıdaki örnek çıktısı üretir.

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `carmichael-primes.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc carmichael primes.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[concurrent_vector Sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[concurrent_queue Sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[task_group sınıfı](reference/task-group-class.md)
