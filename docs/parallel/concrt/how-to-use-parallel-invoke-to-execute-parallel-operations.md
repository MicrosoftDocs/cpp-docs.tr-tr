---
title: "Nasıl yapılır: paralel işlemleri yürütmek için parallel_invoke kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2190d7809791fbc66f6070eb3ae721ec1bc0a04f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>Nasıl yapılır: Paralel İşlemleri Yürütmek için parallel_invoke Kullanma
Bu örnek nasıl kullanılacağını gösterir [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) bir paylaşılan veri kaynağı üzerinde birden çok işlemler gerçekleştiren bir program performansını artırmak için algoritması. Hiçbir işlem kaynağını değiştirmek için bunlar kolay bir şekilde paralel olarak çalıştırılabilir.  

  
## <a name="example"></a>Örnek  
 Türünde bir değişken oluşturur aşağıdaki kod örneği göz önünde bulundurun `MyDataType`, bu değişkeni başlatmak için bir işlev çağırır ve bu verileri birden çok uzun işlemleri gerçekleştirir.  
  
 [!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]  
  
 Varsa `lengthy_operation1`, `lengthy_operation2`, ve `lengthy_operation3` işlevleri değiştirmeyin `MyDataType` değişkeni, bu işlevler paralel ek değişiklik olmadan çalıştırılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, paralel olarak çalıştırmak için önceki örnekte değiştirir. `parallel_invoke` Algoritmasını paralel olarak her görev yürütür ve tüm görevler sona erdikten sonra döndürür.  
  
 [!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek indirmeleri *Iliad* Homer gutenberg.org gelen tarafından ve bu dosyada birden çok işlemleri gerçekleştirir. Örnek, ilk olarak bu işlemlerin seri olarak gerçekleştirir ve ardından paralel olarak aynı işlemleri gerçekleştirir.  
  
 [!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir.  
  
```Output  
Downloading 'The Iliad'...  
 
Running serial version... took 953 ms.  
Running parallel version... took 656 ms.  
 
The most common words that have five or more letters are:  
    their (953)  
    shall (444)  
    which (431)  
    great (398)  
    Hector (349)  
    Achilles (309)  
    through (301)  
    these (268)  
    chief (259)  
The longest sequence of words that have the same first letter is:  
    through the tempest to the tented  
The following palindromes appear in the text:  
    spots stops  
    speed deeps  
    keels sleek  
```  
  
 Bu örnekte `parallel_invoke` birden çok çağırmak için algoritma işlevleri aynı veri kaynağı üzerinde bu eylemi. Kullanabileceğiniz `parallel_invoke` paralel olarak değil yalnızca aynı verileri davranan herhangi bir kümesi işlevleri çağırmak için algoritması.  
  
 Çünkü `parallel_invoke` algoritmasını paralel olarak her iş işlevi çağırır, kendi performansını (diğer bir deyişle, çalışma zamanı her işlev ayrı işlemcide işlediğinde) tamamlanması uzun süren işlevi sınırlıdır. Bu örnek, paralel kullanılabilir işlemci sayısından daha fazla görevleri gerçekleştiriyorsa, birden çok görev her işlemcide çalıştırabilirsiniz. Bu durumda, performans tamamlanması uzun süren görevler grubunda tarafından sınırlıdır.  
  
 Bu örnek paralel olarak üç görev gerçekleştirdiğinden üçten fazla işlemcilere sahip bilgisayarlarda ölçeklemek için performans beklememeniz gerekir. Daha fazla performansı artırmak için uzun soluklu görevlerin daha küçük görevlere bölün ve bu görevlerin paralel olarak çalıştır.  
  
 Kullanabileceğiniz `parallel_invoke` algoritması yerine [concurrency::task_group](reference/task-group-class.md) ve [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) iptalleri desteğine gereksiniminiz yoksa sınıfları. Kullanımını karşılaştıran bir örnek `parallel_invoke` görev grupları ile karşılaştırması algoritması bkz [nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-word-mining.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc /MD/DUNICODE /D_AFXDLL paralel-word-mining.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)


