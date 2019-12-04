---
title: Derleyici hatası C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 4d6f415c8b3c8275ac45ef4d4313021100d9a833
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755154"
---
# <a name="compiler-error-c3160"></a>Derleyici hatası C3160

' Pointer ': yönetilen veya WinRT sınıfının veri üyesi bu türe sahip olamaz

İç çöp toplama işaretçileri, yönetilen veya WinRT sınıfının iç öğesini işaret edebilir. Bunlar, tam nesne işaretçilerinden daha yavaş olduklarından ve çöp toplayıcı tarafından özel işleme gerektirdiklerinden, iç yönetilen işaretçileri bir sınıfın üyesi olarak bildiremezsiniz.

Aşağıdaki örnek C3160 oluşturur:

```cpp
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```
