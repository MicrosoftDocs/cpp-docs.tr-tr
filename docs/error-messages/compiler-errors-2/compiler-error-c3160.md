---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3160'
title: Derleyici hatası C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 863670f30a6a911977ead0d541dcba825e4f124a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242333"
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
