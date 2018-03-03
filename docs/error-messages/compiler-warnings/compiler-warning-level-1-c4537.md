---
title: "Derleyici Uyarısı (düzey 1) C4537 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4537
dev_langs:
- C++
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cdc3cc00b1b6ea52657f441423e61c3003652ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4537"></a>Derleyici Uyarısı (düzey 1) C4537
'object': 'UDT olmayan türüne uygulanacağını ' işleci  
  
 Başvurusu bir nesnenin (kullanıcı tanımlı tür) beklenirken geçirildi. Bir başvuru bir nesne değil ancak satır içi derleyici kod ayrım yapmak mümkün değildir. Derleyici kod olarak ancak oluşturur ***nesne*** bir örneği olan.  
  
 Aşağıdaki örnek C4537 oluşturur:  
  
```  
// C4537.cpp  
// compile with: /W1 /c  
// processor: x86  
struct S {  
   int member;  
};  
  
void f1(S &s) {  
   __asm mov eax, s.member;   // C4537  
   // try the following code instead  
   // or, make the declaration "void f1(S s)"  
   /*  
   mov eax, s  
   mov eax, [eax]s.member  
   */  
}  
```