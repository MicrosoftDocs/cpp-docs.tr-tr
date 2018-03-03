---
title: "Nasıl yapılır: parallel_for_each döngüsü yazma | Microsoft Docs"
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
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 179fa4b055b4743303f5d72ebec851a1d10def93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-parallelforeach-loop"></a>Nasıl yapılır: parallel_for_each Döngüsü Yazma
Bu örnek nasıl kullanılacağını gösterir [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) asal sayılar sayısı işlem için algoritma bir [std::array](../../standard-library/array-class-stl.md) paralel nesne.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki kez asal sayılar dizideki sayısını hesaplar. Örnek ilk kullanır [std::for_each](../../standard-library/algorithm-functions.md#for_each) sayısı seri olarak işlem algoritması. Bu örnek daha sonra kullanır `parallel_for_each` paralel olarak aynı görevi gerçekleştirmenin algoritması. Örnek, ayrıca her iki hesaplamalar gerçekleştirmek için gereken süreyi konsola yazdırır.  
  
 [!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]  
  
 Aşağıdaki örnek çıkış dört işlemciye sahip bir bilgisayar için ' dir.  
  
```Output  
serial version:  
found 17984 prime numbers  
took 6115 ms  
 
parallel version:  
found 17984 prime numbers  
took 1653 ms  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-count-primes.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel-sayısı-primes.cpp**  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Örnek geçirir lambda ifadesi `parallel_for_each` algoritma `InterlockedIncrement` döngü sayaç aynı anda arttırmak için paralel yineleme etkinleştirmek için işlevi. İşlevleri gibi kullanırsanız `InterlockedIncrement` paylaşılan kaynaklara erişimi eşitlemek için performans sorunları kodunuzda sunabilir. Örneğin bir kilidi serbest eşitleme mekanizması kullanabilirsiniz, [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) eşzamanlı paylaşılan kaynaklara erişimi ortadan kaldırmak için sınıf. Kullanan bir örnek `combinable` sınıfı bu şekilde, bkz: [nasıl yapılır: performansı arttırmak için combinable kullanma](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_for_each işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)


