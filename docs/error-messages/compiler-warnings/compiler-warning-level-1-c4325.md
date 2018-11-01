---
title: Derleyici Uyarısı (düzey 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 293cbbcfe134f6cb4f5e1bf924be7c03fa278833
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492618"
---
# <a name="compiler-warning-level-1-c4325"></a>Derleyici Uyarısı (düzey 1) C4325

> Standart bölümün öznitelikleri '*bölüm*' yoksayıldı

## <a name="remarks"></a>Açıklamalar

Standart bir bölümün özniteliklerini değiştiremezsiniz. Örneğin:

```cpp
#pragma section(".sdata", long)
```

Bunun üzerine yazacak `.sdata` kullanan standart bölüm **kısa** veri türü ile **uzun** veri türü.

Öznitelikleri değil değişebilir standart bölümler dahil,

- .Data

- .sdata

- .BSS

- .sbss

- .Text

- .const

- .sconst

- .rdata

- .srdata

Ek olarak bölümlerde daha sonra eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[section](../../preprocessor/section.md)