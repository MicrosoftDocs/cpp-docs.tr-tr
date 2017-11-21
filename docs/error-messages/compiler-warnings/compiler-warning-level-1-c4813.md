---
title: "Derleyici Uyarısı (düzey 1) C4813 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4813
dev_langs: C++
helpviewer_keywords: C4813
ms.assetid: c30bf877-ab04-4fe4-897e-8162092426f0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7ef6f4dad0703c00416c5d2c81e0950195d4f674
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4813"></a>Derleyici Uyarısı (düzey 1) C4813
'function': yerel bir sınıfın arkadaş işlevi önceden bildirilmiş olmalıdır  
  
 Bir iç sınıf arkadaş işlevinde dış sınıfında bildirilmedi.  
  
 Aşağıdaki örnek C4813 oluşturur:  
  
```  
// C4813.cpp  
// compile with: /W1 /LD  
void MyClass()  
{  
   // void func();  
   class InnerClass  
   {  
      friend void func();   // C4813 uncomment declaration above  
   };  
}  
```