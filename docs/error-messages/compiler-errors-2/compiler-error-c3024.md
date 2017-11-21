---
title: "Derleyici Hatası C3024 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3024
dev_langs: C++
helpviewer_keywords: C3024
ms.assetid: 1c031c28-ce37-4de3-aead-cfe76b261856
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a6d1512df35b7ac6042ee1aef05d15eb4392b9d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3024"></a>Derleyici Hatası C3024
'schedule(runtime)': chunk_size ifade izin verilmiyor  
  
 Zamanlama yan tümcesinin çalışma zamanı parametresi için bir değer geçirilemez.  
  
 Aşağıdaki örnek C3024 oluşturur:  
  
```  
// C3024.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
int main() {  
   int i;  
  
   #pragma omp parallel for schedule(runtime, 10)   // C3024  
   for (i = 0; i < 10; ++i) ;  
  
   #pragma omp parallel for schedule(runtime)   // OK  
   for (i = 0; i < 10; ++i) ;  
}  
```