---
title: "Derleyici Uyarısı (düzey 1) C4391 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4391
dev_langs: C++
helpviewer_keywords: C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 91ee6716ee5139da02319925609777ebfec08a56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4391"></a>Derleyici Uyarısı (düzey 1) C4391
'imzası': iç işlevi için dönüş türü yanlış beklenen 'type'  
  
 Bir iç derleyici için işlev bildiriminden yanlış dönüş türü var. Elde edilen görüntü düzgün çalışmayabilir.  
  
 Bu uyarıyı çözmenin bildirimi düzeltin ya da bildirimi silmeniz ve yalnızca # uygun üst bilgi dosyasını include.  
  
 Aşağıdaki örnek C4391 oluşturur:  
  
```  
// C4391.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_load_ss(float *p);   // C4391  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```