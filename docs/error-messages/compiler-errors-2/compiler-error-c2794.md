---
title: Derleyici hatası C2794
ms.date: 11/04/2016
f1_keywords:
- C2794
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
ms.openlocfilehash: 8163a52cd95638e9d24d587f78fb9e20a0da2bb6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739278"
---
# <a name="compiler-error-c2794"></a>Derleyici hatası C2794

' function ': ' class ' öğesinin herhangi bir doğrudan veya dolaylı taban sınıfının üyesi değil

Varolmayan bir üye işlevini çağırmak için [Super](../../cpp/super.md) kullanmaya çalıştınız.

Aşağıdaki örnek C2794 oluşturur

```cpp
// C2794.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::f();  // C2794
   }
};
```
