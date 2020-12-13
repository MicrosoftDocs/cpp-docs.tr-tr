---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2457'
title: Derleyici hatası C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: 1fea5192b97e280a38f674a67b0bf739041ffe97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332376"
---
# <a name="compiler-error-c2457"></a>Derleyici hatası C2457

> '*Macro*': önceden tanımlanmış makro bir işlev gövdesinin dışında yer alamaz

Genel bir alanda [&#95;&#95;işlevi&#95;&#95;](../../preprocessor/predefined-macros.md)gibi önceden tanımlanmış bir makro kullanmaya çalıştınız.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2457 oluşturur ve ayrıca doğru kullanımı gösterir:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```
