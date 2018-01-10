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
ms.workload: cplusplus
ms.openlocfilehash: 348dc23e5ef3744ef1a3f152bf4d4fc5a22d2222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)