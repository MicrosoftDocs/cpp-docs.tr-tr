---
title: __noop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __noop_cpp
- __noop
dev_langs: C++
helpviewer_keywords: __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7bdd595ac7fb70ef00865485a38e9d11cfd0181c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="noop"></a>__noop
**Microsoft özel**  
  
 `__noop` İç işlev yoksayılmalıdır belirtir ve bağımsız değişken listesi Ayrıştırılan ancak hiçbir kod bağımsız değişkenleri oluşturulmuş. Değişken sayıda bağımsız değişken almayan genel hata ayıklama işlevleri kullanmak için tasarlanmıştır.  
  
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
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)