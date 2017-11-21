---
title: "Nasıl yapılır: eşleme gerçekleştirme ve işlemleri paralel azaltmak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6648933aa972ec1391afe2d9cecd37b15ad53f9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Nasıl yapılır: Eşleme Gerçekleştirme ve İşlemleri Paralel Olarak Azaltma

Bu örnek nasıl kullanılacağını gösterir [concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) ve [concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) algoritmaları ve [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)dosyaları sözcükleri yinelendiğini saymak için sınıf.  
  
 A *harita* işlemi dizisindeki her bir değeri bir işlev uygular. A *azaltmak* işlemi sıradaki bir değer halinde birleştirir. C++ Standart Kitaplığı kullanabilirsiniz [std::transform](../../standard-library/algorithm-functions.md#transform) ve [std::accumulate](../../standard-library/numeric-functions.md#accumulate) eşleme gerçekleştirme ve işlemleri azaltmak için işlevleri. Bununla birlikte, çoğu sorunu için performansı artırmak için kullanabileceğiniz `parallel_transform` paralel eşleme işlemi gerçekleştirmek için algoritma ve `parallel_reduce` paralel olarak azaltma işlemi gerçekleştirmek için algoritması. Bazı durumlarda, kullandığınız `concurrent_unordered_map` eşleme ve azaltma tek bir işlemde gerçekleştirmek için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek dosyaları sözcükleri oluşumlarını sayar. Kullandığı [std::vector](../../standard-library/vector-class.md) iki dosyaların içeriğini temsil etmek için. Eşleme işlemi her vektör her sözcüğün oluşumları hesaplar. Küçültme işlemi her iki vektörlerinin sözcük sayıları birikir.  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-map-reduce.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel-map-reduce.cpp**  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Bu örnekte, kullandığınız `concurrent_unordered_map` sınıfı — concurrent_unordered_map.h—to içinde tanımlandığı eşleme gerçekleştirme ve tek bir işlemde azaltın.  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 Genellikle, yalnızca dış veya iç döngü paralel hale. İç döngü paralel hale nispeten daha az sayıda dosya varsa ve her dosya birçok sözcükler içeriyor. Dış döngü paralel hale göreli olarak çok sayıda dosya varsa ve her dosya birkaç sözcükler içeriyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_transform işlevi](reference/concurrency-namespace-functions.md#parallel_transform)   
 [parallel_reduce işlevi](reference/concurrency-namespace-functions.md#parallel_reduce)   
 [concurrent_unordered_map sınıfı](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
