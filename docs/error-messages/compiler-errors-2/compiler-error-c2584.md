---
title: Derleyici hatası C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: 2c3b10ecd6808ccd864ecf877fe9f1d0e9f30a3a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748638"
---
# <a name="compiler-error-c2584"></a>Derleyici hatası C2584

' Class ': ' Base2 ' doğrudan tabanına erişilemiyor; zaten bir ' Base1 ' tabanı var

`Class` zaten `Base1`doğrudan türetiliyor. `Base2` Ayrıca `Base1`türetilir. `Class` `Base2` türetilemez, çünkü `Base1` zaten bir doğrudan temel sınıf olduğundan, bu, yasal olmayan `Base1` yeniden devralmıştı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2584 oluşturur.

```cpp
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```
