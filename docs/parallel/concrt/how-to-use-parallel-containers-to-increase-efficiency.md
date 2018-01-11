---
title: "Nasıl yapılır: etkinliği arttırmak için paralel kapsayıcılar kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64b191b97bcf4b5f1607cde56fac8fefd1505c7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Nasıl yapılır: Etkinliği Arttırmak için Paralel Kapsayıcılar Kullanma
Bu konu, paralel kapsayıcılar verimli bir şekilde depolamak ve paralel verilere erişmek için nasıl kullanılacağını gösterir.  
  
 Örnek kod asal ve paralel Carmichael numaraları kümesini hesaplar. Ardından, her Carmichael numarası için kod prime Etkenler bu sayının hesaplar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `is_prime` bir giriş değerinin asal sayı olup olmadığını belirler, işlevi ve `is_carmichael` giriş değeri bir Carmichael sayı olup olmadığını belirleyen işlev.  
  
 [!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `is_prime` ve `is_carmichael` asal ve Carmichael numaraları kümesini hesaplamak için işlevleri. Örnek kullanır [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) ve [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) her işlem için algoritmaları paralel olarak ayarlayın. Paralel algoritmalar hakkında daha fazla bilgi için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
 Bu örnekte bir [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) Carmichael kümesi tutacak nesne numaralar daha sonra bir iş sırası olarak söz konusu nesne kullanacağınız için. Kullandığı bir [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) , daha sonra bu prime Etkenler bulmak için ayarlanmış yinelemek çünkü asal sayılar kümesi tutacak nesne.  
  
 [!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `prime_factors_of` deneme bölme verilen değer tüm prime faktörleri bulmak için kullandığı işlevi.  
  
 Bu işlev kullanır [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) asal sayılar toplulukta tekrarlama için algoritması. `concurrent_vector` Nesnesi aynı anda prime Etkenler sonucu eklemek paralel döngü sağlar.  
  
 [!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]  
  
## <a name="example"></a>Örnek  
 Bu örnek çağırarak Carmichael numaraları sıra her bir öğe işler `prime_factors_of` prime Etkenler hesaplamak için işlevi. Bu iş paralel olarak gerçekleştirmek için bir görev grubu kullanır. Görev grupları hakkında daha fazla bilgi için bkz: [görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Bu sayıyı dörtten fazla prime Etkenler varsa bu örnekte her Carmichael numarası için prime Etkenler yazdırır.  
  
 [!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod Carmichael sayıların prime Etkenler hesaplamak için paralel kapsayıcılar kullanan tam bir örnek gösterilir.  
  
 [!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir.  
  
```Output  
Prime factors of 9890881 are: 7 11 13 41 241.  
Prime factors of 825265 are: 5 7 17 19 73.  
Prime factors of 1050985 are: 5 13 19 23 37.  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `carmichael-primes.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc carmichael-primes.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel kapsayıcılar ve nesneler](../../parallel/concrt/parallel-containers-and-objects.md)   
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [concurrent_vector sınıfı](../../parallel/concrt/reference/concurrent-vector-class.md)   
 [concurrent_queue sınıfı](../../parallel/concrt/reference/concurrent-queue-class.md)   
 [parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)   
 [parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)   
 [task_group sınıfı](reference/task-group-class.md)
