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
ms.workload: cplusplus
ms.openlocfilehash: 3ce2fa62f525f5f322e0b45f35d129dbd74166ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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