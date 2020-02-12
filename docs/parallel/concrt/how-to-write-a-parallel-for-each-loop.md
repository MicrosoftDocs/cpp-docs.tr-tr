---
title: 'Nasıl yapılır: parallel_for_each Döngüsü Yazma'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
ms.openlocfilehash: 10c281b7db92e2706b20a1c7377fcdb9d924152d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141881"
---
# <a name="how-to-write-a-parallel_for_each-loop"></a>Nasıl yapılır: parallel_for_each Döngüsü Yazma

Bu örnek, bir [std:: Array](../../standard-library/array-class-stl.md) nesnesindeki asal sayıların sayısını paralel olarak hesaplamak için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasının nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dizideki iki kez asal sayı sayısını hesaplar. Örnek öncelikle sayıyı seri olarak hesaplamak için [std:: for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasını kullanır. Örnek daha sonra aynı görevi paralel olarak gerçekleştirmek için `parallel_for_each` algoritmasını kullanır. Örnek ayrıca konsola her iki hesaplama da için gereken zamanı da yazdırır.

[!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]

Aşağıdaki örnek çıktı, dört işlemcili bir bilgisayar içindir.

```Output
serial version:
found 17984 prime numbers
took 6115 ms

parallel version:
found 17984 prime numbers
took 1653 ms
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `parallel-count-primes.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Parallel-Count-Primes. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Örneğin `parallel_for_each` algoritmasına geçirdiği lambda ifadesi, sayacı aynı anda artırmak için döngünün paralel yinelemelerini etkinleştirmek üzere `InterlockedIncrement` işlevini kullanır. Paylaşılan kaynaklara erişimi eşzamanlı hale getirmek için `InterlockedIncrement` gibi işlevler kullanıyorsanız, kodunuzda performans sorunları sunabilir. Paylaşılan kaynaklara eşzamanlı erişimi ortadan kaldırmak için, örneğin [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı gibi bir kilit ücretsiz eşitleme mekanizması kullanabilirsiniz. `combinable` sınıfını bu şekilde kullanan bir örnek için bkz. [nasıl yapılır: performansı artırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for_each Işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)
