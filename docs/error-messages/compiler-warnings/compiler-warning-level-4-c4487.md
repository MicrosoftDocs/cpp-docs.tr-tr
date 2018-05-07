---
title: Derleyici Uyarısı (düzey 4) C4487 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4487
dev_langs:
- C++
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80008dbcfbebe4e91398e651e361efe7df30b641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4487"></a>Derleyici Uyarısı (düzey 4) C4487
'derived_class_function': devralınan sanal olmayan yöntemi 'base_class_function' ile eşleşir, ancak açıkça 'new' işaretli değil  
  
 Türetilmiş bir sınıf işlevinde sanal olmayan taban sınıf işlevi olarak aynı imzaya sahiptir. C4487 türetilmiş sınıf işlevi temel sınıf işlevi kılmaz anımsatır. Açıkça türetilmiş sınıf işlevi işaretleme `new` bu uyarıyı çözümlemek için.  
  
 Daha fazla bilgi için bkz: [yeni (vtable'de yeni yuva)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4487 oluşturur.  
  
```  
// C4487.cpp  
// compile with: /W4 /clr  
using namespace System;  
public ref struct B {  
   void f() { Console::WriteLine("in B::f"); }  
   void g() { Console::WriteLine("in B::g"); }  
};  
  
public ref struct D : B {  
   void f() { Console::WriteLine("in D::f"); }   // C4487  
   void g() new { Console::WriteLine("in D::g"); }   // OK  
};  
  
int main() {  
   B ^ a = gcnew D;  
   // will call base class functions  
   a->f();  
   a->g();  
}  
```