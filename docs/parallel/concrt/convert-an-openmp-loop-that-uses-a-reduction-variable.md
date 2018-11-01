---
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: b58f6025c41091b39375c566d2c1d4b4798437b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633083"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme

Bu örnek bir OpenMP dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) kullanan döngüsünü [azaltma](../../parallel/openmp/reference/reduction.md) eşzamanlılık çalışma zamanı kullanmak için yan tümcesi.

OpenMP `reduction` yan tümcesi bir paralel bölgenin sonunda azaltma işlemi için bir veya daha fazla iş parçacığı özel değişkenler belirtmenize olanak sağlar. OpenMP azaltma işleçleri kümesini önceden belirler. Her bir azaltma değişkeni skaler olması gerekir (örneğin, `int`, `long`, ve `float`). OpenMP da birkaç kısıtlama azaltma değişkenleri bir paralel bölgenin içinde nasıl kullanıldığını tanımlar.

Paralel Desen kitaplığı (PPL) sağlayan [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) ayrıntılı hesaplamalar gerçekleştirin ve ardından bu hesaplamaların bir son birleştirme olanak tanıyan yeniden kullanılabilir, iş parçacığı yerel depolama sağlar sınıfını sonucu. `combinable` Skaler ve karmaşık türlerde işlevi gören bir şablon sınıfıdır. Kullanılacak `combinable` sınıfı, bir paralel yapısı gövdesinde alt hesaplamalar ve sonra çağrı [concurrency::combinable::combine](reference/combinable-class.md#combine) veya [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) nihai sonucu üretmek için yöntemi. `combine` Ve `combine_each` yöntemleri her alır bir *işlev birleştirmek* nasıl her bir öğe çiftinin birleştirileceğini belirtir. Bu nedenle, `combinable` sınıfı sabit azaltma işleçleri kümesini için sınırlı değildir.

## <a name="example"></a>Örnek

Bu örnekte, ilk 35 Fibonacci sayıların toplamını hesaplamak için hem OpenMP hem de eşzamanlılık çalışma zamanı kullanır.

[!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using OpenMP...
The sum of the first 35 Fibonacci numbers is 14930351.
Using the Concurrency Runtime...
The sum of the first 35 Fibonacci numbers is 14930351.
```

Hakkında daha fazla bilgi için `combinable` sınıfı [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-fibonacci-reduction.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

**cl.exe/ehsc/OpenMP concrt-omp-fibonacci-reduction.cpp**

## <a name="see-also"></a>Ayrıca Bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)

