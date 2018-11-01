---
title: Derleyici Uyarısı (Düzey 3) C4554
ms.date: 11/04/2016
f1_keywords:
- C4554
helpviewer_keywords:
- C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
ms.openlocfilehash: 26251e4acac862e0505ea52e40a7aff2527fd472
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646621"
---
# <a name="compiler-warning-level-3-c4554"></a>Derleyici Uyarısı (Düzey 3) C4554

'operator': olası hata;'için işleç önceliğini denetleyin önceliği netleştirmek için parantez kullanın

Aşağıdaki örnek, C4554 oluşturur:

```
// C4554.cpp
// compile with: /W3 /WX
int main() {
   int a = 0, b = 0, c = 0;
   a = a << b + c;   // C4554
   // probably intended (a << b) + c,
   // but will get a << (b + c)
}
```