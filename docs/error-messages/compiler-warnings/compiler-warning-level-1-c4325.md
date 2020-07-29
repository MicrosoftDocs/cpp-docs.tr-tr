---
title: Derleyici Uyarısı (düzey 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 551680bc1d24097200a1e641bc4238f883ad94dd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230707"
---
# <a name="compiler-warning-level-1-c4325"></a>Derleyici Uyarısı (düzey 1) C4325

> '*section*' standart bölümü öznitelikleri yoksayıldı

## <a name="remarks"></a>Açıklamalar

Standart bir bölümün özniteliklerini değiştiremeyebilirsiniz. Örnek:

```cpp
#pragma section(".sdata", long)
```

Bu, veri türünü `.sdata` veri türüyle kullanan standart bölümün üzerine yazacak **`short`** **`long`** .

Öznitelikleri değiştiremeyebilirsiniz standart bölümler,

- . veri

- . sdata

- . bss

- . sbss

- . metin

- . const

- . sconst

- . rdata

- . srdata

Ek bölümler daha sonra eklenebilir.

## <a name="see-also"></a>Ayrıca bkz.

[kısmı](../../preprocessor/section.md)
