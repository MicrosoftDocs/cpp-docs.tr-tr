---
title: Derleyici hatası C2385
ms.date: 11/04/2016
f1_keywords:
- C2385
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
ms.openlocfilehash: 1247e4da05d65677f602a82591efd3e0c0c374e0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745265"
---
# <a name="compiler-error-c2385"></a>Derleyici hatası C2385

' Member ' öğesine belirsiz erişim

Üye birden fazla nesneden türetilebilir (birden fazla nesneden devralınır).  Bu hatayı çözmek için

- Bir atama sağlayarak üyeyi belirsiz hale getirin.

- Taban sınıflardaki belirsiz üyeleri yeniden adlandırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2385 oluşturur.

```cpp
// C2385.cpp
// C2385 expected
#include <stdio.h>

struct A
{
    void x(int i)
    {
        printf_s("\nIn A::x");
    }
};

struct B
{
    void x(char c)
    {
        printf_s("\nIn B::x");
    }
};

// Delete the following line to resolve.
struct C : A, B {}

// Uncomment the following 4 lines to resolve.
// struct C : A, B
// {
//     using B::x;
//     using A::x;
// };

int main()
{
    C aC;
    aC.x(100);
    aC.x('c');
}

struct C : A, B
{
    using B::x;
    using A::x;
};
```
