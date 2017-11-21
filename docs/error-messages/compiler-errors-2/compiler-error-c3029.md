---
title: "Derleyici Hatası C3029 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3029
dev_langs: C++
helpviewer_keywords: C3029
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b04e6004f02a57023ed999f30ec5f318e7a72bb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3029"></a>Derleyici Hatası C3029
'simgesi': yalnızca bir kez veri Paylaşımı'görünebilir yan tümcelerinde OpenMP yönergesi  
  
 Bir sembol, bir veya daha fazla yan tümcelerinde bir yönergesi birden çok kez kullanıldı. Simgenin yönergesinde yalnızca bir kez kullanılabilir.  
  
 Aşağıdaki örnek C3029 oluşturur:  
  
```  
// C3029.cpp  
// compile with: /openmp /link vcomps.lib  
#include "omp.h"  
  
int g_i;  
  
int main() {  
   int i, x;  
  
   #pragma omp parallel reduction(+ : x, x)   // C3029  
      ;  
  
   #pragma omp parallel reduction(+ : x)   // OK  
      ;  
  
   #pragma omp parallel private(x) reduction(+ : x)   // C3029  
      ;  
  
   #pragma omp parallel reduction(+ : x)   // OK  
      ;  
}  
```