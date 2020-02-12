---
title: 'Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: 7ccbb3e8bad5c4d3b6f4177afbfdba3e200681a5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142123"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Nasıl yapılır: Kümeleri Birleştirmek için combinable Kullanma

Bu konuda, asal sayıların kümesini hesaplamak için [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfının nasıl kullanılacağı gösterilmektedir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki kez asal sayılar kümesini hesaplar. Her hesaplama sonucu bir [std:: bitset](../../standard-library/bitset-class.md) nesnesinde depolar. Örnek öncelikle kümeyi bir kez hesaplar ve ardından kümeyi paralel olarak hesaplar. Örnek ayrıca konsola her iki hesaplama da için gereken zamanı da yazdırır.

Bu örnek, iş parçacığı yerel kümeleri oluşturmak için [eşzamanlılık::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritmasını ve bir `combinable` nesnesini kullanır. Daha sonra, iş parçacığı yerel kümelerini son küme olarak birleştirmek için [concurrency:: combinable:: combine_each](reference/combinable-class.md#combine_each) yöntemini kullanır.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

Aşağıdaki örnek çıktı, dört işlemcili bir bilgisayar içindir.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `parallel-combine-primes.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc Parallel-Combine-Primes. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)<br/>
[combinable:: combine_each yöntemi](reference/combinable-class.md#combine_each)
