---
title: Ara bellek düzenlemesi
ms.date: 04/04/2018
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
ms.openlocfilehash: a79bfdb33d2bff5e18c916a2e116ab03251afdf1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443595"
---
# <a name="buffer-manipulation"></a>Ara bellek düzenlemesi

Bayt bir bayt temelinde bellek alanlarıyla çalışmak için bu yordamları kullanın.

## <a name="buffer-manipulation-routines"></a>Arabellek işleme yordamları

|Yordam|Kullanım|
|-------------|---------|
|[_memccpy](../c-runtime-library/reference/memccpy.md)|Verilen karakter veya verilen karakter sayısı kopyalanana kadar bir arabellekteki karakterleri diğerine kopyala|
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|Belirtilen karakter için arabellekteki belirli karakter sayısı içinde, ilk örneğe işaretçiyi döndürün|
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|İki arabelleki belirtilen karakter sayısını karşılaştırın|
|[memckopyala, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy_s, wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Belirtilen karakter sayısını bir arabellekten diğerine kopyala|
|[_memicmp, _memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|Büyük/küçük harfe bakılmaksızın belirtilen sayıda karakteri iki arabelleki karşılaştırın|
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove_s wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Belirtilen karakter sayısını bir arabellekten diğerine kopyala|
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|Arabellekte belirtilen sayıda bayt başlatmak için verilen karakter kullan|
|[_swab](../c-runtime-library/reference/swab.md)|Verilerin baytlarını değiştirin ve belirtilen konumda depolayın|

Kaynak ve hedef bölgeler çakıştığında, tam kaynağı doğru bir şekilde kopyalamak için yalnızca **memmove** garanti edilir.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
