---
title: "Derleyici Hatası C2293 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2293
dev_langs: C++
helpviewer_keywords: C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0b57daead4d355c81d0d411e37665e453d8f76c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2293"></a>Derleyici Hatası C2293
'tanımlayıcısı': __based tanımlayıcısı olarak bir üye değişkeni için geçersiz  
  
 Tanımlayıcıları `__based` değiştiricisi dahil olmayan işaretçileri olması gerekir.  
  
 Aşağıdaki örnek C2293 oluşturur:  
  
```  
// C2293.cpp  
// compile with: /c  
class A {  
   static int *i;  
   void __based(i) *bp;   // C2293  
   void *bp2;   // OK  
};  
```