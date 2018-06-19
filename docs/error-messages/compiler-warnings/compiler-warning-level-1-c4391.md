---
title: Derleyici Uyarısı (düzey 1) C4391 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4391
dev_langs:
- C++
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0152d6e04d40e3e0389cf51ba7bdf71de4cd4791
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277874"
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