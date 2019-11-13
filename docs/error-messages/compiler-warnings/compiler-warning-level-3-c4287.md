---
title: Derleyici Uyarısı (düzey 3) C4287
ms.date: 11/04/2016
f1_keywords:
- C4287
helpviewer_keywords:
- C4287
ms.assetid: 1bf3bff8-6402-4d06-95ba-431678a790a7
ms.openlocfilehash: b37e0692a63f02dc96dec8717d4defd64d7183ac
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051668"
---
# <a name="compiler-warning-level-3-c4287"></a>Derleyici Uyarısı (düzey 3) C4287

' operator ': işaretsiz/negatif sabit uyuşmazlığı

İşaretsiz bir değişken negatif bir sayı olan bir işlemde kullanıldı.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4287 oluşturur:

```cpp
// C4287.cpp
// compile with: /W3
#pragma warning(default : 4287)
#include <stdio.h>

int main()
{
    unsigned int u = 1;
    if (u < -1)   // C4287
        printf_s("u LT -1");
    else
        printf_s("u !LT -1");
    return 0;
}
```