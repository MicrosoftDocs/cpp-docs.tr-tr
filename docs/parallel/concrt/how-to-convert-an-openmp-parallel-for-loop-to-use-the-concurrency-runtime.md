---
title: "Nasıl yapılır: eşzamanlılık çalışma zamanı kullanmak üzere döngü bir OpenMP paralelini dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a27e07884b4ada54f694136ea2fbca474c9d214d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak üzere Döngü için bir OpenMP paralelini Dönüştürme

Bu örnek OpenMP kullanan temel bir döngü dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) ve [için](../../parallel/openmp/reference/for-openmp.md) eşzamanlılık çalışma zamanı kullanmak için yönergeleri [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) algoritma.  
  
## <a name="example"></a>Örnek  
 Bu örnek, rastgele değerler dizisi asal sayılar sayısını hesaplamak için OpenMP ve Eşzamanlılık Çalışma zamanı kullanır.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Using OpenMP...  
found 107254 prime numbers.  
Using the Concurrency Runtime...  
found 107254 prime numbers.  
```  
  
 `parallel_for` Algoritması ve OpenMP 3.0 izin dizin türü işaretli bir tam sayı türe veya imzasız tamsayı türü olmalıdır. `parallel_for` Algoritması ayrıca kılar belirtilen aralık işaretli bir türe taşması değil emin. OpenMP sürümleri 2.0 ve 2.5, yalnızca imzalı tam sayı dizin türü için izin verir. OpenMP dizini aralığın da doğrulamaz.  
  
 Eşzamanlılık Çalışma zamanı kullanan bu örnek sürümünü de kullanan bir [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) yerine nesne [atomik](../../parallel/openmp/reference/atomic.md) gerek kalmadan sayaç değeri artırmak için yönergesi Eşitleme.  
  
 Hakkında daha fazla bilgi için `parallel_for` ve diğer paralel algoritmalar için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md). Hakkında daha fazla bilgi için `combinable` sınıfı için bkz: [paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="example"></a>Örnek  

 Bu örnek önceki bir hareket değiştirir bir [std::array](../../standard-library/array-class-stl.md) yerel bir dizi nesnesi yerine. Tam sayı dizin türleri yalnızca imzalı için OpenMP sürümleri 2.0 ve 2.5 izin verdiğinden bir `parallel_for` yapı, C++ Standart Kitaplığı kapsayıcı paralel öğelerini erişmek için yineleyiciler kullanamazsınız. Paralel Desen kitaplığı (PPL) sağlar [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) C++ Standart Kitaplığı tarafından sağlanan gibi yinelemeli bir kapsayıcısı üzerinde paralel görevleri gerçekleştiren algoritması. Aynı bölümleme mantığını kullanır, `parallel_for` algoritması kullanır. `parallel_for_each` Algoritması benzer C++ Standart Kitaplığı [std::for_each](../../standard-library/algorithm-functions.md#for_each) hariç algoritması `parallel_for_each` algoritması görevler eşzamanlı olarak yürütür.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-count-primes.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc/OpenMP concrt-omp-sayısı-primes.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [Paralel Kapsayıcılar ve Nesneler](../../parallel/concrt/parallel-containers-and-objects.md)

