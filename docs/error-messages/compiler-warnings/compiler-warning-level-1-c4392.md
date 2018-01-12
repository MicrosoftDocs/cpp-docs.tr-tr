---
title: "Derleyici Uyarısı (düzey 1) C4392 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4392
dev_langs: C++
helpviewer_keywords: C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c33a88ae9dda253192fc6ed4616da52ef7c58c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4392"></a>Derleyici Uyarısı (düzey 1) C4392
'imzası': yanlış sayıda bağımsız değişken iç işlevi için beklenen 'numara' bağımsız değişkenleri  
  
 Bir işlev bildirimi bir iç derleyici için yanlış sayıda bağımsız değişken içeriyor. Elde edilen görüntü düzgün çalışmayabilir.  
  
 Bu uyarıyı çözmenin bildirimi düzeltin ya da bildirimi silmeniz ve yalnızca # uygun üst bilgi dosyasını include.  
  
 Aşağıdaki örnek C4392 oluşturur:  
  
```  
// C4392.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_stream_pd(double *dp);   // C4392  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```