---
title: Ara bellek düzenlemesi
ms.date: 04/04/2018
f1_keywords:
- c.memory
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
ms.openlocfilehash: e8a449cbfa6a52ccc2346e2215ce187c09d677e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62290397"
---
# <a name="buffer-manipulation"></a>Ara bellek düzenlemesi

Bir bayt bayt temelinde bellek alanları ile çalışmak için bu yordamları kullanın.

## <a name="buffer-manipulation-routines"></a>Ara bellek düzenlemesi rutinleri

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_memccpy](../c-runtime-library/reference/memccpy.md)|Kopyalama başka bir karakter kadar verilen bir arabellek karakter veya rakam veya karakter sayısını kopyalandı|
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|İşaretçi başlayarak belirtilen sayıda karakteri, içinde ilk yinelenme, belirli bir karakter arabelleği döndürür|
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|Belirtilen sayıda karakteri iki arabellek karşılaştırın|
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy_s, wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Belirtilen sayıda karakteri bir arabellek kopyalayın|
|[_memicmp, _memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|Belirtilen sayıda karakteri çalışması dikkate almaksızın iki arabellek karşılaştırın|
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove_s, wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Belirtilen sayıda karakteri bir arabellek kopyalayın|
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|Belirtilen karakterin belirtilen sayıda baytı arabellekteki başlatmak için kullanın|
|[_swab](../c-runtime-library/reference/swab.md)|Bayt veri değiştirme ve bunları belirli bir konumda depolayın|

Ne zaman kaynak ve hedef alanlarını üst üste, yalnızca **memmove** tam kaynak düzgün bir şekilde kopyalamak için sağlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
