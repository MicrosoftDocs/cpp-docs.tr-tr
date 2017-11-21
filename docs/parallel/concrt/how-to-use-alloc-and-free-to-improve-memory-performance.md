---
title: "Nasıl yapılır: ayırma kullanın ve bellek performansını artırmak ücretsiz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b375c5b3ec9f35050d7da4ae03139f6e809172cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>Nasıl yapılır: Bellek Performansını Artırmak için Alloc ve Free Kullanma

Bu belge nasıl kullanılacağını gösterir [concurrency::Alloc](reference/concurrency-namespace-functions.md#alloc) ve [concurrency::Free](reference/concurrency-namespace-functions.md#free) bellek performansını artırmak için işlevleri. Üç farklı türleri için paralel bir dizinin öğeleri ters çevirmek için gereken süreyi karşılaştırır her belirtin `new` ve `delete` işleçler.  

  
 `Alloc` Ve `Free` birden çok iş parçacığı sık her ikisi de çağırdığınızda işlevler en yararlı `Alloc` ve `Free`. Çalışma zamanı her iş parçacığı için ayrı bir önbellek tutar; Bu nedenle, çalışma zamanı bellek kilitleri ya da bellek engelleri kullanmadan yönetir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, her belirttiğiniz üç tür gösterir `new` ve `delete` işleçler. `new_delete` Sınıfını kullanan genel `new` ve `delete` işleçleri `malloc_free` sınıfını kullanan C çalışma zamanı [malloc](../../c-runtime-library/reference/malloc.md) ve [ücretsiz](../../c-runtime-library/reference/free.md) işlevler ve `Alloc_Free` Eşzamanlılık Çalışma zamanı sınıfı kullanır `Alloc` ve `Free` işlevleri.  
  
 [!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `swap` ve `reverse_array` işlevleri. `swap` İşlevi belirtilen dizinlerini dizisi içeriğini değiştirir. Geçici bir değişken için yığın gelen bellek ayırır. `reverse_array` İşlevi uzun bir diziye oluşturur ve bu dizide birkaç kez paralel tersine çevirmek için gereken süreyi hesaplar.  
  
 [!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği `wmain` için gereken süreyi hesaplar işlevi `reverse_array` hareket etmesine işlevi `new_delete`, `malloc_free`, ve `Alloc_Free` türleri, her biri farklı bellek ayırma şemasını kullanır.  
  
 [!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]  
  
## <a name="example"></a>Örnek  
 Tam bir örnek aşağıda verilmiştir.  
  
 [!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]  
  
 Bu örnek, dört işlemciye sahip bir bilgisayar için aşağıdaki örnek çıktı üretir.  
  
```Output  
Took 2031 ms with new/delete.  
Took 1672 ms with malloc/free.  
Took 656 ms with Alloc/Free.  
```  
  
 Bu örnekte, türü kullanan `Alloc` ve `Free` işlevleri sağlayan en iyi bellek performansı çünkü `Alloc` ve `Free` işlevleri sık ayırma ve birden çok bellekten bloklarını boşaltma için iyileştirilmiş iş parçacığı sayısı.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Örnek kodu kopyalayın ve bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `allocators.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe /EHsc allocators.cpp**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Yönetimi işlevleri](../../parallel/concrt/memory-management-functions.md)   
 [Alloc işlevi](reference/concurrency-namespace-functions.md#alloc)   
 [Free işlevi](reference/concurrency-namespace-functions.md#free)

