---
title: "Derleyici Uyarısı (düzey 4) C4668 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4668
dev_langs:
- C++
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8cd54cbc252bf86fdc974fd0e5a87e44d5c853e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4668"></a>Derleyici Uyarısı (düzey 4) C4668
'symbol' önişlemci makrosu olarak tanımlanmamış, 'directives' için '0' ile değiştiriliyor  
  
 Tanımlanmamış bir simge ile önişlemci yönergesi kullanıldı. Simgenin yanlış olarak değerlendirilir. Bir simge tanımlamak için kullanabilirsiniz [#define yönergesi](../../preprocessor/hash-define-directive-c-cpp.md) veya [/D](../../build/reference/d-preprocessor-definitions.md) derleyici seçeneği.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4668 oluşturur:  
  
```  
// C4668.cpp  
// compile with: /W4  
#include <stdio.h>  
  
#pragma warning (default : 4668)   // turn warning on  
  
int main()   
{  
    #if q   // C4668, q is not defined  
        printf_s("defined");  
    #else  
        printf_s("undefined");  
    #endif  
}  
```