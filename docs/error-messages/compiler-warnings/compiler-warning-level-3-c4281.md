---
title: "Derleyici Uyarısı (Düzey 3) C4281 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4281
dev_langs: C++
helpviewer_keywords: C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 578686472ba23c004a600fa55c616379d4bfd6ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4281"></a>Derleyici Uyarısı (Düzey 3) C4281
türü 'type' '-> işleci' özyineleme oluştu  
  
 Kodunuzun sağlar **-> işleci** kendisini çağırmak için.  
  
 Aşağıdaki örnek C4281 oluşturur:  
  
```  
// C4281.cpp  
// compile with: /W3 /WX  
struct A;  
struct B;  
struct C;  
  
struct A  
{  
   int z;  
   B& operator->();  
};  
  
struct B  
{  
   C& operator->();  
};  
  
struct C  
{  
   A& operator->();  
};  
  
void f(A p)  
{  
   int i = p->z; // C4281  
}  
```