---
title: Derleyici Uyarısı (düzey 1) C4540 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4540
dev_langs:
- C++
helpviewer_keywords:
- C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3939ad2bbcba1ab3b492d83bdbb8f7076c2c5f2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4540"></a>Derleyici Uyarısı (düzey 1) C4540
dynamic_cast erişilemez ya da belirsiz tabanına dönüştürmek için kullanılan; çalışma zamanı test ('type2' ' type1') başarısız olur  
  
 Kullanılan `dynamic_cast` bir türden diğerine dönüştürmek için. Cast her zaman başarısız olur derleyici belirlenen (dönmek **NULL**) bir taban sınıf erişilemediğinden (`private`, örneğin) ya da belirsiz (birden çok kez sınıf hiyerarşisi örneği için görünür).  
  
 Bu uyarı bir örneği gösterir. Sınıf **B** sınıfından türetilen **A**. Program kullanır `dynamic_cast` sınıfından yayınlanamıyor **B** (türetilmiş sınıf) sınıfına **A**, hangi her zaman başarısız olur çünkü sınıfı **B** olan `private` ve bu nedenle erişilemez. Erişimi değiştirme **A** için **ortak** uyarı giderir.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```