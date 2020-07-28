---
title: Derleyici hatası C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: 5907664ba367d6e4005698e112d0a19f3a2a26e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220385"
---
# <a name="compiler-error-c2274"></a>Derleyici hatası C2274

' Type ': '. ' işlecinin sağ tarafı olarak geçersizdir

Bir tür, bir üye erişim (.) işlecinin sağ işleneni olarak görünür.

Bu hata, Kullanıcı tanımlı tür dönüştürmeye erişmeye çalışan bir neden olabilir. **`operator`** Nokta ve arasındaki anahtar sözcüğü kullanın `type` .

Aşağıdaki örnek C2286 oluşturur:

```cpp
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
