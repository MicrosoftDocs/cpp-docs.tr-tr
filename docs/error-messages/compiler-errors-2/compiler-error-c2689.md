---
title: Derleyici Hatası C2689 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2689
dev_langs:
- C++
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 973f8a007080d728a07afae8818ffa2c7bd8ed4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2689"></a>Derleyici Hatası C2689
'function': arkadaş işlev içinde yerel bir sınıf tanımlanamıyor  
  
 Bildirmesine rağmen bir arkadaş işlev içinde yerel bir sınıf tanımlama değil.  
  
 Aşağıdaki örnek C2689 oluşturur:  
  
```  
// C2689.cpp  
// compile with: /c  
void g() {  
   void f2();  
   class X {  
      friend void f2(){}   // C2689  
      friend void f2();   // OK  
   };  
}  
```