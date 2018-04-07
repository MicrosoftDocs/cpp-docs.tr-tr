---
title: Önemsiz, standart düzeni, POD ve değişmez değer türleri | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b23a7be-9bad-49fc-8298-31a9a7c556b0
caps.latest.revision: 13
manager: ghogen
ms.openlocfilehash: e977449c1c31b0b3f83c04b9b52a1a0bacb37f31
ms.sourcegitcommit: d9ee6f777974d031570f4260c9581ea2c81ad875
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="trivial-standard-layout-pod-and-literal-types"></a>Önemsiz, standart düzeni, POD ve değişmez değer türleri

Terim *düzeni* sınıf, yapı veya birleşim türünde bir nesnenin üyelerine bellekte nasıl düzenlenir için başvuruyor. Bazı durumlarda, düzeni dil belirtimi tarafından iyi tanımlanmış. Ancak sanal taban sınıflar, sanal işlevler, farklı bir erişim denetimi üyeleriyle gibi belirli C++ dil özellikleri sınıfta veya yapı içeriyorsa, ardından derleyici boş bir düzen seçin. Bu düzen hangi iyileştirmeleri gerçekleştirilen bağlı olarak farklılık gösterebilir ve çoğu durumda nesne bile bitişik bir bellek alanını belleğinde değil. Örneğin, bir sınıfın sanal işlevler varsa, bu sınıfın tüm örnekleri tek sanal işlev tablosunu paylaş. Gibi türler Elbette de oldukça faydalıdır, ancak bunlar da sınırlamaları vardır. Düzen tanımsız olduğundan, C gibi diğer dillerde yazılmış programları geçirilemez ve bitişik olmayan olabileceğinden, güvenilir bir şekilde hızlı alt düzey işlevleriyle gibi kopyalanamaz `memcopy` veya bir ağ üzerinden seri hale getirilmiş.

 C++ programları ve üzerinde belirli bellek düzeni bağımlı işlemler için herhangi bir türde uygunluğu hakkında nedeni metaprograms yanı sıra derleyicileri etkinleştirmek için C ++ 14 basit sınıflar ve yapılar üç kategorisi sunulan: *Önemsiz*, *standart düzeni*, ve *POD* veya düz eski verileri. İşlev şablonları standart kitaplık sahip `is_trivial<T>`, `is_standard_layout<T>` ve `is_pod<T>` belirli bir türde belirli bir kategoriye ait olup olmadığını belirler.

## <a name="trivial-types"></a>Önemsiz türleri

 Olduğunda sınıfta veya yapı c++ derleyicisi tarafından sağlanan sahip veya önemsiz bir tür ise özel üye işlevleri açıkça varsayılan. Bitişik bellek alanı kaplar. Farklı erişim tanımlayıcıları üyeleriyle olabilir. C++'da, bu durumda üyelerini sıralamak nasıl seçmek derleyici ücretsizdir. Bu nedenle, bu tür nesneleri memcopy edebilirsiniz ancak bunları güvenilir bir C programı kullanamayacaklarını. Önemsiz türü T char veya imzasız char bir diziye kopyalar ve bir T değişkende güvenli bir şekilde kopyalanır. Hizalama gereksinimleri nedeniyle unutmayın, tür üyeleri arasında doldurma bayt olabilir.

 Önemsiz türleri bir önemsiz varsayılan oluşturucu, Önemsiz kopya Oluşturucu, Önemsiz copy atama işleci ve önemsiz yıkıcı sahiptir. Her durumda *Önemsiz* Oluşturucusu/işleci/yıkıcı kullanıcı tarafından sağlanan değil ve sahip bir sınıfın ait olduğu anlamına gelir

- hiçbir sanal işlevler veya sanal taban sınıflar

- Hiçbir temel sınıflarının bir karşılık gelen önemsiz olmayan Oluşturucusu/işleci/yok Edicisi

- sınıf türü ile ilgili önemsiz olmayan Oluşturucusu/işleci/yıkıcı hiçbir veri üyesi

Aşağıdaki örnekler Önemsiz türleri gösterir. Trivial2, varlığını içinde `Trivial2(int a, int b)` Oluşturucusu gerektirir varsayılan bir oluşturucu sağlayın. Önemsiz olarak nitelemek türü için o Oluşturucusu açıkça varsayılan gerekir.

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

## <a name="standard-layout-types"></a>Standart yerleşim türleri

 Bu, bir sınıf veya yapı C dilinde bulunmayan sanal işlevleri gibi belirli C++ dil özellikleri içermiyor ve tüm üyeleri aynı erişim denetimi sahip olduğunda, bir Standart Düzen türüdür. Memcopy yapabilir ve C programlar tarafından kullanılabilecek düzeni yeterince tanımlanır. Standart Düzen türü kullanıcı tanımlı özel üye işlevleri olabilir. Ayrıca, standart yerleşim türleri bu özelliklere sahiptir:

- sanal işlevler ya da sanal taban sınıflar

- tüm statik olmayan veri üyeleri aynı erişim denetimi hakkı

- sınıf türü tüm statik olmayan üye standart düzeni

- Standart düzeni tüm temel sınıflar

- ilk statik olmayan veri üyesi aynı türde hiçbir taban sınıfları içerir.

- Bu koşullardan biri uyuyor:

  - Statik olmayan veri üyeleriyle çoğu türetilmiş sınıf ve birden fazla temel sınıf hiçbir statik olmayan veri üyesi veya

  - Statik olmayan veri üyeleri hiçbir temel sınıflarının sahip

Aşağıdaki kod bir Standart Düzen türünün bir örneği gösterir:

```cpp
struct SL
{
   // All members have same access:
   int i;
   int j;
   SL(int a, int b) : i(a), j(b) {} // User-defined constructor OK
};

```

 Son iki gereksinimleri belki de daha iyi koduyla gösterilebilir. Sonraki örnekte rağmen tabanıdır standart düzeni, `Derived` standart düzeni değildir, çünkü her iki BT (en çok türetilen sınıfı) ve `Base` statik olmayan veri üyelere sahip:

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

 Bu örnekte `Derived` standart düzeni çünkü `Base` hiçbir statik olmayan veri üyesi bulunur:

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

 Türetilmiş ayrıca standart düzeni olacaktır, `Base` veri üyeleri olan ve `Derived` yalnızca üye işlevleri vardı.

## <a name="pod-types"></a>POD türleri

 Sınıfta veya yapı Önemsiz hem standart düzeni olduğunda, bir POD (düz eski verileri) türü olur. POD türleri bellek düzenini bu nedenle bitişik ve her üye ikili g/ç ve daha önce bildirildi ve böylece baytı kopyalar üye bu türlerinde gerçekleştirilebilir daha yüksek bir adresi vardır.  Skaler türler int gibi de POD türleridir. Sınıflardır POD türleri, statik olmayan veri üye olarak yalnızca POD türü olabilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, önemsiz, standart düzeni arasındaki farklılıklar gösterir ve POD türleri:

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
- Diziler void skaler türleri veya başvurur
- Önemsiz yıkıcı olan bir sınıfı ve olan hareket veya oluşturucuları kopyalama bir veya daha fazla constexpr oluşturucular. Ayrıca, tüm temel sınıflar ve statik olmayan veri üyeleri değişmez değer türleri olmalıdır ve kalıcı değil.

## <a name="see-also"></a>Ayrıca Bkz.

 [Temel Kavramlar](../cpp/basic-concepts-cpp.md)