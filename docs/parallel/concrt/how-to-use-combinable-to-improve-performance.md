---
title: 'Nasıl yapılır: performansı arttırmak için combinable kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3185ee9f7546e6927197d2e3452ea4cf86f9ab5c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692096"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Nasıl yapılır: Performansı arttırmak için combinable Kullanma
Bu örnek nasıl kullanılacağını gösterir [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) sayıların toplamını hesaplamak için sınıf bir [std::array](../../standard-library/array-class-stl.md) asal olan nesne. `combinable` Sınıfı, paylaşılan durum ortadan kaldırarak performansını artırır.  
  
> [!TIP]
>  Bazı durumlarda, paralel eşleme ([concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) ve azaltma ([eşzamanlılık:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) üzerinden performans iyileştirmeleri sağlayabilir `combinable`. Kullandığı eşleme ve bu örnek aynı sonuçları üretmek için işlemlerini azaltmak bir örnek için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır [std::accumulate](../../standard-library/numeric-functions.md#accumulate) asal olan bir dizi öğelerin toplamını hesaplamak için işlevi. Bu örnekte, `a` olan bir `array` nesne ve `is_prime` işlevi, giriş değerini asal olup olmadığını belirler.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## <a name="example"></a>Örnek  

 Aşağıdaki örnek, önceki örnekte paralel hale naïve şekilde gösterir. Bu örnekte [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) paralel dizi işlemek için algoritma ve [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) erişimi eşitlemek için nesne `prime_sum` değişken . Her iş parçacığı kullanılabilir hale gelmesi paylaşılan kaynak için beklemeniz gerekir çünkü bu örnek ölçeklenmez.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanan bir `combinable` önceki örnek performansını artırmak için nesne. Bu örnek eşitleme nesneleri gereksinimini ortadan kaldırır; çünkü ölçeklendirir `combinable` nesne bağımsız olarak kendi görevi gerçekleştirmek her bir iş parçacığı sağlar.  
  
 A `combinable` nesnesi genellikle iki adımda kullanılır. İlk olarak, bir dizi hassas hesaplamalar paralel iş gerçekleştirerek üretir. Ardından, birleştirme (veya azaltmak) nihai sonucu içine hesaplamalar. Bu örnekte [concurrency::combinable::local](reference/combinable-class.md#local) yerel toplam başvuru elde etmek için yöntemi. Daha sonra kullanır [concurrency::combinable::combine](reference/combinable-class.md#combine) yöntemi ve [std::plus](../../standard-library/plus-struct.md) yerel hesaplamalar nihai sonucu halinde birleştirmek için nesne.  

  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki tam bir örnek asal sayılar hem toplamını seri olarak ve paralel hesaplar. Örnek, her iki hesaplamalar gerçekleştirmek için gereken süreyi konsola yazdırır.  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 Aşağıdaki örnek çıkış dört işlemciye sahip bir bilgisayar için ' dir.  
  
```Output  
1709600813  
serial time: 6178 ms  
 
1709600813  
parallel time: 1638 ms  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-sum-of-primes.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel-sum-in-primes.cpp**  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Kullandığı eşleme ve aynı sonuçlar işlemlerini azaltmak bir örnek için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable sınıfı](../../parallel/concrt/reference/combinable-class.md)   
 [critical_section Sınıfı](../../parallel/concrt/reference/critical-section-class.md)
