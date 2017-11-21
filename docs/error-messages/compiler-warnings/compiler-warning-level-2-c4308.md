---
title: "Derleyici Uyarısı (Düzey 2) C4308 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4308
dev_langs: C++
helpviewer_keywords: C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 74a17ce1df422e476a8485537fbb284dda8bc830
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4308"></a>Derleyici Uyarısı (Düzey 2) C4308
İmzasız türe dönüştürülüp negatif tamsayı sabiti  
  
 Bir ifadenin negatif tamsayı sabiti bir imzasız türüne dönüştürür. İfade büyük olasılıkla anlamsız sonucudur.  
  
## <a name="example"></a>Örnek  
  
```  
// C4308.cpp  
// compile with: /W2  
unsigned int u = (-5 + 3U);   // C4308  
  
int main()  
{  
}  
```