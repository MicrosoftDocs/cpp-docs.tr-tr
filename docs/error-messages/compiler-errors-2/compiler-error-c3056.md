---
title: "Derleyici Hatası C3056 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3056
dev_langs: C++
helpviewer_keywords: C3056
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e688f9b46186c63167a45eab10e3ce3a66e42ee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3056"></a>Derleyici Hatası C3056
'simgesi': simgesi değil 'threadprivate' yönergesi ile aynı kapsamda  
  
 Kullanılan bir simge bir [threadprivate](../../parallel/openmp/reference/threadprivate.md) yan tümcesi aynı kapsamda olmalıdır `threadprivate` yan tümcesi.  
  
 Aşağıdaki örnek C3056 oluşturur:  
  
```  
// C3056.cpp  
// compile with: /openmp  
int x, y;  
void test() {  
   #pragma omp threadprivate(x, y)   // C3056  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```  
  
 Olası çözüm:  
  
```  
// C3056b.cpp  
// compile with: /openmp /LD  
int x, y;  
#pragma omp threadprivate(x, y)  
void test() {  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```