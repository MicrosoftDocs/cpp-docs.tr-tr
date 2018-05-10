---
title: 'Nasıl yapılır: parallel_for döngüsü yazma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4f3121130cd4b2871e3e3df73dd4117f946caca
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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


