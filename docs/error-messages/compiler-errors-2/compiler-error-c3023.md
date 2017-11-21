---
title: "Derleyici Hatası C3023 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3023
dev_langs: C++
helpviewer_keywords: C3023
ms.assetid: 89dcce98-3cd7-4931-a50f-87df1d2ebc9b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: be45b364bbc87b03fd6898b1cdee339a3cf9e8b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3023"></a>Derleyici Hatası C3023
'value': beklenmeyen bir belirteç OpenMP 'yan tümcesi' yan tümcesi bağımsız değişkende karşılaştı  
  
 Bir yan tümce için geçirilen değer geçerli değil.  
  
 Aşağıdaki örnek C3023 oluşturur:  
  
```  
// C3023.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
int main() {  
   int i;  
  
   #pragma omp parallel for schedule(dynamic 10)   // C3023  
   for (i = 0; i < 10; ++i) ;  
  
   #pragma omp parallel for schedule(dynamic;10)   // C3023  
   for (i = 0; i < 10; ++i) ;  
  
   // OK  
   #pragma omp parallel for schedule(dynamic, 10)  
   for (i = 0; i < 10; ++i)  
   ;  
}  
```