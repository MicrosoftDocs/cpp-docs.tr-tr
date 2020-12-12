---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4738'
title: Derleyici Uyarısı (düzey 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: d57b992438148b3925b5366747db0b9de53ec87e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332146"
---
# <a name="compiler-warning-level-3-c4738"></a>Derleyici Uyarısı (düzey 3) C4738

32 bit kayan sonuç bellekte depolanıyor, olası performans kaybı

C4738 bir atama, atama, geçilen bağımsız değişken ya da başka bir işlemin sonucunun yuvarlanmasını veya işlemin yazmaçların (sıvı kesilmesi) gerekli olduğunu ve gerekli olduğunu uyarır. Bu, performans kaybına neden olabilir.

Bu uyarıyı çözmek ve yuvarlamadan kaçınmak için, [/FP: Fast](../../build/reference/fp-specify-floating-point-behavior.md) veya with **`double`** yerine kullanın **`float`** .

Bu uyarıyı gidermek ve kayıt dışında bırakmak önlemek için hesaplama sırasını değiştirin ve satır içi kullanımı değiştirin

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4738 oluşturur:

```cpp
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
