---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2385'
title: Derleyici hatası C2385
ms.date: 11/04/2016
f1_keywords:
- C2385
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
ms.openlocfilehash: 7978af162045d52e187e41999c55dcad716baeb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185914"
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
