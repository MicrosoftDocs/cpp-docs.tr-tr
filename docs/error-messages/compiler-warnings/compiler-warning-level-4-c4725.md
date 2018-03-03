---
title: "Derleyici Uyarısı (düzey 4) C4725 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4725
dev_langs:
- C++
helpviewer_keywords:
- C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0c8e64fabe1bbd155f4c9474a8927921623a760
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4725"></a>Derleyici Uyarısı (düzey 4) C4725
yönerge üzerinde bazı Pentiums yanlış olabilir  
  
 Kodunuzun doğru sonuçlar üzerinde bazı Pentium mikro vermeyebilir bir satır içi derleme yönerge içerir.  
  
 Aşağıdaki örnek C4725 oluşturur:  
  
```  
// C4725.cpp  
// compile with: /W4  
// processor: x86  
double m32fp = 2.0003e-17;  
  
void f() {  
   __asm  
   {  
      FDIV m32fp   // C4725  
   }  
}  
  
int main() {  
}  
```