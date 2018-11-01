---
title: Derleyici Uyarısı (düzey 1 ve 4) C4112
ms.date: 11/04/2016
f1_keywords:
- C4112
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
ms.openlocfilehash: 3678d0ce5d9eb9568f0272da4173e72502b0557f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655838"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Derleyici Uyarısı (düzey 1 ve 4) C4112

\#Satır numarası ile 1 arasındaki bir tamsayı gerektirir

[#Line](../../preprocessor/hash-line-directive-c-cpp.md) yönergesi belirtir izin verilen aralık dışında bir tam sayı parametresi.

Belirtilen parametre 1'den az ise 1 satır sayacı sıfırlanır. Belirtilen parametre sayısından büyükse *numarası*, derleyici tarafından tanımlanan sınırının, satır sayaç değiştirilmez. Bu düzey 1 uyarısı ANSI Uyumluluğu altında olduğu ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ve düzey 4 uyarısı Microsoft uzantılı ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Aşağıdaki örnek, C4112 oluşturur:

```
// C4112.cpp
// compile with: /W4
#line 0   // C4112, value must be between 1 and number

int main() {
}
```