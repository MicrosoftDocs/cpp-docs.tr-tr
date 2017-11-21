---
title: "Derleyici Hatası C3854 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3854
dev_langs: C++
helpviewer_keywords: C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 34285e8de195b2b7c516cf665f3b2cbf37039e6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3854"></a>Derleyici Hatası C3854
'=' ın sol ifade bir işleve değerlendirir. (Bir işlev l-değeri değildir) bir işleve atayamazsınız.  
  
 Bir başvuru yeniden olamaz. Bir işlev başvurusu başvurusunun kaldırılmasının nesnesine atanamaz bir rvalue olan bir işlev verir. Bu nedenle, bir işlev başvurusu aracılığıyla atayamazsınız.  
  
 Aşağıdaki örnek C3854 oluşturur:  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```