---
title: Derleyici Uyarısı (Düzey 3) C4373
ms.date: 11/04/2016
f1_keywords:
- C4373
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
ms.openlocfilehash: 031b32a03d93a51f6fa00041a5b0bdf99e6eacf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456062"
---
# <a name="compiler-warning-level-3-c4373"></a>Derleyici Uyarısı (Düzey 3) C4373

> '*işlevi*': sanal işlev geçersiz*base_function*', önceki derleyici sürümleri Parametreler yalnızca const/volatile niteleyicileri farklıydı olduğunda kılmadı

## <a name="remarks"></a>Açıklamalar

Uygulamanızı bir temel sınıf sanal bir yöntemi geçersiz kılan türetilmiş bir sınıfta bir yöntem içerir ve geçersiz kılma yöntemi parametrelerinde yalnızca farklı bir [const](../../cpp/const-cpp.md) veya [geçici](../../cpp/volatile-cpp.md) gelen niteleyicisi sanal yöntem parametreleri. Bu, derleyicinin bir işlev başvurusu yöntemine ya da temel bağlamanız gerekir, yoksa türetilmiş sınıf anlamına gelir.

Visual Studio 2008 önceki derleyici sürümleri işlev temel sınıf yöntemi bağlamak ve bir uyarı iletisi yayınlar. Derleyici'nın sonraki sürümleri Yoksay `const` veya `volatile` niteleyicisi, türetilen sınıfın yöntemine bind işlevi ve ardından sorun uyarı **C4373**. Bu ikinci davranışı C++ standardı ile uyumludur.

## <a name="example"></a>Örnek

Aşağıdaki kod örneğinde, uyarı C4373 oluşturur. Bu sorunu çözmek için aynı CV niteleyicilerine temel üye işlevini geçersiz kılma ya da yapabilir veya değil bir geçersiz kılma oluşturmak istediniz, işlev türetilmiş sınıf içinde farklı bir ad verebilirsiniz.

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```