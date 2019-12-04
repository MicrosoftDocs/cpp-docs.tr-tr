---
title: Derleyici hatası C2274
ms.date: 11/04/2016
f1_keywords:
- C2274
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
ms.openlocfilehash: fd807dedb6c300860611d07212b8fc8952a90a65
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758677"
---
# <a name="compiler-error-c2274"></a>Derleyici hatası C2274

' Type ': '. ' işlecinin sağ tarafı olarak geçersizdir

Bir tür, bir üye erişim (.) işlecinin sağ işleneni olarak görünür.

Bu hata, Kullanıcı tanımlı tür dönüştürmeye erişmeye çalışan bir neden olabilir. Nokta ve `type`arasında `operator` anahtar sözcüğünü kullanın.

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
