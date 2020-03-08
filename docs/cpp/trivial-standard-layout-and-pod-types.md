---
title: Önemsiz, Standart Düzen, POD ve değişmez değer türleri
ms.date: 04/05/2018
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: 2745302b3ebd7927e9d839e4661e884a2bd91042
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865799"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>Önemsiz, Standart Düzen, POD ve değişmez değer türleri

*Düzen* terimi, bir sınıf, yapı veya birleşim türü nesnesinin üyelerinin bellekte nasıl düzenlendiğini gösterir. Bazı durumlarda, düzen dil belirtimi tarafından iyi tanımlanır. Ancak, bir sınıf veya yapı, sanal C++ temel sınıflar, sanal işlevler, farklı erişim denetimine sahip Üyeler gibi bazı dil özelliklerini içerdiğinde, bir düzen seçmek için derleyici ücretsizdir. Bu düzen, uygulanan iyileştirmelere göre farklılık gösterebilir ve birçok durumda nesnenin bitişik bir bellek alanını kaplamayabilir. Örneğin, bir sınıfta sanal işlevler varsa, bu sınıfın tüm örnekleri tek bir sanal işlev tablosu paylaşabilir. Bu tür türler çok kullanışlıdır, ancak aynı zamanda sınırlamaları vardır. Düzen tanımsız olduğu için, C gibi diğer dillerde yazılmış programlara geçirilemez ve bunlar bitişik olmayan, `memcopy`veya ağ üzerinden serileştirilmiş gibi hızlı alt düzey işlevlerle güvenilir bir şekilde kopyalanamazlar.

C++ 14, belirli bir bellek C++ düzenine bağlı olan işlemler için verilen herhangi bir tür uygunluğu konusunda nedenlerle derleyicilerin yanı sıra programlar ve metaprogramlar sağlamak için basit sınıfların ve yapıların üç kategorisini sunmuştur: *Önemsiz*, *Standart Düzen*ve *Pod* veya düz eski veriler. Standart Kitaplık, belirli bir türün belirli bir kategoriye ait olup olmadığını belirten `is_trivial<T>`, `is_standard_layout<T>` ve `is_pod<T>` işlev şablonlarına sahiptir.

## <a name="trivial-types"></a>Önemsiz türler

İçindeki C++ bir sınıf veya yapı derleyicinin sağladığı veya açıkça varsayılan olarak ayarlanmış özel üye işlevse, önemsiz bir türdür. Bitişik bir bellek alanı kaplar. Farklı erişim belirticilerine sahip üyelere sahip olabilir. ' C++De, derleyici bu durumda üyelerin nasıl sipariş alınacağını seçmek için ücretsizdir. Bu nedenle, bu tür nesneleri Memcopy yapabilirsiniz ancak bunları bir C programından güvenilir bir şekilde kullanamazsınız. Önemsiz tür T bir char veya işaretsiz char dizisine kopyalanabilir ve güvenle bir T değişkenine geri kopyalanabilir. Hizalama gereksinimleri nedeniyle, tür üyeleri arasında Doldurma baytları olabileceğini unutmayın.

Önemsiz türler için önemsiz bir varsayılan Oluşturucu, Önemsiz kopya Oluşturucu, Önemsiz kopya atama işleci ve basit yıkıcı vardır. Her durumda *Önemsiz* , oluşturucunun/işlecin/yıkıcının Kullanıcı tarafından sağlanmayacağı ve

- sanal işlev veya sanal temel sınıf yok,

- ilgili önemsiz olmayan oluşturucuya/işlece/yok ediciye sahip temel sınıf yok

- karşılık gelen önemsiz olmayan oluşturucuya/işlece/yıkıcıya sahip sınıf türünde veri üyesi yok

Aşağıdaki örneklerde önemsiz türler gösterilmektedir. Trivial2 ' de, `Trivial2(int a, int b)` oluşturucusunun varlığı için varsayılan bir Oluşturucu sağlamanız gerekir. Türün önemsiz olarak nitelendirime için, o oluşturucuyu açık bir şekilde varsayılan yapmanız gerekir.

```cpp
struct Trivial
{
      int i;
private:
   int j;
   };

struct Trivial2
{
   int i;
   Trivial2(int a, int b) : i(a), j(b) {}
   Trivial2() = default;
   private:
   int j;   // Different access control
};
```

## <a name="standard-layout-types"></a>Standart Düzen türleri

Bir sınıf veya yapı, C dilinde bulunmayan sanal C++ işlevler gibi bazı dil özelliklerini içermiyorsa ve tüm Üyeler aynı erişim denetimine sahip olduğunda, bu bir standart Düzen türüdür. Bu, Memcopy ile yapılabilir ve düzen, C programları tarafından tüketilen yeterli tanımlı değildir. Standart Düzen türlerinde Kullanıcı tanımlı özel üye işlevleri bulunabilir. Buna ek olarak, Standart Düzen türleri aşağıdaki özelliklere sahiptir:

- sanal işlev veya sanal temel sınıf yok

- Tüm statik olmayan veri üyeleri aynı erişim denetimine sahip

- sınıf türündeki statik olmayan tüm Üyeler standart düzendir

- Tüm temel sınıflar standart düzendir

- , ilk statik olmayan veri üyesiyle aynı türde temel sınıfa sahip değildir.

- Şu koşullardan birini karşılar:

  - en fazla türetilmiş sınıfta statik olmayan veri üyesi ve statik olmayan veri üyelerine sahip birden fazla temel sınıf yok veya

  - statik olmayan veri üyeleri olan temel sınıflara sahip değil

Aşağıdaki kod, bir standart Düzen türünün bir örneğini göstermektedir:

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};
```

Son iki gereksinim kod ile daha iyi gösterilebilir. Sonraki örnekte, taban Standart Düzen olsa da `Derived` Standart Düzen değildir çünkü her ikisi de (en fazla türetilmiş sınıf) ve `Base` statik olmayan veri üyelerine sahiptir:

```cpp
struct Base
{
   int i;
   int j;
};

// std::is_standard_layout<<Derived> == false!
struct Derived : public Base
{
   int x;
   int y;
};
```

Bu örnekte, `Base` statik olmayan veri üyesi olmadığından `Derived` standart düzendir:

```cpp
struct Base
{
   void Foo() {}
};

// std::is_standard_layout<<Derived> == true
struct Derived : public Base
{
   int x;
   int y;
};
```

`Base` veri üyeleri ve `Derived` yalnızca üye işlevleri içeriyorsa, türetilmiş Standart Düzen de olur.

## <a name="pod-types"></a>POD türleri

Bir sınıf veya yapı hem önemsiz hem de Standart Düzen olduğunda, bu bir POD (düz eski veriler) türüdür. POD türlerinin bellek düzeni bu nedenle birbirini karşılanmıştır ve her üyenin bundan önce belirtilen Üyeden daha yüksek bir adresi vardır ve bu nedenle bayt kopyaları ve ikili g/ç için bayt bu türler üzerinde gerçekleştirilebilir.  İnt gibi skaler türler de POD türleridir. Sınıf olan POD türleri, statik olmayan veri üyeleri olarak yalnızca POD türlerine sahip olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, önemsiz, Standart Düzen ve POD türleri arasındaki farklılıklar gösterilmektedir:

```cpp
#include <type_traits>
#include <iostream>

using namespace std;

struct B
{
protected:
   virtual void Foo() {}
};

// Neither trivial nor standard-layout
struct A : B
{
      int a;
   int b;
   void Foo() override {} // Virtual function
};

// Trivial but not standard-layout
struct C
   {
      int a;
private:
   int b;   // Different access control
};

// Standard-layout but not trivial
struct D
{
   int a;
   int b;
   D() {} //User-defined constructor
};

struct POD
{
   int a;
   int b;
};

int main()
{
   cout << boolalpha;
   cout << "A is trivial is " << is_trivial<A>() << endl; // false
   cout << "A is standard-layout is " << is_standard_layout<A>() << endl;  // false

   cout << "C is trivial is " << is_trivial<C>() << endl; // true
   cout << "C is standard-layout is " << is_standard_layout<C>() << endl;  // false

   cout << "D is trivial is " << is_trivial<D>() << endl;  // false
   cout << "D is standard-layout is " << is_standard_layout<D>() << endl; // true

   cout << "POD is trivial is " << is_trivial<POD>() << endl; // true
   cout << "POD is standard-layout is " << is_standard_layout<POD>() << endl; // true

   return 0;
}
```

## <a name="literal_types"></a>Değişmez değer türleri

Değişmez değer türü, düzen derleme zamanında belirlenebileceği bir türdür. Aşağıdakiler değişmez türlerdir:

- void
- skaler türler
- başvurular
- Void, skaler türler veya başvuruların dizileri
- Önemsiz yok edicisi olan bir sınıf ve taşınmayan ya da kopya Oluşturucu olmayan bir veya daha fazla constexpr Oluşturucusu. Ayrıca, tüm statik olmayan veri üyeleri ve temel sınıflar değişmez türler olmalı ve geçici olmamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)