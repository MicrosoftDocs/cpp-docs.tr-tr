---
title: "Derleyici Hatası C3001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3001
dev_langs: C++
helpviewer_keywords: C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91536da30d359b2c83357d28ba2006404f6f810f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3001"></a>Derleyici Hatası C3001
'error_text': bir OpenMP yönergesi adı bekleniyor  
  
 `omp` Pragma yönergesi tarafından uyulması gerekir.  
  
 Aşağıdaki örnek C3001 oluşturur:  
  
```  
// C3001.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp   // C3001 missing token  
}  
```