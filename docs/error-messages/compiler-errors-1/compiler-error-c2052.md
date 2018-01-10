---
title: "Derleyici Hatası C2052 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2052
dev_langs: C++
helpviewer_keywords: C2052
ms.assetid: 922ca43b-b64b-4ef7-9611-c7313be3fd79
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00b54d84afeed73c31139d19fa35f6af898f4dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2052"></a>Derleyici Hatası C2052
'type': case deyimi için geçersiz tür  
  
 Case ifadeleri tamsayı olmalıdır.  
  
 Aşağıdaki örnek C2052 oluşturur:  
  
```  
// C2052.cpp  
int main() {  
   int index = 0;  
   switch (index) {  
      case 1:  
         return 24;  
      case 1.0:   // C2052  
      // try the following line instead  
      // case 2:  
         return 23;  
   }  
}  
```