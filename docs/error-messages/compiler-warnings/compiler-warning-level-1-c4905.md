---
title: Derleyici Uyarısı (düzey 1) C4905
ms.date: 11/04/2016
f1_keywords:
- C4905
helpviewer_keywords:
- C4905
ms.assetid: 40240bf4-b14e-4c22-aeb2-52f2851532f6
ms.openlocfilehash: 76f4786f808618b02ad93054d31992bbe710613e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199348"
---
# <a name="compiler-warning-level-1-c4905"></a>Derleyici Uyarısı (düzey 1) C4905

geniş düz dize 'LPSTR' değerine atandı

Derleyici güvenli olmayan bir tür algıladı. Atama başarılı oldu, ancak bir dönüştürme yordamı kullanmanız gerekir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4905 oluşturur.

```cpp
// C4905.cpp
// compile with: /W1
#pragma warning(default : 4905)
#include <windows.h>
#include <stdlib.h>
#include <stdio.h>

int main()
{
    LPSTR y = (LPSTR)L"1234";   // C4905

    // try the following lines instead
    // wchar_t y[128];
    // size_t  sizeOfConverted;
    // errcode err = 0;
    //
    // err = mbstowcs_s(&sizeOfConverted, &y[0], 128, "12345", 4);
    // if (err != 0)
    // {
    //     printf_s("mbstowcs_s failed!");
    //     exit (-1);
    // }
    // wprintf(L"%s\n", y);

    return 0;
}
```
