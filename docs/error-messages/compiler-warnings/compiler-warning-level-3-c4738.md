---
title: Derleyici Uyarısı (Düzey 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: 833546d20454e6104a2d5fcb272bf5bb9518ea44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401585"
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