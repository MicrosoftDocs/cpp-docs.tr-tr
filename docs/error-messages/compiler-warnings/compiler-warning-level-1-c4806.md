---
title: "Derleyici Uyarısı (düzey 1) C4806 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bddda6bd683133f278f79544b2bf13aa132e131
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4806"></a>Derleyici Uyarısı (düzey 1) C4806
'işlemi': güvensiz işlemi: hiçbir değer türü 'type 'type' türü için yükseltilen' verilen sabiti eşit olabilir  
  
 Bu ileti kodu karşı gibi uyarır `b == 3`, burada `b` türüne sahip `bool`. Yükseltme kuralları neden `bool` yükseltilmesi için `int`. Bu yasal, ancak hiçbir zaman olabilir **doğru**. Aşağıdaki örnek C4806 oluşturur:  
  
```  
// C4806.cpp  
// compile with: /W1  
int main()  
{  
   bool b = true;  
   // try..  
   // int b = true;  
  
   if (b == 3)   // C4806  
   {  
      b = false;  
   }  
}  
```