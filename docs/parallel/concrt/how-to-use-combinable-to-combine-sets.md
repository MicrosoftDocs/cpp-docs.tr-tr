---
title: 'Nasıl yapılır: Kümeleri birleştirmek için combinable kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: bf8a5bee65ea0ba1718c1d4d436b6af3e0b95961
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296104"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Nasıl yapılır: Kümeleri birleştirmek için combinable kullanma

Bu konu nasıl kullanılacağını gösterir [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) kümesindeki asal sayıları hesaplamak için sınıf.

## <a name="example"></a>Örnek

Aşağıdaki örnek, iki kez asal sayıları kümesini hesaplar. Her hesaplama sonucu depolayan bir [std::bitset](../../standard-library/bitset-class.md) nesne. Örnek ilk kümesi seri olarak hesaplar ve ardından kümesi paralel hesaplar. Örnek ayrıca, her iki hesaplamalar gerçekleştirmek için gerekli olduğu süre konsola yazdırır.

Bu örnekte [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritması ve `combinable` iş parçacığı-yerel kümeleri oluşturmak için nesne. Ardından kullanır [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) son kümesine iş parçacığı-yerel kümeleri birleştirmek için yöntemi.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

Aşağıdaki örnek çıktıda dört işlemciye sahip bir bilgisayar içindir.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `parallel-combine-primes.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc paralel-birleştirme-primes.cpp**

## <a name="see-also"></a>Ayrıca bkz.

[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable Sınıfı](../../parallel/concrt/reference/combinable-class.md)<br/>
[combinable::combine_each yöntemi](reference/combinable-class.md#combine_each)
