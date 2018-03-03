---
title: "Derleyici Uyarısı (Düzey 3) C4334 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7218caa399aec0bd1b9755fb6d0942991732121e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4334"></a>Derleyici Uyarısı (Düzey 3) C4334
'işleci': 32-bit kaydırma sonucunu örtük olarak dönüştürülen 64 bit (64-bit kaydırma hedeflenen oldu mu?)  
  
 32-bit kaydırma sonucunu örtük olarak 64-bit ve 64-bit kaydırma tasarlanmıştır derleyici şüphelendiği dönüştürüldü.  Bu uyarıyı çözmek için 64-bit kaydırma kullanabilir veya 64-bit kaydırma sonucu açıkça dönüştürün.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4334 oluşturur.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```