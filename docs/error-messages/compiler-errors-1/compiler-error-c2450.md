---
title: Derleyici Hatası C2450 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2450
dev_langs:
- C++
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db8702703337d01bf8073dd31bcb54d876010c10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2450"></a>Derleyici Hatası C2450
anahtar ifadesi ' type' türünde geçersiz  
  
 `switch` İfadeyi hesaplar için geçersiz bir tür. Bir tamsayı yazın ya da bir sınıf türü değerlendirilmelidir anlaşılır dönüştürme bir tamsayı türüne sahip. Kullanıcı tanımlı bir tür olarak değerlendirilirse bir dönüşüm işleci sağlamanız gerekir.  
  
 Aşağıdaki örnek C2450 oluşturur:  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```