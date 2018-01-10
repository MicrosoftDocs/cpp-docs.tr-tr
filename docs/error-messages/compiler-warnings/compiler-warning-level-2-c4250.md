---
title: "Derleyici Uyarısı (Düzey 2) C4250 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4250
dev_langs: C++
helpviewer_keywords: C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d92a337e3ded4b958bb9d1dbb7359d21f28d619c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4250"></a>Derleyici Uyarısı (Düzey 2) C4250
'class1': 'class2::member' hakimiyeti aracılığıyla devralır  
  
 İki veya daha fazla üye aynı ada sahip. Bir `class2` , bu üye yer alan diğer sınıflar için temel sınıf olduğundan devralınır.  
  
 C4250 gizlemek için kullanın [uyarı](../../preprocessor/warning.md) pragması.  
  
 Sanal bir temel sınıf birden çok türetilen sınıflar arasında paylaşıldığından, türetilmiş bir sınıf bir adı bir temel sınıf adı dominates. Örneğin, aşağıdaki sınıf hiyerarşisi verildiğinde, vardır içinde baklava devralınan func iki tanımları: zayıf sınıfı ve baskın:: func() baskın sınıf aracılığıyla aracılığıyla vbc::func() örneği. Nitelenmemiş bir Karo sınıf nesnesi üzerinden func() çağrısı her zaman dominate:: func() örneği çağırır.  Zayıf sınıfı func() örneği tanıtmak için olsaydı, ne tanımı üzerinde egemen ve çağrısı belirsiz olarak işaretlenmiş.  
  
```  
// C4250.cpp  
// compile with: /c /W2  
#include <stdio.h>  
struct vbc {  
   virtual void func() { printf("vbc::func\n"); }  
};  
  
struct weak : public virtual vbc {};  
  
struct dominant : public virtual vbc {  
   void func() { printf("dominant::func\n"); }  
};  
  
struct diamond : public weak, public dominant {};  
  
int main() {  
   diamond d;  
   d.func();   // C4250  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4250 oluşturur.  
  
```  
// C4250_b.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
class A {  
public:  
   virtual operator int () {  
      return 2;  
   }  
};  
  
class B : virtual public A {  
public:  
   virtual operator int () {  
      return 3;  
   }  
};  
  
class C : virtual public A {};  
  
class E : public B, public C {};   // C4250  
  
int main() {  
   E eObject;  
   cout << eObject.operator int() << endl;  
}  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek daha karmaşık bir durumu gösterir. Aşağıdaki örnek C4250 oluşturur.  
  
```  
// C4250_c.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
  
class V {  
public:  
   virtual int f() {  
      return 1024;  
   }  
};  
  
class B : virtual public V {  
public:  
   int b() {  
      return f(); // B::b() calls V::f()  
   }  
};  
  
class M : virtual public V {  
public:  
   int f() {  
      return 7;  
   }  
};  
  
// because of dominance, f() is M::f() inside D,  
// changing the meaning of B::b's f() call inside a D  
class D : public B, public M {};   // C4250  
  
int main() {  
   D d;  
   cout << "value is: " << d.b();   // invokes M::f()  
}  
```