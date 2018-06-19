---
title: Derleyici Uyarısı (düzey 1) C4358 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4358
dev_langs:
- C++
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f051673f56bfa66d7cd373b6917a9754c5ffd46a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282564"
---
# <a name="compiler-warning-level-1-c4358"></a>Derleyici Uyarısı (düzey 1) C4358
'işleci': dönüş türü, birleştirilmiş temsilcilerin değil 'void'; döndürülen değer tanımlı değil  
  
 İki temsilciler birleştirilen ve dönüş değeri void değil. İki temsilciler void olmayan dönüş değerleri ile birleştirildiğinde, derleyici temsilci dönüş değeri kullanılırsa, uygun bir atama yapmak mümkün olmaz.  
  
 Aşağıdaki örnek C4358 oluşturur:  
  
```  
// C4358.cpp  
// compile with: /clr /W1  
delegate int D();  
delegate void E();  
  
ref class X {  
   int i;  
public:  
   X(int ii) : i(ii) {}  
   int f() {  
      return i;  
   }  
};  
  
ref class Y {  
   int i;  
public:  
   Y() {}  
   void g() {}  
};  
  
int main() {  
   D^ d = gcnew D(gcnew X(1), &X::f);  
   D^ d2 = gcnew D(gcnew X(2), &X::f);  
  
   d += d2;   // C4358  
   int j = d();   // return value indeterminate  
  
   E^ e = gcnew E(gcnew Y, &Y::g);  
   E^ e2 = gcnew E(gcnew Y, &Y::g);  
   e += e2;   // OK  
}  
```