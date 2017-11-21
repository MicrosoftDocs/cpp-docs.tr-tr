---
title: "Derleyici Hatası C3005 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3005
dev_langs: C++
helpviewer_keywords: C3005
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 711b5083146f4b9a77d65746601eba264f0d41b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3005"></a>Derleyici Hatası C3005
'error_text': beklenmeyen bir belirteç OpenMP 'yönergesi' yönergesi karşılaştı  
  
 OpenMP yönergesi ill oluşturulmuş.  
  
 Aşağıdaki örnek C3005 oluşturur:  
  
```  
// C3005.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel + for   // C3005  
}  
```  
  
 Pragma aynı satırda bir açma ayracı yerleştirirseniz C3005 da oluşabilir.  
  
```  
// C3005b.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel {   // C3005 put open brace on next line  
   lbl2:;  
   }  
   goto lbl2;  
}  
```