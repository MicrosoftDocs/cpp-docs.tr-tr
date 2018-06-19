---
title: Derleyici Hatası C3206 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3206
dev_langs:
- C++
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9b8d8bae310bca939ae7b88fac44728b35a0066
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247423"
---
# <a name="compiler-error-c3206"></a>Derleyici Hatası C3206
'function': 'tür bağımsız değişken listesinin sınıfı türündeki 'typename' eksik param' için geçersiz tür bağımsız değişkeni  
  
 Bir şablon işlevi, bir şablon tür bağımsız değişkeni alma olarak tanımlanır. Ancak, bir şablon şablon bağımsız değişken geçirildi.  
  
 Aşağıdaki örnek C3206 oluşturur:  
  
```  
// C3206.cpp  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S>();   // C3206  
   // try the following line instead  
   // f<S<int> >();  
}  
```  
  
 Olası çözüm:  
  
```  
// C3206b.cpp  
// compile with: /c  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S<int> >();  
}  
```  
  
 Ayrıca C3206 genel türler kullanma ortaya çıkabilir:  
  
```  
// C3206c.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS>();   // C3206  
}  
```  
  
 Olası çözüm:  
  
```  
// C3206d.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS<int> >();  
}  
```  
  
 
 Şablon tür bağımsız değişkeni olarak bir sınıf şablonu izin verilmiyor. Aşağıdaki örnek C3206 başlatır:  
  
```  
// C3206e.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T<int> t;  
}  
  
int main() {  
   func<S>();   // C3206 S is not a type.  
}  
```  
  
 Olası çözüm:  
  
```  
// C3206f.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T t;  
}  
  
int main() {  
   func<S<int> >();  
}  
```  
  
 Şablon Şablon parametresi gerekli ise, işlev bir şablonu şablon parametresi alan bir şablon sınıfı sarmalama gerekir:  
  
```  
// C3206g.cpp  
template <class T>  
struct S {};  
  
template<template<class> class TT>  
struct X {  
   static void func() {  
      TT<int> t1;  
      TT<char> t2;  
   }  
};  
  
int main() {  
   X<S>::func();  
}  
```