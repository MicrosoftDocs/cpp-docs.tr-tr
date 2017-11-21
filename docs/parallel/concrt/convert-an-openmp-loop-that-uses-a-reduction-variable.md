---
title: "Nasıl yapılır: eşzamanlılık çalışma zamanı kullanmak için azaltma değişkeni kullanan bir OpenMP döngüsünü dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5bc485d148c80725f2b9a2b93c37110cc5d08a9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Azaltma Değişkeni Kullanan bir OpenMP Döngüsünü Dönüştürme
Bu örnek bir OpenMP dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) kullanan döngüsünü [azaltma](../../parallel/openmp/reference/reduction.md) eşzamanlılık çalışma zamanı kullanmak için yan tümcesi.  
  
 OpenMP `reduction` yan tümcesi konu paralel bölge sonunda azaltma işlemi için bir veya daha fazla iş parçacığı özel değişkenlerini belirtmenize olanak sağlar. OpenMP azaltma işleçleri bir dizi önceden belirler. Her azaltma değişken bir skaler olmalıdır (örneğin, `int`, `long`, ve `float`). OpenMP azaltma değişkenleri paralel bir bölgede nasıl kullanıldığını birkaç kısıtlamaları da tanımlar.  
  
 Paralel Desen kitaplığı (PPL) sağlar [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) hassas hesaplamalar ve ardından bu hesaplamaların son birleştirmek sağlayan yeniden kullanılabilir, iş parçacığı yerel depolama sağlar sınıfı sonucu. `combinable` Skaler ve karmaşık türlerde görevi gören bir şablon bir sınıftır. Kullanılacak `combinable` sınıfı, paralel yapı gövdesinde alt hesaplamalar ve ardından çağrısı [concurrency::combinable::combine](reference/combinable-class.md#combine) veya [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) nihai sonucu oluşturmak için yöntem. `combine` Ve `combine_each` yöntemlerinin her ele bir *işlevi birleştirmek* nasıl her çiftlerini birleştirileceğini belirtir. Bu nedenle, `combinable` sınıf azaltma işleçleri sabit bir dizi sınırlı değildir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, ilk 35 Fibonacci sayıların toplamını hesaplamak için OpenMP ve Eşzamanlılık Çalışma zamanı kullanır.  
  
 [!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Using OpenMP...  
The sum of the first 35 Fibonacci numbers is 14930351.  
Using the Concurrency Runtime...  
The sum of the first 35 Fibonacci numbers is 14930351.  
```  
  
 Hakkında daha fazla bilgi için `combinable` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-fibonacci-reduction.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc/OpenMP concrt-omp-fibonacci-reduction.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)

