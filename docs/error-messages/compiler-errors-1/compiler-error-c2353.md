---
title: Derleyici hatası C2353
ms.date: 11/04/2016
f1_keywords:
- C2353
helpviewer_keywords:
- C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
ms.openlocfilehash: 89a4a4030e6a38f3a2d95c38b76132c9db0695a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759964"
---
# <a name="compiler-error-c2353"></a>Derleyici hatası C2353

özel durum belirtimine izin verilmiyor

Yönetilen sınıfların üye işlevlerinde özel durum belirtimlerine izin verilmez.

Aşağıdaki örnek C2353 oluşturur:

```cpp
// C2353.cpp
// compile with: /clr /c
ref class X {
   void f() throw(int);   // C2353
   void f();   // OK
};
```
