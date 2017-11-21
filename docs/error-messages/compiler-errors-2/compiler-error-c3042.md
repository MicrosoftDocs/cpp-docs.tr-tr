---
title: "Derleyici Hatası C3042 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3042
dev_langs: C++
helpviewer_keywords: C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f0fe35a4021cca6ac1e3dd9846a3c165f50797f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3042"></a>Derleyici Hatası C3042
'copyprivate' ve 'nowait' yan tümceleri üzerinde OpenMP 'yönergesi' yönergesi birlikte bulunamaz  
  
 [Copyprivate](../../parallel/openmp/reference/copyprivate.md) ve [nowait](../../parallel/openmp/reference/nowait.md) yan tümceleri üzerinde belirtilen yönergesi karşılıklı olarak birbirini dışlar. Bu hatayı düzeltmek için aşağıdakilerden birini veya her ikisini de kaldırmak `copyprivate` veya `nowait` yan tümceleri.  
  
 Aşağıdaki örnek C3042 oluşturur:  
  
```  
// C3042.cpp  
// compile with: /openmp /c  
#include <stdio.h>  
#include "omp.h"  
  
double d;  
  
int main() {  
    #pragma omp parallel private(d)  
   {  
      #pragma omp single copyprivate(d) nowait   // C3042  
      {  
      }  
   }  
}  
```