---
title: Bellek Üzerine Yazmalarını Denetleme
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 2c59cb96d640df6dcd96b9e0eafbcd325ed475f5
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342250"
---
# <a name="checking-for-memory-overwrites"></a>Bellek Üzerine Yazmalarını Denetleme

Yığın işleme işlevine yapılan bir çağrıda erişim ihlali alırsanız, programınız yığını bozmuş olabilir. Bu durumun yaygın bir belirtisi şöyle olacaktır:

```
Access Violation in _searchseg
```

[_Heapchk](../c-runtime-library/reference/heapchk.md) işlevi, çalışma zamanı kitaplığı yığınının bütünlüğünü doğrulamak için hem hata ayıklama hem de sürüm yapılarında (yalnızca Windows NT) kullanılabilir. Yığın üzerine yazmayı `_heapchk` yalıtmak için `AfxCheckMemory` işleviyle aynı şekilde kullanabilirsiniz, örneğin:

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

Bu işlev başarısız olursa, yığının bozuk olduğu noktayı yalıtmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Yayın Derlemesi Sorunlarını Giderme](fixing-release-build-problems.md)
