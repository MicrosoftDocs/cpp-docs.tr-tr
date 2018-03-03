---
title: "Arabellek işleme | Microsoft Docs"
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
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 942d0f881ed6453921f6082024be5247a1bb1b65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="buffer-manipulation"></a>Ara Bellek Düzenlemesi
Bir bayt bayt temelinde bellek alanları ile çalışmak için bu yordamları kullanın.  
  
### <a name="buffer-manipulation-routines"></a>Ara bellek düzenlemesi yordamları  
  
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
  
 Olduğunda kaynak ve hedef alanlarını üst üste, yalnızca `memmove` tam kaynak düzgün kopyalamak için sağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)