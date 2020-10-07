---
title: Bellek Ayırma
ms.date: 11/04/2016
description: Belleği tahsis etmek, serbest bırakmak ve yeniden ayırmak için kullanılan Microsoft C çalışma zamanı işlevlerini listeler.
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
ms.openlocfilehash: 4e01d62fdfd24416f78254a849b3feea97883281
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806506"
---
# <a name="memory-allocation"></a>Bellek ayırma

Belleği ayırmak, serbest bırakmak ve yeniden ayırmak için bu yordamları kullanın.

## <a name="memory-allocation-routines"></a>Bellek ayırma yordamları

|Yordam|Kullanın|
|-------------|---------|
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Yığından bellek ayır|
|[calloc](../c-runtime-library/reference/calloc.md)|Ayrılan bloktaki her baytı 0 ' a başlatarak dizi için depolama alanını ayırın|
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|**Calloc**öğesinin hata ayıklama sürümü yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[işleç silme, işleç silme&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|Serbest ayrılmış blok|
|[_expand](../c-runtime-library/reference/expand.md)|Bellek bloğunu taşımadan genişletme veya küçültme|
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|**_Expand**hata ayıklama sürümü; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[Süz](../c-runtime-library/reference/free.md)|Serbest ayrılmış blok|
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Hata ayıklama sürümü **ücretsiz**; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[_freea](../c-runtime-library/reference/freea.md)|Yığından boş ayrılmış blok|
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|CRT yığınının Win32 TANıTıCıSıNı alın.|
|[_heapadd](../c-runtime-library/heapadd.md)|Yığına bellek ekleme|
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Yığını tutarlılık denetimi|
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Kullanılmayan belleği yığında serbest bırak|
|[_heapset](../c-runtime-library/heapset.md)|Boş yığın girdilerini belirtilen değere doldur|
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Yığındaki her giriş hakkında bilgi döndür|
|[malloc](../c-runtime-library/reference/malloc.md)|Yığından bellek bloğunu ayır|
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|**Malloc**hata ayıklama sürümü; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[_msize](../c-runtime-library/reference/msize.md)|Ayrılmış bloğun dönüş boyutu|
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|**_Msize**hata ayıklama sürümü; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[Yeni, yeni&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Yığından bellek bloğunu ayır|
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|**_Set_new_handler** tarafından ayarlanan geçerli yeni işleyici yordamının dönüş adresi|
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|**Malloc** için **_set_new_mode** tarafından ayarlanan yeni işleyici modunu belirten tamsayı döndür|
|[realloc](../c-runtime-library/reference/realloc.md)|Bloğu yeni boyuta göre yeniden tahsis edin|
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|**Realloc**'ın hata ayıklama sürümü; yalnızca çalışma zamanı kitaplıklarının hata ayıklama sürümlerinde kullanılabilir|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|**`new`** Operatör başarısız olduğunda (bellek ayırmak için) ve C++ standart kitaplıklarının derlemesini etkinleştirmek için hata işleme mekanizmasını etkinleştirin|
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|**Malloc** için yeni işleyici modu ayarla|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
