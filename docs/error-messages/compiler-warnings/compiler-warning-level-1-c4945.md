---
title: "Derleyici Uyarısı (düzey 1) C4945 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4945
dev_langs: C++
helpviewer_keywords: C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b8c42a0a021f1bbe7399fa9fa8564739574b5b28
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4945"></a>Derleyici Uyarısı (düzey 1) C4945
'simgesi': 'assembly2' simgesini alınamıyor: 'simgesi' başka bir derlemeden 'assembly1' içe gibi  
  
 Bir simge başvurulan bir derleme alındı, ancak bu simgeyi zaten başka bir başvurulan derlemesinden içeri aktarıldı. Değil derlemelerden birini başvuru veya derlemeler birinde değiştirilen sembol adını alın.  
  
 Aşağıdaki örnekler C4945 oluşturur.  
  
```  
// C4945a.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 Ardından,  
  
```  
// C4945b.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 Ardından,  
  
```  
// C4945c.cpp  
// compile with: /clr /LD /W1  
#using "C4945a.dll"  
#using "C4945b.dll"   // C4945  
```