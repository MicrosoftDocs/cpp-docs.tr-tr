---
title: "Derleyici Uyarısı (düzey 4) C4701 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4701
dev_langs: C++
helpviewer_keywords: C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d001827c1d3e73ee4724aa52543231a43d41af5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4701"></a>Derleyici Uyarısı (düzey 4) C4701
Potansiyel olarak başlatılmamış yerel değişken kullanılan'name '  
  
 Yerel değişken *adı* bir değer atanmadan kullanılmış. Bu, öngörülemeyen sonuçlara neden olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod C4701 ve C4703 oluşturur.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
```Output  
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used  
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used  
  
```  
  
 Bu uyarı düzeltmek için değişken Bu örnekte gösterildiği gibi başlatın:  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Uyarısı (düzey 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [Uyarılar, / SDL ve başlatılmamış değişken algılama artırma](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)