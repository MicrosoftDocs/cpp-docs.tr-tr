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
ms.workload: cplusplus
ms.openlocfilehash: e18c22358770075785b52215a0167f4aa3ea84af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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