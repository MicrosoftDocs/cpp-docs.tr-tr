---
title: "Derleyici Uyarısı (düzey 1) C4555 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4555
dev_langs: C++
helpviewer_keywords: C4555
ms.assetid: 50b286c1-f7bf-4292-b1fa-baaac9538611
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7db66570d2d913762067d33f186d94a4967160db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4555"></a>Derleyici Uyarısı (düzey 1) C4555
ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu  
  
 Bu uyarı bir ifade hiçbir etkisi olduğunda sizi bilgilendirir.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Örneğin:  
  
```  
// C4555.cpp  
// compile with: /W1  
#pragma warning(default:4555)  
  
void func1()  
{  
   1;   // C4555  
}  
  
void func2()  
{  
   int x;  
   x;   // C4555  
}  
  
int main()  
{  
}  
```