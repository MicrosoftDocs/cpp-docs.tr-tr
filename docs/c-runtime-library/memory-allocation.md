---
title: Bellek Ayırma
ms.date: 11/04/2016
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
ms.openlocfilehash: bcc9865b149c2289f99f6ee13f31179ae58a15e1
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742798"
---
# <a name="memory-allocation"></a>Bellek Ayırma

Ücretsiz olarak ayırmak için bu yordamları kullanın ve belleği yeniden tahsis.

## <a name="memory-allocation-routines"></a>Bellek ayırma rutinleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Yığından bellek ayırma|
|[calloc](../c-runtime-library/reference/calloc.md)|Her bayt 0 ayrılmış bir blok, başlatma, dizi için depolama alanı Ayır|
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Hata ayıklama sürümü, **calloc**; çalışma zamanı kitaplıklarının hata ayıklama sürümlerini yalnızca kullanılabilir|
|[delete işleci](../c-runtime-library/operator-delete-crt.md)|Ayrılan boş blok|
|[delete işleci&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|Ayrılan boş blok|
|[_expand](../c-runtime-library/reference/expand.md)|Bellek bloğunu taşımadan genişlemesine veya|
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Hata ayıklama sürümü, **_expand**; çalışma zamanı kitaplıklarının hata ayıklama sürümlerini yalnızca kullanılabilir|
|[free](../c-runtime-library/reference/free.md)|Ayrılan boş blok|
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Hata ayıklama sürümü, **ücretsiz**; çalışma zamanı kitaplıklarının hata ayıklama sürümlerini yalnızca kullanılabilir|
|[_freea](../c-runtime-library/reference/freea.md)|Yığından ayrılan boş blok|
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|CRT yığın Win32 ele alın.|
|[_heapadd](../c-runtime-library/heapadd.md)|Yığına bellek ekleyin|
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Tutarlılık denetimi yığın|
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Yığında kullanılmayan belleği serbest|
|[_heapset](../c-runtime-library/heapset.md)|Boş yığın girişleri belirtilen değerle doldurun.|
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Yığında her giriş hakkında bilgi döndürür|
|[malloc](../c-runtime-library/reference/malloc.md)|Yığından bellek bloğu ayrılamadı|
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Hata ayıklama sürümü, **malloc**; çalışma zamanı kitaplıklarının hata ayıklama sürümlerini yalnızca kullanılabilir|
|[_msize](../c-runtime-library/reference/msize.md)|Ayrılmış bir blok boyutunu döndürür|
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Hata ayıklama sürümü, **_msize**; çalışma zamanı kitaplıklarının hata ayıklama sürümlerini yalnızca kullanılabilir|
|[new](../c-runtime-library/operator-new-crt.md)|Yığından bellek bloğu ayrılamadı|
|[Yeni&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Yığından bellek bloğu ayrılamadı|
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|Tarafından belirlenen geçerli yeni işleyici rutinini adresini döndürmek **_set_new_handler**|
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|Yeni işleyici modunu belirlediği gösteren dönüş tamsayı **_set_new_mode** için **malloc**|
|[realloc](../c-runtime-library/reference/realloc.md)|Yeni boyut bloğuna yeniden ayırın|
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Hata ayıklama sürümü, **realloc**; çalışma zamanı kitaplıklarının hata ayıklama sürümlerini yalnızca kullanılabilir|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Hata işleme mekanizması etkinleştirme zaman **yeni** işleci başarısız (bellek ayırmak) ve C++ standart kitaplık derlemeyi etkinleştir|
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|İçin yeni işleyici modunu ayarlama **malloc**|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
