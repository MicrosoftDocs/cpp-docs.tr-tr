---
title: Derleyici Uyarısı (Düzey 3) C4738 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e017ef94dd28de8d4c66ab89b1509f755beeb07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053226"
---
# <a name="compiler-warning-level-3-c4738"></a>Derleyici Uyarısı (Düzey 3) C4738

32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı

Tür dönüştürme; atamanın sonucu geçirilen bağımsız değişken veya başka bir işlem yuvarlanmasını gerekebilir veya işlem kayıtları dışında çalıştırılan ve (taşma) bellek kullanmak için atılması gereken C4738 uyarır. Bu performans kaybına neden olabilir.

Bu uyarıyı çözün ve yuvarlama önlemek için derleme [Fast](../../build/reference/fp-specify-floating-point-behavior.md) veya `double` yerine `float`.

Bu uyarıyı çözün ve kayıtları dışında çalışmasını önlemek için hesaplama sırasını değiştirmek ve kullanımını değiştirme satır içi kullanım

Varsayılan olarak bu uyarıyı kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4738 oluşturur:

```
// C4738.cpp
// compile with: /c /fp:precise /O2 /W3
// processor: x86
#include <stdio.h>

#pragma warning(default : 4738)

float func(float f)
{
    return f;
}

int main()
{
    extern float f, f1, f2;
    double d = 0.0;

    f1 = func(d);
    f2 = (float) d;
    f = f1 + f2;   // C4738
    printf_s("%f\n", f);
}
```