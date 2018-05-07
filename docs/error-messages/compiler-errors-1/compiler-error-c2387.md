---
title: Derleyici Hatası C2387 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2387
dev_langs:
- C++
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e490e2c0016649054c557026a5fa691162c40c07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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