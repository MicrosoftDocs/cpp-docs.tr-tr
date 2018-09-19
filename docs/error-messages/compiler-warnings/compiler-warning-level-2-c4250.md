---
title: Derleyici Uyarısı (Düzey 2) C4250 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4250
dev_langs:
- C++
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5797782691385111f0be22854643315f4e596fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031448"
---
# <a name="compiler-warning-level-2-c4250"></a>Derleyici Uyarısı (Düzey 2) C4250

'class1': baskınlık yoluyla ' class2::member' devralıyor

İki veya daha fazla üye aynı ada sahip. Bir `class2` salt okunur olduğundan bu üye yer alan diğer sınıflar için temel sınıf devralınır.

C4250 engellemek için kullanın [uyarı](../../preprocessor/warning.md) pragması.

Bir sanal temel sınıfın birden çok türetilmiş sınıflar arasında paylaşıldığından, türetilen bir sınıfta bir adı bir temel sınıf adı kaplamaktadır. Örneğin, aşağıdaki sınıf hiyerarşisi göz önünde bulundurulduğunda, vardır içinde elmas devralınan func iki tanımları: zayıf sınıfı ve baskın:: func() baskın sınıf aracılığıyla vbc::func() örneği. Func() elmas sınıf nesnesi üzerinden nitelenmemiş bir çağrı, her zaman dominate:: func() örneği çağırır.  Zayıf bir sınıf örneği func() tanıtmak için olsaydı, ne tanımı baskındır ve çağrısı belirsiz olarak işaretlenmiş.

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

Aşağıdaki örnek, C4250 oluşturur.

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

Bu örnek, daha karmaşık bir durum gösterir. Aşağıdaki örnek, C4250 oluşturur.

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