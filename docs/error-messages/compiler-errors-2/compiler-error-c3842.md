---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3842'
title: Derleyici hatası C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: dd5cff7b4a381ca976138720d8af192d594c7836
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255424"
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
