---
title: 'Nasıl yapılır: parallel_for_each döngüsü yazma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c68afa77c46e4d57ef01984b44ecb6f4951494a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427088"
---
# <a name="how-to-write-a-parallelforeach-loop"></a>Nasıl yapılır: parallel_for_each Döngüsü Yazma

Bu örnek nasıl kullanılacağını gösterir [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) sayısı içinde asal sayıları hesaplamak için algoritması bir [std::array](../../standard-library/array-class-stl.md) paralel nesne.

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki kez bir dizideki asal sayıları sayısını hesaplar. İlk örnekte [std::for_each](../../standard-library/algorithm-functions.md#for_each) algoritmasını seri olarak işlem sayısı. Ardından örnekte `parallel_for_each` paralel olarak aynı görevi gerçekleştirmek için kullanılan algoritma. Örnek ayrıca, her iki hesaplamalar gerçekleştirmek için gerekli olduğu süre konsola yazdırır.

[!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]

Aşağıdaki örnek çıktıda dört işlemciye sahip bir bilgisayar içindir.

```Output
serial version:
found 17984 prime numbers
took 6115 ms

parallel version:
found 17984 prime numbers
took 1653 ms
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-count-primes.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel-count-primes.cpp**

## <a name="robust-programming"></a>Güçlü Programlama

Örnek geçirir lambda ifadesi `parallel_for_each` algoritmasını `InterlockedIncrement` döngü sayacı aynı anda artırmak için paralel yineleme etkinleştirmek için işlevi. İşlevleri gibi kullanırsanız `InterlockedIncrement` paylaşılan kaynaklara erişimi eşitlemek için kodunuzda performans sorunları sunabilir. Örneğin bir kilidi serbest eşitleme mekanizması kullanabilirsiniz, [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sınıfı, paylaşılan kaynaklar için eş zamanlı erişim ortadan kaldırmak için. Kullanan bir örnek için `combinable` sınıfı bu şekilde [nasıl yapılır: performansı arttırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for_each işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)

