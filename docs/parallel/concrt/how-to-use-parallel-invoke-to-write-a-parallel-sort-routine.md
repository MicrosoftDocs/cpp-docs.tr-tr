---
title: "Nasıl yapılır: paralel sıralama rutini yazmak için parallel_invoke kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96ef9bde4895cfc35ae5858e913389b51829d864
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>Nasıl yapılır: Paralel Sıralama Rutini Yazmak için parallel_invoke Kullanma
Bu belge nasıl kullanılacağını açıklar [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) bitonic Sıralama algoritması performansını artırmak için algoritması. Bitonic Sıralama algoritması yinelemeli giriş sırası daha küçük sıralanmış bölümlere ayırır. Her bölüm işlemi tüm diğer işlemleri bağımsız olduğundan bitonic Sıralama algoritması paralel olarak çalıştırılabilir.  
  
 Bir örneği bitonic sıralama olmasına rağmen bir *ağ sıralama* giriş dizilerini tüm bileşimleri sıralar, bu örnek, uzunlukta olan iki gücünü sıraları sıralar.  
  
> [!NOTE]
>  Bu örnek bir paralel sıralama yordam çizim için kullanır. PPL'de sağlayan yerleşik sıralama algoritmaları de kullanabilirsiniz: [concurrency::parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), ve [concurrency::parallel_ radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Daha fazla bilgi için bkz: [paralel algoritmalar](../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="top"></a>Bölümler  
 Bu belgede aşağıdaki görevleri açıklanmaktadır:  
  
- [Bitonic sıralama seri olarak gerçekleştirme](#serial)  
  
- [Paralel olarak Bitonic sıralama gerçekleştirmek için parallel_invoke kullanma](#parallel)  
  
##  <a name="serial"></a>Bitonic sıralama seri olarak gerçekleştirme  
 Aşağıdaki örnek bitonic Sıralama algoritması seri sürümünü gösterir. `bitonic_sort` İşlevi dizisi iki bölümlere ayırır, o bölümler ters yönde sıralar ve sonuçları birleştirir. Bu işlev kendisini her bölüm sıralamak için iki kez yinelemeli olarak çağırır.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]  
  
 [[Üst](#top)]  
  
##  <a name="parallel"></a>Paralel olarak Bitonic sıralama gerçekleştirmek için parallel_invoke kullanma  
 Bu bölümde nasıl kullanılacağını açıklar `parallel_invoke` bitonic Sıralama algoritması paralel olarak gerçekleştirmek için algoritması.  
  
### <a name="procedures"></a>Yordamlar  
  
##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>Paralel olarak bitonic sıralama algoritmasını gerçekleştirmek için  
  
1.  Ekleme bir `#include` üstbilgi dosyası ppl.h için yönerge.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]  
  
2.  Ekleme bir `using` için yönerge `concurrency` ad alanı.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]  
  
3.  Adlı yeni bir işlev oluşturun `parallel_bitonic_mege`, kullanan `parallel_invoke` iş yapmak için yeterli miktarda ise paralel sıralarında birleştirme algoritması. Aksi halde çağrı `bitonic_merge` sıraları seri olarak birleştirmek için.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]  
  
4.  Önceki adımda ancak için benzer bir işlem gerçekleştirmek `bitonic_sort` işlevi.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]  
  
5.  Aşırı yüklenmiş bir sürümünü oluşturmak `parallel_bitonic_sort` dizi artan düzende sıralar işlevi.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]  
  
 `parallel_invoke` Algoritması arama bağlamda görev dizisini son gerçekleştirerek ek yükünü azaltır. Örneğin, `parallel_bitonic_sort` işlevi, ayrı bir bağlamda ilk görev çalıştırır ve arama bağlamda ikinci görev çalıştırır.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]  
  
 Aşağıdaki tam bir örnek hem seri hem de bitonic Sıralama algoritması paralel sürümleri gerçekleştirir. Örnek, ayrıca her hesaplama gerçekleştirmek için gereken zaman konsola yazdırır.  
  
 [!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]  
  
 Aşağıdaki örnek çıkış dört işlemciye sahip bir bilgisayar için ' dir.  
  
```Output  
serial time: 4353  
parallel time: 1248  
```  
  
 [[Üst](#top)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `parallel-bitonic-sort.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc paralel-bitonic-sort.cpp**  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Bu örnekte `parallel_invoke` algoritması yerine [concurrency::task_group](reference/task-group-class.md) her görev grubu ömrü işlevi genişletmek değil çünkü sınıfı. Kullanmanızı öneririz `parallel_invoke` zaman yapabileceğiniz ek yükü daha az yürütme içerdiğinden `task group` nesneleri ve bu nedenle daha iyi gerçekleştirme kod yazmanıza olanak tanır.  
  
 Yalnızca yapmak için yeterli iş olduğunda bazı algoritmaları paralel sürümleri daha iyi gerçekleştirin. Örneğin, `parallel_bitonic_merge` işlevi çağırır seri sürüm `bitonic_merge`, sırayla 500 veya daha az sayıda öğe varsa. Ayrıca iş miktarına göre Genel sıralama stratejinize planlayabilirsiniz. Örneğin, dizi 500'den az öğeler içeriyorsa aşağıdaki örnekte gösterildiği gibi hızlı Sıralama algoritması seri sürümünü kullanmak için daha etkili olabilir:  
  
 [!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]  
  
 Algoritmayla tüm paralel olarak, profil ve uygun şekilde kodunuzu ayarlamak öneririz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev Paralelliği](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [parallel_invoke işlevi](reference/concurrency-namespace-functions.md#parallel_invoke)

