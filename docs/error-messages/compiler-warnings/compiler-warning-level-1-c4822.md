---
title: Derleyici Uyarısı (düzey 1) C4822 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4822
dev_langs:
- C++
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9491d522c65eba3599c3618d510c57b55682876
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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