---
title: "Derleyici Hatası C3045 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3045
dev_langs: C++
helpviewer_keywords: C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 99974cf55ae6fe73c1bc51f3f9f2b20268381e16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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