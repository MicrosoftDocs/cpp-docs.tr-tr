---
description: 'Hakkında daha fazla bilgi edinin: derleyici uyarısı C4984'
title: Derleyici Uyarısı C4984
ms.date: 08/19/2019
f1_keywords:
- C4984
helpviewer_keywords:
- C4984
ms.openlocfilehash: 5a6708a1063baf8fa4b5feece65eabd93df7bbeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326006"
---
# <a name="compiler-warning-c4984"></a>Derleyici Uyarısı C4984

> ' if constexpr ' bir C++ 17 dil uzantısıdır

## <a name="remarks"></a>Açıklamalar

Derleyici, `if constexpr` kodda varsayılan c++ 14 standardı kullanılarak derlenen bir ifade buldu. Bu ifade C++ 17 standardı ile başlayarak belirtilmiştir. C++ 11 veya C++ 14 uyumluluğuna ihtiyacınız varsa, bu ifade taşınabilir değildir.

C4984 varsayılan olarak bir hata olarak verilir, ancak bu, bastırbir şekilde yapılır. Kodunuzu C++ 17 olarak derleyerek bu ifadeyi etkinleştirmek için [/std: c++ 17 veya/std: C + + latest](../../build/reference/std-specify-language-standard-version.md)kullanın. `if constexpr`C++ 14 için derlenmiş koddaki Ifadeyi Microsoft uzantısı olarak kullanmak için, hata iletisinin uyarı düzeyini engelleyebilir, devre dışı bırakabilir veya değiştirebilirsiniz. C4984 devre dışı bırakmak için [/wd4984](../../build/reference/compiler-option-warning-level.md) veya bir hata yerine bir düzey *N* uyarısı olarak etkinleştirmek için __/w__*n*__4984__ kullanabilirsiniz. Ya da kaynak dosyanızda uyarıya neden olan satırdan önce [#pragma uyarı (gösterme: 4984)](../../preprocessor/warning.md) kullanın.

Bu uyarı, Visual Studio 2017 sürüm 15,3 ' den itibaren kullanılabilir. Belirli bir derleyici sürümünde veya sonrasında tanıtılan uyarıları devre dışı bırakma hakkında daha fazla bilgi için bkz. derleyici için derleyici [sürümüne göre uyarı](compiler-warnings-by-compiler-version.md).

## <a name="example"></a>Örnek

Bu örnek C4984 oluşturur ve bu hatayı gidermeye yönelik yolları gösterir:

```cpp
// C4984.cpp
// compile with: cl /EHsc C4984.cpp
#include <iostream>

int main()
{
    constexpr bool compile_time = true;
    // Uncomment the following line or use /std:c++17 to fix
    // #pragma warning(suppress:4984)
    if constexpr (compile_time)
    {
        std::cout << "compile_time is true";
    }
    else
    {
        std::cout << "compile_time is false";
    }
}
```
