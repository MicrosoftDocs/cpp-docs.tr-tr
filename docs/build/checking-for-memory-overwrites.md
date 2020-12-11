---
description: 'Hakkında daha fazla bilgi edinin: bellek üzerine yazma denetimi'
title: Bellek Üzerine Yazmalarını Denetleme
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 53361a6aea3de54017be3c966f9500accd21ced1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163177"
---
# <a name="checking-for-memory-overwrites"></a>Bellek Üzerine Yazmalarını Denetleme

Yığın işleme işlevine yapılan bir çağrıda erişim ihlali alırsanız, programınız yığını bozmuş olabilir. Bu durumun yaygın bir belirtisi şöyle olacaktır:

```
Access Violation in _searchseg
```

[_Heapchk](../c-runtime-library/reference/heapchk.md) işlevi, çalışma zamanı kitaplığı yığınının bütünlüğünü doğrulamak için hem hata ayıklama hem de sürüm yapılarında (yalnızca Windows NT) kullanılabilir. `_heapchk` `AfxCheckMemory` Yığın üzerine yazmayı yalıtmak için işleviyle aynı şekilde kullanabilirsiniz, örneğin:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Bu işlev başarısız olursa, yığının bozuk olduğu noktayı yalıtmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın derleme sorunlarını giderme](fixing-release-build-problems.md)
