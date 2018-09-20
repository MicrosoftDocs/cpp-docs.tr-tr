---
title: 'Nasıl yapılır: - clr derlemesini algılama | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3ea3c18a06e993e67106955f48d7fe1caec101ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436981"
---
# <a name="how-to-detect-clr-compilation"></a>Nasıl yapılır: /clr Derlemesini Algılama

Kullanım `_MANAGED` veya `_M_CEE` bir modül ile derlenmiş, görmek için makro **/CLR**. Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

Makrolar hakkında daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md).

## <a name="example"></a>Örnek

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)