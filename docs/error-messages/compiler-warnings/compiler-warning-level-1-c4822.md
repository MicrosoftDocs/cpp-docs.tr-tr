---
title: "Derleyici Uyarısı (düzey 1) C4822 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4822
dev_langs: C++
helpviewer_keywords: C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8c57b23d23faf27b0f59f9c1ad1cc1065105c7e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4822"></a>Derleyici Uyarısı (düzey 1) C4822
'member': yerel sınıf üye işlevi bir gövde yok  
  
 Yerel sınıf üye işlevi bildirimi ancak sınıfında tanımlı değil. Yerel sınıf üye işlevi kullanmak için sınıfı tanımlamanız gerekir. Sınıfında bildirin ve sınıf dışında tanımlayın.  
  
 Herhangi bir sınıf çıkış tanımının yerel sınıf üye işlevi için bir hata olacaktır.  
  
 Aşağıdaki örnek C4822 oluşturur:  
  
```  
// C4822.cpp  
// compile with: /W1  
int main() {  
   struct C {  
      void func1(int);   // C4822  
      // try the following line instead  
      // void func1(int){}  
  };  
}  
```