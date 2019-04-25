---
title: Derleyici Hatası C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 96fd97aa5021b7e1bc5226162f9c54ff4d6211b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175233"
---
# <a name="compiler-error-c3160"></a>Derleyici Hatası C3160

'işaretçisi': WinRT sınıfı ya da yönetilen bir veri üyesi bu türe sahip olamaz

İç çöp toplama işaretçileri, iç yönetilen bir kısmını veya WinRT sınıfa işaret edebilir. Çünkü bunlar tam nesne işaretçisi yavaş çalışır ve atık toplayıcı tarafından özel işlem gerektiren bir sınıfın üyeleri olarak iç yönetilen işaretçiler bildiremezsiniz.

Aşağıdaki örnek, C3160 oluşturur:

```
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
