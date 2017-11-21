---
title: "Paralel Desen kitaplığı (PPL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Parallel Patterns Library (PPL)
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d7850721f5005ac1a1ab47c6557dcd99cede897
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="parallel-patterns-library-ppl"></a>Paralel Desen Kitaplığı (PPL)
Paralel Desen kitaplığı (PPL), ölçeklenebilirlik ve kolaylığı eşzamanlı uygulamaları geliştirmek için kullanım yükseltir kesinlik temelli bir programlama modeli sağlar. PPL'de zamanlama ve kaynak yönetimi bileşenlerine eşzamanlılık çalışma zamanı oluşturur. Uygulama kodunuz ve temel iş parçacığı mekanizması arasında Özet düzeyine genel, tür kullanımı uyumlu algoritmaları ve hareket kapsayıcıları verileri paralel sağlayarak başlatır. PPL'de ayrıca paylaşılan durum alternatifleri sağlayarak ölçeklendirme uygulamaları geliştirmenize olanak tanır.  
  
 PPL'de aşağıdaki özellikleri sağlar:  
  
- *Görev Paralelliği*: paralel olarak birden fazla iş öğeleri (Görevler) yürütmek için Windows iş parçacığı havuzu üzerinde çalıştığı bir mekanizma  
  
- *Paralel algoritmalar*: paralel veri toplulukları yapması eşzamanlılık çalışma üstünde çalışır genel algoritmaları  
  
- *Paralel kapsayıcılar ve nesneler*: öğelerini eşzamanlı güvenli erişim sağlayan genel kapsayıcı türleri  
  
## <a name="example"></a>Örnek  
 PPL'de C++ Standart Kitaplığı benzeyen bir programlama modelidir. Aşağıdaki örnek, PPL'de özelliklerinin çoğu gösterir. Seri olarak ve paralel birkaç Fibonacci numarası hesaplar. Her iki hesaplamalar hareket bir [std::array](../../standard-library/array-class-stl.md) nesnesi. Örnek, ayrıca her iki hesaplamalar gerçekleştirmek için gereken süreyi konsola yazdırır.  
  
 C++ Standart Kitaplığı seri sürümünü kullanır [std::for_each](../../standard-library/algorithm-functions.md#for_each) dizi gezinmesine algoritması ve sonuçları depolayan bir [std::vector](../../standard-library/vector-class.md) nesnesi. Paralel sürüm aynı görevi gerçekleştirir, ancak PPL'de kullanır [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması ve sonuçları depolayan bir [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) nesnesi. `concurrent_vector` Sınıfı eşzamanlı olarak kapsayıcıya yazma erişimi eşitleme gereksinimi olmadan öğeler eklemek, her döngü tekrarında sağlar.  
  
 Çünkü `parallel_for_each` paralel sürümü bu örnek, aynı anda sıralama gerekir davranır `concurrent_vector` nesne seri sürümle aynı sonucu verir.  
  
 Örnek Fibonacci sayıları hesaplamak için naïve yöntemini kullandığını unutmayın; Ancak, bu yöntem eşzamanlılık çalışma zamanı uzun hesaplamalar performansını geliştirebilirsiniz nasıl gösterilmektedir.  
  
 [!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/cpp/parallel-patterns-library-ppl_1.cpp)]  
  
 Aşağıdaki örnek çıkış dört işlemciye sahip bir bilgisayar için ' dir.  
  
```Output  
serial time: 9250 ms  
parallel time: 5726 ms  
 
fib(24): 46368  
fib(26): 121393  
fib(41): 165580141  
fib(42): 267914296  
```  
  
 Her döngü tekrarında tamamlamak için farklı bir süre gerektirir. Performansını `parallel_for_each` son bittikten işlemi tarafından sınırlıdır. Bu nedenle, bu örnek seri ve paralel sürümleri arasında doğrusal performans iyileştirmeleri beklememeniz gerekir.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Görevler ve görev grupları ppl'de rolü açıklanmaktadır.|  
|[Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)|Paralel algoritmalar gibi kullanmayı açıklar `parallel_for` ve `parallel_for_each`.|  
|[Paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)|Çeşitli paralel kapsayıcılar ve PPL tarafından sağlanan nesneleri açıklar.|  
|[PPL'de iptal](cancellation-in-the-ppl.md)|Paralel bir algoritma tarafından gerçekleştirilen işi iptal etme açıklanmaktadır.|  
|[Eşzamanlılık Çalışma zamanı](../../parallel/concrt/concurrency-runtime.md)|Paralel Programlama basitleştiren ve ilgili konulara bağlantılar içerir eşzamanlılık çalışma, açıklar.|

