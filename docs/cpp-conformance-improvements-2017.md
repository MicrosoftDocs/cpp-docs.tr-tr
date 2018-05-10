---
title: C++ uygunluk geliştirmeleri | Microsoft Docs
ms.custom: ''
ms.date: 03/11/2018
ms.technology:
- cpp-language
ms.topic: conceptual
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd640b838c10e010cf2ea028d5f693cd2e5ba14
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="c-conformance-improvements-in-visual-studio-2017-versions-150-153improvements153-155improvements155-156improvements156-and-157improvements157"></a>C++ uygunluk geliştirmeleri 15.0, Visual Studio 2017 sürümlerde [15.3](#improvements_153), [15,5](#improvements_155), [15,6](#improvements_156), ve [15.7](#improvements_157)

Genelleştirilmiş constexpr desteği ve Toplamalar için NSDMI, Microsoft Visual C++ Derleyici C ++ 14 standart eklenen özellikler için tamamlanmıştır. Yine de derleyicide C++11 ve C++98 Standartlarındaki bazı özellikler eksiktir. Bkz: [Visual C++ dili uygunluk](visual-cpp-language-conformance.md) derleyici geçerli durumunu gösteren bir tablo için.

## <a name="c11"></a>C++11

### <a name="expression-sfinae-support-in-more-libraries"></a>Daha fazla kitaplık ifade SFINAE desteği

Derleyici decltype ve constexpr deyimleri şablon parametreleri olarak görüntülendiği şablon bağımsız değişken kesintisi ve değiştirme için gerekli olduğu ifade SFINAE, kendi desteği geliştirmeye devam eder. Daha fazla bilgi için bkz: [Visual Studio 2017 RC ifade SFINAE yenilikleri](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

## <a name="c-14"></a>C++ 14

### <a name="nsdmi-for-aggregates"></a>Toplamalar için NSDMI

Bir toplama, bir dizi veya hiçbir kullanıcı tarafından sağlanan oluşturucusu, hiçbir özel veya korumalı olmayan statik veri üyeleri, hiçbir temel sınıflar ve hiçbir sanal işlevler sınıfıyla ' dir. C ++ 14 toplamalar'den itibaren üye başlatıcıları içerebilir. Daha fazla bilgi için bkz: [üye başlatıcılar ve toplamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

### <a name="extended-constexpr"></a>Genişletilmiş constexpr

Bildirimler, belirli türde varsayarsak ve ifadeler, döngü ifadeleri ve mutation, yaşam süresi içinde constexpr ifade değerlendirme başlangıcından nesnelerin geçiş constexpr şimdi izin gibi ifadeler bildirildi. Ayrıca, artık constexpr statik olmayan üye işlevi örtük olarak const bir gereksinimi yoktur. Daha fazla bilgi için bkz: [constexpr işlevleri kısıtlamalar gevşetme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html).

## <a name="c17"></a>C++17

### <a name="terse-staticassert"></a>Terse static_assert

ileti için static_assert isteğe bağlı bir parametredir. Daha fazla bilgi için bkz: [geniletmek static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

### <a name="fallthrough-attribute"></a>[[fallthrough]] özniteliği

İçinde **/Std: c ++ 17** modu [[fallthrough]] özniteliği switch deyimleri bağlamında başarısızlığı davranışı geçmesini derleyici ipucu olarak kullanılabilir. Bu, derleyici uyarıları bu gibi durumlarda vermesini engeller. Daha fazla bilgi için bkz: [[[fallthrough]] özniteliği için ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

### <a name="generalized-range-based-for-loops"></a>Döngüler için aralık tabanlı genelleştirilmiş

Aralık tabanlı için begin() ve end() aynı türde nesneler döndürmeye döngüler artık gerek yoktur. Bu aralıklardaki tarafından kullanılan bir sentinel döndürülecek end() sağlar [aralığı v3](https://github.com/ericniebler/range-v3) ve tamamlandı ancak-değil-sessiz-yayımlanmış aralıkları teknik belirtim. Daha fazla bilgi için bkz: [Range-Based genelleme For döngüsü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a> Visual Studio 2017 sürüm 15.3 yenilikleri

### <a name="constexpr-lambdas"></a>constexpr lambdas

Lambda ifadeleri şimdi sabit ifadeler kullanılabilir. Daha fazla bilgi için bkz: [Constexpr Lambda](http://open-std.org/JTC1/SC22/WG21/docs/papers/2015/n4487.pdf).

### <a name="if-constexpr-in-function-templates"></a>varsa işlevi şablonlarındaki constexpr

İşlev şablonu içerebilir `if constexpr` derleme zamanı dallanma etkinleştirmek için deyimleri. Daha fazla bilgi için bkz: [varsa constexpr](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0128r1.html).

### <a name="selection-statements-with-initializers"></a>Seçim deyimleri ile başlatıcıları

Bir `if` deyimi bir değişkene deyimi içinde blok kapsamında tanıtan bir başlatıcı içerebilir. Daha fazla bilgi için bkz: [Başlatıcısı ile seçim deyimleri](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0305r1.html).

### <a name="maybeunused-and-nodiscard-attributes"></a>[[maybe_unused]] ve [[nodiscard]] öznitelikleri

Bir varlık kullanılmadığı görünürken uyarıları Sessiz ya da bir işlev çağrısının dönüş değerini atılır halinde bir uyarı oluşturmak için yeni öznitelikler. Daha fazla bilgi için bkz: [maybe_unused özniteliği için ifadesi](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0212r0.pdf) ve [kullanılmayan, nodiscard ve fallthrough öznitelikleri önerisini](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0068r0.pdf).

### <a name="using-attribute-namespaces-without-repetition"></a>Yineleme olmadan özniteliği ad alanlarını kullanma

Bir öznitelik listesinde yalnızca bir tek bir ad tanımlayıcısı etkinleştirmek için yeni söz dizimi'ı seçin. Daha fazla bilgi için bkz: [C++ öznitelikleri](cpp/attributes.md).

### <a name="structured-bindings"></a>Yapılandırılmış bağlamaları

Artık, değer bir dizi, std::tuple veya std::pair olduğunda veya tüm ortak statik olmayan veri üyeleri olan bir değer, bileşenleri tek tek adlarıyla depolamak için tek bir bildirimde de mümkündür. Daha fazla bilgi için bkz: [yapılandırılmış bağlamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf).

### <a name="construction-rules-for-enum-class-values"></a>Enum sınıfı değerleri için yapım kuralları

Yapıldığında şimdi bir örtük/olmayan-daraltma kapsamlı bir numaralandırmanın temel türüne dönüştürme numaralandırması kendisi için hiçbir Numaralandırıcı tanımına tanıtır ve kaynak listesi başlatma sözdizimini kullanır. Daha fazla bilgi için bkz: [enum için yapım kuralları sınıf değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf).

### <a name="capturing-this-by-value"></a>Yakalama * bu değere göre

`*this` Lambda ifadesi nesnesinde şimdi yakalanıp değeri. Bu, özellikle yeni makine mimarileri üzerinde paralel ve zaman uyumsuz işlemleri lambda çağrılır senaryolara olanak sağlar. Daha fazla bilgi için bkz: [Lambda yakalamayı \*bu değere göre [=\*bu]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html).

### <a name="removing-operator-for-bool"></a>Operator ++ bool için kaldırma

`operator++` artık desteklenir `bool` türleri. Daha fazla bilgi için bkz: [kaldırmak kullanım dışı operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

### <a name="removing-deprecated-register-keyword"></a>Kaldırma "register anahtar sözcüğü" kullanım dışı

`register` Anahtar sözcüğü, daha önce kullanım dışı (ve derleyici tarafından göz ardı) dilinden artık kaldırılmıştır. Daha fazla bilgi için bkz: [kullanım dışı kullanımı anahtar sözcük kaydı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

Visual Studio 2015 güncelleştirme 3 ile uyum geliştirmeleri tam listesi için bkz: [Visual C++ ne ait yeni 2003 2015 aracılığıyla](https://msdn.microsoft.com/en-us/library/mt723604.aspx).

## <a name="improvements_155"></a>  Visual Studio 2017 sürüm 15,5 yenilikleri

[14] ile işaretli özellikleri kullanılabilir koşulsuz olarak bile **/Std: c ++ 14** modu.

### <a name="new-compiler-switch-for-extern-constexpr"></a>Yeni derleyici geçiş için extern constexpr

Visual Studio'nun önceki sürümleri derleyici her zaman vermiş bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15,5, yeni bir derleyici anahtar içinde [/Zc:externConstexpr](build/reference/zc-externconstexpr.md), doğru standartları uyumsuz davranışı etkinleştirir. Daha fazla bilgi için bkz: [extern constexpr bağlantı](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimleri kaldırma

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) dinamik özel durum belirtimleri C ++ 11'de kullanım dışı. Özellik C ++ 17 ' kaldırılır, ancak (hala) kullanım dışı `throw()` belirtimi için diğer ad olarak kesinlikle tutulur `noexcept(true)`. Daha fazla bilgi için bkz: [dinamik özel durum belirtimi kaldırma ve noexcept](#noexcept_removal).

### <a name="notfn"></a>not_fn()

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) `not_fn` , yerini `not1` ve `not2`.

### <a name="rewording-enablesharedfromthis"></a>Enable_shared_from_this uygun sözcükler kullanmak

[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this` C ++ 11'de eklendi. C ++ 17 standart daha iyi belirli köşe durumlarında belirtimi güncelleştirir. [14]

### <a name="splicing-maps-and-sets"></a>Boşluklarına ayıran eşlemeleri ve kümeleri

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) ilişkilendirilebilir kapsayıcıları düğümlerinin ayıklama bu özelliği sağlar (örn., harita, ayarlayın, sırasız\_harita, sırasız\_ayarlayın), daha sonra değiştirilebilir ve geri aynı kapsayıcı veya farklı bir eklenen aynı düğüm türü kullanan kapsayıcı. (Bir düğümden ayıklamak için ortak bir kullanım örneği olan bir `std::map`kayıt anahtarını değiştirin ve yeniden.)

### <a name="deprecating-vestigial-library-parts"></a>Onaysız kılınmadan Vestigial kitaplığı bölümleri

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) birkaç C++ Standart Kitaplığı özelliklerini göre yeni özellikler yıllar içinde kılınan, aksi takdirde çok kullanışlı olmaması veya sorunlu bulundu. Bu özellikler C ++ 17 resmi olarak kullanım dışı bırakılmıştır.

### <a name="removing-allocator-support-in-stdfunction"></a>Destek ayırıcısı olarak std::function kaldırma

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) C ++ 17 önce sınıf şablonu `std::function` ayırıcısı bağımsız değişken sürdü birkaç Oluşturucusu vardı. Ancak, bu bağlamda allocators kullanımını sorunlu ve semantiğini belirsiz. Bu nedenle bu contructors kaldırıldı.

### <a name="fixes-for-notfn"></a>Not_fn() yönelik düzeltmeler

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) için yeni ifadesi `std::not_fn` değeri kategori sarmalayıcı çağırma durumunda yayılmasını desteği sağlar.

### <a name="sharedptrt-sharedptrtn"></a>shared_ptr\<T [] >, shared_ptr\<T [N] >

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) birleştirme `shared_ptr` kitaplığı temelleri C ++ 17'ye değiştirir. [14]

### <a name="fixing-sharedptr-for-arrays"></a>Shared_ptr diziler için düzeltme

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) shared_ptr destek diziler için giderir. [14]

### <a name="clarifying-insertreturntype"></a>Açıklayıcı insert_return_type

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) benzersiz anahtarlar ile ilişkilendirilebilir kapsayıcıları ve sırasız kapsayıcıları benzersiz anahtarlara sahip bir üye işlevi sahip `insert` iç içe geçmiş tür döndüren `insert_return_type`. Bu türü artık uzmanlık Yineleyici ve kapsayıcının NodeType parametreli bir türü olarak tanımlanmış olan döndür.

### <a name="inline-variables-for-the-stl"></a>STL için satır içi değişkenleri

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>Kullanım dışı annex D özellikleri

C++ Standart Annex D dahil olmak üzere onaylanmamış tüm özellikler içeriyor `shared_ptr::unique()`, `<codecvt>`, ve `namespace std::tr1`. Zaman **/Std: c ++ 17** derleyici anahtar olarak ayarlanmışsa, eki d neredeyse tüm standart kitaplığı özellikleri kullanım dışı olarak işaretlenir. Daha fazla bilgi için bkz: [eki D standart kitaplığı özellikleri kullanım dışı olarak işaretlenmiş](#annex_d).

`std::tr2::sys` Ad alanında `<experimental/filesystem>` artık kullanımdan kaldırma Uyarısı altında yayar **/Std: c ++ 14** varsayılan olarak ve şimdi altında kaldırılır **/Std: c ++ 17** varsayılan olarak.

Standart olmayan bir uzantı (sınıf açık özelleştirmeleri) önleme tarafından iostreams geliştirilmiş uyumluluğu.

Standart Kitaplığı şimdi değişken şablonlar dahili olarak kullanır.

Standart Kitaplığı, yanıt noexcept eklenmesi tür sistemi ve dinamik özel durum belirtimleri kaldırılmasını dahil C ++ 17 derleyici değişiklikler olarak güncelleştirildi.

## <a name="improvements_156"></a>  Visual Studio 2017 sürüm 15,6 yenilikleri

### <a name="c17-library-fundamentals-v1"></a>C ++ 17 kitaplığı temelleri V1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) kitaplığı temelleri teknik belirtimi C ++ 17 için standart içerir. Kapsayan güncelleştirmeleri \<Deneysel/tanımlama grubu >, \<Deneysel ve isteğe bağlı >, \<Deneysel/işlevsel >, \<Deneysel ve her türlü >, \<Deneysel/string_view >, \<Deneysel/bellek >, \<Deneysel/memory_resource >, ve \<Deneysel/algoritması >.

### <a name="c17-improving-class-template-argument-deduction-for-the-stl"></a>C ++ 17 geliştirme sınıfı şablon bağımsız değişken kesintisi STL için

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html) taşıma `adopt_lock_t` için parametre listesinin öne `scoped_lock` tutarlı kullanımını etkinleştirmek için `scoped_lock`. İzin `std::variant` kopya atama etkinleştirmek için aşırı yük çözüm daha fazla durumlarda katılmayı Oluşturucusu.

## <a name="improvements_157"></a> Visual Studio 2017 sürüm 15.7 yenilikleri

### <a name="c17-rewording-inheriting-constructors"></a>C ++ 17 Rewording devralan oluşturucular

[P0136R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html) belirleyen bir **kullanarak** bir oluşturucu artık adları bildirimini yapar yerine ek bildirme türetilmiş sınıf oluşturucular türetilmiş sınıf başlatmaları için görünür temel karşılık gelen sınıf oluşturucuları. Bu, C ++ 14 farklıdır. Visual Studio 2017 sürüm 15.7 ve daha sonra içinde **/Std: c ++ 17** modu, C ++ 14 ve oluşturucular devralma kullandığı geçerli kod geçerli olmayabilir veya farklı semantiklerine sahip.

Aşağıdaki örnek, C ++ 14 davranış gösterir:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n) = delete; // Error C2280
};

B b(42L); // Calls B<long>(long), which calls A(int)
          //  due to substitution failure in A<long>(long).
```

Aşağıdaki örnekte gösterildiği **/Std: c ++ 17** Visual Studio 15.7 davranışı:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n)
    {
        //do something
    }
};

B b(42L); // now calls B(int)
```

### <a name="c17-extended-aggregate-initialization"></a>C ++ 17 genişletilmiş toplu başlatma

[P0017R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)

Taban sınıf genel olmayan, ancak altında türetilmiş bir sınıf, ardından erişilebilir ise **/Std: c ++ 17** Visual Studio sürümü artık boş küme ayraçları türetilen türdeki bir nesneyi başlatmak için kullanabileceğiniz 15.7 modunda.

Aşağıdaki örnek, C ++ 14 uyumluluğunu davranış gösterir:

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};

Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

C ++ 17 ' de `Derived` bir toplama artık kabul türü; bu nedenle, başlatılması `Base` özel varsayılan oluşturucusu doğrudan genişletilmiş toplu başlatma kuralının bir parçası gerçekleşir. Daha önce `Base` özel oluşturucu aracılığıyla çağrıldı `Derived` oluşturucusu ve arkadaş bildirimi nedeniyle başarılı oldu.

Aşağıdaki örnek, Visual Studio sürümünde 15.7, C ++ 17 davranış gösterir. **/Std: c ++ 17** modu:

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};

Derived d1; // OK. No aggregate init involved.

Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C ++ 17 bildirme tür olmayan şablon parametreleri otomatik ile

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

İçinde **/Std: c ++ 17** modu, derleyici şimdi türetme ile bildirilmiş bir tür olmayan şablon bağımsız değişken türü **otomatik**:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Geçerli C ++ 14 kod geçerli olmayabilir veya farklı semantiklerine sahip, bu yeni özelliğin bir etkisidir. Örneğin, daha önce geçersiz bazı aşırı artık geçerli değil. Aşağıdaki örnek, çünkü derlenen C ++ 14 kod gösterir çağrısı `foo(p)` bağlı `foo(void*);`. Visual Studio 2017 sürüm 15.7, içinde içinde **/Std: c ++ 17** modu, `foo` işlevi şablonudur en iyi eşleşme.

```cpp
template <int N> struct A;
template <typename T, T N> int foo(A<N>*) = delete;

void foo(void *);

void bar(A<0> *p)
{
    foo(p); // OK in C++14
}
```

Aşağıdaki örnek Visual Studio 15.7 C ++ 17 kodu gösterir **/Std: c ++ 17** modu:

```cpp
template <int N> struct A;
template <typename T, T N> int foo(A<N>*);

void foo(void *);

void bar(A<0> *p)
{
    foo(p); // C2280: 'int foo<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C ++ 17 başlangıç dize dönüştürmeleri (kısmi)

[P0067R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html) tamsayılar ile dizeler arasındaki ve kayan nokta sayıları ile dizeler arasındaki dönüştürmeleri için alt düzey, yerel ayar bağımsız işlevleri. (Visual Studio 15.7 Önizleme yalnızca tamsayı desteklenen 2 itibariyle,.)

### <a name="c20-avoiding-unnecessary-decay-partial"></a>Gereksiz önleme c ++ 20 (kısmi) decay

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf) "decay" kavramı ve, yalnızca const veya reference niteleyicileri kaldırmanın arasında ayrım ekler.  Yeni tür ayırdedici nitelik `remove_reference_t` değiştirir `decay_t` bazı bağlamlarda. Desteği `remove_cvref_t` değil henüz Visual Studio 2017 sürüm itibariyle 15.7 Preview 2 uygulanmadı.

### <a name="c17-parallel-algorithms"></a>C ++ 17 paralel algoritmalar

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html) küçük değişiklikler ile standart içine paralellik TS birleştirilmiş.

### <a name="c17-hypotx-y-z"></a>C ++ 17 hypot (x, y, z)

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf) için üç yeni aşırı ekler `std::hypot`, türleri için **float**, **çift**, ve **uzun çift**, her biri üç giriş parametresi yok.

### <a name="c17-filesystem"></a>C ++ 17 \<filesystem >

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html) birkaç ifadesi değişiklikleri ile standart içine dosya sistemi TS devralır.

### <a name="c17-mathematical-special-functions"></a>C ++ 17 matematiksel özel işlevler

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) önceki teknik belirtimlere matematiksel özel işlevler için standart uyarlar \<cmath > Üstbilgi.

### <a name="c17-deduction-guides-for-the-stl"></a>C ++ 17 kesintisi STL için size yol gösterir

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html) C ++ 17 benimsenmesi yararlanmak için STL güncelleştirmeleri [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), sınıf şablon bağımsız değişken kesintisi için destek ekler.

### <a name="c17-repairing-elementary-string-conversions"></a>C ++ 17 onardıktan başlangıç dize dönüşümleri

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html) yeni başlangıç dize dönüştürme işlevleri yeni bir üstbilgi P0067R5 taşıma \<charconv > ve hata işleme kullanmayı değiştirme gibi diğer geliştirmeler yapmak `std::errc` yerine `std::error_code`.

### <a name="c17-constexpr-for-chartraits-partial"></a>C ++ 17 constexpr char_traits (kısmi) için

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) değişikliklerini `std::traits_type` üye işlevleri `length`, `compare`, ve `find` olun yapmak için `std::string_view` sabit ifadeler de kullanılabilir. (Visual Studio 2017 içinde sürüm 15,6, Clang/LLVM için yalnızca desteklenir. 15.7 2, destek neredeyse önizlemesidir sürümünde ClXX için de tamamlayın.)

## <a name="bug-fixes-in-visual-studio-versions-150-153update153-155update155-and-157update157"></a>Visual Studio sürümlerinde 15.0, hata düzeltmeleri [15.3](#update_153), [15,5](#update_155), ve [15.7](#update_157)

### <a name="copy-list-initialization"></a>Kopya listesi başlatma

Visual Studio 2017, doğru nesne oluşturma, Visual Studio 2015'te yakalanan değil ve çökme (Crash) için yol açabilecek Başlatıcı Listeleri kullanarak ilgili derleyici hataları başlatır veya tanımsız çalışma zamanı davranışı. Copy-listesi-başlatılmasında N4594 13.3.1.7p1 göredir derleyici aşırı yükleme çözünürlüğü için açık bir oluşturucu dikkate alınması gereken gereklidir, ancak bu aşırı gerçekte seçilirse hatayla yükseltmeniz gerekir.

Aşağıdaki iki örnek Visual Studio 2015'te ancak Visual Studio 2017'de derleyin.

```cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

Hatayı düzeltmek için doğrudan başlatma kullanın:

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015'te derleyici yanlışlıkla kopyalama listesi başlatma Normal kopyalama başlatma aynı şekilde ele; yalnızca oluşturucuları aşırı yükleme çözünürlüğü için dönüştürme kabul. Aşağıdaki örnekte, Visual Studio 2015 MyInt(23) ancak Visual Studio 2017 doğru hata başlatır seçer.

```cpp
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
    explicit MyStore(int initialCapacity);
};

struct MyInt {
    MyInt(int i);
};

struct Printer {
    void operator()(MyStore const& s);
    void operator()(MyInt const& i);
};

void f() {
    Printer p;
    p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

Bu örnek önceki bir benzer ancak farklı bir hata oluşturur. Visual Studio 2015'te başarılı ve Visual Studio 2017 C2668 ile de başarısız olur.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>Kullanım dışı tür tanımları

Visual Studio 2017 şimdi bir sınıf veya yapı biriminde bildirilen kullanım dışı tür tanımları için doğru uyarı verir. Aşağıdaki örnek, Visual Studio 2015'te uyarılar olmadan derler ancak Visual Studio 2017 C4996 üretir.

```cpp
struct A
{
    // also for __declspec(deprecated)
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>constexpr

Koşullu değerlendirilirken işlemi sol işleneni bir constexpr bağlamında geçerli olmadığında visual Studio 2017 doğru bir hata oluşturur. Aşağıdaki kod, Visual Studio 2015'te ancak Visual Studio 2017 (C3615 constexpr işlevi 'f' sabit bir ifade olamaz) derler:

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615
}
```

Hatayı düzeltmek için ya da bildirme `array::size()` olarak işlev `constexpr` Kaldır `constexpr` niteleyicisi gelen `f`.

### <a name="class-types-passed-to-variadic-functions"></a>Variadic, işlevlere geçirilen sınıf türleri

Visual Studio 2017 sınıfları veya printf gibi variadic işlevine geçirilen yapılar trivially copyable olması gerekir. Bu tür nesneleri geçirirken, derleyici, sadece Bitsel bir kopya oluşturur ve oluşturucunun ya da yıkıcı çağırmaz.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function.
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Hatayı düzeltmek için trivially copyable türü döndüren bir üye işlev çağrısı,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

Aksi takdirde geçirmeden önce nesneyi dönüştürmek için bir statik atama gerçekleştirin:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Oluşturulan ve yönetilen CStringW, kullanarak dizeleri için sağlanan `operator LPCWSTR()` biçim dizesi tarafından beklenen C işaretçi CStringW nesnesine dönüştürmek için kullanılmalıdır.

```cpp
CStringW str1;
CStringW str2;
str1.Format(L"%s", static_cast<LPCWSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>MS-niteleyicileri içinde sınıfı oluşturma

Visual Studio 2015'te derleyici bazen yanlış Oluşturucusu aramasıyla sınıf nesnesi oluşturulurken MS-niteleyici yoksayar. Bu büyük olasılıkla bir kilitlenme veya beklenmeyen çalışma zamanı davranışını neden olabilir. Aşağıdaki örnek, Visual Studio 2015'te derler ancak Visual Studio 2017'deki bir derleyici hatası oluşturur:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Hatayı düzeltmek için bildirme `operator int()` olarak `const`.

### <a name="access-checking-on-qualified-names-in-templates"></a>Nitelikli adlar şablonlarındaki denetimi erişim

Derleyici önceki sürümleri, bazı şablon bağlamlarında nitelenmiş adlar denetimi erişim gerçekleştirmedi. Bu, beklenen SFINAE davranışı değiştirme bir ad inaccessibility nedeniyle başarısız olmasına beklenirken etkileyebilir. Bu olası kilitlenme veya yanlış işleci yanlış yüklemesini çağırma derleyici nedeniyle çalışma zamanında beklenmeyen davranışlara neden olmuş. Visual Studio 2017 ' bir derleyici hatası oluştu. Özel hata farklılık gösterebilir, ancak genellikle "eşleşme bulundu işlevi aşırı C2672" dır. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017 bir hata oluşturur:

```cpp
#include <type_traits>

template <class T> class S {
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```

### <a name="missing-template-argument-lists"></a>Eksik şablon bağımsız değişken listeleri

Şablon (örneğin varsayılan şablon bağımsız değişken veya kapsamında tür olmayan şablon parametresi) bir şablon parametre listesinde görüntülendiğinde Visual Studio 2015 ve önceki sürümlerinde, derleyici eksik şablon bağımsız değişken listeleri tanılayın değil. Bu derleyici çökme (Crash) dahil olmak üzere beklenmeyen davranışlara veya beklenmeyen çalışma zamanı davranışı neden olabilir. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017 hata üretir.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>İfade SFINAE

Şablonları bildirilen örneği yerine olduğunda ifade SFINAE desteği için derleyici şimdi decltype bağımsız değişkenlerini ayrıştırır. Sonuç olarak, bağlı olmayan uzmanlık decltype değişkeninde bulunursa, örnek oluşturma zamanında ertelenmiş değil ve hemen işlenir ve sonuçta ortaya çıkan hataları o anda tanı koydu.

Aşağıdaki örnek, bildirim noktasında tetiklenir böyle bir derleyici hatası gösterir:

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT>
class IsCallable
{
public:
    struct BadType {};

    template <class U>
    static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>

    template <class U>
    static BadType Test(...);

    static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

### <a name="classes-declared-in-anonymous-namespaces"></a>Anonim ad alanlarında bildirilen sınıfları

C++ Standart göre anonim bir ad alanı içinde bildirilen bir sınıf iç bağlantı vardır ve bu nedenle verilemez. Visual Studio 2015 ve önceki sürümleri, bu kural zorunlu değildir. Visual Studio 2017 içinde kural kısmen zorlanır. Aşağıdaki örnek Visual Studio 2017 bu hatayı başlatır: "hata C2201: const anonim namespace::S1::vftable: dış bağlantı dışarı/alınması için olması gerekir."

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Varsayılan başlatıcılar değeri için sınıf üyeleri (C + +/ CLI)

Visual Studio 2015 ve önceki sürümlerinde, derleyici izin (ancak göz ardı) bir değer sınıfı üyesi için varsayılan üye başlatıcıdan. Varsayılan olarak başlatılması değer sınıfı her zaman sıfır-üyeleri başlatır; Varsayılan bir oluşturucu izin verilmez. Visual Studio 2017 ' varsayılan üye başlatıcıları Bu örnekte gösterildiği gibi bir derleyici hatası Yükselt:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Varsayılan dizin oluşturucular (C + +/ CLI)

Visual Studio 2015 ve önceki sürümleri, bazı durumlarda derleyici varsayılan bir özellik bir varsayılan dizin oluşturucu misidentified. Tanımlayıcısını kullanarak sorunu çözmek olası `default` özelliğine erişmek için. Geçici çözüm kendisini sonra sorunlu hale geldi `default` C ++ 11 bir anahtar olarak sunulmuştur. Bu nedenle, Visual Studio 2017 içinde geçici çözüm gerekli hatalar düzeltilmiştir ve derleyici şimdi hata başlatır, `default` bir sınıf için varsayılan özellik erişmek için kullanılır.

```cpp
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

Visual Studio 2017 ', her iki değeri özellik adına göre erişebilirsiniz:

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a> Visual Studio 2017 sürüm 15.3 hata düzeltmeleri

### <a name="calls-to-deleted-member-templates"></a>Silinen üye şablonları çağrıları

Visual Studio'nun önceki sürümleri, bazı durumlarda derleyici hatalı oluşturulmuş çağrılar çökme (Crash) çalışma zamanında olası nedeni silinmiş üyeyi şablon için bir hata yaymak üzere başarısız olur. Aşağıdaki kod C2280, şimdi üreten "'int S\<int >:: f\<int > (void)': silinen işlevi başvuru girişimi":

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail
}
```

Hatayı düzeltmek için i bildirme olarak `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Tür özellikleri için ön koşul denetimleri

Visual Studio 2017 sürüm 15.3 daha kesinlikle standart izlemek tür-özellikleri için ön koşul denetimleri artırır. Bu tür bir denetimi içindir atanabilir. Aşağıdaki kod, Visual Studio 2017 sürüm 15.3 C2139 üretir:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yönetilen yerel hazırlama üzerinde yeni derleyici uyarı ve çalışma zamanı denetimleri

Yerel işlevleri çağırma yönetilen işlevlerden dizimi gerektirir. Hazırlama CLR yapar ancak C++ semantiği anlamıyor. Yerel bir nesne değeri geçirirseniz, CLR nesnenin copy-constructor çağıran veya çalışma zamanında tanımsız davranışa neden olabilir BitBlt kullanır.

Şimdi, silinen copy ctor yerel bir nesneyle değeriyle yerel ve yönetilen sınır arasında geçirilen derleme zamanında biliyorsanız, derleyici bir uyarı gösterir. Böylece programın çağırır içinde derleyici değil bilmeniz derleme zamanında bu gibi durumlarda, bir çalışma zamanı denetimi yerleştirir `std::terminate` hemen bir hatalı oluşturulmuş dizimi oluştuğunda. Visual Studio 2017 içinde sürüm 15.3, aşağıdaki kod uyarı C4606 üreten "'A': bağımsız değişkeni değere göre yerel ve yönetilen sınırından geçirme geçerli kopya Oluşturucu gerektirir. Aksi halde çalışma zamanı davranışı tanımlı değil".

```cpp
class A
{
public:
   A() : p_(new int) {}
   ~A() { delete p_; }

   A(A const &) = delete;
   A(A &&rhs) {
   p_ = rhs.p_;
}

private:
   int *p_;
};

#pragma unmanaged

void f(A a)
{
}

#pragma managed

int main()
{
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

Hatayı düzeltmek için kaldırma `#pragma managed` arayanı yerel olarak işaretlemek ve dizimi önlemek için yönergesi.

### <a name="experimental-api-warning-for-winrt"></a>WinRT için Deneysel API Uyarısı

Deneme ve görüşlerinizi ile donatılmış için yayımlanan WinRT API'leri `Windows.Foundation.Metadata.ExperimentalAttribute`. Visual Studio 2017 içinde sürüm 15.3, öznitelik karşılaştığında derleyici uyarı C4698 üretir. Öznitelik önceki sürümlerinde Windows SDK'sı, birkaç API'leri zaten donatılmış ve bu API çağrıları Bu derleyici uyarısı şimdi tetikleyebilir. Daha yeni Windows SDK'ları tüm sevk edilen türlerinden kaldırılan özniteliğine sahip, ancak daha eski bir SDK kullanıyorsanız, tüm çağrılar sevk edilen türleri için bu uyarıları bastırma gerekir.

Aşağıdaki kod C4698 uyarı üretir: "'Windows:: Depolama:: IApplicationDataStatics2::GetForUserAsync' olduğu değerlendirme yalnızca amacıyla ve değiştirilebilir veya temizleme gelecekteki güncelleştirmeleri":

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Uyarıyı devre dışı bırakmak için bir #pragma ekleyin:

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Satır dışı tanımını bir şablon üye işlevi

Sınıfında bildirilmedi bir şablon üye işlevi satır dışı tanımını karşılaştığında visual Studio 2017 sürüm 15.3 bir hata oluşturur. Aşağıdaki kod artık hata C2039 üretir: 'f': bir üyesi değil 'S':

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Hatayı düzeltmek için bir bildirim sınıfına ekleyin:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>"Bu" işaretçi adresini alın çalışılıyor

C++'ta `this` bir prvalue türü işaretçinin x olduğu. Adresini alamıyor `this` ya da bir lvalue başvuru bağlayabilirsiniz. Visual Studio'nun önceki sürümleri derleyici, bu kısıtlamayı bir cast gerçekleştirerek sağlamasına olanak tanır. Visual Studio 2017 içinde sürüm 15.3, derleyici hatası C2664 oluşturur.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemez bir temel sınıf dönüştürme

Erişilemez bir taban sınıfı için bir tür dönüştürme girişiminde bulunduğunuzda visual Studio 2017 sürüm 15.3 bir hata oluşturur. Derleyici şimdi başlatır "hata C2243: 'tür belirtimi': dönüştürme vardı *' için ' B *' var, ancak erişilemiyor". Aşağıdaki kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Aşağıdakine benzer bir kod karşılaştığında derleyici C2243 şimdi üretir:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>Varsayılan bağımsız değişkenler üye işlevleri satır tanımları dışında izin verilmez

Varsayılan bağımsız değişkenler yapılamaz derleyici altında bir uyarı cihaza şablon sınıflardaki üye işlevleri satır dışı tanımları **/ izin veren**ve bir donanım hatası altında **/ izin veren-**.

Visual Studio'nun önceki sürümleri aşağıdaki hatalı oluşturulmuş kodu olası çalışma zamanı çökmeyle neden olabilir. Visual Studio 2017 sürüm 15.3 üreten uyarı C5034: ' A\<T >:: f': sınıf şablonu üyesi satır dışı tanımını varsayılan bağımsız değişkenler olamaz:

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034
{
    // ...
}
```

Hatayı düzeltmek için kaldırma `= false` varsayılan bağımsız değişkeni.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Offsetof ile bileşik üye göstergesi kullanımı

Visual Studio kullanarak 2017 sürüm 15.3, içinde `offsetof(T, m)` nerede *m* "bileşik üye Belirleyicisi" ile derlerken bir uyarı sonuçları olan **/duvar** seçeneği. Aşağıdaki kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Visual Studio 2017 sürüm 15.3 üreten "C4841 Uyarı: kullanılan standart uzantısı: bileşik üye Belirleyicisi offsetof içinde":

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Kod düzeltmek için bir pragma uyarıyla devre dışı bırakın ya kullanmak için kodu değiştirmek `offsetof`:

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Statik veri üyesi veya üye işlevi offsetof kullanma

Visual Studio kullanarak 2017 sürüm 15.3, içinde `offsetof(T, m)` nerede *m* statik veri üyesi veya bir üye hata işlevi sonuçlarında anlamına gelir. Aşağıdaki kod üretir "hata C4597: tanımsız davranış: 'foo' üye işlevine uygulanan offsetof" ve "hata C4597: tanımsız davranış: statik veri üyesi 'Çubuğu' uygulanan offsetof":

```cpp
#include <cstddef>

struct A {
   int foo() { return 10; }
   static constexpr int bar = 0;
};

constexpr auto off = offsetof(A, foo);
constexpr auto off2 = offsetof(A, bar);
```

Bu kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Hatayı düzeltmek için artık tanımsız davranışı çağırmak için kodu değiştirin. C++ Standart tarafından izin verilmeyen taşınabilir olmayan kodu budur.

### <a name="declspec"></a> Yeni uyarı declspec öznitelikleri hakkında

Visual Studio 2017 içinde sürüm 15.3, derleyici artık öznitelikleri yoksayar `__declspec(...)` önce uygulanan `extern "C"` bağlantı belirtimi. Daha önce derleyici, çalışma zamanı etkileri olabilir öznitelik göz ardı. Zaman **/duvar** ve **/WX** seçenekleri ayarlanır, aşağıdaki kod üretmez "C4768 Uyarı: bağlantı belirtimi önce __declspec öznitelikleri yok sayılır":

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarı, put extern "C" ilk düzeltmek için:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı kapalıdır 15.3 varsayılan olarak, ancak üzerinde varsayılan 15,5 ve yalnızca etkileri kod derlenmiş ile **/duvar** **/WX**.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype ve Silinen yıkıcı çağrıları

Silinen yıkıcı bir çağrı 'decltype' ile ilişkili ifade bağlamda oluştuğunda Visual Studio'nun önceki sürümleri derleyici algılamadı. Visual Studio 2017 içinde sürüm 15.3, aşağıdaki kod üretir "hata C2280: ' A\<T >:: ~ A(void)': silinen işlevi başvuru girişimi":

```cpp
template<typename T>
struct A
{
   ~A() = delete;
};

template<typename T>
auto f() -> A<T>;

template<typename T>
auto g(T) -> decltype((f<T>()));

void h()
{
   g(42);
}
```

### <a name="uninitialized-const-variables"></a>Başlatılmamış const değişkenleri

Visual Studio 2017 RTW yayın 'const' değişkeni başlatılmadı, C++ derleyicisi bir tanılama verilmediğine olmayan bir gerileme vardı. Bu regresyon Visual Studio 2017 sürüm 15.3 düzeltilmiştir. Aşağıdaki kod artık üretir "C4132 Uyarı: 'Value': const nesne başlatılmalıdır":

```cpp
const int Value; //C4132
```

Hatayı düzeltmek için bir değer atadığınız `Value`.

### <a name="empty-declarations"></a>Boş bildirimleri

Visual Studio 2017 sürüm 15.3 tüm türleri için yalnızca yerleşik türler boş bildirimlerinde şimdi sizi uyarır. Aşağıdaki kod artık tüm dört bildirimleri Düzey 2 C4091 uyarı üretir:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Uyarıları, yalnızca açıklama genişletme kaldırın veya boş bildirimleri kaldırmak için. Burada beklemediğiniz adlandırılmış nesne (RAII gibi) bir yan etkisi olması amaçlanmıştır durumlarda bir ad verilmelidir.

Uyarı altında hariç tutulan **/Wv:18** ve uyarı düzeyi W2 altında varsayılan olarak açıktır.

### <a name="stdisconvertible-for-array-types"></a>dizi türleri için Std::is_convertible

Derleyici önceki sürümleri için yanlış sonuçları vermiş [std::is_convertible](standard-library/is-convertible-class.md) dizi türleri için. Bu kitaplık yazıcılarının özel durum için Microsoft Visual C++ Derleyici kullanırken gerekli `std::is_convertible<...>` türü ayırdedici nitelik. Aşağıdaki örnekte, Visual Studio'nun önceki sürümleri geçişinde statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>` bir sanal işlev tanımı iyi biçimlendirilmiş olup olmadığını görmek için kontrol ederek hesaplanır:

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdisconstructible"></a>Özel yok ediciler ve std::is_constructible

Bir yıkıcı sonucu karar verirken özel olup olmadığını göz ardı Derleyici önceki sürümlerini [std::is_constructible](standard-library/is-constructible-class.md). Artık bunları değerlendirir. Aşağıdaki örnekte, Visual Studio'nun önceki sürümleri geçişinde statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

```cpp
#include <type_traits>

class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};

// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```

Özel Yıkıcılar oluşturulabilir olmayan olması için bir türü neden. `std::is_constructible<T, Args...>` Aşağıdaki bildirimi yazılmışsa gibi hesaplanır:

```cpp
   T obj(std::declval<Args>()...)
```

Bu çağrı bir yıkıcı çağrı anlamına gelir.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: Belirsiz aşırı yükleme çözümü

Derleyici önceki sürümlerini bazen başarısız her ikisi de aracılığıyla birden çok adayları bulduğunuz sırada belirsizlik algılamak bildirimler ve değişken bağımlı arama kullanma. Bu yanlış aşırı seçilmekte ve beklenmeyen çalışma zamanı davranışını neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 doğru C2668 'f' başlatır: aşırı yüklenmiş işlevi çağrısı belirsiz:

```cpp
namespace N {
   template<class T>
   void f(T&, T&);

   template<class T>
   void f();
}

template<class T>
void f(T&, T&);

struct S {};
void f()
{
   using N::f;

   S s1, s2;
   f(s1, s2); // C2668
}
```

Kullanarak kodu düzeltmek için kaldırmak `N::f` çağırmak amaçlıyorsanız deyimi `::f()`.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişkeni bağımlı arama

Yerel işlev bildirimleri çevreleyen kapsamdaki işlevi bildiriminde gizleyebilir ve bağımsız değişkeni bağımlı arama devre dışı bırakın. Ancak, derleyici önceki sürümlerini bağımsız değişkeni bağımlı arama bu durumda, büyük olasılıkla yanlış baştaki aşırı seçilmekte ve beklenmeyen çalışma zamanı davranışı gerçekleştirilir. Genellikle, bir yerel işlev bildirimi hatalı imza nedeniyle hatasıdır. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 doğru C2660 'f' başlatır: işlevi 2 bağımsız değişkenleri olmaz:

```cpp
struct S {};
void f(S, int);

void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

Sorunu düzeltmek için ya da değiştirme `f(S)` imza veya kaldırın.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: Başlatıcı Listeleri başlatma sırasını

Sınıf üyeleri bildirilir, sırayla değil Başlatıcı Listeleri göründükleri sırada başlatılır. Bildirim sıra başlatıcı listesi sırasını farklıydı geçtiğinde Derleyici önceki sürümlerini uyar değil. Başka bir üye zaten başlatılmış listesinde bir üye başlatma bağımlı varsa bu tanımsız çalışma zamanı davranışı neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 (ile **/duvar**) başlatır "C5038 Uyarı: 'A::y' veri üyesi 'A::x' sonra başlatılacaktır veri üyesi":

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Sorunu düzeltmek için bildirimler aynı sırada olmasını ıntializer listesini düzenleyin. Bir veya iki başlatıcıları taban sınıf üyelerine başvurduğunuzda benzer bir uyarı oluşturulur.

Uyarı-varsayılan olarak kapalı olduğunu ve yalnızca ile derlenmiş kod etkiler unutmayın **/duvar**.

## <a name="update_155"></a> Hata düzeltmeleri ve diğer Visual Studio 2017 sürüm 15,5 davranış değişiklikleri

### <a name="partial-ordering-change"></a>Kısmi sıralama Değiştir

Derleyici artık doğru aşağıdaki kodu reddeder ve doğru hata iletisi verir:

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```

```Output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
```

Yukarıdaki örnekte türleri iki farklılıklar vardır bir sorundur (const const olmayan karşılaştırması ve paketi olmayan ve paketi). Derleyici Hatası ortadan kaldırmak için farklar birini kaldırın. Bu işlevler belirsizliğe sıralamak derleyici sağlar.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```

### <a name="exception-handlers"></a>Özel durum işleyicileri

Dizi ya da işlevi türü referansı işleyicileri hiçbir zaman herhangi bir özel durum nesnesi için bir eşleşme var. Derleyici artık doğru şekilde bu kural geliştirir ve düzey 4 uyarı başlatır. Ayrıca artık bir işleyiciyi eşleşecek `char*` veya `wchar_t*` dize değişmez değer olduğunda **/ZC: strictstrings** kullanılır.

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```Output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```

Aşağıdaki kod hata ortadan kaldırır:

```cpp
catch (int (*)[1]) {}
```

### <a name="tr1"></a>Std::tr1 namespace kullanım dışıdır

Standart olmayan `std::tr1` ad alanı şimdi işaretlenmiş C ++ 14 ve C ++ 17 modları içinde kullanım dışı. Visual Studio 2017 içinde sürüm 15,5, aşağıdaki kodu C4996 başlatır:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```Output
warning C4996: 'std::tr1': warning STL4002: The non-Standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

Hatayı düzeltmek için başvurusunu kaldırın `tr1` ad alanı:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

### <a name="annex_d"></a>Eki D standart kitaplığı özellikleri kullanım dışı olarak işaretlenir.

Zaman **/Std: c ++ 17** modu derleyici anahtar olarak ayarlanmışsa, eki d neredeyse tüm standart kitaplığı özellikleri kullanım dışı olarak işaretlenir.

Visual Studio 2017 içinde sürüm 15,5, aşağıdaki kodu C4996 başlatır:

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```Output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ Standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

Hatayı düzeltmek için aşağıdaki kodda gösterildiği gibi uyarı metni'ndaki yönergeleri izleyin:

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>Başvurulmayan yerel değişkenler

Visual Studio 15,5 içinde uyarı C4189 aşağıdaki kodda gösterildiği gibi daha fazla durumlarda yayılır:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Hatayı düzeltmek için kullanılmayan değişkeni kaldırın.

### <a name="single-line-comments"></a>Tek satırlı açıklamaları

Visual Studio 2017 içinde sürüm 15,5, uyarılar C4001 ve C4179 artık C derleyicisi tarafından gösterilen. Daha önce bunlar yalnızca altında gösterilen **/Za** derleyici anahtar.  Tek satırlı yorumlar itibaren C99 standart C parçası bırakıldığından uyarıları artık gerekli değildir.

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

Kod geriye dönük olarak uyumlu olması gerekmez, C4001/C4179 gizleme kaldırarak uyarı önleyebilirsiniz. Kod geriye dönük uyumluluk gerekiyorsa, C4619 yalnızca engelleyin.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="declspec-attributes-with-extern-c-linkage"></a>extern "C" bağlantı __declspec özniteliklerle

Visual Studio'nun önceki sürümleri derleyici göz ardı `__declspec(...)` ne zaman öznitelikleri `__declspec(...)` önce uygulandı `extern "C"` bağlantı belirtimi. Kod neden bu davranış, oluşturulan kullanıcı kaydetmedi düşünüyorsanız, olası çalışma zamanı uygulamaları ile. Uyarı Visual Studio sürüm 15.3 eklendi, ancak varsayılan olarak kapalı olan. Visual Studio 2017 içinde sürüm 15,5, uyarı varsayılan olarak etkindir.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Hatayı düzeltmek için __declspec özniteliği önce bağlantı belirtimi koyun:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu yeni uyarı C4768 ile Visual Studio 2017 15.3 geldiği bazı Windows SDK'sı üst bilgileri verilen ya da eski (örneğin: sürüm 10.0.15063.0, RS2 SDK olarak da bilinir). Ancak, böylece bu uyarıyı üreten değil Windows SDK üst bilgilerinin (özellikle, ShlObj.h ve ShlObj_core.h) sonraki sürümlerinde düzeltildi. Windows SDK üstbilgileri yakında bu uyarıyı gördüğünüzde, bu eylemleri gerçekleştirebilirsiniz:

1. Visual Studio 2017 sürüm 15,5 sürüm ile birlikte gelen en son Windows SDK geçin.
2. Geçici uyarıyı Kapat # Windows SDK üstbilgi deyiminin include:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>Extern constexpr bağlantı

Visual Studio'nun önceki sürümleri derleyici her zaman vermiş bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15,5, yeni derleyici anahtar içinde (**/Zc:externConstexpr**) doğru standartları uyumsuz davranışı etkinleştirir. Sonuç olarak bu varsayılan olur.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Üstbilgi dosyası bildirilen bir değişken içeriyorsa `extern constexpr`, işaretlenmesi gerekir `__declspec(selectany)` birlikte, yinelenen bildirimler doğru olması için:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>TypeId tamamlanmamış sınıfı türünde kullanılamaz

Visual Studio'nun önceki sürümleri derleyici aşağıdaki kod, büyük olasılıkla yanlış türde bilgileri kaynaklanan yanlış izin. Visual Studio 2017 içinde sürüm 15,5, derleyici, doğru bir hata oluşturur:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdisconvertible-target-type"></a>Std::is_convertible hedef türü

`std::is_convertible` Hedef türü geçerli bir dönüş türü olmasını gerektirir. Visual Studio'nun önceki sürümleri derleyici yanlış yanlış aşırı yükleme çözümü ve istenmeyen çalışma zamanı davranışını yol açabilecek soyut türler izin verilir.  Aşağıdaki kod artık doğru C2338 başlatır:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Kullanırken hatayı önlemek için `is_convertible` soyut bir tür ise bir işaretçi türü karşılaştırma işlemi başarısız olduğundan işaretçi türleri karşılaştırmanız gerekir:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="noexcept_removal"></a> Dinamik özel durum belirtimi kaldırma ve noexcept

C ++ 17 ' de `throw()` için diğer ad olduğu `noexcept`, `throw(<type list>)` ve `throw(...)` kaldırılır ve belirli türleri içerebilir `noexcept`. Bu C ++ 14 veya önceki sürümleri uyumlu koduyla kaynak uyumluluk sorunlarına neden olabilir. **/Zc:noexceptTypes-** anahtar, C ++ 14 sürümüne geri dönmek için kullanılabilir `noexcept` genel C ++ 17 modu kullanırken. Bu, C ++ 17'ye tüm yeniden yazmaya gerek kalmadan uygun olması için kaynak kodu güncelleştirmenizi sağlar, `throw()` aynı anda kodu.

Derleyici de artık daha fazla eşleşmeyen özel durum belirtimleri bildirimlerden C ++ 17 modunda veya ile tanılar **/ izin veren-** C5043 yeni uyarı.

Aşağıdaki kod C5043 ve C5040 Visual Studio 2017 sürüm 15,5 oluşturur, **/Std: c ++ 17** anahtar uygulanır:

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```

Hala kullanırken hataları kaldırmak için **/Std: c ++ 17**, ekleyip ya da **/Zc:noexceptTypes-** geçiş için komut satırını, aksi takdirde kullanmak için kodunuzu güncelleştirin `noexcept`, aşağıdaki örnekte gösterildiği gibi:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```

### <a name="inline-variables"></a>Satır içi değişkenleri

Statik constexpr veri üyeleri kendi bildirimi bir sınıf içinde artık kendi tanımı anlamına gelir satır içi örtük olarak sunulmuştur. Statik constexpr veri üyesi için bir satır sonu tanımı kullanılarak yedekli ve artık kullanım dışı. Visual Studio 2017 sürüm 15,5 içinde olduğunda **/Std: c ++ 17** anahtar uygulandığında, aşağıdaki kod artık uyarı C5041 üreten *'boyutu': satır dışı tanım constexpr statik veri üyesi için gerekli değildir ve kullanım dışıdır C ++ 17 içinde*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>extern "C" __declspec(...) C4768 şimdi üzerinde varsayılan olarak uyarı

Uyarı, Visual Studio 2017 sürüm 15.3 eklendi ancak varsayılan olarak kapalı olan. Visual Studio 2017 sürüm 15,5 varsayılan olarak açıktır. Bkz: [declspec özniteliklerinde yeni uyarı](#declspec) daha fazla bilgi için.

### <a name="defaulted-functions-and-declspecnothrow"></a>Varsayılan işlevler ve __declspec(nothrow)

Derleyici önceden ile bildirilmesi varsayılan işlevleri izin verilen `__declspec(nothrow)` karşılık gelen taban/üye işlevleri özel durumlara ne zaman izin verilir. Bu davranış C++ Standart aykırı ve çalışma zamanında tanımsız davranış neden olabilir. Standart bir özel durum belirtimi uyuşmazlığı ise silindi olarak tanımlanması için bu tür işlevler gerektirir.  Altında **/Std: c ++ 17**, aşağıdaki kodu C2280 başlatır *silinen işlevi başvuru girişimi. Açık özel durum belirtimi, örtük bildirimi ile uyumlu olmadığı için işlevi örtük olarak silindi.* :

```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

Bu kod düzeltmek için varsayılan işlevinden __declspec(nothrow) kaldırın ya da kaldırma `= default` ve tüm gerekli özel durum işleme birlikte işlevi için bir tanım girin:

```cpp
struct A {
    A& operator=(const A& other) {
        // ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```

### <a name="noexcept-and-partial-specializations"></a>noexcept ve kısmi özelleştirmeleri

Türü sistemindeki noexcept ile eşleşen belirli "aranabilir" türleri için kısmi özelleştirmeleri derleme veya İşlevler noexcept işaretçileri için eksik bir kısmi uzmanlığı nedeniyle birincil şablon seçmek başarısız olabilir.

Böyle durumlarda, noexcept işlev işaretçileri ve üye işlevleri noexcept işaretçileri işlemek için ek kısmi özelleştirmeleri eklemeniz gerekebilir. Bu aşırı yalnızca yasal **/Std: c ++ 17** modu. Geriye dönük uyumluluk C ++ 14 ile tutulan gerekir ve diğerleri tüketen kod yazma olduğunuz durumunda bu yeni aşırı içinde koruması `#ifdef` yönergeleri. Kendi içinde bulunan modülü ve ardından kullanmak yerine çalışıyorsanız `#ifdef` yalnızca derleyebileceğiniz ile koruyucuları **/Zc:noexceptTypes-** geçin.

Altında aşağıdaki kodu derler **/Std: c ++ 14** ancak altında başarısız **/Std: c ++ 17** ile "hata C2027:use tanımsız türü ' A\<T >'":

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

Altında aşağıdaki kodu başarılı **/Std: c ++ 17** derleyici yeni kısmi uzmanlığı seçtiği için `A<void (*)() noexcept>`:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="update_157"></a> Hata düzeltmeleri ve diğer Visual Studio 2017 sürüm 15.7 davranış değişiklikleri

### <a name="c17-default-argument-in-the-primary-class-template"></a>C ++ 17 varsayılan birincil sınıf şablonu bağımsız değişkeni

Bu davranış değişikliği için bir önkoşul olan [şablon bağımsız değişken kesintisi sınıf şablonları - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), sonraki Visual Studio 2017 sürüm 15.7 önizlemede tam olarak desteklenmesi için planlanan.

Daha önce derleyici birincil sınıf şablonu varsayılan değişkeninde yoksayıldı.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

İçinde **/Std: c ++ 17** Visual Studio 2017 sürüm 15.7, varsayılan bağımsız değişkeni modunda değil göz ardı edilir:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Bağımlı ad çözümlemesi

Bu davranış değişikliği için bir önkoşul olan [şablon bağımsız değişken kesintisi sınıf şablonları - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), sonraki Visual Studio 2017 sürüm 15.7 önizlemede tam olarak desteklenmesi için planlanan.

Aşağıdaki örnekte, Visual Studio 15,6 ve önceki sürümleri derleyici çözümler `D::type` için `B<T>::type` birincil Sınıf şablonunda.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = B<T*>::type;
};
```

Visual Studio 2017 sürüm 15.7, içinde **/Std: c ++ 17** modu, gerektirir `typename` anahtar sözcük `using` D. deyiminde Olmadan `typename` derleyici uyarı C4346 başlatır: *' B < T\*>:: türü ': bağımlı adı bir tür değil* ve hata C2061: *söz dizimi hatası: tanımlayıcısı 'type'*:

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = typename B<T*>::type;
};
```

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>Uyarı düzeyi artış c ++ 17 [[nodiscard]] özniteliği-

Visual Studio 2017 sürümünde 15.7 içinde **/Std: c ++ 17** modu, C4834 uyarı düzeyini ("'nodiscard' özniteliğine sahip işlevinin dönüş değeri atılıyor") için W1 W3 yükseltilmiştir. Bir cast uyarıyla devre dışı bırakabilirsiniz `void`, veya geçirerek **/wd:4834** derleyici

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Variadic şablon Oluşturucusu temel sınıf başlatma listesi

Visual Studio'nun önceki sürümleri, şablon bağımsız değişken eksik variadic şablon Oluşturucusu temel sınıf başlatma listesi yanlışlıkla hatasız izin. Visual Studio 2017 içinde sürüm 15.7, derleyici hatası oluştu.

Visual Studio 2017 sürüm 15.7 başlatır aşağıdaki kod örneğinde *hata C2614: D\<int >: Geçersiz üye başlatma: 'B' bir temel veya üyesi değil*

```cpp
template<typename T>
struct B {};

template<typename T>
struct D : B<T>
{

    template<typename ...C>
    D() : B() {} // C2614. Missing template arguments to B.
};

D<int> d;
```

Hatayı düzeltmek için B B() ifade değiştirmek\<T > ().

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dil Uyumluluğu](visual-cpp-language-conformance.md)
