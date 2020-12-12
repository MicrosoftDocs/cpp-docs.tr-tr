---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: azaltma değişkeni kullanan bir OpenMP döngüsünü dönüştürme Eşzamanlılık Çalışma Zamanı kullanmak için'
title: 'Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: 131585caf3e06a11ed45bda4b58efa541272006f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325764"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme

Bu örnek, Eşzamanlılık Çalışma Zamanı kullanmak için [azaltma](../openmp/reference/openmp-clauses.md#reduction) yan tümcesini kullanan bir OpenMP [Parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) döngüsünün nasıl dönüştürüleceğini gösterir.

OpenMP `reduction` yan tümcesi, paralel bölgenin sonundaki bir azaltma işlemine tabi olan bir veya daha fazla iş parçacığı özel değişkeni belirtmenize olanak tanır. OpenMP önceden bir azaltma işleçleri kümesi tanımlar. Her azaltma değişkeni bir skaler olmalıdır (örneğin,,, **`int`** **`long`** ve **`float`** ). OpenMP Ayrıca azaltma değişkenlerinin paralel bölgede nasıl kullanıldığı hakkında çeşitli kısıtlamalar tanımlar.

Paralel Desenler kitaplığı (PPL), hassas hesaplamalar gerçekleştirmenizi ve ardından bu hesaplamaları nihai bir sonuçla birleştirmeye imkan tanıyan, yeniden kullanılabilir, iş parçacığı yerel depolama sağlayan [eşzamanlılık:: combinable](../../parallel/concrt/reference/combinable-class.md) sınıfını sağlar. `combinable`Sınıfı, hem skaler hem de karmaşık türlerde davranan bir şablondur. Sınıfını kullanmak için `combinable` , paralel bir yapının gövdesinde alt hesaplamalar yapın ve ardından son sonucu oluşturmak için [concurrency:: combinable:: birleştirin](reference/combinable-class.md#combine) veya [concurrency:: combinable:: combine_each](reference/combinable-class.md#combine_each) metodunu çağırın. `combine`Ve `combine_each` yöntemleri her bir öğe çiftinin nasıl birleştirileceğini belirten bir *birleştirme işlevi* alır. Bu nedenle, `combinable` sınıf sabit bir azaltma işleçleri kümesiyle sınırlı değildir.

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

Sınıfı hakkında daha fazla bilgi için `combinable` bkz. [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="compiling-the-code"></a>Kod Derleniyor

Örnek kodu kopyalayın ve bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `concrt-omp-fibonacci-reduction.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

> **cl.exe/EHsc/OpenMP concrt-omp-fibonacci-reduction. cpp**

## <a name="see-also"></a>Ayrıca bkz.

[OpenMP döngüsünden Eşzamanlılık Çalışma Zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[Paralel Kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)
