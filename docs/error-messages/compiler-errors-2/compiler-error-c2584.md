---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2584'
title: Derleyici hatası C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: 7820019c3ec49928f59980adbd9ec814d67c3499
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177685"
---
# <a name="compiler-error-c2584"></a>Derleyici hatası C2584

' Class ': ' Base2 ' doğrudan tabanına erişilemiyor; zaten bir ' Base1 ' tabanı var

`Class` zaten doğrudan türetiliyor `Base1` . `Base2` Ayrıca öğesinden türetilir `Base1` . `Class` öğesinden türetilemiyor `Base2` çünkü bu, yasal olmayan (dolaylı) `Base1` `Base1` bir doğrudan temel sınıf olduğundan, bir daha devralınamaz.

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
