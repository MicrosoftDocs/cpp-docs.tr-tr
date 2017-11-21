---
title: "Nasıl yapılır: - clr derlemesini algılama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 471e4727d7c3484e66af5bc9add196c0fa2651f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-detect-clr-compilation"></a>Nasıl yapılır: /clr Derlemesini Algılama
Kullanım `_MANAGED` veya `_M_CEE` ile bir modül derlenmiş olmadığını görmek için makrosu **/CLR**. Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Makrolar hakkında daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md).  
  
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
 [C++ birlikte çalışması (örtük PInvoke) kullanarak](../dotnet/using-cpp-interop-implicit-pinvoke.md)