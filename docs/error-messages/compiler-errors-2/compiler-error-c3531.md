---
title: Derleyici hatası C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 7da9da2daedc79db619f82848dc864d1cb7bd1f1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750097"
---
# <a name="compiler-error-c3531"></a>Derleyici hatası C3531

' symbol ': türü ' Auto ' içeren bir simgenin bir başlatıcısı olmalıdır

Belirtilen değişkenin bir başlatıcı ifadesi yok.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Değişkeni bildirdiğinizde, eşittir işareti sözdizimini kullanan basit bir atama gibi bir başlatıcı ifadesi belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3531 verir çünkü `x1`, `y1, y2, y3`ve `z2` değişkenleri başlatılmamış.

```cpp
// C3531.cpp
// Compile with /Zc:auto
int main()
{
   auto x1;                  // C3531
   auto y1, y2, y3;          // C3531
   auto z1 = 1, z2, z3 = -1; // C3531
   return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)
