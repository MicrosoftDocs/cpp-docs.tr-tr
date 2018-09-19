---
title: Derleyici Hatası C3531 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 375eb419e3f2f492df328a964eeb1bb77bc0d5dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106857"
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

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)