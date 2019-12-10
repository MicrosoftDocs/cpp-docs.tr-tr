---
title: 'Nasıl yapılır: algılama-CLR derlemesi'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 42b2952e3b63023ca26c6b1f7d0ccb8871082499
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988216"
---
# <a name="how-to-detect-clr-compilation"></a>Nasıl yapılır: /clr Derlemesini Algılama

Bir modülün **/clr**ile derlenmiş olup olmadığını görmek için `_MANAGED` veya `_M_CEE` makrosunu kullanın. Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

Makrolar hakkında daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md).

## <a name="example"></a>Örnek

```cpp
// detect_CLR_compilation.cpp
// compile with: /clr
#include <stdio.h>

int main() {
   #if (_MANAGED == 1) || (_M_CEE == 1)
      printf_s("compiling with /clr\n");
   #else
      printf_s("compiling without /clr\n");
   #endif
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
