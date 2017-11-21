---
title: "Nasıl yapılır: eşzamanlılık çalışma zamanı kullanmak için özel durum işleme kullanan bir OpenMP döngüsünü dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: beac8ca095388428986569433f0461a505f2a7e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için Özel Durum İşleme Kullanan bir OpenMP Döngüsünü Dönüştürme
Bu örnek bir OpenMP dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) döngü eşzamanlılık çalışma zamanı özel durum mekanizması işleme kullanmak için özel durum işleme gerçekleştirir.  
  
 OpenMP, paralel bir bölgede oluşturulan bir özel durum yakalandı ve aynı bölgede aynı iş parçacığı tarafından işlenir. Varsayılan olarak işlemi sonlandırır işlenmeyen bir özel durum işleyici tarafından paralel bölge çıkışları bir özel durum yakalandı.  
  

 Eşzamanlılık görev grubuna gibi geçirdiğiniz iş işlevi gövdesinde bir özel durum, çalışma zamanında, bir [concurrency::task_group](reference/task-group-class.md) veya [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) nesnesi veya gibi paralel algoritmalar için [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for), çalışma zamanı bu özel durum depolar ve görev grubu veya sonlandırmak için algoritma için bekler bağlamını sıralar. Görev grupları için bekleme bağlam çağıran bağlamdır [concurrency::task_group::wait](reference/task-group-class.md#wait), [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait), [concurrency::task_group::run_and _wait](reference/task-group-class.md#run_and_wait), veya [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait). Paralel bir algoritma için o algoritması olarak da bilinir bağlam bekleme bağlamdır. Çalışma zamanı de alt görev grupları dahil görev grubunda yer alan tüm etkin görevleri durdurur ve henüz başlatılmamış herhangi bir görevi atar.  


  
## <a name="example"></a>Örnek  
 Bu örnek bir OpenMP özel durumları nasıl ele alınacağını gösterir `parallel` bölge ve çağrıda `parallel_for`. `do_work` İşlevi gerçekleştiren başarılı olmaz ve bu nedenle türünde bir özel durum atar bellek ayırma isteği [std::bad_alloc](../../standard-library/bad-alloc-class.md). OpenMP kullanan sürümünü, özel durum oluşturur iş parçacığı de onu catch gerekir. Diğer bir deyişle, her bir yineleme OpenMP paralel döngüsü özel durum işlemesi gerekir. Eşzamanlılık Çalışma zamanı kullanan sürümünde başka bir iş parçacığı tarafından oluşturulan bir özel durum ana iş parçacığı yakalar.  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Using OpenMP...  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
Using the Concurrency Runtime...  
An error of type 'class std::bad_alloc' occurred.  
```  
  
 OpenMP kullanan bu örnek sürümünde, özel durum oluşur ve her döngü tekrarında tarafından gerçekleştirilir. Eşzamanlılık Çalışma zamanı kullanan sürümünde, çalışma zamanı özel depolar, tüm etkin görevleri durdurur, sahip değilse henüz başlatılan tüm görevler atar ve özel durum çağıran bağlamını sıralar `parallel_for`.  
  
 Özel durum oluştu sonra OpenMP kullanan sürüm sonlandırır gerektiriyorsa, diğer döngü yinelemelere hata oluştuğunu göstermek için bir Boole bayrağı kullanabilirsiniz. Konu örnekte olduğu gibi [nasıl yapılır: Bu kullanan eşzamanlılık çalışma zamanı kullanmak için İptali bir OpenMP döngüsünü dönüştürme](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), sonraki döngüsü yinelemeleri aşağıdakini yapın hiçbir şey bayrağı ayarlanmışsa. Özel durum gerçekleştikten sonra eşzamanlılık çalışma zamanı kullanır döngünün devam gerektiriyorsa, buna karşılık, paralel döngü gövdesine özel durumu işler.  
  
 Eşzamanlılık Çalışma zamanı, zaman uyumsuz aracılar ve Basit görevler gibi diğer bileşenlerden özel durumlar aktarım değil. Bunun yerine, varsayılan olarak işlemi sonlandırır işlenmeyen bir özel durum işleyici tarafından işlenmeyen özel durumlar yakalanır. Özel durum işleme hakkında daha fazla bilgi için bkz: [özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Hakkında daha fazla bilgi için `parallel_for` ve diğer paralel algoritmalar için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-exceptions.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc/OpenMP concrt-omp-exceptions.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Özel durum işleme](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md)

