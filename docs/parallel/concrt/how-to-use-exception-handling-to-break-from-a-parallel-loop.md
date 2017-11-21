---
title: "Nasıl yapılır: özel durum paralel bir döngüden kurtulmak için işleme kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b75c1779ae4f660acb925b07e857c1883f43fe8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>Nasıl yapılır: Paralel Bir Döngüden Kurtulmak için Özel Durum İşlemeyi Kullanma
Bu konuda, temel ağaç yapısı için bir arama algoritması yazma gösterilmektedir.  
  
 Konu [iptal](cancellation-in-the-ppl.md) iptal paralel desen Kitaplığı'ndaki rolünü açıklar. Özel durum işleme kullanımını kullanımını daha paralel iş iptal daha az verimli yoludur [concurrency::task_group::cancel](reference/task-group-class.md#cancel) ve [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) yöntemleri. Görevler veya paralel algoritmalar kullanır ancak sağlamaz bir üçüncü taraf kitaplık içine çağırdığınızda ancak, iş iptal etmek için özel durum işleme kullanımını olduğu uygun bir senaryodur bir `task_group` veya `structured_task_group` iptal etmek için nesne.  

  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, temel bir gösterir `tree` bir veri öğesi ve alt düğümleri listesini içeren türü. Aşağıdaki bölümde gövdesini gösterilmektedir `for_all` yöntemi, art arda her alt düğümünde iş işlevi gerçekleştirir.  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `for_all` yöntemi. Kullandığı [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmasını paralel ağacının her düğümde bir iş işlevi gerçekleştirir.  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `search_for_value` sağlanan değer arar işlevi `tree` nesnesi. Bu işlev geçirir `for_all` sağlanan değer içeren bir ağaç düğümü bulduğunda, oluşturur çalışma işlevi bir yöntem.  
  
 Varsayımında `tree` sınıfı bir üçüncü taraf kitaplığı tarafından sağlanan ve onu değiştiremezsiniz. Bu durumda, özel durum işleme uygun kullanılır çünkü `for_all` yöntem sağlamaz bir `task_group` veya `structured_task_group` çağırana nesnesi. Bu nedenle, iş işlevi doğrudan kendi üst görev grubu iptal etmek alamıyor.  
  
 Bir görev grubuna sağladığınız çalışma işlevi bir özel durum oluşturduğunda, çalışma zamanı (tüm alt görev grupları dahil) görev grubundaki tüm görevler durdurur ve henüz başlatılmamış herhangi bir görevi atar. `search_for_value` İşlev kullanan bir `try` - `catch` blok özel durum yakalama ve sonucu konsola yazdırır.  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir `tree` nesne ve paralel çeşitli değerleri arar. `build_tree` İşlevi, bu konunun devamında gösterilir.  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 Bu örnekte [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) değerleri paralel arama algoritması. Bu algoritma hakkında daha fazla bilgi için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki tam bir örnek değerleri temel ağaç yapısındaki aramak için özel durum işleme kullanır.  
  
 [!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]  
  
 Bu örnekte aşağıdaki örnek çıkışı üretir.  
  
```Output  
Found a node with value 32614.  
Found a node with value 86131.  
Did not find node with value 17522.  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `task-tree-search.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc görev-ağaç-search.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [Özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)   
 [task_group sınıfı](reference/task-group-class.md)   
 [structured_task_group sınıfı](../../parallel/concrt/reference/structured-task-group-class.md)   
 [parallel_for_each işlevi](reference/concurrency-namespace-functions.md#parallel_for_each)


