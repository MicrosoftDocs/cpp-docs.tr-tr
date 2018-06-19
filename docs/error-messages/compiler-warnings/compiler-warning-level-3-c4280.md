---
title: Derleyici Uyarısı (Düzey 3) C4280 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4280
dev_langs:
- C++
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6d4e9743a584249e2ec51c639423f56280f2d8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289912"
---
# <a name="compiler-warning-level-3-c4280"></a>Derleyici Uyarısı (Düzey 3) C4280
'-> işleci', 'type' türü aracılığıyla kendi kendine özyinelemeli edildi  
  
 Kodunuzun yanlış sağlar **-> işleci** kendisini çağırmak için.  
  
 Aşağıdaki örnek C4280 oluşturur:  
  
```  
// C4280.cpp  
// compile with: /W3 /WX  
struct A  
{  
   int z;  
   A& operator ->();  
};  
  
void f(A y)  
{  
   int i = y->z; // C4280  
}  
```