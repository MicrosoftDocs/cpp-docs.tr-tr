---
title: Derleyici Hatası C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: 2737f9078e1c17358e3c975a5c3f8b6d211fd308
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165781"
---
# <a name="compiler-error-c2575"></a>Derleyici Hatası C2575

'identifier': yalnızca üye işlevler ve tabanlar sanal olabilir

Bir genel işlev veya sınıf bildirilen `virtual`. Buna izin verilmez.

Aşağıdaki örnek, C2575 oluşturur:

```
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```