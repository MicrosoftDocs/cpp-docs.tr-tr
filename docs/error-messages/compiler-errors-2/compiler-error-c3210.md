---
title: Derleyici hatası C3210
ms.date: 11/04/2016
f1_keywords:
- C3210
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
ms.openlocfilehash: 513f08d4dddc37d36a240ee0d72b24383f951cdf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755128"
---
# <a name="compiler-error-c3210"></a>Derleyici hatası C3210

' Type ': erişim bildirimi yalnızca bir temel sınıf üyesine uygulanabilir

[Using bildirimi](../../cpp/using-declaration.md) yanlış belirtildi.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3210 oluşturur.

```cpp
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```
