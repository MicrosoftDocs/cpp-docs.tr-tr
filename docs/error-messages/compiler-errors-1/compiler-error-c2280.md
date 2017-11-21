---
title: "Derleyici Hatası C2280 | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2280
helpviewer_keywords: C2280
dev_langs: C++
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af19f0a0c347ab0f898a3a3d72b8cca5cb07dad8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2280"></a>Derleyici Hatası C2280  
  
'*bildirimi*': silinen işlevi başvurulmaya çalışılıyor  
  
Derleyici başvuru girişimi algılandı bir `deleted` işlevi. Bu hata, açıkça olarak işaretlenmiş bir üye işlevine bir çağrı tarafından kaynaklanabilir `= deleted` kaynak kodundaki. Bu hata, bir yapı ya da otomatik olarak bildirilen ve olarak işaretlenmiş sınıfı bir örtük özel üye işlevine bir çağrı tarafından da oluşabilir `deleted` derleyici tarafından. Derleyici otomatik olarak oluşturduğunda hakkında daha fazla bilgi için `default` veya `deleted` özel üye işlevleri bkz [özel üye işlevleri](../../cpp/special-member-functions.md).  
  
## <a name="example-explicitly-deleted-functions"></a>Örnek: İşlevleri açıkça silindi  

Çağrısı bir açıkça `deleted` işlevi bu hataya neden olur. Bir açıkça `deleted` üye işlevi gelir sınıfta veya yapı isteyerek bu nedenle bu sorunu gidermek için kullanımını önlemek üzere tasarlanmış, bunu önlemek için kodunuzu değiştirmeniz gerekir.  
  
```cpp  
// C2280_explicit.cpp
// compile with: cl /c /W4 C2280_explicit.cpp
struct A {
    A();
    A(int) = delete;
};

struct B {
    A a1;
    A a2 = A(3); // C2280, calls deleted A::A(int)
    // To fix, remove the call to A(int)
};

void f() {
    B b;    // calls implicit B::B(void)
}
```  
  
## <a name="example-uninitialized-data-members"></a>Örnek: Başlatılmamış veri üyeleri  
  
Başlatılmamış başvuru türü veri üyesi veya `const` veri üyesi örtük olarak bildirmek derleyici neden olan bir `deleted` varsayılan oluşturucu. Bu sorunu gidermek için onu bildirilmişse veri üyesi başlatır.  
  
```cpp  
// C2280_uninit.cpp
// compile with: cl /c C2280_uninit.cpp
struct A {
    const int i; // uninitialized const-qualified data
    // members or reference type data members cause
    // the implicit default constructor to be deleted.
    // To fix, initialize the value in the declaration:
    // const int i = 42;
} a;    // C2280
```  
  
## <a name="example-reference-and-const-data-members"></a>Örnek: Başvuru ve const veri üyeleri  
  
A `const` veya reference türü veri üyesi bildirmek derleyici neden bir `deleted` kopya atama işleci. Basit kopyalama veya taşıma çalışamaz şekilde başlatıldıktan sonra bu üyeler için atanamaz. Bu sorunu düzeltmek için hata neden atama işlemleri kaldırmak için mantığınızı değiştirmek öneririz.  
  
```cpp  
// C2280_ref.cpp
// compile with: cl /c C2280_ref.cpp
extern int k;
struct A {
    A();
    int& ri = k; // a const or reference data member causes 
    // implicit copy assignment operator to be deleted.
};

void f() {
    A a1, a2;
    // To fix, consider removing this assignment.
    a2 = a1;    // C2280
}
```  
  
## <a name="example-movable-deletes-implicit-copy"></a>Örnek: Taşınabilir örtük kopyalama siler.  
  
Bir sınıf bir taşıma oluşturucusuna veya taşıma atama işleci bildirir, ancak açıkça kopya Oluşturucu bildirmiyor, derleyici örtük olarak kopya Oluşturucu bildirir ve olarak tanımlayan `deleted`. Benzer şekilde, bir sınıf bir taşıma oluşturucusuna veya taşıma atama işleci bildirir, ancak açıkça bir kopya atama işleci bildirmiyor, derleyici örtük olarak bir kopya atama işleci bildirir ve olarak tanımlayan `deleted`. Bu sorunu gidermek için bu üyeleri açıkça bildirmeniz gerekir.  
 
Hata C2280 birlikte gördüğünüzde bir `unique_ptr`, neredeyse kesinlikle olan çağırma olduğu kopya kurucusu denediğinizden bir `deleted` işlevi. Tasarıma göre bir `unique_ptr` kopyalanamaz. Bunun yerine sahipliğini aktarma için bir taşıma oluşturucusuna kullanın.  

```cpp  
// C2280_move.cpp
// compile with: cl /c C2280_move.cpp
class base  
{  
public:  
    base();  
    ~base(); 
    base(base&&); 
    // Move constructor causes copy constructor to be
    // implicitly declared as deleted. To fix this 
    // issue, you can explicitly declare a copy constructor:
    // base(base&);
    // If you want the compiler default version, do this:
    // base(base&) = default;
};  

void copy(base *p)  
{  
    base b{*p};  // C2280
}  
```  

## <a name="example-variant-and-volatile-members"></a>Örnek: Değişken ve volatile üyeleri  
  
Visual Studio 2015 güncelleştirme 2 önce derleyici sürümleri uyumsuz ve oluşturulan varsayılan oluşturucular ve anonim birleşimler için Yıkıcılar yoktu. Bunlar artık dolaylı olarak bildirilen `deleted`. Bu sürümleri de uyumsuz örtük tanımını izin `default` kopyalama ve taşıma oluşturucuları ve `default` kopyalama ve taşıma atama işleçleri sınıfları ve sahip yapılar `volatile` üye değişkenleri. Derleyici şimdi bu Önemsiz olmayan oluşturucuları ve atama işleçleri sağlamak için göz önünde bulundurur ve üretmez `default` uygulamaları. Böyle bir sınıfın UNION ya da bir sınıf içinde anonim bir birleşim üyesi olduğunda, kopyalama ve taşıma oluşturucuları ve kopyalama ve taşıma atama işleçleri UNION veya sınıfın örtük olarak tanımlanır `deleted`. Bu sorunu düzeltmek için gerekli özel üye işlevleri açıkça bildirmeniz gerekir.  
  
```cpp  
// C2280_variant.cpp
// compile with: cl /c C2280_variant.cpp
struct A {  
    A() = default;
    A(const A&);
};  

struct B {  
    union {  
        A a;  
        int i;  
    };
    // To fix this issue, declare the required 
    // special member functions:
    // B(); 
    // B(const B& b);
};  

int main() {
    B b1;  
    B b2(b1);  // C2280  
}
```  
  
## <a name="example-indirect-base-members-deleted"></a>Örnek: silinen dolaylı temel üyeleri  
  
Visual Studio 2015 güncelleştirme 2 önce derleyici sürümleri uyumsuz ve özel üye dolaylı olarak türetilmiş işlevleri çağırmak türetilmiş bir sınıf izin `private virtual` temel sınıflar. Bu tür bir çağrısı yapıldığında derleyici şimdi derleyici hatası C2280 verir.  
  
Bu örnekte, sınıf `top` doğrudan özel sanal türer `base`. Uyumlu kodunda bu üyeleri yapar `base` için erişilemez `top`; türündeki nesne bir `top` varsayılan oluşturulan veya yok. Eski derleyici davranışı dayanıyordu kodda bu sorunu gidermek için kullanmak üzere ara sınıfı değiştirme `protected virtual` türetme ya da değişiklik `top` doğrudan türetme kullanılacak sınıfı:  

```cpp  
// C2280_indirect.cpp
// compile with: cl /c C2280_indirect.cpp
class base  
{  
protected:  
    base();  
    ~base();  
};  

class middle : private virtual base {}; 
// Possible fix: Replace line above with:
// class middle : protected virtual base {};
class top : public virtual middle {};    // C4594, C4624
// Another possible fix: use direct derivation:
// class top : public virtual middle, private virtual base {};   

void destroy(top *p)  
{  
    delete p;  // C2280  
}  
```  
  