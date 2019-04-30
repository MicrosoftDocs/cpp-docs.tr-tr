---
title: Derleyici Hatası C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: f2fcb75098f18ad113ba68959035b37d9cddd6e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388884"
---
# <a name="compiler-error-c2274"></a>Derleyici Hatası C2274

'type': sağ tarafı olarak geçersizdir '.' işleci

Bir tür, üye erişimi (.) işlecinin sağ işlenen görünür.

Bu hata, bir kullanıcı tanımlı tür dönüştürme erişmeye tarafından kaynaklanabilir. Anahtar sözcüğünü kullanın `operator` dönem arasında ve `type`.

Aşağıdaki örnek, C2286 oluşturur:

```
// C2274.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};

int main() {
   MyClass ClassName;
   int i = ClassName.int();   // C2274
   int j = ClassName.operator int();   // OK
}
```