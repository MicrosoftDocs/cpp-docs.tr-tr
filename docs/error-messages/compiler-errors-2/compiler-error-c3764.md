---
title: Derleyici hatası C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 657cb6598eedf8abd050b47c124c78c3a028509f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214509"
---
# <a name="compiler-error-c3764"></a>Derleyici hatası C3764

' override_function ': ' base_class_function ' temel sınıf yöntemi geçersiz kılınamaz

Derleyici hatalı oluşturulmuş bir geçersiz kılma algıladı. Örneğin, temel sınıf işlevi değildi **`virtual`** . Daha fazla bilgi için bkz. [geçersiz kılma](../../extensions/override-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3764 oluşturur.

```cpp
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>Örnek

Ayrıca, bir temel sınıf yöntemi açık bir şekilde ve geçersiz kılınırsa C3764 de oluşabilir. Aşağıdaki örnek C3764 oluşturur.

```cpp
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```
