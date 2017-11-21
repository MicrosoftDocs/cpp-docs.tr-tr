---
title: "Derleyici Hatası C2232 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2232
dev_langs: C++
helpviewer_keywords: C2232
ms.assetid: 76f302b7-30a7-4a81-9a39-b4edde33b54c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0c02f9b3953abf107cf4e3c33316c9d68f00b7b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2232"></a>Derleyici Hatası C2232
'->': sol işleneni '' kullanmak sınıf anahtarı türe sahip, '.'  
  
 İşlenen solundaki `->` işleci bir işaretçi değil. Bir sınıf, yapı veya UNION nokta (.) işlecini kullanın.  
  
 Aşağıdaki örnek C2232 oluşturur:  
  
```  
// C2232.c  
struct X {  
    int member;  
} x, *px;  
int main() {  
    x->member = 0;   // C2232, x is not a pointer  
  
    px->member = 0;  
    x.member = 0;  
}  
```