---
title: Bellek Üzerine Yazmalarını Denetleme
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 2c59cb96d640df6dcd96b9e0eafbcd325ed475f5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824078"
---
# <a name="checking-for-memory-overwrites"></a>Bellek Üzerine Yazmalarını Denetleme

Yığın işleme işlevi çağrısında bir erişim ihlali alırsanız, programınızı yığın bozdu mümkündür. Bu durumun yaygın bir belirtisi olabilir:

```
Access Violation in _searchseg
```

[_Heapchk](../c-runtime-library/reference/heapchk.md) işlev, hem hata ayıklama ve yayın derlemeleri (yalnızca Windows NT) çalışma zamanı kitaplığı yığının bütünlüğünü doğrulamak için. Kullanabileceğiniz `_heapchk` kadar aynı şekilde `AfxCheckMemory` işlevi bir yığın üzerine yaz, örneğin yalıtmak için:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Şimdiye kadar bu işlev başarısız olursa, yalıtmak hangi noktada yığın bozulmuş gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemesi Sorunlarını Giderme](fixing-release-build-problems.md)
