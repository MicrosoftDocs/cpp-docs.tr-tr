---
title: "Derleyici Hatası C2275 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2275
dev_langs: C++
helpviewer_keywords: C2275
ms.assetid: c1eafa71-48de-46e0-82f3-b575538ef205
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 584eb7b3099c52cb8f2a9bded570b4b76ca683d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2275"></a>Derleyici Hatası C2275
'tanımlayıcısı': Bu tür bir ifade olarak geçersiz kullanımı  
  
 Bir ifade kullanır `->` işleciyle bir `typedef` tanımlayıcısı.  
  
 Aşağıdaki örnek C2275 oluşturur:  
  
```  
// C2275.cpp  
typedef struct S {  
    int mem;  
} *S_t;  
void func1( int *parm );  
void func2() {  
    func1( &S_t->mem );   // C2275, S_t is a typedef  
}  
```