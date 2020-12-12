---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır:/clr derlemesini algılama'
title: 'Nasıl yapılır: algılama-CLR derlemesi'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 25cd241a08f79bcae629c05fb3c7982a387120ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175722"
---
# <a name="how-to-detect-clr-compilation"></a>Nasıl yapılır: /clr Derlemesini Algılama

`_MANAGED` `_M_CEE` Bir modülün **/clr** ile derlenmiş olup olmadığını görmek için veya makrosunu kullanın. Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

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

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
