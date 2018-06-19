---
title: Derleyici Hatası C2457 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2457
dev_langs:
- C++
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61cdb4f4b679bab858717a6fb96838f389822a6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33224929"
---
# <a name="compiler-error-c2457"></a>Derleyici Hatası C2457

> '*makrosu*': önceden tanımlanmış makrosu işlev gövdesi dışında yer alamaz

Önceden tanımlanmış bir makrosu gibi kullanma girişiminde [ &#95; &#95;işlevi&#95;&#95;](../../preprocessor/predefined-macros.md), genel alanda.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2457 oluşturur ve ayrıca doğru kullanımını gösterir:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```