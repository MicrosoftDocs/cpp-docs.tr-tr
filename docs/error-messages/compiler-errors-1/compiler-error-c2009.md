---
title: "Derleyici Hatası C2009 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2009
dev_langs: C++
helpviewer_keywords: C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2bbae441d7b4c9e57a4080dd643f6563eed6c48e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2009"></a>Derleyici Hatası C2009
Makro resmi 'tanımlayıcısı' kullanılmasını  
  
 Bir makro tanımı biçimsel parametresi listesini tanımlayıcısı birden çok kez kullanır. Makro parametre listesi tanımlayıcılarının benzersiz olması gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2009 oluşturur:  
  
```  
// C2009.cpp  
#include <stdio.h>  
  
#define macro1(a,a) (a*a)   // C2009  
  
int main()   
{  
    printf_s("%d\n", macro1(2));  
}  
```  
  
## <a name="example"></a>Örnek  
 Olası çözüm:  
  
```  
// C2009b.cpp  
#include <stdio.h>  
  
#define macro2(a)   (a*a)   
#define macro3(a,b) (a*b)  
  
int main()   
{  
    printf_s("%d\n", macro2(2));  
    printf_s("%d\n", macro3(2,4));  
}  
```