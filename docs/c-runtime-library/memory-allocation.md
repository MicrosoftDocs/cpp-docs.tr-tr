---
title: "Bellek ayırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e419cbd30b523121ae1902b49a25d60c0b9d21eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memory-allocation"></a>Bellek Ayırma
Belleği yeniden tahsis ve ücretsiz olarak ayırmak için bu yordamları kullanın.  
  
### <a name="memory-allocation-routines"></a>Bellek ayırma yordamları  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Yığınından bellek ayırma|  
|[calloc](../c-runtime-library/reference/calloc.md)|0 ayrılmış bloğundaki her bir bitini başlatma dizisi için depolama alanı Ayır|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Hata ayıklama sürümü `calloc`; çalışma zamanı kitaplıkları hata ayıklama sürümlerinde yalnızca kullanılabilir|  
|[delete işleci](../c-runtime-library/operator-delete-crt.md)|Boş ayrılan bloğu|  
|[delete işleci &#91; &#93;](../c-runtime-library/delete-operator-crt.md)|Boş ayrılan bloğu|  
|[_expand](../c-runtime-library/reference/expand.md)|Bellek bloğu taşımadan genişlemesine veya|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Hata ayıklama sürümü `_expand`; çalışma zamanı kitaplıkları hata ayıklama sürümlerinde yalnızca kullanılabilir|  
|[free](../c-runtime-library/reference/free.md)|Boş ayrılan bloğu|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Hata ayıklama sürümü `free`; çalışma zamanı kitaplıkları hata ayıklama sürümlerinde yalnızca kullanılabilir|  
|[_freea](../c-runtime-library/reference/freea.md)|Yığından boş ayrılan bloğu|  
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|Win32 TUTAMACINI CRT yığın alın.|  
|[_heapadd](../c-runtime-library/heapadd.md)|Bellek için yığın ekleyin|  
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Yığın tutarlılığını denetleyin|  
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Yığınındaki kullanılmayan belleği serbest|  
|[_heapset](../c-runtime-library/heapset.md)|Belirtilen değerle boş yığın girişleri doldurun|  
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Öbeğe her giriş hakkında bilgi döndürür|  
|[malloc](../c-runtime-library/reference/malloc.md)|Bellek bloğu yığınından ayırın|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Hata ayıklama sürümü `malloc`; çalışma zamanı kitaplıkları hata ayıklama sürümlerinde yalnızca kullanılabilir|  
|[_msize](../c-runtime-library/reference/msize.md)|Ayrılmış blok boyutunu döndürme|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Hata ayıklama sürümü `_msize`; çalışma zamanı kitaplıkları hata ayıklama sürümlerinde yalnızca kullanılabilir|  
|[new](../c-runtime-library/operator-new-crt.md)|Bellek bloğu yığınından ayırın|  
|[Yeni &#91; &#93;](../c-runtime-library/new-operator-crt.md)|Bellek bloğu yığınından ayırın|  
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|Tarafından belirlenen geçerli yeni işleyici yordamının dönüş adresi`_set_new_handler`|  
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|Tarafından belirlenen yeni işleyici modu gösteren dönüş tamsayı `_set_new_mode` için`malloc`|  
|[realloc](../c-runtime-library/reference/realloc.md)|Yeni bir boyut blok yeniden ayırma|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Hata ayıklama sürümü `realloc`; çalışma zamanı kitaplıkları hata ayıklama sürümlerinde yalnızca kullanılabilir|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Hata işleme mekanizmasını etkinleştirmek zaman `new` işleci başarısız (bellek ayırmak) ve C++ Standart Kitaplığı derlemeyi etkinleştir|  
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|İçin yeni işleyici modunu ayarlama`malloc`|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)