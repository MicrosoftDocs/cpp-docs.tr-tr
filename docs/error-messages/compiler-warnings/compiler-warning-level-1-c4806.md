---
title: "Derleyici Uyarısı (düzey 1) C4806 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4806
dev_langs: C++
helpviewer_keywords: C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a9c9c48f01746aaf208db28ce84fe006e990aaf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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