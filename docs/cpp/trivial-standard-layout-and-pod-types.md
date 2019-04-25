---
title: Önemsiz, Standart Düzen ve POD değişmez değer türleri
ms.date: 04/05/2018
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
ms.openlocfilehash: c742f4c84a1b2ba558b790d7eea7760902da7818
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266770"
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>Önemsiz, Standart Düzen ve POD değişmez değer türleri

Terim *Düzen* bellekte sınıf, yapı veya birleşim türü, bir nesnenin üyelerine nasıl düzenlenir için ifade eder. Bazı durumlarda, Düzen dil belirtimine göre iyi tanımlanmış. Ancak bir sınıf veya yapı sanal temel sınıflar, sanal işlevler, farklı erişim denetimi ile üyeleri gibi belirli C++ dil özellikleri içerdiğinde, ardından derleyici bir düzen seçebilirsiniz. Bu düzen hangi iyileştirmeleri gerçekleştirilen bağlı olarak değişiklik gösterebilir ve çoğu durumda nesne bile bir bitişik bellek alanının belleğinde değil. Örneğin, bir sınıf sanal işlevler varsa, bu sınıfın tüm örnekleri tek sanal işlev tablosuna paylaşabilir. Gibi türler Elbette çok yararlı olur, ancak aynı zamanda sınırlamalara sahiptirler. Düzen tanımsız olduğundan bunlar C gibi diğer dillerde yazılmış programlar için geçirilemez ve bitişik olmayan olabileceğinden, güvenilir bir şekilde hızlı alt düzey işlevlerle gibi kopyalanamaz `memcopy` veya bir ağ üzerinden seri hale getirilmiş.

C ++ 14 derleyicileri hem de C++ programları ve üzerinde bir belirli bellek düzeni bağlı işlemler için belirtilen her türlü uygunluğu konusunda nedeni metaprograms etkinleştirmek için basit sınıflar ve yapılar üç kategorisi sunulan: *Önemsiz*, *Standart Düzen*, ve *POD* veya düz eski veriler. Standart kitaplık işlev şablonları sahip `is_trivial<T>`, `is_standard_layout<T>` ve `is_pod<T>` verilen tür belirli bir kategoriye ait olup olmadığını belirler.

## <a name="trivial-types"></a>Önemsiz türler

Ne zaman bir sınıfın veya yapının c++ derleyici tarafından sağlanan olan veya basit bir tür ise özel üye işlevleri, açıkça varsayılan. Bu, bitişik bellek alanı kaplar. Farklı erişim belirticileri üyeleriyle sağlayabilirsiniz. C++'da, derleyici bu durumda üyelerini sıralamak üzere nasıl seçme ücretsiz olarak kullanılabilir. Bu nedenle, bu tür nesneler memcopy edebilirsiniz ancak bunların güvenilir bir şekilde bir C programı kullanamıyor. Bir basit türü T char unsigned char veya bir diziye kopyalanır ve güvenli bir şekilde geri T değişkene kopyalanır. Hizalama gereksinimleri nedeniyle unutmayın, tür üyeleri arasında doldurma bayt olabilir.

Önemsiz türler Önemsiz varsayılan oluşturucu, basit bir kopya Oluşturucu, Önemsiz kopya atama işleci ve önemsiz yok Edicisi vardır. Her durumda *Önemsiz* Oluşturucu/işleci/yıkıcı kullanıcı tarafından sağlanan değil ve sahip bir sınıfın ait olduğu anlamına gelir

- hiçbir sanal işlevler veya sanal temel sınıflar

- karşılık gelen önemsiz Oluşturucu/işleci/yıkıcı ile temel olmayan sınıflar

- karşılık gelen önemsiz Oluşturucu/işleci/yıkıcı ile sınıf türünün hiçbir veri üyeleri

Aşağıdaki örnekler, basit türleri gösterir. Trivial2, varlığı içinde `Trivial2(int a, int b)` Oluşturucusu gerektirir bir varsayılan oluşturucu sağlayın. Önemsiz olarak nitelemek türü için bu oluşturucu açıkça varsayılan gerekir.

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

Bu, bir sınıf veya yapı, C dilinde bulunmayan sanal işlevleri gibi belirli C++ dil özellikleri içermiyor ve tüm üyeleri aynı erişim denetimine sahip bir Standart Düzen türüdür. Memcopy yapabilir ve düzenini yeterince C programları tarafından tüketilebilecek tanımlanır. Standart Düzen türü kullanıcı tanımlı özel üye işlevleri olabilir. Ayrıca, Standart Düzen türü şu özelliklere sahiptir:

- hiçbir sanal işlevler veya sanal temel sınıflar

- tüm statik olmayan veri üyeleri aynı erişim denetimi sahiptir

- Standart Düzen sınıf türünün tüm statik olmayan üyeler

- Standart Düzen tüm temel sınıflar

- ilk statik olmayan veri üyesi aynı türden temel sınıfa sahip.

- Bu koşullardan biri karşılar:

  - Statik olmayan veri üyeleriyle en çok türetilen sınıf ve birden fazla temel sınıf yok statik olmayan veri üyesi veya

  - Statik olmayan veri üyeleriyle temel sınıfa sahip

Aşağıdaki kod, bir Standart Düzen türünün bir örneği gösterilmektedir:

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};
```

Son iki gereksinimleri belki de daha iyi kod ile gösterilebilir. Sonraki örnekte olsa bile tabanıdır Standart Düzen `Derived` Standart Düzen olmadığından, hem BT (en çok türetilen sınıf) ve `Base` statik olmayan veri üyeleri sahiptir:

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

Bu örnekte `Derived` Standart Düzen çünkü `Base` statik olmayan veri üyeleri yoktur:

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

Türetilmiş ayrıca standart Düzen olacaktır, `Base` veri üyeleri vardı ve `Derived` yalnızca üye işlevler vardı.

## <a name="pod-types"></a>POD türleri

Bir sınıf veya yapı hem basit hem de Standart Düzen olduğunda, bir POD (düz eski veriler) türü olur. Bellek düzeni POD türleri, bu nedenle bitişik değil ve her üyesinin bu türlerde ikili g/ç ve böylece baytı kopyalar, daha önce bildirilen üye gerçekleştirilebilir daha yüksek bir adresi vardır.  Skaler türler int gibi da POD türleridir. Sınıflar POD türleri yalnızca POD türleri statik olmayan veri üyesi olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, önemsiz, Standart Düzen arasındaki farklılıklar gösterir ve POD türleri:

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

## <a name="literal_types"></a> Değişmez değer türleri

Değişmez değer türü, düzen derleme zamanında belirlenebilir biridir. Değişmez değer türleri şunlardır:

- void
- skaler türler
- başvurular
- Void diziler, skaler türleri veya başvuruyor
- Önemsiz bir yok Edicisi olan bir sınıf ve bir veya daha fazla constexpr oluşturucular olan hareket ya da oluşturucular kopyalayın. Ayrıca, tüm temel sınıflar ve statik olmayan veri üyeleri değişmez değer türleri olmalıdır ve kalıcı değil.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)