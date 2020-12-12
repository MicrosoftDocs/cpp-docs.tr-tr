---
description: 'Daha fazla bilgi: veri hizalama'
title: Veri Hizalama
ms.date: 11/04/2016
f1_keywords:
- data.alignment
helpviewer_keywords:
- data alignment [C++]
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
ms.openlocfilehash: cd942d0ec9c4cdfbedf473bf005123061dece669
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326356"
---
# <a name="data-alignment"></a>Veri Hizalama

Aşağıdaki C çalışma zamanı işlevleri veri hizalamasını destekler.

## <a name="data-alignment-routines"></a>Data-Alignment yordamlar

|Yordam|Kullanın|
|-------------|---------|
|[_aligned_free](../c-runtime-library/reference/aligned-free.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)ayrılmış bir bellek bloğunu serbest bırakır.|
|[_aligned_free_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ayrılmış bir bellek bloğunu serbest bırakır (yalnızca Hata Ayıkla).|
|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)|Belirtilen hizalama sınırında belleği ayırır.|
|[_aligned_malloc_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Bir hata ayıklama üst bilgisi ve üzerine yazma arabellekleri (yalnızca hata ayıklama sürümü) için ek alanla belirtilen hizalama sınırında bellek ayırır.|
|[_aligned_msize](../c-runtime-library/reference/aligned-msize.md)|Yığında ayrılan bellek bloğunun boyutunu döndürür.|
|[_aligned_msize_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Yığında ayrılan bellek bloğunun boyutunu döndürür (yalnızca hata ayıklama sürümü).|
|[_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Belirtilen hizalama sınırında belleği ayırır.|
|[_aligned_offset_malloc_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Belirtilen hizalama sınırında bellek ayırır (yalnızca hata ayıklama sürümü).|
|[_aligned_offset_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)ile ayrılmış bir bellek bloğunun boyutunu değiştirir.|
|[_aligned_offset_realloc_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü) ile ayrılmış bir bellek bloğunun boyutunu değiştirir.|
|[_aligned_offset_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır.|
|[_aligned_offset_recalloc_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır (yalnızca hata ayıklama sürümü).|
|[_aligned_realloc](../c-runtime-library/reference/aligned-realloc.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)ile ayrılmış bir bellek bloğunun boyutunu değiştirir.|
|[_aligned_realloc_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (yalnızca hata ayıklama sürümü) ile ayrılmış bir bellek bloğunun boyutunu değiştirir.|
|[_aligned_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır.|
|[_aligned_recalloc_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|[_Aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) veya [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) ile ayrılmış bir bellek bloğunun boyutunu değiştirir ve belleği 0 olarak başlatır (yalnızca hata ayıklama sürümü).|

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
