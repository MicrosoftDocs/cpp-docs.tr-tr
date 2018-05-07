---
title: Derleyici Hatası C2247 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2247
dev_langs:
- C++
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed27398ea1f51ccc2ef0d3339446b422c7a503c0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2247"></a>Derleyici Hatası C2247
'tanımlayıcısı' 'class', ' sınıfından ' için 'tanımlayıcısı' kullandığından erişilemiyor  
  
 `identifier` Özel veya korumalı erişimle bildirilen sınıfından devralınır.  
  
 Aşağıdaki örnek C2247 oluşturur:  
  
```  
// C2247.cpp  
class A {  
public:  
   int i;  
};  
class B : private A {};    // B inherits a private A  
class C : public B {} c;   // so even though C's B is public  
int j = c.i;               // C2247, i not accessible  
```  
  
 Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucunda da oluşturulabilir: erişim denetimi ile korumalı üyeleri. Korumalı üye (n) yalnızca bir üye işlevi, (n) üyesi olduğu (A) sınıftan bir sınıfın (B) üzerinden erişilebilir.  
  
 Geçerli Visual Studio .NET 2003 ve Visual Studio .NET sürümlerini Visual C++ kodu için bir arkadaş türü olmasını üyesi bildirin. Ortak devralma de kullanılabilir.  
  
```  
// C2247b.cpp  
// compile with: /c  
// C2247 expected  
class A {  
public:  
   void f();  
   int n;  
};  
  
class B: protected A {  
   // Uncomment the following line to resolve.  
   // friend void A::f();  
};  
  
void A::f() {  
   B b;  
   b.n;  
}  
```  
  
 C2247 de oluşturulabilir için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucunda: özel temel erişilemez sınıflar şimdi. Özel bir taban sınıf türü için bir sınıf (A) (C) B temel sınıf olarak kullanan bir türü için erişilebilir olmamalıdır (B).  
  
 Visual Studio .NET 2003 ve Visual Studio .NET Visual C++ sürümü geçerli kod kapsam işleci kullanın.  
  
```  
// C2247c.cpp  
// compile with: /c  
struct A {};  
  
struct B: private A {};  
  
struct C : B {  
   void f() {  
      A *p1 = (A*) this;   // C2247  
      // try the following line instead  
      // ::A *p2 = (::A*) this;  
   }  
};  
```