---
title: using bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c40a69e9c8d584d91a1b6401ec0da57368641975
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941531"
---
# <a name="using-declaration"></a>using Bildirimi
Using bildirimi tanıtır bir ad bildirim temelli bölgede içine using bildirimi görünür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
using [typename] nested-name-specifier unqualified-id ;  
using declarator-list ;  
```  
  
### <a name="parameters"></a>Parametreler
  
*iç içe-ad-tanımlayıcısı*  
    Bir kapsam çözümleme işleci sonlandırılmış bir dizi ad alanı, sınıf veya numaralandırma adlarını ve kapsam çözümleme işleçleri (:). Tek bir kapsam çözümleme işleci, bir adı genel ad alanından tanıtmak için kullanılabilir. Anahtar sözcüğü **typename** isteğe bağlıdır ve bir taban sınıftan bir sınıf şablonunun içinde sunulan, bağımlı adları çözümlemek için kullanılabilir.  
  
*Nitelenmemiş kimliği*  
    Bir nitelenmemiş kimliği-bir tanımlayıcı, aşırı yüklenmiş işleç adı, bir kullanıcı tanımlı sabit değer operatörü veya dönüştürme işlev adı, bir sınıf yok edici adı veya bir şablon adı ve bağımsız değişken listesi olabilen ifade.  
  
*bildirimci listesi*  
    Virgülle ayrılmış bir listesi [**typename**] *iç içe-adı-specifier* *kimliği nitelenmemiş* Bildirimciler, isteğe bağlı olarak üç nokta ve ardından.
    
## <a name="remarks"></a>Açıklamalar  
Bir using bildirimi tanıtır nitelenmemiş bir ad bir varlık için bir eşanlamlı olarak başka bir yerde bildirilmiş. Açık nitelik göründüğü bildirimi bölgede olmadan kullanılacak belirli bir ad alanındaki tek bir ad sağlar. Tersine budur [using yönergesi](../cpp/namespaces-cpp.md#using_directives), veren *tüm* adların niteleme olmadan kullanılmasını için bir ad alanı. **Kullanarak** için de anahtar sözcüğü kullanılır [tür diğer adları](../cpp/aliases-and-typedefs-cpp.md).  
  
## <a name="example"></a>Örnek  
 Bir using bildirimi bir sınıf tanımı içinde kullanılabilir.  
  
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
Kullanarak bir bir üye bildirmek için kullanıldığında bildiriminin bir temel sınıf üyesine başvurmalıdır.  
  
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
Üyeleri bildirilen kullanarak bir kullanarak bildirim açık nitelik kullanılarak başvurulabilir. `::` Ön ek, genel ad alanına başvuruyor.  
  
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
Bir kullanırken, bildirim tarafından oluşturulan eş anlamlı kullanarak noktasında geçerli olan tanımlara başvurur, bildirimi yapılan bildirimi. Kullandıktan sonra bir ad alanına eklenen tanımları bildirimi geçerli eş anlamlı sözcükler değildir.  
  
Bir ad tarafından tanımlanan bir **kullanarak** özgün adı için bir diğer ad bildirimi şu şekildedir. Türü, bağlantı veya diğer özgün bildiriminin öznitelikleri etkilemez.  
  
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
Ad alanlarında, bir dizi yerel bildirimleri işlevleri göre ve bildirimlerini kullanarak herhangi bir tek bir ad, bildirim temelli bir bölgede yer verilmiştir, bunların tümü aynı varlığa başvurmalıdır ya da tüm işlevlere başvurması gerekir.  
  
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
  
 Yukarıdaki örnekte `using B::i` deyimi neden olan ikinci bir `int i` içinde bildirilmelerini `g()` işlevi. `using B::f` Deyimi ile çakışan değil `f(char)` işlev adlarını tarafından tanıtılan olduğundan işlev `B::f` farklı parametre türleri vardır.  
  
## <a name="example"></a>Örnek  
 Yerel işlev bildirimi bildirim kullanarak sunulan işlevi olarak aynı ada ve türe sahip olamaz. Örneğin:  
  
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
 Devralma göre bir kullanırken, bildirimi bir ad bir temel sınıftan türetilmiş sınıf geçersiz kılma sanal üye işlevleri, üye işlevleri temel sınıfında aynı adı ve bağımsız değişken türlerine sahip bir türetilmiş sınıf kapsamı içinde sunar.  
  
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
Using deyiminde belirtilen adın tüm örneklerini bildirimi erişilebilir olmalıdır. Kullanarak bir türetilmiş bir sınıf kullanıyorsa, belirli bir taban sınıfın üye adı bir üyesine erişmek için bildirim erişilebilir olmalıdır. Adlı tüm işlevlere erişilebilir olmalıdır. ad, aşırı yüklü üye işlevini ise.  
  
Üyeleri erişilebilirlik hakkında daha fazla bilgi için bkz. [üye erişim denetimi](../cpp/member-access-control-cpp.md).  
  
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