---
title: Derleyici Uyarısı (Düzey 3) C4243 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4243
dev_langs:
- C++
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3e3f616e9eec1785f586b019b0faa752a578f0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290822"
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