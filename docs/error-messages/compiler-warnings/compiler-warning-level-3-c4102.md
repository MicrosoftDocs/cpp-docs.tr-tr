---
title: "Derleyici Uyarısı (Düzey 3) C4102 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4102
dev_langs: C++
helpviewer_keywords: C4102
ms.assetid: 349f308a-daf3-48c6-bd53-6c38b73f8880
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9a2d13f51660c57fc0e1e14fcc350db17606cbaf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4102"></a>Derleyici Uyarısı (Düzey 3) C4102
'etiket': başvurulmayan etiketi  
  
 Etiket tanımlı ancak asla başvurulmaz. Derleyici etiketi yok sayar.  
  
 Aşağıdaki örnek C4102 oluşturur:  
  
```  
// C4102.cpp  
// compile with: /W3  
int main() {  
   int a;  
  
   test:   // C4102, remove the unreferenced label to resolve  
  
   a = 1;  
}  
```