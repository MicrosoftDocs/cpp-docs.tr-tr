---
title: Derleyici Uyarısı (düzey 3) C4267
ms.date: 11/04/2016
f1_keywords:
- C4267
helpviewer_keywords:
- C4267
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
ms.openlocfilehash: 2ae4b53dfa5050e178bf5ddd366e97c4ff773dd0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161522"
---
# <a name="compiler-warning-level-3-c4267"></a>Derleyici Uyarısı (düzey 3) C4267

' var ': ' size_t ' değerinden ' Type ' öğesine dönüştürme, olası veri kaybı

Derleyici, `size_t` öğesinden daha küçük bir türe dönüştürme algıladı.

Bu uyarıyı onarmak için `type`yerine `size_t` kullanın. Alternatif olarak, en az `size_t`kadar büyük bir integral türü kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4267 oluşturur.

```cpp
// C4267.cpp
// compile by using: cl /W4 C4267.cpp
void Func1(short) {}
void Func2(int) {}
void Func3(long) {}
void Func4(size_t) {}

int main() {
   size_t bufferSize = 10;
   Func1(bufferSize);   // C4267 for all platforms
   Func2(bufferSize);   // C4267 only for 64-bit platforms
   Func3(bufferSize);   // C4267 only for 64-bit platforms
   Func4(bufferSize);   // OK for all platforms
}
```
