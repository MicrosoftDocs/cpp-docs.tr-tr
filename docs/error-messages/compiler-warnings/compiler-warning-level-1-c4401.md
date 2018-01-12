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
ms.workload: cplusplus
ms.openlocfilehash: b1042550b4ea176a314e174549ed560cd3ece025
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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