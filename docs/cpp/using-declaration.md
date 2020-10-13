---
title: using bildirimi
ms.date: 11/04/2016
helpviewer_keywords:
- using declaration
- declarations [C++], using-declaration
- namespaces [C++], unqualified names in
- using keyword [C++]
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
ms.openlocfilehash: 072ecd325a76e80dbd710c241e39fdf7b969e537
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008256"
---
# <a name="using-declaration"></a>using bildirimi

**`using`** Bildirimi, using bildiriminin göründüğü bildirime dayalı bölgeye bir ad getirir.

## <a name="syntax"></a>Sözdizimi

```
using [typename] nested-name-specifier unqualified-id ;
using declarator-list ;
```

### <a name="parameters"></a>Parametreler

*iç içe ad belirleyicisi* Bir kapsam çözümleme işleci tarafından sonlandırılan bir ad alanı, sınıf veya sabit listesi adı ve kapsam çözümleme işleçleri (::) dizisi. Genel ad alanından bir ad tanıtmak için tek bir kapsam çözümleme işleci kullanılabilir. Anahtar sözcüğü **`typename`** isteğe bağlıdır ve temel sınıftan bir sınıf şablonuna getirilen bağımlı adları çözümlemek için kullanılabilir.

*nitelenmemiş kimlik* Tanımlayıcı, aşırı yüklenmiş bir operatör adı, Kullanıcı tanımlı sabit değer operatörü veya dönüştürme işlevi adı, sınıf yıkıcısı adı veya şablon adı ve bağımsız değişken listesi olabilecek nitelenmemiş bir kimlik ifadesi.

*bildirimci-liste* [ **`typename`** ] *İç içe-ad belirleyicisi* *nitelenmemiş kimlik* bildiricileri ve isteğe bağlı olarak üç nokta olan virgülle ayrılmış bir liste.

## <a name="remarks"></a>Açıklamalar

Using bildirimi, başka bir yerde bildirildiği bir varlığın eşanlamlısı olarak nitelenmemiş bir ad sağlar. Belirli bir ad alanındaki tek bir adın, göründüğü bildirim bölgesinde Açık nitelendirme olmadan kullanılmasına izin verir. Bu, bir ad alanındaki *Tüm* adların nitelik olmadan kullanılmasına izin veren [using yönergesine](../cpp/namespaces-cpp.md#using_directives)karşılık gelir. **`using`** Anahtar sözcüğü, [tür diğer adları](../cpp/aliases-and-typedefs-cpp.md)için de kullanılır.

## <a name="example-using-declaration-in-class-field"></a>Örnek: `using` sınıf alanındaki bildirim

Using bildirimi, sınıf tanımında kullanılabilir.

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

## <a name="example-using-declaration-to-declare-a-member"></a>Örnek: `using` bir üyeyi bildirmek için bildirim

Bir üyeyi bildirmek için kullanıldığında, bir using bildirimi, bir temel sınıfın üyesine başvurmalıdır.

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

## <a name="example-using-declaration-with-explicit-qualification"></a>Örnek: `using` Açık nitelikle bildirim

Using bildirimi kullanılarak belirtilen üyelere, açık nitelik kullanılarak başvurulabilir. `::`Ön ek, genel ad alanına başvurur.

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

## <a name="example-using-declaration-synonyms-and-aliases"></a>Örnek: `using` bildirim eşanlamlıları ve diğer adları

Bir using bildirimi yapıldığında, bildirim tarafından oluşturulan eş anlamlı yalnızca using bildiriminin noktasında geçerli olan tanımlara başvurur. Using bildiriminden sonra bir ad alanına eklenen tanımlar geçerli eş anlamlı değildir.

Bildirim tarafından tanımlanan bir ad **`using`** , özgün adı için bir diğer addır. Özgün bildirimin türünü, bağlantı veya diğer özniteliklerini etkilemez.

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

## <a name="example-local-declarations-and-using-declarations"></a>Örnek: yerel bildirimler ve `using` Bildirimler

Ad alanındaki işlevlere göre, bir dizi yerel bildirim ve tek bir ad için bildirimleri kullanmak bildirim temelli bir bölgede verilirse, bunların tümü aynı varlığa başvurmalıdır veya tümü işlevlere başvurmalıdır.

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

Yukarıdaki örnekte, `using B::i` ifade, işlevde saniyenin bildirilmesine neden olur `int i` `g()` . `using B::f` `f(char)` Tarafından tanıtılan işlev adları `B::f` farklı parametre türlerine sahip olduğundan, ifade işlevle çakışmaz.

## <a name="example-local-function-declarations-and-using-declarations"></a>Örnek: yerel işlev bildirimleri ve `using` Bildirimler

Yerel işlev bildirimi, bildirimi kullanılarak tanıtılan bir işlevle aynı ada ve türe sahip olamaz. Örneğin:

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

## <a name="example-using-declaration-and-inheritance"></a>Örnek: `using` bildirim ve devralma

Devralmayla ilgili olarak, bir using bildirimi temel sınıftan türetilmiş bir sınıf kapsamına bir ad oluşturduğunda, türetilmiş sınıftaki üye işlevleri, temel sınıftaki aynı ad ve bağımsız değişken türleriyle sanal üye işlevlerini geçersiz kılar.

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

## <a name="example-using-declaration-accessibility"></a>Örnek: `using` bildirim erişilebilirliği

Using bildiriminde bahsedilen bir adın tüm örneklerinin erişilebilir olması gerekir. Özellikle, türetilmiş bir sınıf bir temel sınıfın üyesine erişmek için using bildirimi kullanıyorsa, üye adı erişilebilir olmalıdır. Ad, aşırı yüklenmiş bir üye işlevinin ise, adlı tüm işlevlere erişilebilir olması gerekir.

Üyelerin erişilebilirliği hakkında daha fazla bilgi için bkz. [member-Access Control](../cpp/member-access-control-cpp.md).

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

## <a name="see-also"></a>Ayrıca bkz.

[Ad alanları](../cpp/namespaces-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
