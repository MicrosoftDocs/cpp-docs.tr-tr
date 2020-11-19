---
title: Bellek Ayırma
ms.date: 11/18/2020
description: Belleği ayırmak, serbest bırakmak ve yeniden ayırmak için kullanılan Microsoft C çalışma zamanı işlevlerinin listesi.
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.openlocfilehash: 39be48a4ebdf8ee917395d7b743846196200878d
ms.sourcegitcommit: e82e13b80150fcb27a1387018aafb00d99a3827a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94920748"
---
# <a name="memory-allocation"></a>Bellek ayırma

Bu yordamlar belleği ayırır, serbest ve yeniden ayırır.

## <a name="memory-allocation-routines"></a>Bellek ayırma yordamları

|Yordam|Kullanın|
|-------------|---------|
|[`_alloca`](../c-runtime-library/reference/alloca.md), [`_malloca`](../c-runtime-library/reference/malloca.md)|Yığından bellek ayır|
|[`calloc`](../c-runtime-library/reference/calloc.md)|Bir dizi ayırın ve öğelerini 0 (sıfır) olarak başlatın|
|[`_calloc_dbg`](../c-runtime-library/reference/calloc-dbg.md)|Hata ayıklama sürümü **`calloc`** . Yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[`operator delete`, `operator delete[]`](../c-runtime-library/delete-operator-crt.md)|Yığında ayrılan boş bellek |
|[`_expand`](../c-runtime-library/reference/expand.md)|Bir bellek bloğunu taşımadan genişletme veya küçültme|
|[`_expand_dbg`](../c-runtime-library/reference/expand-dbg.md)|Hata ayıklama sürümü **`_expand`** . Yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[`free`](../c-runtime-library/reference/free.md)|Yığında ayrılan boş bellek|
|[`_free_dbg`](../c-runtime-library/reference/free-dbg.md)|Hata ayıklama sürümü **`free`** . Yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[`_freea`](../c-runtime-library/reference/freea.md)|Yığında ayrılan boş bellek|
|[`_get_heap_handle`](../c-runtime-library/reference/get-heap-handle.md)|`HANDLE`C çalışma zamanı (CRT) yığınına bir Win32 alın.|
|[`_heapadd`](../c-runtime-library/heapadd.md)|Yığına bellek ekleme|
|[`_heapchk`](../c-runtime-library/reference/heapchk.md)|Yığına tutarlılık denetimi yapın|
|[`_heapmin`](../c-runtime-library/reference/heapmin.md)|Yığında kullanılmayan belleği serbest bırakma|
|[`_heapset`](../c-runtime-library/heapset.md)|Serbest yığın girdilerini bir değer ile doldur|
|[`_heapwalk`](../c-runtime-library/reference/heapwalk.md)|Yığındaki her giriş hakkında bilgi alın|
|[`malloc`](../c-runtime-library/reference/malloc.md)|Yığından bellek ayır|
|[`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md)|Hata ayıklama sürümü **`malloc`** ; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[`_msize`](../c-runtime-library/reference/msize.md)|Ayrılmış bellek bloğunun boyutunu döndürür|
|[`_msize_dbg`](../c-runtime-library/reference/msize-dbg.md)|Hata ayıklama sürümü **`_msize`** ; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[`new`, `new[]`](../c-runtime-library/new-operator-crt.md)|Yığından bir bellek bloğu ayırın|
|[`_query_new_handler`](../c-runtime-library/reference/query-new-handler.md)|Tarafından ayarlanan geçerli yeni işleyici yordamının adresini al **`_set_new_handler`**|
|[`_query_new_mode`](../c-runtime-library/reference/query-new-mode.md)|İçin tarafından ayarlanan yeni işleyici modunu Al **`_set_new_mode`****`malloc`**|
|[`realloc`](../c-runtime-library/reference/realloc.md)|Bir bloğu yeni bir boyuta yeniden tahsis edin|
|[`_realloc_dbg`](../c-runtime-library/reference/realloc-dbg.md)|Hata ayıklama sürümü **`realloc`** ; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md)|**`new`** Operatör bellek ayıramadığında hata işleme mekanizmasını etkinleştirin ve C++ standart kitaplıklarının derlemesini etkinleştirin|
|[`_set_new_mode`](../c-runtime-library/reference/set-new-mode.md)|İçin yeni işleyici modunu ayarla **`malloc`**|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)