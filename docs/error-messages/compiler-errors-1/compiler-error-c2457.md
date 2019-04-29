---
title: Derleyici Hatası C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: a08ac9f9cfbc332b90ad16c663349ee227427278
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347109"
---
# <a name="compiler-error-c2457"></a>Derleyici Hatası C2457

> '*makrosu*': önceden tanımlanmış makro bir işlev gövdesinin dışında yer alamaz

Önceden tanımlanmış bir makro gibi kullanma girişiminde [ &#95; &#95;işlevi&#95;&#95;](../../preprocessor/predefined-macros.md), genel bir alana.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2457 oluşturur ve ayrıca doğru kullanımını gösterir:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```