---
title: Derleyici Hatası C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 498aefae4dfe8fd13184b9da1685494d533575dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556435"
---
# <a name="compiler-error-c3764"></a>Derleyici Hatası C3764

'override_function': 'base_class_function' taban sınıfı yöntemi geçersiz kılınamıyor

Derleyici, hatalı oluşturulmuş bir geçersiz kılma algıladı. Örneğin, temel sınıf işlevi değildi `virtual`. Daha fazla bilgi için [geçersiz kılma](../../windows/override-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3764 oluşturur.

```
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

C3764 bir temel sınıf yöntemini hem de açık olduğunda da meydana gelebilir ve adlandırılmış geçersiz kılındı. Aşağıdaki örnek, C3764 oluşturur.

```
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