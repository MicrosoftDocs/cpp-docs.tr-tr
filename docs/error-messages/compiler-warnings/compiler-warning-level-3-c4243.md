---
title: "Derleyici Uyarısı (Düzey 3) C4243 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4243
dev_langs:
- C++
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3449dc305495848517687b7404dbdab5528e9a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4243"></a>Derleyici Uyarısı (Düzey 3) C4243
'dönüştürme türü' dönüştürme 'type1' 'type2' var, ancak erişilemiyor  
  
 Türetilmiş bir sınıf için bir işaretçi bir taban sınıfı için bir işaretçi dönüştürülür, ancak özel veya Korumalı Erişim ile temel sınıfı türetilmiş sınıf devralır.  
  
 Aşağıdaki örnek C4243 oluşturur:  
  
```  
// C4243.cpp  
// compile with: /W3  
// C4243 expected  
struct B {  
   int f() {  
      return 0;  
   };  
};  
  
struct D : private B {};  
struct E : public B {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   int (D::* d)() = (int(D::*)()) &B::f;   
   d;  
  
   int (E::* e)() = (int(E::*)()) &B::f; // OK  
   e;  
}  
```