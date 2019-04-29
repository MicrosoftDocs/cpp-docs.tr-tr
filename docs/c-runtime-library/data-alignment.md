---
title: Veri Hizalama
ms.date: 11/04/2016
f1_keywords:
- data.alignment
helpviewer_keywords:
- data alignment [C++]
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
ms.openlocfilehash: 92b8df81751e01e655e348d5f090705e5194312b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344531"
---
# <a name="data-alignment"></a>Veri Hizalama

Veri hizalama aşağıdaki C çalışma zamanı işlevleri destekler.

## <a name="data-alignment-routines"></a>Veri hizalama rutinleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_aligned_free](../c-runtime-library/reference/aligned-free.md)|İle ayrılmış olan bellek bloğunu serbest bırakır [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_free_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|İle ayrılmış olan bellek bloğunu serbest bırakır [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama).|
|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)|Belirtilen hizalama sınırındaki belleği ayırır.|
|[_aligned_malloc_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Hata ayıklama üst bilgisi için ek alana sahip bir belirtilen hizalama sınırındaki belleği ayırır ve arabellek (yalnızca hata ayıklama sürümü) üzerine yazılır.|
|[_aligned_msize](../c-runtime-library/reference/aligned-msize.md)|Yığında ayrılan bir bellek bloğu boyutu döndürür.|
|[_aligned_msize_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|(Yalnızca hata ayıklama sürümü) yığında ayrılan bir bellek bloğu boyutu döndürür.|
|[_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Belirtilen hizalama sınırındaki belleği ayırır.|
|[_aligned_offset_malloc_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Belirtilen hizalama sınırındaki (yalnızca hata ayıklama sürümü) bellek ayırır.|
|[_aligned_offset_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_offset_realloc_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü).|
|[_aligned_offset_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve 0 belleği başlatır.|
|[_aligned_offset_recalloc_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve belleği 0 (yalnızca hata ayıklama sürümü) başlatır.|
|[_aligned_realloc](../c-runtime-library/reference/aligned-realloc.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_realloc_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü).|
|[_aligned_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve 0 belleği başlatır.|
|[_aligned_recalloc_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|İle ayrılan bir bellek bloğunu boyutunu değiştirir [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ve belleği 0 (yalnızca hata ayıklama sürümü) başlatır.|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
