---
title: "Nasıl yapılır: parallel_for döngüsü yazma | Microsoft Docs"
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
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60ae6b7f496f86bde91801e486315587fb693436
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-parallelfor-loop"></a>Nasıl yapılır: parallel_for Döngüsü Yazma
Bu örnek nasıl kullanılacağı ortaya [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) iki matrisi çarpımını hesaplar için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `matrix_multiply` iki kare matrisi çarpımını hesaplar işlevi.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `parallel_matrix_multiply` kullanan işlevi `parallel_for` paralel olarak dış döngü gerçekleştirmek için algoritması.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]  
  
 Bu örnek yalnızca paralel işleme yükünü yararlanmasını yeterli iş gerçekleştirdiğinden dış döngü parallelizes. İç döngü paralel hale, iç döngü gerçekleştiren iş az miktarda paralel işleme yükünü üstesinden değil çünkü, kazanç performansı alırsınız. Bu nedenle, dış döngü parallelizing yalnızca çoğu sistemlerde eşzamanlılık yararlarını en üst düzeye çıkarmak için en iyi yoludur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki daha kapsamlı örnek performansını karşılaştırır `matrix_multiply` karşı işlev `parallel_matrix_multiply` işlevi.  
  
 [!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]  
  
 Aşağıdaki örnek çıkış dört işlemciye sahip bir bilgisayar için ' dir.  
  
```Output  
serial: 3853  
parallel: 1311  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-matrix-multiply.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel-matris-multiply.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_for işlevi](reference/concurrency-namespace-functions.md#parallel_for)


