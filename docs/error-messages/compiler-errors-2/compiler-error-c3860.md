---
title: "Derleyici Hatası C3860 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3860
dev_langs: C++
helpviewer_keywords: C3860
ms.assetid: 1fb5110d-594e-4f1c-8773-888233af1313
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7f06878b5d7c364704cd028ae87a5b43bd0d738
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3860"></a>Derleyici Hatası C3860
tür bağımsız değişkeni, sınıf türü adı aşağıdaki parametreleri türü parametre listesine kullanılan sırayla listesi olmalıdır  
  
 Genel veya şablon bağımsız değişken listesi ill oluşturulmuş.  
  
 Aşağıdaki örnek C3860 oluşturur:  
  
```  
// C3860.cpp  
// compile with: /LD  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T1, T2>::f() {}   // C3860  
```  
  
 Olası çözüm:  
  
```  
// C3860b.cpp  
// compile with: /c  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T2, T1>::f() {}  
```  
  
 Ayrıca C3860 genel türler kullanma ortaya çıkabilir:  
  
```  
// C3860c.cpp  
// compile with: /clr  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,T>::f() {}   // C3860  
```  
  
 Olası çözüm:  
  
```  
// C3860d.cpp  
// compile with: /clr /c  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,U>::f() {}  
```