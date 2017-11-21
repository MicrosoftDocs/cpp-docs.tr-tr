---
title: "Derleyici Hatası C2387 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2387
dev_langs: C++
helpviewer_keywords: C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 18233efc81a63a29c1350d1addb67f8ea20e877e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2387"></a>Derleyici Hatası C2387
'type': belirsiz taban sınıfı  
  
 Taban sınıf içinde birden fazla işlev var olduğundan derleyici bir işlev çağrısı belirsizliğe çözümlenemedi.  
  
 Bu hatayı gidermek için taban sınıflarından biri içinden devralma kaldırın veya açıkça işlev çağrısı hakkını kullanmaya devam eder.  
  
 Aşağıdaki örnek C2387 oluşturur:  
  
```  
// C2387.cpp  
namespace N1 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
namespace N2 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
struct D : N1::B, N2::B {  
   virtual void f() {  
      B::f();   // C2387  
      // try the following line instead  
      // N1::B::f();  
   }  
};  
  
int main() {  
   D aD;  
   aD.f();  
}  
```