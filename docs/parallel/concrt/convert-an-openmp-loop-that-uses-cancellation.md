---
title: "Nasıl yapılır: eşzamanlılık çalışma zamanı kullanmak için İptali kullanan bir OpenMP döngüsünü dönüştürme | Microsoft Docs"
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
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3c4d37dfe5182e375e7581d6f5ef8188b922e5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>Nasıl yapılır: Eşzamanlılık Çalışma Zamanı Kullanmak için İptali Kullanan bir OpenMP Döngüsünü Dönüştürme
Bazı paralel döngüler tüm yinelemeleri yürütülmesi gerektirmez. Örneğin, değer bulunduktan sonra için bir değer arayan bir algoritma sonlandırabilir. OpenMP dışında paralel bir döngüden ayırmak için bir mekanizma sağlamaz. Ancak, bir döngü çözüm bulunmuştur belirtmek üzere etkinleştirmek için bir Boole değeri veya bayrağını kullanabilirsiniz. Eşzamanlılık Çalışma zamanı henüz başlatılmamış diğer görevleri iptal etmek bir görev sağlayan işlevselliği sağlar.  
  
 Bu örnek bir OpenMP dönüştürülmesi gösterilmektedir [paralel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[için](../../parallel/openmp/reference/for-openmp.md) döngü çalıştırmak tüm yinelemeleri eşzamanlılık çalışma zamanı iptal mekanizması kullanmak için gerekli değildir.  
  
## <a name="example"></a>Örnek  

 Bu örnek bir paralel sürümü uygulamak için OpenMP ve Eşzamanlılık Çalışma zamanı kullanır [std::any_of](../../standard-library/algorithm-functions.md#any_of) algoritması. Bu örnek OpenMP sürümü bir bayrak koşul karşılanır tüm paralel döngüsü yinelemeleri arasında koordine etmek için kullanır. Eşzamanlılık Çalışma zamanı kullanan sürümünü kullanır [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) koşul karşılandığında ve genel işlemi durdurmak için yöntem.  

  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 Bu örnek şu çıkışı üretir.  
  
```Output  
Using OpenMP...  
9114046 is in the array.  
Using the Concurrency Runtime...  
9114046 is in the array.  
```  
  
 OpenMP kullanan sürümünde döngü tüm yinelemeleri yürütme, hatta bayrağı ayarlandığında. Tüm alt görevler için bir görev olsaydı, ayrıca, bayrağı da iptal iletişim kurmak için bu alt görevler kullanılabilir olması gerekir. Eşzamanlılık Çalışma Zamanı'nda bir görev grubu iptal edildiğinde, çalışma zamanı alt görevler de dahil olmak üzere iş ağacının tümünü iptal eder. [Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritması işlerini yapmak için görevler kullanır. Bu nedenle, bir döngü kök görev iptal ettiğinde hesaplama ağacının tümünü da iptal edildi. Çalışma Zamanı İş ağacının iptal edildiğinde yeni görevler başlatılmaz. Ancak, çalışma zamanı tamamlanması başladıysanız görevlerin olanak sağlar. Bu nedenle, içinde durumunda, `parallel_for_each` algoritması etkin döngüsü yinelemeleri temiz kendi kaynakları.  
  
 Bu örnekte her iki sürümünde de dizi, arama için değer birden çok kopyasını içeriyorsa birden çok döngüsü yinelemeleri her aynı anda sonuç kümesi ve genel işlemi iptal edebilirsiniz. Sorununuzu bir koşul karşılandığında yalnızca görev çalışma gerçekleştirir gerektiriyorsa gibi önemli bir bölümü, bir eşitleme temel kullanabilirsiniz.  
  
 Özel durum işleme PPL'de kullanmak görevleri iptal etmek için de kullanabilirsiniz. İptal etme hakkında daha fazla bilgi için bkz: [PPL'de iptal](cancellation-in-the-ppl.md).  
  
 Hakkında daha fazla bilgi için `parallel_for_each` ve diğer paralel algoritmalar için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `concrt-omp-parallel-any-of.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc/OpenMP concrt-omp-paralel-any-of.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP öğesinden eşzamanlılık çalışma zamanına geçiş](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [PPL'de iptal](cancellation-in-the-ppl.md)   
 [Paralel Algoritmalar](../../parallel/concrt/parallel-algorithms.md)

