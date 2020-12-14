---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1 ve 4) C4112'
title: Derleyici Uyarısı (düzey 1 ve 4) C4112
ms.date: 11/04/2016
f1_keywords:
- C4112
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
ms.openlocfilehash: a4958cbd4537ab9c1f5686383f27414ae366e72b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234559"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Derleyici Uyarısı (düzey 1 ve 4) C4112

\#satır 1 ile sayı arasında bir tamsayı gerektirir

[#Line](../../preprocessor/hash-line-directive-c-cpp.md) yönergesi, izin verilen aralığın dışında bir tamsayı parametresi belirtir.

Belirtilen parametre 1 ' den küçükse satır sayacı 1 ' e sıfırlanır. Belirtilen parametre *sayıdan* büyükse, bu, derleyici tanımlı sınırı olan satır sayacı değiştirilmez. Bu, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında bir düzey 1 uyarıdır ve Microsoft uzantıları ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) ile bir düzey 4 uyarısı olur.

Aşağıdaki örnek C4112 oluşturur:

```cpp
// C4112.cpp
// compile with: /W4
#line 0   // C4112, value must be between 1 and number

int main() {
}
```
