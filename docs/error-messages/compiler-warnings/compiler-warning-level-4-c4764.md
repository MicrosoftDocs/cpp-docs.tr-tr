---
title: Derleyici Uyarısı (düzey 4) C4764
ms.date: 11/04/2016
f1_keywords:
- C4764
helpviewer_keywords:
- C4764
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
ms.openlocfilehash: dd16b3f6e6591ec5b079f421fb199eb201c64483
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388559"
---
# <a name="compiler-warning-level-4-c4764"></a>Derleyici Uyarısı (düzey 4) C4764

Yakalama nesneleri 16 baytın üzerinde hizalanamaz

16 ' büyük bir hizalama belirtildi ancak işlev bir özel durum oluşturursa bazı platformlarda, 16'dan büyük bir hizalama yığınına zorlar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4764 oluşturur:

```
// C4764.cpp
// compile with: /W4 /EHsc
// processor: x64 IPF
#include <stdio.h>

class A
{
public:
    int x;
};

typedef __declspec(align(32)) A ALIGNEDA;

int main()
{
    ALIGNEDA a;
    try
    {
        a.x = 15;
        throw a;
    }
    catch (ALIGNEDA b) // can’t align b to > 16 bytes
    {
        printf_s("%d\n", b.x);
    }
}   // C4764
```