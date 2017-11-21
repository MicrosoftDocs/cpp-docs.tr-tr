---
title: "Derleyici Uyarısı (Düzey 3) C4557 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4557
dev_langs: C++
helpviewer_keywords: C4557
ms.assetid: 7d9db716-03b2-4ee5-9b09-ba8aa5aa7e4c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b25fcc0e2a5c9cc5204c3a1947cd8460af77188e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4557"></a>Derleyici Uyarısı (Düzey 3) C4557
'__assume' 'effect' etkisini içeriyor  
  
 Geçirilen değerini bir [__assume](../../intrinsics/assume.md) statement2 değiştirildi.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4557 oluşturur:  
  
```  
// C4557.cpp  
// compile with: /W3  
#pragma warning(default : 4557)  
int main()  
{  
   int i;  
   __assume(i++);   // C4557  
}  
```