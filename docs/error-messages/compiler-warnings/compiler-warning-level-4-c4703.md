---
title: Derleyici Uyarısı (düzey 4) C4703
ms.date: 11/04/2016
f1_keywords:
- C4703
helpviewer_keywords:
- C4703
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
ms.openlocfilehash: ab0e4ef0024446f51f7ee1e50480c1ab2b277652
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518041"
---
# <a name="compiler-warning-level-4-c4703"></a>Derleyici Uyarısı (düzey 4) C4703

Potansiyel olarak yerel işaretçi değişkeninin kullanılan'name ' başlatılmamış

Yerel işaretleyici değişken *adı* bir değer atanmadan kullanıldı. Bu, öngörülemeyen sonuçlara neden olabilir.

## <a name="example"></a>Örnek

Aşağıdaki kod, C4701 ve C4703 oluşturur.

```cpp
#include <malloc.h>

void func(int size)
{
    void* p;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr) // C4701 and C4703
        free(p);
}

void main()
{
    func(9);
}
```

```Output
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used
```

Bu uyarıyı düzeltmek için değişkeni aşağıdaki örnekte gösterildiği gibi başlatın:

```cpp
#include <malloc.h>

void func(int size)
{
    void* p = nullptr;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr)
        free(p);
}

void main()
{
    func(9);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Uyarısı (düzey 4) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)<br/>
[Uyarılar, / SDL ve değişken başlatılmamış algılama geliştirme](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)