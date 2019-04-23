---
title: C++ uyumluluk geliştirmeleri
ms.date: 03/26/2019
ms.technology: cpp-language
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 6a0e296e4a5542c1aad848c55d35d3e40244478d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779477"
---
# <a name="c-conformance-improvements-in-visual-studio-2017-versions-150-153improvements153-155improvements155-156improvements156-157improvements157-158update158-159improvements159"></a>Visual Studio 2017 sürüm 15.0,'deki C++ uyumluluk geliştirmeleri [15.3](#improvements_153), [15.5](#improvements_155), [15.6](#improvements_156), [15.7](#improvements_157), [15,8](#update_158), [15.9](#improvements_159)

İçin genelleştirilmiş constexpr ve NSDMI ile Microsoft Visual C++ Derleyici C ++ 14 standardına eklenen özelliklerin tamamlanmıştır. Yine de derleyicide C++11 ve C++98 Standartlarındaki bazı özellikler eksiktir. Bkz: [Visual C++ dil uyumluluğu](../visual-cpp-language-conformance.md) derleyici geçerli durumunu gösteren bir tablo için.

## <a name="c11"></a>C++11

### <a name="expression-sfinae-support-in-more-libraries"></a>Daha fazla kitaplıklarında ifade SFINAE desteği

Decltype ve constexpr ifadeleri şablon parametreleri olarak görüntülendiği şablon bağımsız değişkeni kesintisi ve değiştirme için gerekli olan, ifade SFINAE, desteğini geliştirmek derleyici devam eder. Daha fazla bilgi için [ifade SFINAE geliştirmeleri Visual Studio 2017 rc'de](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

## <a name="c-14"></a>C++ 14

### <a name="nsdmi-for-aggregates"></a>NSDMI

Toplama, bir dizi veya hiçbir kullanıcı tarafından sağlanan oluşturucusu, hiçbir özel veya korumalı statik olmayan veri üyesi, temel olmayan sınıflar ve sanal işlev yok sınıfı ' dir. C ++ 14 toplamalar'den itibaren üye başlatıcılar içerebilir. Daha fazla bilgi için [üye başlatıcılarında ve toplamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

### <a name="extended-constexpr"></a>Genişletilmiş constexpr

İfadeler, bildirimleri, belirli türde içerir ve ifadeler, döngü deyimi ve ömürlerinin içinde constexpr ifade değerlendirme başladı nesnelerin Mutasyon geçiş yapmak için constexpr artık izin verilir olarak bildirilmiş. Ayrıca, artık bir constexpr statik olmayan üye işlev örtük olarak const bir gereksinimi yoktur. Daha fazla bilgi için [constexpr işlevlerdeki kısıtlamalar gevşetme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html).

## <a name="c17"></a>C++17

### <a name="terse-staticassert"></a>Terse static_assert

ileti parametresi static_assert için isteğe bağlıdır. Daha fazla bilgi için [genişletme static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

### <a name="fallthrough-attribute"></a>[[fallthrough]] özniteliği

İçinde **/Std: c ++ 17** modu, [[fallthrough]] özniteliği, switch deyimleri bağlamında başarısızlığı davranışı geçmesini derleyici bir ipucu olarak kullanılabilir. Bu, derleyici Böyle durumlarda uyarı vermesini engeller. Daha fazla bilgi için [[[fallthrough]] özniteliği için ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

### <a name="generalized-range-based-for-loops"></a>Aralık tabanlı for döngüleri genelleştirilmiş

Aralık tabanlı const_iterator ve end() aynı türe ait nesneleri iade döngüler artık gereksinim için. Bu aralıklardaki tarafından kullanılan bir sentinel döndürülecek end() sağlar [aralığı v3](https://github.com/ericniebler/range-v3) ve tamamlandı ancak-not-sessiz-yayımlanmış aralıkları teknik belirtimi. Daha fazla bilgi için [Genelleştiriliyor aralık tabanlı For döngüsü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a> Visual Studio 2017 sürüm 15.3 geliştirmeleri

### <a name="constexpr-lambdas"></a>constexpr lambdas

Lambda ifadeleri artık sabit ifadelerde kullanılabilir. Daha fazla bilgi için [C++ constexpr lambda ifadelerinde](../../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>constexpr işlevi şablonlarındaki

Bir işlev şablonu içerebilir `if constexpr` derleme zamanı dallanma etkinleştirmek için deyimleri. Daha fazla bilgi için [, constexpr deyimleri](../../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Başlatıcıları olan seçim deyimleri

Bir `if` deyimi bir değişkene deyimi içinde blok kapsamındaki tanıtan bir başlatıcı içerebilir. Daha fazla bilgi için [varsa deyimleri başlatıcısıyla](../../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybeunused-and-nodiscard-attributes"></a>[[maybe_unused]] ve [[nodiscard]] öznitelikleri

Bir varlık olmadığında uyarı Sessiz ya da işlev çağrısının dönüş değerini atılır halinde bir uyarı oluşturmak için yeni öznitelikler. Daha fazla bilgi için [c++ öznitelikleri](../../cpp/attributes.md).

### <a name="using-attribute-namespaces-without-repetition"></a>Yineleme olmadan öznitelik ad alanlarını kullanma

Bir öznitelik listesinde yalnızca tek bir ad tanımlayıcısı etkinleştirmek için yeni söz dizimi'ı seçin. Daha fazla bilgi için [c++ öznitelikleri](../../cpp/attributes.md).

### <a name="structured-bindings"></a>Yapılandırılmış bağlamalar

Artık, tek bir bildirimde değer bir dizi, std::tuple veya std::pair veya tüm ortak statik olmayan veri üyelerine sahip olduğunda, bileşenleri için ayrı ayrı adlara sahip bir değer depolamak için de mümkündür. Daha fazla bilgi için [yapılandırılmış bağlamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) ve [birden çok değer döndüren bir işlevden](../../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Enum sınıfı değerleri için oluşturma kuralları

Aynı zamanda hiçbir Numaralandırıcı, tanımını sunar ve bir liste başlatma söz dizimi kaynak kullanması durumunda şimdi bir örtük/olmayan-daraltma dönüşümü kapsamlı bir sabit listesinin temel alınan türünden numaralandırma kendisi için yoktur. Daha fazla bilgi için [oluşturma kuralları sabit listesi için değerleri sınıfı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) ve [numaralandırmalar](../../cpp/enumerations-cpp.md#no_enumerators).

### <a name="capturing-this-by-value"></a>Yakalama \*bu değere göre

`*this` Lambda ifadesindeki bir nesne artık yakalanıp değere göre. Bu, özellikle daha yeni bir makine mimarileri üzerinde paralel ve zaman uyumsuz işlemler, lambda çağrılan senaryolarını olanaklı kılar. Daha fazla bilgi için [Lambda yakalama, \*bu olarak değer [=\*bu]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html).

### <a name="removing-operator-for-bool"></a>Operator ++'bool için'kaldırma

`operator++` artık desteklenir `bool` türleri. Daha fazla bilgi için [kullanımdan kaldırma operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

### <a name="removing-deprecated-register-keyword"></a>"Register anahtar sözcüğü" kullanımdan kaldırılıyor

`register` Anahtar sözcüğü, daha önce kullanım (ve derleyici tarafından yok sayılır), artık dilinden kaldırılır. Daha fazla bilgi için [kullanım dışı kullanımı register anahtar sözcüğü Kaldır](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

Visual Studio 2015 güncelleştirme 3 ile uyumluluk geliştirmeleri tam listesi için bkz. [Visual C++ neler yeni 2003 ile 2015 arasındaki](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

## <a name="improvements_155"></a>  Visual Studio 2017 sürüm 15.5 geliştirmeleri

[14] ile işaretli hangi özelliklerin kullanılabilir koşulsuz bile **/Std: c ++ 14** modu.

### <a name="new-compiler-switch-for-extern-constexpr"></a>Yeni derleyici extern constexpr için geçiş

Visual Studio'nun önceki sürümlerinde, derleyici her zaman verdiğiniz bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15.5, yeni bir derleyici anahtarı [/ZC: externconstexpr](../../build/reference/zc-externconstexpr.md), doğru standartlara uyan davranışını etkinleştirir. Daha fazla bilgi için [extern constexpr bağlantı](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimleri kaldırılıyor

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) dinamik özel durum belirtimleri C ++ 11'de kullanım dışı. Bu özellik C ++ 17'den kaldırılır, ancak hâlâ kullanım dışı `throw()` belirtimi için bir diğer ad olarak kesinlikle korunur `noexcept(true)`. Daha fazla bilgi için [dinamik özel durum belirtimi kaldırma ve noexcept](#noexcept_removal).

### <a name="notfn"></a>not_fn()

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) `not_fn` yerini, `not1` ve `not2`.

### <a name="rewording-enablesharedfromthis"></a>Rewording enable_shared_from_this

[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this` C ++ 11'de eklenmiştir. C ++ 17 standardı belirli köşe durumlarında daha iyi belirtimi güncelleştirir. [14]

### <a name="splicing-maps-and-sets"></a>Boşluklarına ayıran Haritalar ve kümeler

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) ayıklama düğümlerinin ilişkilendirilebilir kapsayıcılar bu özelliği sağlar (örneğin, harita, ayarla, sırasız\_sıralanmamış eşleme,\_ayarlayın), ardından değiştirilebilir ve geri aynı kapsayıcı ya da farklı bir eklenen kapsayıcı aynı düğüm türü kullanır. (Bir düğümden ayıklamak için yaygın bir kullanım örneği olan bir `std::map`anahtarını değiştirin ve yeniden ekleyin.)

### <a name="deprecating-vestigial-library-parts"></a>İşlevini kaybetmiş kitaplık parçaları kullanımdan kaldırılıyor

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) C++ Standart Kitaplığı'nin birtakım özelliklerini yıllar içinde yeni özellikler tarafından yenisiyle değiştirilmiş, aksi takdirde yararlı olmaması veya sorunlu bulunamadı. Bu özellikler resmi olarak C ++ 17'de kullanım dışı bırakılmıştır.

### <a name="removing-allocator-support-in-stdfunction"></a>Ayırıcı desteği de std::function kaldırılıyor

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) C ++ 17 önce sınıf şablonu `std::function` ayırıcı bağımsız değişken alan birçok oluşturucuya sahip. Ancak, bu bağlamda ayırıcılar kullanımını sorunlu ve semantiği belirsiz. Bu nedenle bu yapıcısı kaldırıldı.

### <a name="fixes-for-notfn"></a>Fixes for not_fn()

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) için yeni ifade `std::not_fn` değeri kategori sarmalayıcı çağırma durumunda yayılmasının desteği sağlar.

### <a name="sharedptrt-sharedptrtn"></a>shared_ptr\<T [] >, shared_ptr\<T [N] >

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) birleştirme `shared_ptr` Library Fundamentals'dan C ++ 17'ye değiştirir. [14]

### <a name="fixing-sharedptr-for-arrays"></a>Shared_ptr diziler için düzeltme

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) diziler için destek shared_ptr giderir. [14]

### <a name="clarifying-insertreturntype"></a>İnsert_return_type açıklığa kavuşturan

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) benzersiz anahtarları olan ilişkili kapsayıcılar ve benzersiz anahtarları sırasız kapsayıcıları bir üye işlevine sahip `insert` iç içe geçmiş bir tür döndüren `insert_return_type`. Bu türü artık Yineleyici ve kapsayıcının NodeType parametreli bir türde bir özelleştirmesi olarak tanımlanan döndürür.

### <a name="inline-variables-for-the-stl"></a>STL için satır içi değişkenler

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>Kullanımdan Kaldırılan annex D özellikleri

C++ standart D Annex dahil olmak üzere bırakılmıştır tüm özelliklerini içeren `shared_ptr::unique()`, `<codecvt>`, ve `namespace std::tr1`. Zaman **/Std: c ++ 17** derleyici anahtarı olarak ayarlanmışsa, d Annex neredeyse tüm standart kitaplık özellikleri kullanım dışı olarak işaretlenir. Daha fazla bilgi için [Annex d standart kitaplık özellikleri kullanım dışı olarak işaretlenmiş](#annex_d).

`std::tr2::sys` Ad alanında `<experimental/filesystem>` artık kullanımdan kaldırma Uyarısı altında yayan **/Std: c ++ 14** varsayılan olarak ve altında artık kaldırılır **/Std: c ++ 17** varsayılan olarak.

İostreams önleme bir standart olmayan uzantı (sınıfının açık uzmanlık) tarafından geliştirilmiş uyumluluğu.

Standart kitaplık artık dahili değişken şablonlar kullanır.

Tür sistemi ve dinamik özel durum belirtimleri kaldırılmasını noexcept eklenmesi de dahil olmak üzere C ++ 17 derleyici değişikliklere, standart kitaplık güncelleştirildi.

## <a name="improvements_156"></a>  Visual Studio 2017 sürüm 15.6 geliştirmeleri

### <a name="c17-library-fundamentals-v1"></a>C ++ 17 kitaplığı temelleri V1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) Library Fundamentals teknik belirtimi, C ++ 17 standart içerir. Kapsayan güncelleştirmeleri \<Deneysel/tanımlama grubu >, \<Deneysel ve isteğe bağlı >, \<Deneysel/işlev >, \<Deneysel/any >, \<Deneysel/string_view >, \<Deneysel/bellek >, \<Deneysel/memory_resource >, ve \<Deneysel/algoritma >.

### <a name="c17-improving-class-template-argument-deduction-for-the-stl"></a>C ++ 17 geliştirme sınıfı şablon bağımsız değişkeni kesintisi stl

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html) taşıma `adopt_lock_t` için parametre listesinin öne `scoped_lock` tutarlı kullanımını etkinleştirmek için `scoped_lock`. İzin `std::variant` kopya atamasından etkinleştirmek için aşırı yükleme çözünürlüğü içinde daha fazla durumda katılmak için oluşturucu.

## <a name="improvements_157"></a> Visual Studio 2017 sürüm 15.7 geliştirmeleri

### <a name="c17-rewording-inheriting-constructors"></a>C ++ 17 Rewording devralma oluşturucuları

[P0136R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html) belirten bir **kullanarak** bir oluşturucu artık adları bildirimi yerine ek bildirme türetilmiş sınıf oluşturucuları türetilen sınıfın oluşturucusundaki için görünür temel karşılık gelen yapar sınıf oluşturucular. Bu, C ++ 14 farklıdır. Visual Studio 2017 sürüm 15.7 ve daha sonra **/Std: c ++ 17** modu, C ++ 14 ve oluşturucuların devralınması kullanan geçerli kod geçerli olmayabilir veya farklı semantiklere sahip.

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

Daha fazla bilgi için [oluşturucular](../../cpp/constructors-cpp.md#inheriting_constructors).

### <a name="c17-extended-aggregate-initialization"></a>C ++ 17 genişletilmiş toplu başlatma

[P0017R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)

Genel olmayan ancak altında bir türetilmiş sınıf, ardından erişilebilir bir taban sınıfın oluşturucusu olması durumunda **/Std: c ++ 17** modu Visual Studio'da sürüm 15.7 artık boş küme ayraçları türetilmiş bir türde bir nesneyi başlatmak için kullanabilirsiniz.

Aşağıdaki örnek, C ++ 14 ve uyumlu davranışın gösterir:

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

C ++ 17 ' de `Derived` toplama artık kabul türü; bu nedenle, başlatma `Base` aracılığıyla özel varsayılan oluşturucu doğrudan genişletilmiş toplama başlatma kuralının bir parçası gerçekleşir. Daha önce `Base` özel Oluşturucu ile çağrıldı `Derived` oluşturucusu ve friend bildirimi nedeniyle başarılı oldu.

Aşağıdaki örnek, Visual Studio sürüm 15.7 olarak C ++ 17 davranış gösterir. **/Std: c ++ 17** modu:

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

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C ++ 17 bildirme tür olmayan şablon parametreleri otomatik

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

İçinde **/Std: c ++ 17** modu, derleyici artık türetme ile bildirilen bir tür olmayan şablon bağımsız değişken türünü **otomatik**:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Geçerli C ++ 14 kod geçerli olmayabilir veya farklı semantiklere sahip, bu yeni özelliğin bir etkisidir. Örneğin, daha önce geçersiz olan bazı aşırı yüklemeleri artık geçerli değil. Aşağıdaki örnek, çünkü derleyen C ++ 14 kodu gösterir. çağrı `foo(p)` bağlı `foo(void*);`. Visual Studio 2017 sürüm 15.7, içinde **/Std: c ++ 17** modu `foo` işlevi şablonu olarak en iyi eşleşme.

```cpp
template <int N> struct A;
template <typename T, T N> int foo(A<N>*) = delete;

void foo(void *);

void bar(A<0> *p)
{
    foo(p); // OK in C++14
}
```

Aşağıdaki örnek, Visual Studio 15.7 sürümündeki içinde C ++ 17 kodu gösterir. **/Std: c ++ 17** modu:

```cpp
template <int N> struct A;
template <typename T, T N> int foo(A<N>*);

void foo(void *);

void bar(A<0> *p)
{
    foo(p); // C2280: 'int foo<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C ++ 17 başlangıç dizesi dönüştürmeler (kısmi)

[P0067R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html) arasında kayan noktalı sayılar ve dizeler ve tamsayılar ve dizelerin arasında dönüştürmeler için alt düzey ve yerel ayarlardan bağımsızdır işlevler. (Visual Studio 15.7 Önizleme yalnızca tamsayılar için desteklenen 2 itibariyle,.)

### <a name="c20-avoiding-unnecessary-decay-partial"></a>Gereksiz önleme c ++ 20 (kısmi) decay

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf) "decay" kavramını ve, yalnızca const veya başvuru niteleyicileri kaldırmanın arasında ayrım ekler.  Yeni türü niteliğine `remove_reference_t` değiştirir `decay_t` bazı bağlamlarda. Destek `remove_cvref_t` değil henüz itibarıyla Visual Studio 2017 sürüm 15.7 Önizleme 2 uygulanır.

### <a name="c17-parallel-algorithms"></a>C ++ 17 paralel algoritmalar

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html) paralellik TS küçük değişiklikler ile standart içine dahil.

### <a name="c17-hypotx-y-z"></a>C ++ 17 hypot (x, y, z)

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf) için üç yeni yükler ekler `std::hypot`, türleri için **float**, **çift**, ve **uzun çift**, her biri üç giriş parametresi yok.

### <a name="c17-filesystem"></a>C ++ 17 \<filesystem >

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html) birkaç ifadesi değişiklikler ile standart içine dosya sistemi TS devralır.

### <a name="c17-mathematical-special-functions"></a>C ++ 17 matematik özel işlevler

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) standart matematiksel özel işlevler için önceki teknik belirtimlerini uyarlar \<cmath > Üstbilgi.

### <a name="c17-deduction-guides-for-the-stl"></a>C ++ 17 kesintisi, STL için size yol gösterir

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html) C ++ 17 benimsenmesini yararlanmak için STL güncelleştirmeleri [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), sınıfın şablon bağımsız değişkeni kesintisi için destek ekler.

### <a name="c17-repairing-elementary-string-conversions"></a>C ++ 17 onardıktan temel dize dönüştürme

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html) yeni temel dize dönüştürme işlevleri P0067R5 yeni üstbilgisine taşıma \<charconv > ve kullanmak için hata işleme değiştirme gibi diğer geliştirmeler yapmaya `std::errc` yerine `std::error_code`.

### <a name="c17-constexpr-for-chartraits-partial"></a>C ++ 17 constexpr char_traits (kısmi) için

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) değişikliklerini `std::traits_type` üye işlevleri `length`, `compare`, ve `find` yapmak için `std::string_view` sabit ifadelerde kullanılabilir. (Visual Studio 2017 sürüm 15.6, Clang/LLVM yalnızca desteklenir. Sürüm 15.7 Önizleme 2, destek neredeyse olduğu için ClXX de tamamlayın.)

## <a name="improvements_159"></a> Visual Studio 2017 sürüm 15.9 geliştirmeleri

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>Soldan sağa Değerlendirme sırasını işleçleri için -> *, [], >>, ve <<

C ++ 17'de başlayarak, işlenenler işleç -> *, [], >>, ve \< \< soldan sağa doğru sırayla değerlendirilir. Derleyici bu düzeni olmasını garanti etmek mümkün olduğu iki durum vardır:
- işlenen ifadelerden biri bir nesne değer olarak geçilemez veya değere göre geçirilen nesneyi içerdiğinde veya
- kullanılarak derlendiğinde **/CLR**, ve işlenenleri biri bir alan bir nesne veya dizi öğesi.

Derleyici Uyarısı gösterir [C4866](https://docs.microsoft.com/cpp/error-messages/compiler-warnings/c4866?view=vs-2017) zaman bunu garanti etmez soldan sağa değerlendirme. Bu uyarı, yalnızca oluşturulan **/Std: c ++ 17** veya bu işleçler soldan sağa sıralı gereksinimi C ++ 17'de kullanılmaya başlanan olarak daha sonra belirtilir.

Bu uyarıyı çözmek için önce işlenenlerin soldan sağa Değerlendirme sırasını bağımlı yan etkileri işlenenlerin zaman üretebilir gibi gerekli olup olmadığını göz önünde bulundurun. Çoğu durumda, işlenenleri değerlendirilme sırasını gözlemlenebilir bir etkisi yok. Soldan sağa Değerlendirme sırasını olması gerekiyorsa, işlenenleri sabit başvuruya göre bunun yerine geçirebilirsiniz olup olmadığını göz önünde bulundurun. Bu değişiklik, aşağıdaki kod örneği'nde uyarı ortadan kaldırır.

```cpp
// C4866.cpp
// compile with: /w14866 /std:c++17

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x) : x(x) {}
    HasCopyConstructor(const HasCopyConstructor& h) : x(h.x) { }
};

int operator>>(HasCopyConstructor a, HasCopyConstructor b) { return a.x >> b.x; }

// This version of operator>> does not trigger the warning:
// int operator>>(const HasCopyConstructor& a, const HasCopyConstructor& b) { return a.x >> b.x; }

int main()
{
    HasCopyConstructor a{ 1 };
    HasCopyConstructor b{ 2 };

    a>>b;        // C4866 for call to operator>>
};
```

## <a name="bug-fixes-in-visual-studio-versions-150-153update153-155update155-157update157-158update158-and-159update159"></a>Visual Studio sürümlerinde 15.0, hata düzeltmeleri [15.3](#update_153), [15.5](#update_155), [15.7](#update_157), [15,8](#update_158), ve [15.9](#update_159)

### <a name="copy-list-initialization"></a>Kopya listesi başlatması

Visual Studio 2017, doğru nesne oluşturma için kilitlenmelere neden olabilir ve Visual Studio 2015'te yakalanan olmayan Başlatıcı Listeleri kullanarak ilgili derleyici hataları oluşturur veya çalışma zamanı davranışı tanımsız. Kopya listesi başlatması içinde N4594 13.3.1.7p1 göre derleyici açık bir oluşturucu aşırı yükleme çözümlemesi için dikkate alınması gereken gereklidir, ancak aşırı yükleyen gerçekten seçilirse hata yükseltmeniz gerekir.

Aşağıdaki iki örnek, Visual Studio 2015'te ancak Visual Studio 2017 içinde derleyin.

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

Visual Studio 2015'te derleyici deneyebileceğinizi kopya listesi başlatması normal kopya başlatma aynı şekilde ele; yalnızca oluşturucu aşırı yükleme çözümlemesi için dönüştürme kabul. Aşağıdaki örnekte, Visual Studio 2015 MyInt(23) ancak Visual Studio 2017 hata başlatır doğru şekilde seçer.

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

Bu örnek Öncekine benzer, ancak farklı bir hata oluşturur. Visual Studio 2015'te başarılı olur ve C2668 ile Visual Studio 2017'de başarısız olur.

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

Visual Studio 2017 artık bir sınıf veya yapı içinde bildirilen kullanım dışı tür tanımları için doğru uyarı verir. Aşağıdaki örnek, Visual Studio 2015'te uyarılar olmadan derlenir, ancak Visual Studio 2017'de C4996 oluşturur.

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

Koşullu olarak değerlendirilmesini işleminin sol işlenen bir constexpr bağlamında geçerli olmadığında visual Studio 2017 doğru bir hata oluşturur. Aşağıdaki kod, Visual Studio 2015'te ancak Visual Studio 2017 ('f' constexpr işlevi sabit ifade ile sonuçlanamaz C3615) derler:

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

Hatayı düzeltmek için ya da bildirin `array::size()` işleve `constexpr` Kaldır `constexpr` gelen niteleyicisi `f`.

### <a name="class-types-passed-to-variadic-functions"></a>Değişen sayıda bağımsız değişken, işlevlere geçirilen sınıf türleri

Visual Studio 2017'de, sınıf ya da printf gibi değişen sayıda bağımsız değişken işleve geçirilen yapının artık önemsiz olarak kopyalanabilir olmalıdır. Bu tür nesneleri geçirirken, derleyici, basit bit düzeyinde bir kopya oluşturur ve oluşturucu veya yıkıcı çağırmaz.

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

Hatayı düzeltmek için artık önemsiz olarak kopyalanabilir türü döndüren bir üye işlevi çağırabilir,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

Aksi takdirde iletmeden önce nesneyi dönüştürmek için bir statik dönüştürme işlemi gerçekleştirin:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Oluşturulan ve yönetilen CString, kullanarak dizeleri için sağlanan `operator LPCTSTR()` bir biçim dizesi tarafından beklenen C işaretçi CString nesnesi kullanılmalıdır.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>sınıf oluşturma CV niteleyicileri

Visual Studio 2015'te derleyici bazen yanlışlıkla bir sınıf nesnesi bir oluşturucu çağrısı aracılığıyla oluştururken cv niteleyici yoksayar. Bu durum bir kilitlenme veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnek, Visual Studio 2015'te derler ancak Visual Studio 2017'de bir derleyici hatası oluşturur:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Hatayı düzeltmek için bildirin `operator int()` olarak `const`.

### <a name="access-checking-on-qualified-names-in-templates"></a>Nitelikli adlar şablonlarındaki denetimi erişim

Önceki derleyici sürümleri, bazı şablon bağlamlarında nitelenmiş adlar denetimi erişim gerçekleştirmedi. Bu, burada değiştirme adının inaccessibility nedeniyle başarısız olması bekleniyor, beklenen SFINAE davranışı etkileyebilir. Bu büyük olasılıkla bir kilitlenme veya yanlış yanlış İşleç aşırı yüklemesini çağırmak derleyici nedeniyle çalışma zamanında beklenmeyen davranışlara neden olmuş. Visual Studio 2017'de, bir derleyici hatası oluşturulur. Belirli bir hata gösterebilir, ancak genellikle "C2672 eşleşen aşırı yüklenmiş işlev bulunamadı" olacaktır. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017'de bir hata oluşturur:

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

Şablon (örneğin parçası varsayılan şablon bağımsız değişkeni veya bir tür olmayan şablon parametresi) bir şablon parametre listesinde özelliğiyken Visual Studio 2015 ve önceki sürümlerinde, derleyici eksik şablon bağımsız değişken listeleri tanılayın değil. Bu, derleyici kilitlenmeleri dahil, öngörülemeyen davranışlara veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017'de bir hata oluşturur.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>Expression-SFINAE

Şablonları bildirilen örneği yerine olduğunda ifade SFINAE desteği için derleyici artık decltype bağımsız değişkenleri ayrıştırır. Sonuç olarak, bağımlı olmayan özelleştirmesi decltype değişkeninde bulunursa, örnekleme zamanı ertelenmiş değil ve hemen işlenir ve ortaya çıkan hataları o anda tanı koydu.

Aşağıdaki örnek, bildirildiği tetiklenir böyle bir derleyici hatası gösterir:

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

### <a name="classes-declared-in-anonymous-namespaces"></a>Bildirilen anonim ad alanlarındaki sınıflar

C++ standardına göre anonim bir ad alanı içinde bildirilmiş bir sınıfın iç bağlantısı vardır ve bu nedenle dışarı aktarılamaz. Visual Studio 2015 ve önceki sürümlerinde, bu kural zorunlu değildir. Visual Studio 2017'de bir kural kısmen uygulanır. Aşağıdaki örnek Visual Studio 2017'de bu hata oluşturur: "hatası C2201: const anonim namespace::S1::vftable: dışarı/içeri aktarılmak için dış bağlantıya sahip olması gerekir."

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Varsayılan başlatıcılar değeri için sınıf üyeleri (C++/CLI)

Visual Studio 2015 ve önceki sürümlerinde, derleyici izin verilir (ancak göz ardı) bir değer sınıfının üyesi için varsayılan üye başlatıcıya. Her zaman varsayılan bir değer sınıfının başlatma sıfır-üyeleri başlatır; Varsayılan bir oluşturucu izin verilmez. Visual Studio 2017'de, bu örnekte gösterildiği gibi varsayılan üye Başlatıcı bir derleyici hatası Yükselt:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Varsayılan dizin oluşturucular (C++/CLI)

Visual Studio 2015 ve önceki sürümlerinde, bazı durumlarda, derleyici varsayılan bir özellik bir varsayılan dizin oluşturucu misidentified. Tanımlayıcısını kullanarak sorunu çözmek mümkün olan `default` özelliğine erişmek için. Çözüm sonra sorunlu hale geldi `default` C ++ 11'de bir anahtar olarak kullanıma sunulmuştur. Bu nedenle, Visual Studio 2017'de gerekli geçici hatalar düzeltilmiştir ve derleyici artık bir hata oluşturur, `default` bir sınıfının varsayılan özelliğine erişmek için kullanılır.

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

Visual Studio 2017'de her iki değer özellik adlarına göre erişebilirsiniz:

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

Visual Studio'nun önceki sürümlerinde, derleyicinin bazı durumlarda hatalı oluşturulmuş çağrılar potansiyel olarak zamanında kilitlenmelere neden silinmiş üyeyi şablon için bir hata yaymak başarısız olur. Aşağıdaki kod C2280, artık üretir "'int S\<int >:: f\<int > (void)': silinmiş bir işleve başvurmaya çalışıyor":

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

Hatayı düzeltmek için i bildirmek olarak `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Tür özellikleri için ön koşul denetimleri

Visual Studio 2017 sürüm 15.3 daha kesinlikle standarda tür özellikleri için ön koşul denetimleri artırır. Bu tür bir denetimi içindir atanabilir. Aşağıdaki kod, Visual Studio 2017 sürüm 15.3 C2139 üretir:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yönetilen yerel hazırlama üzerinde yeni derleyici uyarı ve çalışma zamanı denetimleri

Yönetilen işlevlerden yerel işlevleri çağırma taşıma gerektirir. CLR sıralama gerçekleştirir, ancak C++ semantiği anlamıyor. Yerel bir nesne değeri geçirirseniz, CLR nesnenin Kopyala oluşturucusunu çağırır veya çalışma zamanında tanımsız davranışlara neden olabilecek BitBlt kullanır.

Artık, derleme zamanında silinen copy ctor yerel bir nesnesiyle arasında yerel ve yönetilen sınır değeri tarafından geçirilir biliyorsanız, derleyici bir uyarı verir. Böylece programın çağırır, derleyici değil bilmeniz derleme zamanında bu gibi durumlarda, bir çalışma zamanı denetimi eklediği `std::terminate` hemen hatalı oluşturulmuş bir taşıma gerçekleştiğinde. Visual Studio 2017 sürüm 15.3, uyarı C4606 aşağıdaki kodu üretir "'A': yerel ve yönetilen sınırda değere göre bağımsız değişken geçirme, geçerli bir kopya Oluşturucusu gerektirir. Aksi takdirde çalışma zamanı davranışı tanımsızdır".

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

Hatayı düzeltmek için kaldırma `#pragma managed` çağıran yerel olarak işaretlemek ve taşıma önlemek için yönergesi.

### <a name="experimental-api-warning-for-winrt"></a>WinRT için Deneysel API Uyarısı

WinRT deneme ve geri bildirim ile donatılmış için yayımlanan API'leri `Windows.Foundation.Metadata.ExperimentalAttribute`. Bu öznitelik karşılaştığında Visual Studio 2017 sürüm 15.3, derleyici uyarı C4698 üretir. Özniteliği ile Windows SDK'sının önceki sürümlerde, birkaç API'ları zaten donatılmış ve bu API'lere giden çağrıların şimdi bu derleyici uyarı Tetikle. Yeni Windows SDK'ları tüm sevk edilen türlerinden kaldırılmış öznitelik sahip, ancak daha eski bir SDK kullanıyorsanız, tüm çağrılar sevk edilen türleri için bu uyarıları bastırmak gerekir.

Aşağıdaki kod C4698 uyarı üretir: "'Windows:: Depolama:: IApplicationDataStatics2::GetForUserAsync', yalnızca değerlendirme amaçlıdır ve değişikliğe tabidir veya gelecekte kaldırılması güncelleştirmeler için":

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Uyarı devre dışı bırakmak için bir #pragma ekleyin:

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Bir şablon üye işlev satır dışı tanımı

Bir sınıfta bildirilmedi bir şablon üye işlev satır dışı tanımı karşılaştığında visual Studio 2017 sürüm 15.3, bir hata oluşturur. Aşağıdaki kod hatası C2039 artık oluşturur: 'f': bir üyesi değil. kullanıcının ':

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Hatayı düzeltmek için sınıfa bir bildirimi ekleyin:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>"Bu" işaretçi adresi alınamaz çalışılıyor

C++'ta `this` işaretçi türüne X bir prvalue olduğu. Adresi alınamaz `this` ya da bir lvalue başvurusuna bağlayabilirsiniz. Visual Studio'nun önceki sürümlerinde, derleyici, bir yayın gerçekleştirerek bu kısıtlama aşmak çalıştırmasına olanak tanır. Visual Studio 2017 sürüm 15.3, derleyici hatası C2664 oluşturur.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemez bir temel sınıf dönüştürme

Visual Studio 2017 sürüm 15.3, erişilebilir değil temel bir sınıf için bir tür dönüştürmeye çalıştığınızda bir hata oluşturur. Derleyici artık başlatır "hatası C2243: 'tür cast': dönüştürme vardı *' için ' B *' var, ancak erişilebilir değil". Aşağıdaki kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Bu kodu karşılaştığında derleyici artık C2243 üretir:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>Varsayılan bağımsız değişkenler üye işlevleri satır tanımlarını dışında izin verilmez

Varsayılan bağımsız değişkenler, derleyici bir uyarı vermek şablon sınıflarındaki üye işlevlerin satır dışı tanımları üzerinde verilmez **/ permissive**ve bir donanım hatası altında **/ permissive-**.

Visual Studio'nun önceki sürümlerinde, hatalı oluşturulmuş aşağıdaki kodu potansiyel olarak çalışma zamanı kilitlenmeye neden olabilir. Visual Studio 2017 sürüm 15.3 C5034 uyarı üretir: ' A\<T >:: f': bir sınıf şablonunun üyesi bir satır dışı tanımı varsayılan bağımsız değişkenlere sahip olamaz:

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

Hatayı düzeltmek için kaldırma `= false` varsayılan bağımsız değişken.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Offsetof bileşik üye göstergesi ile kullanımı

Visual Studio kullanarak 2017 sürüm 15.3, `offsetof(T, m)` burada *m* bir "bileşik üye göstergesi" bir uyarı ile derleme yaparken sonuçları olan **/Wall** seçeneği. Aşağıdaki kod, hatalı biçimlendirilmiş ve potansiyel olarak çalışma zamanında Çökmeye neden. Visual Studio 2017 sürüm 15.3 üretir "C4841 Uyarı: standart olmayan uzantı kullanıldı: offsetof içinde bileşik üye göstergesi":

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Kodu düzeltmek için uyarı bir pragma ile devre dışı bırakın ya da değil kullanmak için kodu değiştirin `offsetof`:

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Statik veri üyesine veya üye işlevine offsetof kullanma

Visual Studio kullanarak 2017 sürüm 15.3, `offsetof(T, m)` burada *m* statik veri üyesine veya üye işlevi bir hata sonuçlarında ifade eder. Aşağıdaki kod üretir "hatası C4597: tanımsız davranış: offsetof 'foo' üye işlevine uygulanan" ve "hatası C4597: tanımsız davranış: 'bar' statik veri üyesine offsetof uygulandı":

```cpp
#include <cstddef>

struct A {
   int foo() { return 10; }
   static constexpr int bar = 0;
};

constexpr auto off = offsetof(A, foo);
constexpr auto off2 = offsetof(A, bar);
```

Bu kod, hatalı biçimlendirilmiş ve potansiyel olarak çalışma zamanında Çökmeye neden. Hatayı düzeltmek için artık tanımlanmamış davranışı çağırmak için kodu değiştirin. C++ Standart tarafından izin verilmeyen taşınabilir kod budur.

### <a name="declspec"></a> Yeni uyarı declspec öznitelikleri hakkında

Visual Studio 2017 sürüm 15.3, derleyici artık öznitelikleri yok sayar `__declspec(...)` önce uygulanan `extern "C"` bağlama belirtimi. Daha önce derleyici çalışma zamanı etkileri olabilir özniteliği yok. Zaman **/Wall** ve **wx** seçenekleri ayarlanır, aşağıdaki kodu üretir "C4768 Uyarı: bağlantı belirtiminden önceki __declspec öznitelikleri yoksayılır":

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarıyı çözmek için extern "C" yerleştirin:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı kapalı 15.3, varsayılan olarak, ancak şirket varsayılan 15.5 sürümünde ve yalnızca etkileyen kod ile derlenmiş olan **/Wall** **wx**.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype ve Silinen yıkıcı çağrıları

Silinen bir yıkıcı çağrısı 'decltype' ile ilişkili ifadenin bağlamında gerçekleştiğinde, Visual Studio'nun önceki sürümlerinde, derleyici algılamadı. Visual Studio 2017 sürüm 15.3, aşağıdaki kod üretir "hatası C2280: \<T >:: ~ A(void)': silinmiş bir işleve başvurmaya çalışıyor ":

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

Visual Studio 2017 RTW Sürüm 'const' değişken başlatılmadı içinde C++ derleyicisi bir tanılama verilmediğine değil bir gerileme vardı. Visual Studio 2017 sürüm 15.3 Bu gerileme düzeltildi. Aşağıdaki kod artık üretir "C4132 Uyarı: 'Value': const nesnenin başlatılması gerekir ":

```cpp
const int Value; //C4132
```

Hatayı düzeltmek için bir değer atayın `Value`.

### <a name="empty-declarations"></a>Boş bildirimleri

Visual Studio 2017 sürüm 15.3, artık tüm türleri, yalnızca yerleşik türler için boş bildirimlerinde sizi uyarır. Aşağıdaki kod, artık tüm dört bildirimleri Düzey 2 C4091 uyarı üretir:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Uyarıları kaldırmak için yalnızca açıklama veya boş bildirimleri. Burada beklemediğiniz adlandırılmış nesne (RAII gibi) bir yan etkisi amaçlanmıştır durumlarda bir ad verilmelidir.

Uyarı altında hariç tutulan **/Wv:18** ve uyarı düzeyi W2 altında varsayılan olarak açıktır.

### <a name="stdisconvertible-for-array-types"></a>dizi türleri için Std::is_convertible

Önceki derleyici sürümleri için hatalı sonuçlar verdi [std::is_convertible](../../standard-library/is-convertible-class.md) dizi türleri için. Bu kitaplık yazıcılar özel durum için Microsoft Visual C++ Derleyici kullanırken gerekli `std::is_convertible<...>` türü niteliğine. Aşağıdaki örnekte, Visual Studio'nun önceki sürümlerini geçişte statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

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

Bir yok edici sonucunu verirken özel olup olmadığını göz ardı derleyicinin önceki sürümlerini [std::is_constructible](../../standard-library/is-constructible-class.md). Artık bunları değerlendirir. Aşağıdaki örnekte, Visual Studio'nun önceki sürümlerini geçişte statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

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

Özel yok ediciler atmamalıdır olmayan olması için bir tür neden. `std::is_constructible<T, Args...>` Aşağıdaki bildirimi yazılmışlar gibi hesaplanır:

```cpp
   T obj(std::declval<Args>()...)
```

Bu çağrı, yok edici bir çağrıdan anlamına gelir.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: Belirsiz aşırı yükleme çözünürlüğü

Bazen derleyicinin önceki sürümlerini başarısız her ikisi de aracılığıyla birden fazla adayı bulduğunuzda belirsizlik algılamak bildirimler ve değişken bağımlı arama kullanarak. Bu, yanlış aşırı seçildiği ve beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 C2668 'f' doğru başlatır: aşırı yüklenmiş işleve belirsiz çağrı:

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

Kullanarak kodu düzeltmek için kaldırmak `N::f` çağrılacak hedeflediyseniz deyimi `::f()`.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişken bağımlı arama

Yerel işlev bildirimleri, işlev bildirimi kapsayan kapsamda gizleyebilir ve bağımsız değişken bağımlı arama devre dışı bırakın. Ancak, derleyici önceki sürümlerini bağımsız değişken bağımlı arama bu durumda, büyük olasılıkla yanlış için önde gelen aşırı seçildiği ve beklenmeyen çalışma zamanı davranışı gerçekleştirilir. Genellikle, yanlış bir yerel işlev bildiriminin imzasının nedeniyle hatasıdır. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 C2660 'f' doğru başlatır: işlevi, 2 bağımsız değişken almaz:

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

Sorunu gidermek için ya da değiştirme `f(S)` imza ya da kaldırın.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: Başlatıcı Listeleri içindeki başlatma sırasını

Sınıf üyeleri, bildirildikleri, sırayla değil Başlatıcı Listeleri göründükleri sırayla başlatılır. Başlatıcı listesi sırası sırasının bildirim farklıydı önceki derleyici sürümleri uyar değil. Başka bir üye zaten başlatılmış listesinde bir üye başlatma bağımlı değilse bu tanımsız çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 (ile **/Wall**) başlatır "uyarısı C5038: veri üyesi 'A::x' 'A::y' başlatılacaktır veri üyesi":

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Sorunu gidermek için bildirimleri aynı sırada olmasını başlatıcı listesi düzenleyin. Bir veya iki başlatıcılar temel sınıf üyelerine başvuru benzer bir uyarı tetiklenir.

Uyarı devre dışı varsayılan olarak ve yalnızca ile derlenmiş kod etkiler unutmayın **/Wall**.

## <a name="update_155"></a> Hata düzeltmeleri ve diğer Visual Studio 2017 sürüm 15.5 davranış değişiklikleri

### <a name="partial-ordering-change"></a>Kısmi sıralaması Değiştir

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

Yukarıdaki örnekte sorun türlerinde iki fark yoktur (const sabit olmayan karşılaştırması ve paketi olmayan ve paketi). Derleyici Hatası ortadan kaldırmak için farklardan biri kaldırın. Bu, kesin bir şekilde işleve sıralamak derleyiciyi etkinleştirir.

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

Dizi veya işlev türüne yapılan başvurunun hiçbir zaman herhangi bir özel durum nesnesi için bir eşleşme işleyicileridir. Derleyici artık doğru şekilde bu kuralı geliştirir ve düzey 4 uyarısı oluşturur. Ayrıca artık, bir işleyici eşleşmiyor `char*` veya `wchar_t*` bir dizeye değişmez değer olduğunda **/ZC: strictstrings** kullanılır.

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

Aşağıdaki kodu, hatanın ortadan kaldırır:

```cpp
catch (int (*)[1]) {}
```

### <a name="tr1"></a>Std::tr1 namespace kullanım dışıdır

Standart olmayan `std::tr1` ad alanı artık C ++ 14 ve C ++ 17 modları kullanım dışı olarak işaretlenen. Visual Studio 2017 sürüm 15.5, aşağıdaki kodu C4996 oluşturur:

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

### <a name="annex_d"></a>Standart kitaplık özellikleri Annex d kullanım dışı olarak işaretlendi

Zaman **/Std: c ++ 17** modu derleyici anahtarı olarak ayarlanmışsa, neredeyse tüm standart kitaplık özellikleri Annex d kullanım dışı olarak işaretlenir.

Visual Studio 2017 sürüm 15.5, aşağıdaki kodu C4996 oluşturur:

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

Visual Studio 15.5 sürümünde, aşağıdaki kodda gösterildiği gibi daha fazla durumlarda, uyarı C4189 yayıldığını:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Hatayı düzeltmek için kullanılmayan değişkeni Kaldır.

### <a name="single-line-comments"></a>Tek satırlı yorumlar

Visual Studio 2017 sürüm 15.5, C4001 ve C4179 uyarılar artık C derleyicisi tarafından gönderilir. Daha önce bunlar yalnızca altında yayılan **/Za** derleyici anahtarı.  Tek satırlı yorumlar beri C99 standart C parçası bırakıldığından uyarıları artık gereklidir.

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

Kod geriye dönük olarak uyumlu olması gerekmez, uyarı C4001/C4179 gizleme kaldırarak önleyebilirsiniz. Kod geriye dönük uyumlu olmasını gerekli olmaması halinde C4619 yalnızca gösterme.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="declspec-attributes-with-extern-c-linkage"></a>extern "C" bağlaması olan __declspec öznitelikleri

Visual Studio'nun önceki sürümlerinde, derleyici göz ardı `__declspec(...)` ne zaman öznitelikleri `__declspec(...)` önce uygulandığı `extern "C"` bağlama belirtimi. Kod neden bu davranış, oluşturulan kullanıcı yaramadı düşünüyorsanız, olası çalışma zamanı uygulamaları ile. Uyarı, Visual Studio'da sürüm 15.3 eklendi, ancak varsayılan olarak kapalı olan. Visual Studio 2017 sürüm 15.5, uyarı, varsayılan olarak etkindir.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Hatayı düzeltmek için önce __declspec öznitelik bağlama belirtimi yerleştirin:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu yeni uyarı C4768 ile Visual Studio 2017 15.3 sevk edilen bazı Windows SDK'sı başlıklarında verilen ya da eski (örneğin: sürüm 10.0.15063.0, RS2 SDK olarak da bilinir). Ancak, bu uyarı vermez böylece sonraki sürümlerinde Windows SDK'sı üst bilgileri (özellikle ShlObj.h ve ShlObj_core.h) düzeltildi. Windows SDK'sı üst bilgileri yakında bu uyarıyı gördüğünüzde, bu eylemleri gerçekleştirebilirsiniz:

1. Visual Studio 2017 sürüm 15.5 sürüm ile birlikte gelen en son Windows SDK geçin.

1. Uyarı geçici olarak devre dışı bırakma # Windows SDK'sı üstbilgi deyiminin include:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>Extern constexpr bağlantı

Visual Studio'nun önceki sürümlerinde, derleyici her zaman verdiğiniz bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15.5, yeni bir derleyici anahtarı (**/ZC: externconstexpr**) doğru standartlara uyan davranışını etkinleştirir. Sonuçta bu varsayılan olur.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Bir üstbilgi dosyası bildirilen bir değişken içeriyorsa `extern constexpr`, işaretlenmesi gerekir `__declspec(selectany)` doğru birleştirilmiş, yinelenen bildirimler sahip olmak için:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>typeid eksik sınıf türü üzerinde kullanılamaz

Visual Studio'nun önceki sürümlerinde, derleyici yanlış potansiyel olarak yanlış tür bilgileri aşağıdaki koddaki izin verilir. Visual Studio 2017 sürüm 15.5, derleyici doğru bir hata oluşturur:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdisconvertible-target-type"></a>Std::is_convertible hedef türü

`std::is_convertible` Hedef türü geçerli bir dönüş türü olmasını gerektirir. Visual Studio'nun önceki sürümlerinde, derleyici yanlış yanlış aşırı yükleme çözünürlüğü ve istenmeyen çalışma zamanı davranışına neden soyut türler izin verilir.  Aşağıdaki kod şimdi doğru C2338 başlatır:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Kullanırken, hatayı önlemek için `is_convertible` soyut bir tür ise bir işaretçi türü karşılaştırma işlemi başarısız olduğundan işaretçi türleri karşılaştırmanız gerekir:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="noexcept_removal"></a> Dinamik özel durum belirtimi kaldırma ve noexcept

C ++ 17 ' de `throw()` için bir diğer addır `noexcept`, `throw(<type list>)` ve `throw(...)` kaldırılır, ve belirli türlerini içerebilir `noexcept`. Bu, C ++ 14 veya önceki uyan koduyla kaynak uyumluluk sorunlarına neden olabilir. **/Zc:noexceptTypes-** anahtarı, C ++ 14 sürümüne geri almak için kullanılabilir `noexcept` genel C ++ 17 modunda kullanırken. Bu, tüm yeniden yazmak zorunda kalmadan C ++ 17'ye uyması için kaynak kodunuzu güncelleştirmenizi sağlar, `throw()` aynı zamanda kod.

Derleyici artık daha fazla eşleşmeyen bir özel durum belirtimleri C ++ 17 modunda veya ile bildirimlerinde tanılar **/ permissive-** C5043 yeni uyarı.

Aşağıdaki kod Visual Studio 2017 sürüm 15.5 C5043 ve C5040 oluşturur, **/Std: c ++ 17** anahtar uygulanır:

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

Yine de kullanırken hataları kaldırmak için **/Std: c ++ 17**, ekleyin ya da **/Zc:noexceptTypes-** komut satırına geçin, aksi takdirde kullanmak için kodunuzu güncelleştirin `noexcept`, aşağıdaki örnekte gösterildiği gibi:

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

### <a name="inline-variables"></a>Satır içi değişkenler

Constexpr statik veri üyeleri, bir sınıf içerisinde bildirim artık kendi tanım olduğu anlamına gelir satır içi örtük olarak sunulmuştur. Constexpr statik veri üyesi için satır dışı tanımı kullanarak yedekli ve artık kullanım dışı. Visual Studio 2017 sürüm 15.5 olduğunda **/Std: c ++ 17** anahtar uygulanır, aşağıdaki kod, artık uyarı C5041 üretir *'size': constexpr statik veri üyesi için satır dışı tanımı gerekli değildir ve kullanım dışıdır C ++ 17'de*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>extern "C" __declspec(...) C4768 şimdi üzerinde varsayılan olarak uyarı

Uyarı, Visual Studio 2017 sürüm 15.3 eklendi ancak varsayılan olarak kapalı olan. Visual Studio 2017 sürüm 15.5 varsayılan olarak açıktır. Bkz: [declspec özniteliklerde yeni uyarı](#declspec) daha fazla bilgi için.

### <a name="defaulted-functions-and-declspecnothrow"></a>Varsayılan olarak ayarlanan işlevler ve __declspec(nothrow)

Derleyici, daha önce ile bildirilmesi varsayılan olarak ayarlanan işlevler izin `__declspec(nothrow)` karşılık gelen taban/üye işlevleri özel durumların ne zaman izin verilir. Bu davranış C++ Standart aykırı ve çalışma zamanında tanımsız davranışlara neden olabilir. Standart özel durum belirtimi bir uyuşmazlık varsa silindi olarak tanımlanmış olması için bu tür işlevleri gerektirir.  Altında **/Std: c ++ 17**, aşağıdaki kodu C2280 başlatır *silinmiş bir işleve başvurmaya çalışıyor. Açık özel durum belirtimi, örtük bildirim ile uyumsuz olduğundan işlev örtük olarak silindi.* :

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

Bu kodu düzeltmek için varsayılan haline getirilen işlevden __declspec(nothrow) kaldırın veya kaldırın `= default` ve tüm gerekli özel durum işleme ile birlikte bir işlev için bir tanımı sağlayın:

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

### <a name="noexcept-and-partial-specializations"></a>noexcept ve kısmi uzmanlıklar

Tür sisteminde noexcept ile eşleşen belirli "çağrılabilir" türleri için kısmi uzmanlıkları nedeniyle işaretçiler için noexcept işlevleri için eksik kısmi özelleştirme birincil şablonu seçin ya da derleme başarısız olabilir.

Böyle durumlarda noexcept işlev işaretçileri ve üye işlevlerinin işaretçileri noexcept işlemek için ek kısmi uzmanlıklar eklemeniz gerekebilir. Bu aşırı yüklemeler yalnızca yasal **/Std: c ++ 17** modu. Geriye doğru uyumluluk C ++ 14 ile korunan gerekir ve diğerleri kullanan kod yazma olduğunuz durumunda bu yeni aşırı yüklemeler içinde koruyucu `#ifdef` yönergeleri. Kendi içinde bir modül, ardından kullanmak yerine çalışıyorsanız `#ifdef` yalnızca derleyebileceğiniz ile cf **/Zc:noexceptTypes-** geçin.

Altında aşağıdaki kodu derler **/Std: c ++ 14** altında başarısız olduğunda **/Std: c ++ 17** ile "hata C2027:use Tanımsız Tür ' A\<T >'":

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

Altında aşağıdaki kodu başarılı **/Std: c ++ 17** derleyicinin seçtiği yeni kısmi özelleştirmesi için `A<void (*)() noexcept>`:

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

Bu davranış değişikliği için önkoşul olduğundan [şablon bağımsız değişkeni kesintisi sınıf şablonları - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), tam olarak bir sonraki Visual Studio 2017 sürüm 15.7 Önizleme desteklenmesi planlanan.

Daha önce derleyici varsayılan bağımsız bir birincil Sınıf şablonunda yok sayıldı.

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

İçinde **/Std: c ++ 17** Visual Studio 2017 sürüm 15.7, varsayılan bağımsız değişken modunda yok sayılır:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Bağımlı ad çözümlemesi

Bu davranış değişikliği için önkoşul olduğundan [şablon bağımsız değişkeni kesintisi sınıf şablonları - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), tam olarak bir sonraki Visual Studio 2017 sürüm 15.7 Önizleme desteklenmesi planlanan.

Aşağıdaki örnekte, derleyicinin Visual Studio 15.6 ve daha önce çözümlenen `D::type` için `B<T>::type` birincil Sınıf şablonunda.

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

Visual Studio 2017 sürüm 15.7, içinde **/Std: c ++ 17** modunu gerektirir `typename` anahtar sözcüğünü `using` D. deyiminde Olmadan `typename` derleyici uyarı C4346 meydana getirir: *' B < T\*>:: türü ': bağımlı öğe adı bir tür değil* hatası C2061: *söz dizimi hatası: tanımlayıcı 'type'*:

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

Visual Studio 2017 sürüm 15.7 olarak **/Std: c ++ 17** modunda c4834 uyarı düzeyi ("'nodiscard' özniteliği ile işlevin dönüş değeri atılıyor"), W3'ten W1 yükseltilmiştir. Bir atamanın uyarıyla devre dışı bırakabilirsiniz `void`, veya geçirerek **/wd:4834** derleyici

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Değişen sayıda bağımsız değişken şablonu oluşturucu temel sınıf başlatma listesi

Visual Studio'nun önceki sürümlerinde, şablon bağımsız değişkenleri eksik variadic şablon oluşturucu temel sınıf başlatma listesi deneyebileceğinizi hatasız izin verildi. Visual Studio 2017 sürüm 15.7, bir derleyici hatası oluşturulur.

Visual Studio 2017 sürüm 15.7 başlatır aşağıdaki kod örneğinde *hatası C2614: D\<int >: Geçersiz üye başlatma: 'B' bir taban veya üye değil*

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

Hatayı düzeltmek için B B() ifadesini değiştirmeyi\<T > ().

### <a name="constexpr-aggregate-initialization"></a>constexpr toplu başlatma

C++ derleyicisinin önceki sürümlerinde, yanlış constexpr toplama başlatma işlenen; Bunu, toplama başlatma listesi çok fazla öğe vardı ve hatalı codegen için üretilen geçersiz kod kabul etti. Aşağıdaki kod, bu tür bir kod örneğidir:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {
        { 1, 2 },
        { 3, 4 }
    };
    return 0;
}
```

Visual Studio 2017 sürüm 15.7 güncelleştirme 3 ve daha sonra önceki örnekte artık başlatır *C2078 çok fazla başlatıcı*. Aşağıdaki örnek kodu düzeltmek nasıl gösterir. Başlatılırken bir `std::array` iç içe geçmiş küme ayracı listelerinde ile bir küme ayracıyla belirtilen liste kendi iç diziyi verin:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {{ // note double braces
        { 1, 2 },
        { 3, 4 }
    }}; // note double braces
    return 0;
}
```

## <a name="update_158"></a> Hata düzeltmeleri ve Visual Studio 2017 sürüm 15,8 davranış değişiklikleri

Visual Studio 2017 sürüm 15,8 derleyici değişiklikleri tüm hata düzeltmeleri ve davranış değişiklikleri kategorisinde ayrılır ve aşağıda listelenmiştir:

### <a name="typename-on-unqualified-identifiers"></a>TypeName nitelenmemiş tanımlayıcıları hakkında

İçinde [/ permissive-](../../build/reference/permissive-standards-conformance.md) modu, sahte `typename` diğer şablon tanımlarında nitelenmemiş tanımlayıcılar anahtar sözcükleri artık derleyici tarafından kabul edilir. Aşağıdaki kod artık C7511 üretir *'T': 'typename' anahtar sözcüğü, bir tam ad gelmelidir*:

```cpp
template <typename T>
using  X = typename T;
```

Hatayı düzeltmek için ikinci satırın değiştirmek yeterlidir `using  X = T;`.

### <a name="declspec-on-right-side-of-alias-template-definitions"></a>diğer şablon tanımlarında sağ tarafında __declspec()

[__declspec](../../cpp/declspec.md) sağ tarafında bir diğer ad şablon tanımının artık izin verilir. Bu derleyici tarafından daha önce kabul edildi ancak tamamen yok sayıldı ve diğer kullanıldığında hiçbir zaman içinde bir kullanımdan kaldırılma uyarısı neden olur.

Standart C++ öznitelik [ \[ \[kullanım dışı\] \] ](../../cpp/attributes.md) yerine kullanılabilir ve Visual Studio 2017 sürüm 15.6'den itibaren geçerlidir. Aşağıdaki kod artık C2760 üretir *söz dizimi hatası: beklenmeyen belirteç '__declspec' beklenen 'türü tanımlayıcısı'*:

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

Hatayı düzeltmek için aşağıdaki kodu (yerleştirilen 'diğer ad tanımı =' öncesinde öznitelik ile) değiştirin:

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>İki aşamalı ad arama tanılama

İki aşamalı ad aramayı bağımlı olmayan adları şablon gövdeleri kullanılan tanımı zaman şablona görünür olmasını gerektirir. Daha önce Microsoft C++ derleyicisi bir unfound adı oluşturmada zamanlarının un looked yukarı bırakabilir. Şimdi, bağımlı olmayan adları şablon gövdesinde ilişkili gerektirir.

Bu bildirim bir arama bağımlı temel sınıflar ile yoludur. Daha önce derleyici bunlar oluşturmada süre boyunca tüm türlerin çözümlenmiş olduğunda aranabilir çünkü bağımlı temel sınıflarında tanımlanan adlarının kullanımına izin verilir. Artık, kod hata kabul edilir. Bu gibi durumlarda, örnek oluşturma zamanında taban sınıf türünde uygun veya aksi halde, örneğin ekleyerek bağımlı Bakılacak değişkeni zorlayabilirsiniz bir `this->` işaretçi.

İçinde **/ permissive-** modu, aşağıdaki kod şimdi C3861 başlatır: *'base_value': tanımlayıcı bulunamadı*:

```cpp
template <class T>
struct Base {
    int base_value = 42;
};

template <class T>
struct S : Base<T> {
    int f() {
        return base_value;
    }
};
```

Hatayı düzeltmek için değiştirme `return` ifadesine `return this->base_value;`.

**Not:** Boost python Kitaplığı'nda olmuştur uzun bir süre için bir şablon iletme bildiriminde bir MSVC özgü geçici çözüm [unwind_type.hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp). Altında [/ permissive-](../../build/reference/permissive-standards-conformance.md) Visual Studio 2017 sürüm 15,8 başlangıç modu (_MSC_VER 1915 =), bu geçici çözüm guard yapma ve diğer derleyiciler ile tutarlıdır ve bağımsız değişkene bağlı ad araması (ADL) desteklemez doğru MSVC derleyicisi gereksiz. Bu hatadan kaçınmak için *C3861: 'unwind_type': tanımlayıcı bulunamadı*, bakın [çekme isteği 229](https://github.com/boostorg/python/pull/229) Boostorg depodaki üstbilgi dosyasını güncelleştirin. Biz zaten yama [vcpkg](../../build/vcpkg.md) Boost paketi alın ya da Boost kaynaklarınızı vcpkg ' yükseltme ardından, ayrı olarak düzeltme eki uygulamaya gerek yoktur.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>iletme bildirimlerinin ve tanımlarının ad alanında std

C++ standart iletme bildirimlerine veya tanımlarına ad alanında eklemek bir kullanıcı izin vermeyen `std`. Ad alanına bildirimlerine veya tanımlarına ekleme `std` veya ad alanı içinde bir ad alanına std artık tanımlanmayan davranışla sonuçlanır.

Bazı zaman gelecekteki Microsoft bazı STL türlerinin tanımlandığı konumuna taşınır. Bu durumda, ad alanına bildirimleri ekler mevcut kodu keser `std`. Yeni bir uyarı C4643, bu tür kaynak sorunlarını belirlemenize yardımcı olur. Uyarı etkin **/varsayılan** modunu ve varsayılan olarak kapalıdır. İle derlenmiş programlar etkiler **/Wall** veya **wx**.

Aşağıdaki kod, şimdi C4643 başlatır: *İleri 'vektör' ad alanında std C++ standardı tarafından izin verilmiyor bildirme*.

```cpp
namespace std {
    template<typename T> class vector;
}
```

Hatayı düzeltmek için kullanmak bir **dahil** İleri dönük bildirimi yerine yönergesi:

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>Kendilerine temsilci oluşturucuları

C++ Standart temsilci oluşturucusu kendisini yetkilendirir, derleyici bir tanılama yayması önerir. Microsoft C++ derleyicisindeki [/Std: c ++ 17](../../build/reference/std-specify-language-standard-version.md) ve [/Std: c ++ Son](../../build/reference/std-specify-language-standard-version.md) modları artık C7535 başlatır: *'X::X': temsilci Oluşturucu, çağıran kendisini*.

Bu hata olmadan aşağıdaki programın derleyeceği ancak sonsuz bir döngü oluşturur:

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
};
```

Sonsuz döngü önlemek için farklı bir oluşturucu temsilci:

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>offsetof ile sabit ifadeler

[offsetof](../../c-runtime-library/reference/offsetof-macro.md) gerektiren bir makro kullanarak geleneksel olarak uygulanmıştır bir [reinterpret_cast](../../cpp/reinterpret-cast-operator.md). Bu sabit ifade gerektiren bağlamlarda geçersiz, ancak Microsoft C++ derleyicisi, geleneksel olarak tanıdı. STL parçası doğru bir iç derleyici kullandığından, gönderildiğini offsetof makrosu (**__builtin_offsetof**), ancak çoğu kişi makrosu ux'in kendi tanımlamak için kullanılan **offsetof**.

Visual Studio 2017 sürüm 15,8, derleyici bu reinterpret_casts standardına uygun kod yardımcı olmak için varsayılan modunda görüntülenen alanları kısıtlar C++ davranışı. Altında [/ permissive-](../../build/reference/permissive-standards-conformance.md), kısıtlamaları taşıyabilmek. Offsetof işleminin bir sonucu sabit ifadeler gerektiren farklı yerde kullanarak C4644 uyarı veren kodu neden olabilir *sabit ifadeler offsetof makrosu tabanlı desende kullanımını standart; kullanım offsetof C++ standardında tanımlanan Kitaplık yerine* veya C2975 *geçersiz şablon bağımsız değişkeni, beklenen derleme zamanı sabit ifadesi*.

Aşağıdaki kod içinde C4644 başlatır **/varsayılan** ve **/Std: c ++ 17** modları ve içinde C2975 **/ permissive-** modu:

```cpp
struct Data {
    int x;
};

// Common pattern of user-defined offsetof
#define MY_OFFSET(T, m) (unsigned long long)(&(((T*)nullptr)->m))

int main()

{
    switch (0) {
    case MY_OFFSET(Data, x): return 0;
    default: return 1;
    }
}
```

Hatayı düzeltmek için kullanmak **offsetof** aracılığıyla tanımlanan \<cstddef >:

```cpp
#include <cstddef>

struct Data {
    int x;
};

int main()
{
    switch (0) {
    case offsetof(Data, x): return 0;
    default: return 1;
    }
}
```

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>Paket genişletmesi tabi temel sınıfları CV niteleyicileri

Microsoft C++ derleyicisinin önceki sürümlerinde, ayrıca paket genişletmesi tabi olduysa bir temel sınıf cv niteleyicileri olan algılamadı.

Visual Studio 2017 sürüm 15,8, içinde **/ permissive-** modu aşağıdaki kodu başlatır C3770 *'const S': geçerli bir taban sınıf değil*:

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>Şablon anahtar sözcüğü ve iç içe-ad-tanımlayıcıları

İçinde **/ permissive-** modu, derleyici artık gerektirir `template` anahtar sözcüğü, bir şablon adı öncesinde, bir iç içe-adı-bağımlı olan belirticisinden sonra geldiğinde.

Aşağıdaki kod içinde **/ permissive-** modu şimdi C7510 başlatır: *'foo': bağımlı şablon adı 'şablon' ile önekini almalıdır. Not: sınıf şablonu örneklemesi için bkz ' X<T>' oluşturuluyor derlenmiş*:

```cpp
template<typename T> struct Base
{
    template<class U> void foo() {}
};

template<typename T>
struct X : Base<T>
{
    void foo()
    {
        Base<T>::foo<int>();
    }
};
```

Hatayı düzeltmek için ekleme `template` anahtar `Base<T>::foo<int>();` aşağıdaki örnekte gösterildiği gibi deyimi:

```cpp
template<typename T> struct Base
{
    template<class U> void foo() {}
};

template<typename T>
struct X : Base<T>
{
    void foo()
    {
        // Add template keyword here:
        Base<T>::template foo<int>();
    }
};
```
## <a name="update_159"></a> Hata düzeltmeleri ve Visual Studio 2017 sürüm 15.9 davranış değişiklikleri

### <a name="identifiers-in-member-alias-templates"></a>Üye diğer ad şablonları tanımlayıcıları
Diğer şablon tanımı üyesi kullanılan tanımlayıcı kullanılmadan önce bildirilmelidir. 

Aşağıdaki kod Derleyici önceki sürümlerinde izin verilmiyordu:

```cpp
template <typename... Ts>
struct A
{
  public:
    template <typename U>
    using from_template_t = decltype(from_template(A<U>{}));

  private:
    template <template <typename...> typename Type, typename... Args>
    static constexpr A<Args...> from_template(A<Type<Args...>>);
};

A<>::from_template_t<A<int>> a;
```

Visual Studio 2017 sürüm 15.9, içinde **/ permissive-** modu, derleyici harekete geçirirse C3861: *'from_template': tanımlayıcı bulunamadı*.

Hatayı düzeltmek için bildirmek `from_template` önce `from_template_t`.

### <a name="modules-changes"></a>Modüller değişiklikleri

Modüller için komut satırı seçenekleri modülü oluşturulmasını ve modül tüketim yüz arasında tutarlı olmayan her Visual Studio 2017'de sürüm 15.9, derleyici C5050 başlatır. Aşağıdaki örnekte, iki sorun vardır:

- Tüketim tarafında (Main.cpp öğesi) seçeneğini **/ehsc** belirtilmedi.
- C++ sürümü **/Std: c ++ 17** oluşturma tarafında ve **/Std: c ++ 14** tüketim tarafında. 

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Her iki durumda C5050 derleyici başlatır: *C5050 Uyarı: Modülün içeri aktarılması sırasında olası uyumlu ortamı 'M ': C++ sürümleri eşleşmiyor.  Geçerli "201402" Modül sürümü "201703"*.

Ayrıca, .ifc dosyası ile oynanmış her derleyici C7536 başlatır. Modül arabirimi üstbilgisi bir SHA2 karma aşağıdaki içeriği içerir. İçeri aktarma işlemi sırasında .ifc dosya aynı şekilde karma ve üst bilgide sağlanan karma karşılaştırılarak; Bu hata C7536 oluşturulur eşleşmiyorsa: *IFC bütünlük denetimi başarısız oldu.  SHA2 bekleniyor: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'*.

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Kısmi sıralama içeren diğer adlar ve atanan bağlamları

Atanan bağlamlarda diğer adları içeren kısmi sıralama kuralları'nda uygulama Geçitler yoktur. Aşağıdaki örnek, GCC ve Microsoft C++ derleyicisi (içinde **/ permissive-** modu) kodu Clang kabul ederken bir hata oluştur. 

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <class T, class Alloc>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

Önceki örnekte C2668 başlatır:

```Output
partial_alias.cpp(32): error C2668: 'f': ambiguous call to overloaded function
partial_alias.cpp(18): note: could be 'int f<Alloc,void>(A<void> &,const AlignedBuffer<10,4> &)'
partial_alias.cpp(12): note: or       'int f<Alloc,A<void>>(Alloc &,const AlignedBuffer<10,4> &)'
        with
        [
            Alloc=A<void>
        ]
partial_alias.cpp(32): note: while trying to match the argument list '(A<void>, AlignedBuffer<10,4>)'
```

Uygulama Geçitler standart ifade'teki bir gerileme burada 2235 temel sorun çözümü Bu aşırı yüklemeler sıralanmasına izin bazı metin kaldırıldı kaynaklanır. Geçerli bir C++ Standart belirsiz kabul edilir, böylece bu işlevler, Kısmen sipariş mekanizması sağlamaz.

Geçici bir çözüm olarak, değil kısmi bu sorunu çözmek için sıralamasını ve bunun yerine SFINAE belirli yüklemelerini kaldırmak için kullanmanızı öneririz. Aşağıdaki örnekte yardımcı bir sınıf kullandığımız `IsA` kaldırmak için ilk aşırı zaman `Alloc` özelleştirmesi olan `A`:

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <typename T> struct IsA : std::false_type {};
template <typename T> struct IsA<A<T>> : std::true_type {};

template <class T, class Alloc, typename = std::enable_if_t<!IsA<Alloc>::value>>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>Geçersiz ifadeleri ve şablonlu işlev tanımlarındaki sabit olmayan değer türleri

Geçersiz ifadeleri ve sabit olmayan değer türleri artık doğru şekilde açıkça özelleştirilmiş şablonlu işlevleri tanımlarında tanı koydu. Daha önce bu tür hatalar için işlev tanımı yayılmadı. Ancak geçersiz ifade veya sabit olmayan değer türü yine de sabit bir ifade bir parçası olarak değerlendirildiğinde tanı koydu. 

Visual Studio'nun önceki sürümlerinde, uyarı vermeden aşağıdaki kodu derler:

```cpp
void g();
 
template<typename T>
struct S 
{
    constexpr void f();
};
  
template<>
constexpr void S<int>::f() 
{
    g(); // C3615 in 15.9
}
```

Visual Studio 2017 sürüm 15.9, bu hata kodu oluşturur: *hatası C3615: constexpr işlevinin<int>:: f' bir sabit ifade. Not sonuçlanamaz: hata, tanımlanmamış bir işlev veya bir değil bildirilen 'constexpr' çağrı tarafından nedeniyle oluştu Not: 'g' kullanımına bakın*. Hatayı önlemek için kaldırma `constexpr` işlevi f() açıkça örneğinin gelen niteleyicisi. 

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dil Uyumluluğu](../visual-cpp-language-conformance.md)
