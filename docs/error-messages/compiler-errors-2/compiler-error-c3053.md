---
title: Derleyici Hatası C3053 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3053
dev_langs:
- C++
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e140e2da535ebebbc332a8342d8970ff61a528d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3053"></a>Derleyici Hatası C3053
'simgesi': 'threadprivate' geçerli yalnızca genel veya statik veri öğeleri için  
  
 Simgeler geçirilen [threadprivate](../../parallel/openmp/reference/threadprivate.md) ya da genel veya statik olmalıdır.  
  
 Aşağıdaki örnek C3053 oluşturur:  
  
```  
// C3053.cpp  
// compile with: /openmp  
void Test() {  
   int x, y;  
   #pragma omp threadprivate(x, y)   // C3053  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```  
  
 Olası çözüm:  
  
```  
// C3053b.cpp  
// compile with: /openmp /LD  
int x, y;  
#pragma omp threadprivate(x, y)  
  
void Test() {  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```