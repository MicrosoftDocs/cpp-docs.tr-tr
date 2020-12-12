---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3764'
title: Derleyici hatası C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: d4bd2db494acbcdbbec2e40c72aff300cae1a38e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291746"
---
# <a name="compiler-error-c3764"></a>Derleyici hatası C3764

' override_function ': ' base_class_function ' temel sınıf yöntemi geçersiz kılınamaz

Derleyici hatalı oluşturulmuş bir geçersiz kılma algıladı. Örneğin, temel sınıf işlevi değildi **`virtual`** . Daha fazla bilgi için bkz. [geçersiz kılma](../../extensions/override-cpp-component-extensions.md).

## <a name="examples"></a>Örnekler

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
