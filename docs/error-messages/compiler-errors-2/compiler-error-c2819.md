---
title: "Derleyici Hatası C2819 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2819
dev_langs: C++
helpviewer_keywords: C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 770609ed06fd3e123ce02688e3f091018c9f5444
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2819"></a>Derleyici Hatası C2819
türü 'type' 'bir aşırı yüklenmiş üye işleci ->' yok  
  
 Tanımlamanız `operator->()` Bu işaretçi işlemi kullanmak için.  
  
 Aşağıdaki örnek C2819 oluşturur:  
  
```  
// C2819.cpp  
// compile with: /c  
class A {  
   public:  
      int i;  
};  
  
class B {};  
  
void C(B j) {  
   j->i;   // C2819  
}  
  
class D {  
   A* pA;  
  
   public:  
      A* operator->() {  
         return pA;  
      }  
};  
  
void F(D j) {  
   j->i;  
}  
```  
  
 C2819 kullanırken da gerçekleşebilir [başvuru türleri için C++ yığın anlamları](../../dotnet/cpp-stack-semantics-for-reference-types.md). Aşağıdaki örnek C2819 oluşturur:  
  
```  
// C2819_b.cpp  
// compile with: /clr  
ref struct R {  
   void Test() {}  
};  
  
int main() {  
   R r;  
   r->Test();   // C2819  
   r.Test();   // OK  
}  
```