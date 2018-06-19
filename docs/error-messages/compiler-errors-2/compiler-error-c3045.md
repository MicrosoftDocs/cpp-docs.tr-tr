---
title: Derleyici Hatası C3045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3045
dev_langs:
- C++
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93cdf51c7976dac0c1563a01a2111abea7e87042
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249404"
---
# <a name="compiler-error-c3045"></a>Derleyici Hatası C3045
Bileşik deyim beklenen OpenMP 'bölüm' yönergesi aşağıdaki. Eksik ' {'  
  
 Kaşlı ayraç ayrılmış bir kod bloğu izlemeniz gereken bir [bölümleri](../../parallel/openmp/reference/sections-openmp.md) yönergesi.  
  
 Aşağıdaki örnek C3045 oluşturur:  
  
```  
// C3045.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
         ++n2;   // C3045  
  
      #pragma omp sections   // OK  
      {  
         ++n3;  
      }  
   }  
}  
```