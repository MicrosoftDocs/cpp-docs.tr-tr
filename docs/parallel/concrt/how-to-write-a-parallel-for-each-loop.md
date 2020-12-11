---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: parallel_for_each döngüsü yazma'
title: 'Nasıl yapılır: parallel_for_each Döngüsü Yazma'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
ms.openlocfilehash: cb80173d3d4c78fe4d46f017d60af2c3c6659096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112238"
---
# <a name="how-to-write-a-parallel_for_each-loop"></a>Nasıl yapılır: parallel_for_each Döngüsü Yazma

Bu örnek, bir [std:: Array](../../standard-library/array-class-stl.md) nesnesindeki asal sayıların sayısını paralel olarak hesaplamak için [eşzamanlılık::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasının nasıl kullanılacağını gösterir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir dizideki iki kez asal sayı sayısını hesaplar. Örnek öncelikle sayıyı seri olarak hesaplamak için [std:: for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasını kullanır. Örnek daha sonra `parallel_for_each` aynı görevi paralel olarak gerçekleştirmek için algoritmayı kullanır. Örnek ayrıca konsola her iki hesaplama da için gereken zamanı da yazdırır.

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

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `parallel-count-primes.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc Parallel-Count-Primes. cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Örneğin algoritmaya geçirdiği lambda ifadesi, `parallel_for_each` `InterlockedIncrement` sayacı aynı anda artırmak için döngünün paralel yinelemelerini etkinleştirmek üzere işlevini kullanır. `InterlockedIncrement`Paylaşılan kaynaklara erişimi eşzamanlı hale getirmek için gibi işlevleri kullanıyorsanız, kodunuzda performans sorunları sunabilir. Paylaşılan kaynaklara eşzamanlı erişimi ortadan kaldırmak için, örneğin [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı gibi bir kilit ücretsiz eşitleme mekanizması kullanabilirsiniz. Bu şekilde sınıfını kullanan bir örnek için `combinable` bkz. [nasıl yapılır: combinable kullanma performansı geliştirmek için](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).

## <a name="see-also"></a>Ayrıca bkz.

[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for_each Işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)
