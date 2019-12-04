---
title: Derleyici hatası C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: 881165a1100d1c8791ecd5f50eda6a2e9f1650eb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754920"
---
# <a name="compiler-error-c3842"></a>Derleyici hatası C3842

' function ': WinRT veya yönetilen türlerin üye işlevlerinde ' const ' ve ' volatile ' niteleyicileri desteklenmiyor

Windows Çalışma Zamanı veya yönetilen türlerin üye işlevlerinde [const](../../cpp/const-cpp.md) ve [volatile](../../cpp/volatile-cpp.md) desteklenmez.

Aşağıdaki örnek C3842 oluşturur:

```cpp
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```
