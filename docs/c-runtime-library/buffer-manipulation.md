---
title: Arabellek işleme | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a7544dfa80ce0c7481846383dd812ce30b78290
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="buffer-manipulation"></a>Ara bellek düzenlemesi

Bir bayt bayt temelinde bellek alanları ile çalışmak için bu yordamları kullanın.

## <a name="buffer-manipulation-routines"></a>Ara bellek düzenlemesi yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_memccpy](../c-runtime-library/reference/memccpy.md)|Karakterleri bir arabelleğinden başka karakter kadar verilen kopyalama veya karakter sayısını kopyalandı|
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|İşaretçi, belirtilen sayıda karakteri, içinde ilk a geçişi, arabellekteki karakterin verilen geri dönün|
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|Belirtilen sayıda karakteri iki arabelleğini Karşılaştır|
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy_s, wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Belirtilen sayıda karakteri bir arabelleğinden kopyalayın|
|[_memicmp, _memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|Belirtilen sayıda servis talebi dikkate almaksızın iki arabellekleri karakterlerden Karşılaştır|
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove_s, wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Belirtilen sayıda karakteri bir arabelleğinden kopyalayın|
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|Belirtilen sayıda baytı arabelleği başlatılamadı karakter verilen kullanın|
|[_swab](../c-runtime-library/reference/swab.md)|Bayt veri değiştirme ve belirtilen konumda depolayın|

Olduğunda kaynak ve hedef alanlarını üst üste, yalnızca **memmove** tam kaynak düzgün kopyalamak için sağlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)
