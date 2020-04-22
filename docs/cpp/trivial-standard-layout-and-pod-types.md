---
title: Önemsiz, standart düzen, POD ve gerçek türleri
ms.date: 04/05/2018
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: 6fe237386e63fcdd96621edabf2b0b66ce72e4f8
ms.sourcegitcommit: 435133128b18cdd02d33d929b16c33e7ec40e9eb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81664130"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>Önemsiz, standart düzen, POD ve gerçek türleri

*Düzen* terimi, sınıf, yapı veya birleşim türünden bir nesnenin üyelerinin bellekte nasıl düzenlendiğini ifade eder. Bazı durumlarda, düzen dil belirtimi tarafından iyi tanımlanır. Ancak bir sınıf veya yapı sanal temel sınıflar, sanal işlevler, farklı erişim denetimine sahip üyeler gibi belirli C++ dil özelliklerini içeriyorsa, derleyici bir düzen seçmekte özgürdür. Bu düzen, hangi optimizasyonların gerçekleştirildiğine bağlı olarak değişebilir ve çoğu durumda nesne bitişik bir bellek alanını bile işgal etmeyebilir. Örneğin, bir sınıfın sanal işlevleri varsa, bu sınıfın tüm örnekleri tek bir sanal işlev tablosunu paylaşabilir. Bu tür çok yararlıdır, ancak sınırlamaları da vardır. Düzen tanımlanmadığından C gibi diğer dillerde yazılmış programlara aktarılamazlar ve bitişik olmadıkları için ağ üzerinden `memcopy`seri hale getirilmiş veya hızlı düşük düzeyli işlevlerle güvenilir bir şekilde kopyalanamazlar.

Derleyicilerin yanı sıra C++ programlarının ve meta programlarının belirli bir bellek düzenine bağlı işlemler için belirli bir türe uygunluğu hakkında muhakeme etmesini sağlamak için, C++14 basit sınıflar ve yapıların üç kategorisini tanıttı: *önemsiz,* *standart düzen*ve POD veya *Düz* Eski Veriler. Standart Kitaplık işlev `is_trivial<T>` `is_standard_layout<T>` şablonları `is_pod<T>` vardır ve belirli bir türün belirli bir kategoriye ait olup olmadığını belirler.

## <a name="trivial-types"></a>Önemsiz türleri

C++'daki bir sınıf veya yapı derleyici tarafından sağlanan veya açıkça varsayılan özel üye işlevleri varsa, bu önemsiz bir türdür. Bitişik bir bellek alanı kaplar. Farklı erişim belirtecileri ile üyeleri olabilir. C++'da derleyici bu durumda üyeleri nasıl sıralamayı seçmekte serbesttir. Bu nedenle, bu tür nesneleri taklit edebilirsiniz, ancak bunları güvenilir bir Şekilde C programından tüketemezsiniz. Önemsiz bir T türü bir dizi char veya imzasız char'a kopyalanabilir ve güvenli bir şekilde t değişkenine kopyalanabilir. Hizalama gereksinimleri nedeniyle, tür üyeleri arasında dolgu baytları olabileceğini unutmayın.

Önemsiz türleri önemsiz bir varsayılan oluşturucu, önemsiz kopya oluşturucu, önemsiz kopya atama işleci ve önemsiz yıkıcı var. Her durumda, *önemsiz* yapıcı / operatör / yıkıcı kullanıcı tarafından sağlanan değildir ve olan bir sınıfa ait anlamına gelir

- sanal işlevler veya sanal temel sınıfları,

- karşılık gelen önemsiz olmayan bir oluşturucu/işleç/yıkıcı ile hiçbir temel sınıf

- ilgili önemsiz olmayan bir oluşturucu/işleç/yıkıcı ile sınıf türünde veri üyesi yok

Aşağıdaki örnekler önemsiz türleri gösterir. Trivial2'de, `Trivial2(int a, int b)` oluşturucunun varlığı varsayılan bir oluşturucu sağlamanızı gerektirir. Türün önemsiz olarak nitelendirilemesi için, bu oluşturucuyu açıkça varsayılan olarak varsayılan olarak belirtmelisiniz.

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

## <a name="standard-layout-types"></a>Standart düzen türleri

Bir sınıf veya yapı C dilinde bulunmayan sanal işlevler gibi belirli C++ dil özelliklerini içermiyorsa ve tüm üyeler aynı erişim denetimine sahipse, standart düzen türüdür. Bu memcopy-able ve düzen yeterince C programları tarafından tüketilen olabilir tanımlanır. Standart düzen türleri, kullanıcı tanımlı özel üye işlevlerine sahip olabilir. Buna ek olarak, standart düzen türleri şu özelliklere sahiptir:

- sanal işlevler veya sanal temel sınıfları yok

- tüm statik olmayan veri üyeleri aynı erişim denetimine sahiptir

- sınıf türünün tüm statik olmayan üyeleri standart düzen

- herhangi bir temel sınıf standart düzen

- ilk statik olmayan veri üyesiyle aynı türden taban sınıfları yoktur.

- bu koşullardan birini karşılar:

  - en çok türetilmiş sınıfta statik olmayan veri üyesi ve statik olmayan veri üyeleri ile birden fazla taban sınıf veya

  - statik olmayan veri üyeleri ile hiçbir temel sınıfları vardır

Aşağıdaki kod, standart düzen türüne bir örnek gösterir:

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};
```

Son iki gereksinimleri belki de daha iyi kod ile gösterilebilir. Sonraki örnekte, Temel standart düzen olsa `Derived` da, hem (en çok türetilmiş `Base` sınıf) hem de statik olmayan veri üyeleri olduğundan standart düzen değildir:

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

Statik olmayan `Derived` veri üyesi `Base` olmadığından, bu örnekte standart düzen vardır:

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

Türemiş, veri üyeleri `Base` varsa ve `Derived` yalnızca üye işlevleri varsa standart düzen de olacaktır.

## <a name="pod-types"></a>POD türleri

Bir sınıf veya yapı hem önemsiz hem de standart düzen olduğunda, bu bir POD (Düz Eski Veri) türüdür. Bu nedenle POD türlerinin bellek düzeni bitişiktir ve her üyenin daha önce bildirilen üyeden daha yüksek bir adresi vardır, böylece bayt kopyaları için bayt ve ikili G/Ç bu türde gerçekleştirilebilir.  Int gibi skaler türleri de POD türleridir. Sınıf olan POD türleri yalnızca statik olmayan veri üyesi olarak yalnızca POD türlerine sahip olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, önemsiz, standart düzen ve POD türleri arasındaki ayrımları gösterir:

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

## <a name="literal-types"></a><a name="literal_types"></a>Edebi türler

Gerçek bir tür, düzeni derleme zamanında belirlenebilen bir türdür. Aşağıdaki gerçek türleri şunlardır:

- void
- skaler türler
- başvurular
- Boşluk, skaler türleri veya referansdizileri
- Önemsiz bir yıkıcısı olan bir sınıf ve bir veya daha fazla constexpr yapıcılar hareket veya kopya yapıcılar değildir. Ayrıca, tüm statik olmayan veri üyeleri ve temel sınıfları gerçek türleri olmalı ve geçici olmamalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)
