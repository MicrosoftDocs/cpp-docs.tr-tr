---
title: Derleyici hatası C2216
ms.date: 11/04/2016
f1_keywords:
- C2216
helpviewer_keywords:
- C2216
ms.assetid: 250f6bdc-a5e1-495f-a1e8-6e8e7021ad9d
ms.openlocfilehash: 78426722a4d23f8cf0b94c0b1989002e6a23f90b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741319"
---
# <a name="compiler-error-c2216"></a>Derleyici hatası C2216

' keyword1 ', ' keyword2 ' ile kullanılamaz

Birbirini dışlamalı iki anahtar sözcük birlikte kullanılmıştır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2216 oluşturur.

```cpp
// C2216.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   static int staticConst2 = 10;   // C2216
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C2216 oluşturur.

```cpp
// C2216b.cpp
// compile with: /clr /c
public ref class X {
   extern property int i { int get(); }   // C2216 extern not allowed on property
   typedef property int i2;   // C2216 typedef not allowed on property
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C2216 oluşturur.

```cpp
// C2216c.cpp
// compile with: /clr /c
public interface struct I {
   double f();
   double g();
   double h();
};

public ref struct R : I {
   virtual double f() new override { return 0.0; }   // C2216
   virtual double g() new { return 0.0; }   // OK
   virtual double h() override { return 0.0; }   // OK
};
```
