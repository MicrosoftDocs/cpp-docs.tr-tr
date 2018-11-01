---
title: Derleyici Hatası C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: a61a69aca53f7f8996d0261a57b749930ecc01cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638353"
---
# <a name="compiler-error-c3842"></a>Derleyici Hatası C3842

'function': WinRT yönetilen tür veya üye işlevlerinde 'const' ve 'volatile' niteleyicileri desteklenmiyor

[const](../../cpp/const-cpp.md) ve [geçici](../../cpp/volatile-cpp.md) Windows çalışma zamanı yönetilen tür veya üye işlevleri desteklenmez.

Aşağıdaki örnek, C3842 oluşturur:

```
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```