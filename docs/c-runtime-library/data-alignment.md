---
title: Veri hizalama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: data.alignment
dev_langs: C++
helpviewer_keywords: data alignment [C++]
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f1fa9d918e0032a0ca718ec9c2c97b83f1d5462
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-alignment"></a>Veri Hizalama
Veri hizalama aşağıdaki C çalışma zamanı işlevleri destekler.  
  
### <a name="data-alignment-routines"></a>Veri hizalama yordamları  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[_aligned_free](../c-runtime-library/reference/aligned-free.md)|İle ayrılmış bellek bloğu boşaltır [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|  
|[_aligned_free_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|İle ayrılmış bellek bloğu boşaltır [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama).|  
|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)|Belirtilen hizalama sınırında bellek ayırır.|  
|[_aligned_malloc_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Hata ayıklama başlığı için belirtilen hizalama sınırında ek alan ile bellek ayırır ve arabellekler (yalnızca hata ayıklama sürümü) üzerine yazın.|  
|[_aligned_msize](../c-runtime-library/reference/aligned-msize.md)|Yığın ayrılan bellek bloğu boyutu döndürür.|  
|[_aligned_msize_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Yığın (yalnızca hata ayıklama sürümü) ayrılan bellek bloğu boyutu döndürür.|  
|[_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Belirtilen hizalama sınırında bellek ayırır.|  
|[_aligned_offset_malloc_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Belirtilen hizalama sınırında (yalnızca hata ayıklama sürümü) bellek ayırır.|  
|[_aligned_offset_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|  
|[_aligned_offset_realloc_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü).|  
|[_aligned_offset_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve 0 belleği başlatır.|  
|[_aligned_offset_recalloc_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve bellek 0 (yalnızca hata ayıklama sürümü) başlatır.|  
|[_aligned_realloc](../c-runtime-library/reference/aligned-realloc.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|  
|[_aligned_realloc_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü).|  
|[_aligned_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve 0 belleği başlatır.|  
|[_aligned_recalloc_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve bellek 0 (yalnızca hata ayıklama sürümü) başlatır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)