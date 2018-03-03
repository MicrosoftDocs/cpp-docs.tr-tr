---
title: "Derleyici Uyarısı (düzey 1) C4920 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4920
dev_langs:
- C++
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c87237f5ac2240cfd2063c58055d626b72285287
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4920"></a>Derleyici Uyarısı (düzey 1) C4920
Enum numaralandırma üyesi üye zaten enum enum içindeki üye olarak görünen değer = value =  
  
 #İmport için geçirdiğiniz .tlb iki veya daha fazla numaralandırmaları tanımlanmış simgenin varsa, bu uyarı sonraki aynı sembolleri göz ardı edilir ve çıkışı .tlh dosyasında açıklanır gösterir.  
  
 İçeren bir .tlb varsayılır:  
  
```  
library MyLib  
{  
    typedef enum {  
        enumMember = 512  
    } AProblem;  
  
    typedef enum {  
        enumMember = 1024  
    } BProblem;  
};  
```  
  
 Aşağıdaki örnekler C4920 oluşturur,  
  
```  
// C4920.cpp  
// compile with: /W1  
#import "t4920.tlb"   // C4920  
  
int main() {  
}  
```