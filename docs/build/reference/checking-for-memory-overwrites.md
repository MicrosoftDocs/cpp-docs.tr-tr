---
title: Bellek Üzerine Yazmalarını Denetleme
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: ff900c7366a28d19d3b90cbd4a6d9ee732e4ce02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621565"
---
# <a name="checking-for-memory-overwrites"></a>Bellek Üzerine Yazmalarını Denetleme

Yığın işleme işlevi çağrısında bir erişim ihlali alırsanız, programınızı yığın bozdu mümkündür. Bu durumun yaygın bir belirtisi olabilir:

```
Access Violation in _searchseg
```

[_Heapchk](../../c-runtime-library/reference/heapchk.md) işlev, hem hata ayıklama ve yayın derlemeleri (yalnızca Windows NT) çalışma zamanı kitaplığı yığının bütünlüğünü doğrulamak için. Kullanabileceğiniz `_heapchk` kadar aynı şekilde `AfxCheckMemory` işlevi bir yığın üzerine yaz, örneğin yalıtmak için:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Şimdiye kadar bu işlev başarısız olursa, yalıtmak hangi noktada yığın bozulmuş gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)