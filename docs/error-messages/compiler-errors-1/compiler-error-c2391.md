---
title: Derleyici hatası C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: f000287c5934a39d56342bce0f6c9ca2c69e2297
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212741"
---
# <a name="compiler-error-c2391"></a>Derleyici hatası C2391

' tanımlayıcı ': ' Friend ' tür tanımı sırasında kullanılamaz

**`friend`** Bildirim, bir bütün sınıf bildirimi içerir. Bir **`friend`** bildirim, bir üye işlevi veya bir ayrıntılı tür belirleyicisi belirtebilir, ancak bir sınıf bildirimi içeremez.

Aşağıdaki örnek C2326 oluşturur:

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```
