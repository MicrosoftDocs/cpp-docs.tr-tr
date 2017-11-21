---
title: "Derleyici Hatası C2227 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2227
dev_langs: C++
helpviewer_keywords: C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 57ace27f349eeb32fac0b916979c30cf2bce01c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2227"></a>Derleyici Hatası C2227
'üye ->' ın sol sınıfı/struct/union/genel tür işaret etmesi gerekir  
  
 İşlenen solundaki `->` bir işaretçi bir sınıf, yapı veya birleşim değil.  
  
 Aşağıdaki örnek C2227 oluşturur:  
  
```  
// C2227.cpp  
int *pInt;  
struct S {  
public:  
    int member;  
} s, *pS = &s;  
  
int main() {  
   pInt->member = 0;   // C2227 pInt points to an int  
   pS->member = 0;   // OK  
}  
```