---
title: "Derleyici Hatası C2184 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2184
dev_langs: C++
helpviewer_keywords: C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7e5402835be51b67bece4853996f281cf0ab5cfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2184"></a>Derleyici Hatası C2184
'type': ifade __except geçersiz türü için bir integral olması gerekir  
  
 Bir tür olarak kullanılan bir [__except](../../c-language/try-except-statement-c.md) deyimi, ancak türü izin verilmez.  
  
 Aşağıdaki örnek C2184 oluşturur:  
  
```  
// C2184.cpp  
void f() {  
   int * p;  
   __try{}  
   __except(p){};   // C2184  
}  
```  
  
 Olası çözüm:  
  
```  
// C2184b.cpp  
// compile with: /c  
void f() {  
   int i = 0;  
   __try{}  
   __except(i){};  
}  
```