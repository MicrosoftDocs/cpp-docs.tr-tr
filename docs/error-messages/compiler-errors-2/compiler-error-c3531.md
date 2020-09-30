---
title: Derleyici hatası C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 4537c6c76814f2aeb8f8d62579caec86785de252
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510144"
---
# <a name="compiler-error-c3531"></a>Derleyici hatası C3531

' symbol ': türü ' Auto ' içeren bir simgenin bir başlatıcısı olmalıdır

Belirtilen değişkenin bir başlatıcı ifadesi yok.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Değişkeni bildirdiğinizde, eşittir işareti sözdizimini kullanan basit bir atama gibi bir başlatıcı ifadesi belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek,, `x1` ve değişkenleri,, ve Için C3531 verir `y1, y2, y3` `z2` .

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

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)
