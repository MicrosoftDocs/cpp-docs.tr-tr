---
title: Derleyici Hatası C3059 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3059
dev_langs:
- C++
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 831dd1c73cf732e76a78138d55a7fecb204012a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249313"
---
# <a name="compiler-error-c3059"></a>Derleyici Hatası C3059
'var': 'threadprivate' simgesi 'yan tümcesi' yan tümcesinde kullanılamaz  
  
 A [threadprivate](../../parallel/openmp/reference/threadprivate.md) simge yan tümcesinde kullanıldı.  
  
 Aşağıdaki örnek C3059 oluşturur:  
  
```  
// C3059.cpp  
// compile with: /openmp  
#include "omp.h"  
int x, y;  
#pragma omp threadprivate(x, y)  
  
int main() {  
   #pragma omp parallel private(x, y)   // C3059  
   {  
      x = y;  
   }  
}  
```  
  
 Olası çözüm:  
  
```  
// C3059b.cpp  
// compile with: /openmp  
#include "omp.h"  
int x = 0, y = 0;  
  
int main() {  
   #pragma omp parallel firstprivate(y) private(x)  
   {  
      x = y;  
   }  
}  
```