---
title: 'Nasıl yapılır: Eşzamanlılık Çalışma zamanı kullanmak için azaltma değişkeni kullanan bir OpenMP döngüsünü dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: d75e115bdb1d13c9e8f45ed67d0f3993eac1b387
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413963"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma zamanı kullanmak için azaltma değişkeni kullanan bir OpenMP döngüsünü dönüştürme

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

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)
