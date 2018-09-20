---
title: __noop | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __noop_cpp
- __noop
dev_langs:
- C++
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97820367f0960925dfcac1db339260cd3f52b8bc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430221"
---
# <a name="noop"></a>__noop

**Microsoft'a özgü**

`__noop` İç işlev yoksayılıp yoksayılmaması gerektiğini belirtir ve bağımsız değişken listesi ayrıştırılır ancak kod üretilmedi bağımsız değişkenleri. Değişken sayıda bağımsız değişken genel hata ayıklama işlevlerini kullanmak için tasarlanmıştır.

Derleyici dönüştürür `__noop` 0 derleme zamanında iç.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanabileceğinizi gösterir `__noop`.

```
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)