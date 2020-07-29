---
title: Derleyici hatası C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f5780c299eb4da03ece3611ee55062ee7ebcdaae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212793"
---
# <a name="compiler-error-c2273"></a>Derleyici hatası C2273

' Type ': '-> ' işlecinin sağ tarafı olarak geçersizdir

Bir tür, işlecin sağ işleneni olarak görünür `->` .

Bu hata, Kullanıcı tanımlı tür dönüştürmeye erişmeye çalışan bir neden olabilir. **`operator`**-> ile anahtar sözcüğünü kullanın `type` .

Aşağıdaki örnek C2273 oluşturur:

```cpp
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```
