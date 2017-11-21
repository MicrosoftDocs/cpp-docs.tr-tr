---
title: "Derleyici Uyarısı (düzey 1) C4401 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4401
dev_langs: C++
helpviewer_keywords: C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cabb50ca025390cd00f4c9db68f3aa97d606fa57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4401"></a>Derleyici Uyarısı (düzey 1) C4401
'saklayıcısında': üyesidir bit alanı  
  
 Satır içi derleme kodunda bit alanı üyesi erişmeyi dener. Son paket sınır bit alanı üye önce kullanılan şekilde satır içi derleme bit alan üyeleri erişemiyor.  
  
 Bu uyarıyı önlemek için satır içi derleme kodunda referans yapmadan önce uygun bir tür bit alana dönüştürün. Aşağıdaki örnek C4401 oluşturur:  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```