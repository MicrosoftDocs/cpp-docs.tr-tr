---
title: "Derleyici Hatası C2385 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2385
dev_langs: C++
helpviewer_keywords: C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f36b2bf3800e0f95fa35ad2a72cead4018c69dbb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2385"></a>Derleyici Hatası C2385
'üyesinin' belirsiz erişim  
  
 Üye (birden fazla nesneden devralındı) birden fazla nesne öğesinden türetilen.  Bu hatayı gidermek için  
  
-   Üye anlaşılır bir cast sağlayarak olun.  
  
-   Temel sınıflar belirsiz üyeleri yeniden adlandırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2385 oluşturur.  
  
```  
// C2385.cpp  
// C2385 expected  
#include <stdio.h>  
  
struct A   
{  
    void x(int i)   
    {  
        printf_s("\nIn A::x");  
    }  
};  
  
struct B   
{  
    void x(char c)   
    {  
        printf_s("\nIn B::x");  
    }  
};  
  
// Delete the following line to resolve.  
struct C : A, B {}  
  
// Uncomment the following 4 lines to resolve.  
// struct C : A, B   
// {  
//     using B::x;  
//     using A::x;  
// };  
  
int main()   
{  
    C aC;  
    aC.x(100);  
    aC.x('c');  
}  
  
struct C : A, B   
{  
    using B::x;  
    using A::x;  
};  
```