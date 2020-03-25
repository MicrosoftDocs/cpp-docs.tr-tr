---
title: Derleyici Uyarısı (düzey 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: e0a13761b0657d054065358994638779817dad6a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163030"
---
# <a name="compiler-warning-level-1-c4325"></a>Derleyici Uyarısı (düzey 1) C4325

> '*section*' standart bölümü öznitelikleri yoksayıldı

## <a name="remarks"></a>Açıklamalar

Standart bir bölümün özniteliklerini değiştiremeyebilirsiniz. Örneğin:

```cpp
#pragma section(".sdata", long)
```

Bu, **uzun** veri türü ile **kısa** veri türünü kullanan `.sdata` standart bölümünün üzerine yazar.

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

[section](../../preprocessor/section.md)
