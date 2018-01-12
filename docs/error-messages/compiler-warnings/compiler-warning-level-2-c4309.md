---
title: "Derleyici Uyarısı (Düzey 2) C4309 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4309
dev_langs: C++
helpviewer_keywords: C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ca5b3386053713362a90ce8b2404794905193ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4309"></a>Derleyici Uyarısı (Düzey 2) C4309
'dönüştürme': sabit değer kesilmesi  
  
 Tür dönüştürmeleri için ayrılan alanı aşan bir sabit neden olur. Daha büyük bir tür için sabit kullanmanız gerekebilir.  
  
 Aşağıdaki örnek C4309 oluşturur:  
  
```  
// C4309.cpp  
// compile with: /W2  
int main()  
{  
   char c = 128;   // C4309  
}  
```