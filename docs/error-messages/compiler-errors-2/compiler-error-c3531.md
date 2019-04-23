---
title: Derleyici Hatası C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 6961d99d1a0d7d0ea063aee5544a1009af2547c7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031267"
---
# <a name="compiler-error-c3531"></a>Derleyici Hatası C3531

'symbol': türü, 'auto' içeren bir simgenin bir Başlatıcısı olmalıdır

Belirtilen değişken, bir başlatıcı ifadesinin yok.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Değişken bildirdiğinizde, eşittir işareti sözdizimi kullanan basit bir atama gibi bir başlatıcı ifadesinin belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çünkü C3531 verir değişkenleri `x1`, `y1, y2, y3`, ve `z2` başlatılmaz.

```
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