---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4325'
title: Derleyici Uyarısı (düzey 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 17e14d4909e4b76d6a0a71d6e77fad1d01e3f41b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311597"
---
# <a name="compiler-warning-level-1-c4325"></a>Derleyici Uyarısı (düzey 1) C4325

> '*section*' standart bölümü öznitelikleri yoksayıldı

## <a name="remarks"></a>Açıklamalar

Standart bir bölümün özniteliklerini değiştiremeyebilirsiniz. Örneğin:

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
