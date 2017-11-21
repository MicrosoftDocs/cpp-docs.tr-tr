---
title: "Derleyici Hatası C3002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3002
dev_langs: C++
helpviewer_keywords: C3002
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 972df6a4260c8f14190371ddd439ff6456c3259e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3002"></a>Derleyici Hatası C3002
'ad1 ad2': birden çok OpenMP yönergesi adları  
  
 Birden çok yönerge adlarına izin verilmemektedir.  
  
 Aşağıdaki örnek C3002 oluşturur:  
  
```  
// C3002.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel single   // C3002  
}  
```