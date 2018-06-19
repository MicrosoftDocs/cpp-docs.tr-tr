---
title: Derleyici Uyarısı (düzey 1) C4806 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92d5b36a653680285523c7cebb605238b37d57c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283399"
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