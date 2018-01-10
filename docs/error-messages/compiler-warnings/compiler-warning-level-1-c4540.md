---
title: "Derleyici Uyarısı (düzey 1) C4540 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4540
dev_langs: C++
helpviewer_keywords: C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aaaef1edaa6af093ae03fe69231a9686e3d087a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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