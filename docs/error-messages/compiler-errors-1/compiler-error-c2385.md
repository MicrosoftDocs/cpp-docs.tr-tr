---
title: Derleyici Hatası C2385
ms.date: 11/04/2016
f1_keywords:
- C2385
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
ms.openlocfilehash: bffb4c1088c41832e69b0c6f161b47f6f9f08d06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571398"
---
# <a name="compiler-error-c2385"></a>Derleyici Hatası C2385

'üyesinin' belirsiz erişim

Üye (birden fazla nesneden devralınır) birden fazla nesne türeyebilir.  Bu hatayı gidermek için

- Üyenin benzersiz bir yayın sağlayarak olun.

- Temel sınıflar belirsiz üyeleri yeniden adlandırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2385 oluşturur.

```
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