---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3830'
title: Derleyici hatası C3830
ms.date: 11/04/2016
f1_keywords:
- C3830
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
ms.openlocfilehash: 6d5dff2b45a79d3156533caf8020497f422d2474
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249236"
---
# <a name="compiler-error-c3830"></a>Derleyici hatası C3830

' type1 ': ' type2 ' öğesinden devralma yapılamaz, değer türleri yalnızca arabirim sınıflarından devralınabilir

Değer türü, temel bir sınıfı alamaz.  Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3830 oluşturur:

```cpp
// C3830a.cpp
// compile with: /clr /c
public value struct MyStruct4 {
   int i;
};

public value class MyClass : public MyStruct4 {};   // C3830

// OK
public interface struct MyInterface4 {
   void i();
};

public value class MyClass2 : public MyInterface4 {
public:
   virtual void i(){}
};
```
