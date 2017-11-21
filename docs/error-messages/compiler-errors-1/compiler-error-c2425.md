---
title: "Derleyici Hatası C2425 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2425
dev_langs: C++
helpviewer_keywords: C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4f1740a0896560f81aaf1660a028aacbdddba892
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2425"></a>Derleyici Hatası C2425
'belirteci': 'context' sabit olmayan ifade  
  
 Bir sabit olmayan ifadesi bu bağlamda belirteci forms bölümü.  
  
 Bu sorunu gidermek için belirteci bir hesaplama veya bir sabit değişmez değer ile değiştirin.  
  
 Aşağıdaki örnek C2425 oluşturur:  
  
```  
// C2425.cpp  
// processor: x86  
int main() {  
   int i = 3;  
   __asm {  
      mov eax, [ebp - i]   // C2425  
      mov eax, [ebp - 3]   // OK  
   }  
}  
```