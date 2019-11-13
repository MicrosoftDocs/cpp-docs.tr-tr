---
title: Derleyici Uyarısı (düzey 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: c6a62b399aa32ec6caf2e5a9ee6d4c5836601ba4
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965968"
---
# <a name="compiler-warning-level-1-c4566"></a>Derleyici Uyarısı (düzey 1) C4566

' Char ' evrensel karakter adı ile temsil edilen karakter geçerli kod sayfasında (sayfa) gösterilemez

Geçerli ANSI kod sayfanızda her Unicode karakteri temsil edilebilir.

Dar dizeler (bir baytlık karakterler) çok baytlı karakterlere dönüştürülür, geniş dizeler (iki baytlık karakterler) değildir.

Aşağıdaki örnek C4566 oluşturur:

```cpp
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```