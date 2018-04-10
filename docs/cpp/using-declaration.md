---
title: using bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- using declaration
- declaring namespaces, unqualified names in namespaces
- declarations [C++], using-declaration
- namespaces [C++], unqualified names in
- using keyword [C++]
- declarations [C++], namespaces
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6bf39dfdb4f59bcf54ce1ddd5174f1e3a55e3a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-declaration"></a>using Bildirimi
Using bildirimi tanıtır bir ad bildirim temelli bölgede içine using bildirimi görüntülenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
using [typename] nested-name-specifier unqualified-id ;  
using declarator-list ;  
```  
  
### <a name="parameters"></a>Parametreler
  
*iç içe-adı-belirticisi*  
    Kapsam çözümü işleci tarafından sonlandırıldı sırası ad alanı, sınıf veya numaralandırması adları ve kapsamı çözümleme işleçleri (:). Tek bir kapsam çözümü işleci genel ad alanından bir ad tanıtmak için kullanılabilir. Anahtar sözcüğü `typename` isteğe bağlıdır ve bir taban sınıftan bir sınıf şablonuna sunulan zaman bağımlı adları çözümlemek için kullanılabilir.  
  
*Nitelenmemiş kimliği*  
    Nitelenmemiş kimliği-bir tanımlayıcı, bir aşırı yüklenmiş işleci adı, bir kullanıcı tanımlı değişmez değer işleci veya dönüştürme işlevi adı, bir sınıf yıkıcı adı veya bir şablon adı ve bağımsız değişken listesi olabilen ifade.  
  
*bildirimcisi listesi*  
    Virgülle ayrılmış bir listesi [`typename`] *iç içe-adı-belirleyici* *kimliği nitelenmemiş* Bildirimciler, ardından isteğe bağlı üç nokta.
    
## <a name="remarks"></a>Açıklamalar  
A bildirimi kullanarak tanıtır nitelenmemiş bir adı bir varlık için eş anlamlı olarak başka bir yerde bildirilmedi. Açık nitelik göründüğü bildirimi bölgede olmadan kullanılacak belirli bir ad alanındaki tek bir ad sağlar. Tersine için budur [using yönergesi](../cpp/namespaces-cpp.md#using_directives), böylece *tüm* nitelemesiz kullanılacak bir ad alanı adları. `using` Anahtar sözcüğü için kullanılan aynı zamanda [yazın diğer adlar](../cpp/aliases-and-typedefs-cpp.md).  
  
## <a name="example"></a>Örnek  
 A bildirimi kullanarak bir sınıf tanımı'nda kullanılabilir.  
  
```cpp  
// using_declaration1.cpp  
#include <stdio.h>  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class D : B {  
public:  
   using B::f;    // B::f(char) is now visible as D::f(char)  
   using B::g;    // B::g(char) is now visible as D::g(char)  
   void f(int) {  
      printf_s("In D::f()\n");  
      f('c');     // Invokes B::f(char) instead of recursing  
   }  
  
   void g(int) {  
      printf_s("In D::g()\n");  
      g('c');     // Invokes B::g(char) instead of recursing  
   }  
};  
  
int main() {  
   D myD;  
   myD.f(1);  
   myD.g('a');  
}  
```  
  
```Output  
In D::f()  
In B::f()  
In B::g()  
```  
  
## <a name="example"></a>Örnek  
Kullanarak bir üyesi bildirmek için kullanıldığında bildirimi, bir taban sınıf üyelerine başvurmalıdır.  
  
```cpp  
// using_declaration2.cpp  
#include <stdio.h>  
  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class C {  
public:  
   int g();  
};  
  
class D2 : public B {  
public:  
   using B::f;   // ok: B is a base of D2  
   // using C::g;   // error: C isn't a base of D2  
};  
  
int main() {  
   D2 MyD2;  
   MyD2.f('a');  
}  
```  
  
```Output  
In B::f()  
```  
  
## <a name="example"></a>Örnek  
Üyeleri olarak bildirilen kullanarak bir kullanarak bildirimi açık nitelik kullanarak başvurulabilir. `::` Öneki genel ad alanına başvuruyor.  
  
```cpp  
// using_declaration3.cpp  
#include <stdio.h>  
  
void f() {  
   printf_s("In f\n");  
}  
  
namespace A {  
   void g() {  
      printf_s("In A::g\n");  
   }  
}  
  
namespace X {  
   using ::f;   // global f is also visible as X::f  
   using A::g;   // A's g is now visible as X::g 
}  
  
void h() {  
   printf_s("In h\n");  
   X::f();   // calls ::f  
   X::g();   // calls A::g  
}  
  
int main() {  
   h();  
}  
```  
  
```Output  
In h  
In f  
In A::g  
```  
  
## <a name="example"></a>Örnek  
Bir kullanırken bildirimi yapıldığında, yalnızca kullanarak noktasında geçerli tanımları bildirimi tarafından oluşturulan eş başvurduğu bildirimi. Kullanıldıktan sonra bir ad alanınıza eklenen tanımları bildirimi geçerli eş anlamlıları değildir.  
  
Tarafından tanımlanan bir ad bir `using` bildirimidir özgün adına için diğer ad. Tür, bağlantı veya diğer öznitelikleri özgün bildirimi etkilemez.  
  
```cpp  
// post_declaration_namespace_additions.cpp  
// compile with: /c  
namespace A {  
   void f(int) {}  
}  
  
using A::f;   // f is a synonym for A::f(int) only  
  
namespace A {  
   void f(char) {}  
}  
  
void f() {  
   f('a');   // refers to A::f(int), even though A::f(char) exists  
}  
  
void b() {  
   using A::f;   // refers to A::f(int) AND A::f(char)  
   f('a');   // calls A::f(char);  
}  
```  
  
## <a name="example"></a>Örnek  
Ad alanları, bir dizi yerel bildirimler işlevlerde göre ve bildirimlerini kullanarak herhangi bir tek bir ad bildirim temelli bir bölgede belirtilen olduğundan, tüm aynı varlığa başvuruda bulunmalıdır ya da tüm işlevlere başvurması gerekir.  
  
```cpp  
// functions_in_namespaces1.cpp  
// C2874 expected  
namespace B {  
    int i;  
    void f(int);  
    void f(double);  
}  
  
void g() {  
    int i;  
    using B::i;   // error: i declared twice  
    void f(char);  
    using B::f;   // ok: each f is a function  
}  
```  
  
 Yukarıdaki örnekte `using B::i` deyimi neden saniyenin `int i` içinde bildirilmesi için `g()` işlevi. `using B::f` Deyimi ile çakışıp `f(char)` işlev adları tarafından sunulan çünkü işlev `B::f` farklı parametre türlerine sahip.  
  
## <a name="example"></a>Örnek  
 Yerel işlev bildirimi bildirimi kullanarak tarafından sunulan bir işlevi olarak aynı ad ve türe sahip olamaz. Örneğin:  
  
```cpp  
// functions_in_namespaces2.cpp  
// C2668 expected  
namespace B {  
    void f(int);  
    void f(double);  
}  
  
namespace C {  
    void f(int);  
    void f(double);  
    void f(char);  
}  
  
void h() {  
    using B::f;          // introduces B::f(int) and B::f(double)  
    using C::f;          // C::f(int), C::f(double), and C::f(char)  
    f('h');              // calls C::f(char)  
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?  
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)  
}  
```  
  
## <a name="example"></a>Örnek  
 Devralma göre bir kullanırken bildirimi bir adı bir taban sınıftan türetilmiş sınıf geçersiz kılma sanal üye işlevleri üye işlevleri temel sınıf aynı ad ve bağımsız değişken türlerine sahip bir türetilmiş sınıf kapsamı içine tanıtır.  
  
```cpp  
// using_declaration_inheritance1.cpp  
#include <stdio.h>  
struct B {  
   virtual void f(int) {  
      printf_s("In B::f(int)\n");  
   }  
  
   virtual void f(char) {  
      printf_s("In B::f(char)\n");  
   }  
  
   void g(int) {  
      printf_s("In B::g\n");  
   }  
  
   void h(int);  
};  
  
struct D : B {  
   using B::f;  
   void f(int) {   // ok: D::f(int) overrides B::f(int)  
      printf_s("In D::f(int)\n");  
   }  
  
   using B::g;  
   void g(char) {   // ok: there is no B::g(char)  
      printf_s("In D::g(char)\n");  
   }  
  
   using B::h;  
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)  
};  
  
void f(D* pd) {  
   pd->f(1);     // calls D::f(int)  
   pd->f('a');   // calls B::f(char)  
   pd->g(1);     // calls B::g(int)  
   pd->g('a');   // calls D::g(char)  
}  
  
int main() {  
   D * myd = new D();  
   f(myd);  
}  
```  
  
```Output  
In D::f(int)  
In B::f(char)  
In B::g  
In D::g(char)  
```  
  
## <a name="example"></a>Örnek  
Bir ad kullanarak bir bahsedilen tüm örneklerini bildirimi erişilebilir olmalıdır. Kullanarak bir türetilmiş bir sınıf kullanıyorsa, özellikle, bir taban sınıf üye adı üyesi erişmek için bildirim erişilebilir olmalıdır. Tüm işlevleri adlı erişilebilmelidir adı, bir aşırı yüklenmiş üye işlevi ise.  
  
Üyeleri erişilebilirlik hakkında daha fazla bilgi için bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md).  
  
```cpp  
// using_declaration_inheritance2.cpp  
// C2876 expected  
class A {  
private:  
   void f(char);  
public:  
   void f(int);  
protected:  
   void g();  
};  
  
class B : public A {  
   using A::f;   // C2876: A::f(char) is inaccessible  
public:  
   using A::g;   // B::g is a public synonym for A::g  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ad alanları](../cpp/namespaces-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)