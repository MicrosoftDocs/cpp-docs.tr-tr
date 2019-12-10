---
title: Derleyici Uyarısı (düzey 4) C4764
ms.date: 11/04/2016
f1_keywords:
- C4764
helpviewer_keywords:
- C4764
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
ms.openlocfilehash: 28672d2271e380f6a8240bff98326d5334a0f98f
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989184"
---
# <a name="compiler-warning-level-4-c4764"></a>Derleyici Uyarısı (düzey 4) C4764

Catch nesneleri 16 bayttan fazla hizalanamaz

16 ' dan büyük bir hizalama belirtildi, ancak bazı platformlarda işlev bir özel durum oluşturursa, yığın 16 ' dan büyük bir hizalamayı zorlayacaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4764 oluşturur:

```cpp
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
