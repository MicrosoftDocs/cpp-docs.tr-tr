---
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: ee0a600f4234c3ebf4681ad92b5e3623be5665c3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141271"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme

Bu örnek, Eşzamanlılık Çalışma Zamanı kullanmak için [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesini kullanan bir OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../../parallel/openmp/reference/for-openmp.md) döngüsünün nasıl dönüştürüleceğini gösterir.

OpenMP `reduction` yan tümcesi, paralel bölgenin sonundaki bir azaltma işlemine tabi olan bir veya daha fazla iş parçacığı özel değişkeni belirtmenize olanak tanır. OpenMP önceden bir azaltma işleçleri kümesi tanımlar. Her azaltma değişkeni bir skaler olmalıdır (örneğin, `int`, `long`ve `float`). OpenMP Ayrıca azaltma değişkenlerinin paralel bölgede nasıl kullanıldığı hakkında çeşitli kısıtlamalar tanımlar.

Paralel Desenler kitaplığı (PPL), hassas hesaplamalar gerçekleştirmenizi ve ardından bu hesaplamaları nihai bir sonuçla birleştirmeye imkan tanıyan, yeniden kullanılabilir, iş parçacığı yerel depolama sağlayan [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını sağlar. `combinable` sınıfı, hem skaler hem de karmaşık türlerde davranan bir şablondur. `combinable` sınıfını kullanmak için, paralel bir yapının gövdesinde alt hesaplamalar yapın ve ardından son sonucu oluşturmak için [concurrency:: combinable:: birleştirin](reference/combinable-class.md#combine) veya [concurrency:: combinable:: combine_each](reference/combinable-class.md#combine_each) metodunu çağırın. `combine` ve `combine_each` yöntemleri her bir öğe çiftinin nasıl birleştirileceğini belirten bir *birleştirme işlevi* alır. Bu nedenle, `combinable` sınıfı sabit bir azaltma işleçleri kümesiyle sınırlı değildir.

## <a name="example"></a>Örnek

Bu örnek, ilk 35 Fibonacci numaralarının toplamını hesaplamak için hem OpenMP hem de Eşzamanlılık Çalışma Zamanı kullanır.

[!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]

Bu örnek aşağıdaki çıktıyı üretir.

```Output
Using OpenMP...
The sum of the first 35 Fibonacci numbers is 14930351.
Using the Concurrency Runtime...
The sum of the first 35 Fibonacci numbers is 14930351.
```

`combinable` sınıfı hakkında daha fazla bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya `concrt-omp-fibonacci-reduction.cpp` adlı bir dosyaya yapıştırın ve sonra bir Visual Studio komut Istemi penceresinde aşağıdaki komutu çalıştırın.

> **CL. exe/EHsc/OpenMP concrt-omp-fibonacci-reduction. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)
