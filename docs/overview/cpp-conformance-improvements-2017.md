---
title: Visual Studio 2017’deki C++ uyumluluk geliştirmeleri
description: Visual Studio 2017 ' de Microsoft C/C++, C++ 20 dil standardı ile tam uygunluğu doğru ilerliyor.
ms.date: 03/10/2021
ms.technology: cpp-language
ms.openlocfilehash: b2f697148c7671dcc56a6fd27a53131d01e3b88f
ms.sourcegitcommit: f8ba5db09d05683b24c58505f0e57c21f85545dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103147308"
---
# <a name="c-conformance-improvements-behavior-changes-and-bug-fixes-in-visual-studio-2017"></a>Visual Studio 2017 ' de C++ uygunluk geliştirmeleri, davranış değişiklikleri ve hata düzeltmeleri

Visual Studio 'da Microsoft C/C++ (MSVC) her sürümde uyumluluk geliştirmeleri ve hata düzeltmeleri yapar. Bu makalede, ana sürüme ve ardından sürüme göre iyileştirmeler listelenmektedir. Belirli bir sürümdeki değişikliklere doğrudan geçmek için **Bu makalede** aşağıdaki listeyi kullanın.

Bu belgede, Visual Studio 2017 'deki değişiklikler listelenir. Visual Studio 2019 ' deki değişikliklere yönelik bir kılavuz için bkz. [Visual studio 2019 ' de C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md). Önceki uyumluluk geliştirmelerinden oluşan kapsamlı bir liste için bkz. yenilikler [2003 ile 2015 arasında Visual C++](../porting/visual-cpp-what-s-new-2003-through-2015.md).

## <a name="conformance-improvements-in-visual-studio-2017-rtw-version-150"></a><a name="improvements_150"></a> Visual Studio 2017 RTW (sürüm 15,0) ile uyumluluk geliştirmeleri

**`constexpr`** Toplamalarda Genelleştirilmiş ve statik olmayan veri üyesi başlatma (NSDMı) desteğiyle, Visual Studio 2017 ' de MSVC derleyicisi artık c++ 14 standardına eklenen özellikler için tamamlanmıştır. Ancak, derleyicinin yine de C++ 11 ve C++ 98 standartlarından birkaç özelliği yoktur. Derleyicinin geçerli durumunu gösteren bir tablo için bkz. [Microsoft C++ dil uygunluğu tablosu](./visual-cpp-language-conformance.md) .

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++ 11: daha fazla kitaplıklarda Ifade SFıNAE desteği

Derleyici, SFıNAE ifadesi için desteğini iyileştirmeye devam eder. Şablon bağımsız değişken kesintisi ve değiştirme için **`decltype`** ve **`constexpr`** ifadelerin şablon parametreleri olarak görünebileceği bir değer gereklidir. Daha fazla bilgi için bkz. [Visual Studio 2017 RC 'de Expression SFINAE geliştirmeleri](https://devblogs.microsoft.com/cppblog/expression-sfinae-improvements-in-vs-2015-update-3/).

### <a name="c14-nsdmi-for-aggregates"></a>C++ 14: toplamalar için NSDMı

*Toplama* , bir dizi veya bir sınıftır: Kullanıcı tarafından sağlanmayan Oluşturucu yoktur, özel veya korumalı olmayan statik olmayan veri üyeleri yoktur, temel sınıf yoktur ve hiçbir sanal işlev yoktur. C++ 14 ' ten başlayarak, toplamalar üye başlatıcıları içerebilir. Daha fazla bilgi için bkz. [üye başlatıcıları ve toplamaları](https://wg21.link/n3605).

### <a name="c14-extended-constexpr"></a>C++ 14: genişletilmiş `constexpr`

Olarak belirtilen ifadeler **`constexpr`** , bazı bildirim türlerini, if ve Switch deyimlerini, Loop deyimlerini ve yaşam süresi ifade değerlendirmesi içinde başlayan nesnelerin zaman larını içermesine izin verilir **`constexpr`** . Artık **`constexpr`** statik olmayan bir üye işlevin örtük olarak olması gerekmez **`const`** . Daha fazla bilgi için bkz. [ `constexpr` Işlevlerde kısıtlamaları Gevşlama](https://wg21.link/n3652).

### <a name="c17-terse-static_assert"></a>C++ 17: terse `static_assert`

için ileti parametresi **`static_assert`** isteğe bağlıdır. Daha fazla bilgi için bkz. [N3928: genişletme static_assert, v2](https://wg21.link/n3928).

### <a name="c17-fallthrough-attribute"></a>C++ 17: `[[fallthrough]]` özniteliği

**`/std:c++17`** Modunda, öznitelik, `[[fallthrough]]` anahtar deyimlerinin bağlamında, bir derleyicinin bir ipucu olarak, dönüş davranışının istendiği bir ipucu olarak kullanılabilir. Bu öznitelik, derleyicinin bu gibi durumlarda uyarı vermesini engeller. Daha fazla bilgi için bkz. [P0188R0-ifadeleri for `[[fallthrough]]` Attribute](https://wg21.link/p0188r0).

### <a name="generalized-range-based-for-loops"></a>Genelleştirilmiş Aralık tabanlı `for` döngüler

Aralık tabanlı `for` döngüler artık bunu gerektirmez `begin()` ve `end()` aynı türdeki nesneleri döndürebilir. Bu değişiklik `end()` , içindeki aralıklar tarafından kullanılan bir Sentinel [`range-v3`](https://github.com/ericniebler/range-v3) ve tamamlanan-,-henüz yayımlanmış aralıklar teknik belirtiminde dönmesini sağlar. Daha fazla bilgi için bkz. [Range-Based `for` döngüsünü Genelleştirme P0184R0](https://wg21.link/p0184r0).

### <a name="copy-list-initialization"></a>Kopya listesini başlatma

Visual Studio 2017, başlatıcı listeleri kullanarak nesne oluşturmayla ilgili derleyici hatalarını doğru şekilde yükseltir. Bu hatalar Visual Studio 2015 ' de yakalanmadı ve kilitlenmelere veya tanımsız çalışma zamanı davranışına neden olabilir. İçinde, [N4594 13.3.1.7 P1](https://wg21.link/n4594)başına, içinde *`copy-list-initialization`* , aşırı yükleme çözümlemesi için açık bir oluşturucuyu düşünmek için derleyici gerekir. Ancak, belirli bir aşırı yükleme seçilirse bir hata oluşturması gerekir.

Aşağıdaki iki örnek Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de değildir.

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

Hatayı düzeltmek için, doğrudan başlatma kullanın:

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015 ' de, derleyici yanlışlıkla kopya listesini başlatmayı düzenli kopyalama başlatması ile aynı şekilde kabul ediyor: yalnızca aşırı yükleme çözümlemesi için Oluşturucu dönüştürmekte sayılır. Aşağıdaki örnekte, Visual Studio 2015 ' i seçer `MyInt(23)` . Visual Studio 2017, hatayı doğru şekilde yükseltir.

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
    p({ 23 }); // C3066: there are multiple ways that an object
        // of this type can be called with these arguments
}
```

Bu örnek bir öncekine benzerdir, ancak farklı bir hata oluşturur. Visual Studio 2015 ' de başarılı olur ve Visual Studio 2017 ' de C2668 ile başarısız olur.

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

Visual Studio 2017 artık bir sınıf veya yapıda belirtilen kullanım dışı tür tanımları için doğru uyarıyı yayınlar. Aşağıdaki örnek, Visual Studio 2015 ' de uyarılar olmadan derlenir. Visual Studio 2017 ' de C4996 oluşturur.

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

### `constexpr`

Koşullu değerlendirme işleminin sol işleneni bağlamda geçerli olmadığında Visual Studio 2017 doğru bir şekilde hata oluşturur `constexpr` . Aşağıdaki kod Visual Studio 2015 ' de derlenir, ancak Visual Studio 2017 ' de C3615.

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 constexpr function 'f' cannot result in a constant expression
}
```

Hatayı düzeltmek için, `array::size()` işlevi olarak bildirin **`constexpr`** ya da **`constexpr`** belirteci kaldırın `f` .

### <a name="class-types-passed-to-variadic-functions"></a>Değişken bağımsız değişken işlevlere geçirilen sınıf türleri

Visual Studio 2017 ' de, gibi farklı bir bağımsız değişken işleve geçirilen sınıflar veya yapılar, `printf` Üçlü kopyalanabilir olmalıdır. Bu tür nesneler geçirilirken, derleyici yalnızca bit düzeyinde bir kopya yapar ve oluşturucuyu veya yıkıcıyı çağırmaz.

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

Hatayı düzeltmek için, üç aylık kopyalanabilir türü döndüren bir üye işlevini çağırabilirsiniz

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

ya da başka bir deyişle, nesneyi geçirmeden önce dönüştürmek için statik bir tür kullanın:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Kullanılarak oluşturulan ve yönetilen dizeler için `CString` , `operator LPCTSTR()` bir `CString` nesneyi biçim dizesi tarafından beklenen C işaretçisine dönüştürmek için kullanılmalıdır.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>Sınıf yapııncv niteleyicileri

Visual Studio 2015 ' de, derleyici bazen bir Oluşturucu çağrısı aracılığıyla bir sınıf nesnesi oluştururken CV niteleyicisi yanlış yoksayar. Bu sorun muhtemelen kilitlenme veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnek Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de bir derleyici hatası oluşturur:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Hatayı düzeltmek için `operator int()` olarak bildirin **`const`** .

### <a name="access-checking-on-qualified-names-in-templates"></a>Şablonlarda nitelikli adlar üzerinde erişim denetimi

Derleyicinin önceki sürümleri bazı şablon bağlamlarındaki nitelikli adlara erişimi denetmedi. Bu sorun, bir adın erişilebilirliği nedeniyle değiştirme 'nin başarısız olması beklenen SFıNAE davranışına engel olabilir. Derleyici yanlış bir işlecin aşırı yüklemesini hatalı olarak çağırdığından, büyük olasılıkla çalışma zamanında kilitlenme veya beklenmeyen davranışlara neden olmuş olabilir. Visual Studio 2017 ' de bir derleyici hatası tetiklenir. Belirli hata değişebilir, ancak tipik bir hata C2672, "eşleşen aşırı yüklenmiş işlev bulunamadı" olur. Aşağıdaki kod Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de bir hata oluşturur:

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

### <a name="missing-template-argument-lists"></a>Eksik şablon bağımsız değişkeni listeleri

Visual Studio 2015 ve önceki sürümlerde, derleyici eksik olan tüm şablon bağımsız değişken listelerini tanımadı. Eksik şablon bir şablon parametre listesinde görünmezdi. Örneğin, varsayılan bir şablon bağımsız değişkeninin veya tür olmayan bir şablon parametresinin parçası olmadığında. Bu sorun, derleyici kilitlenmeleri veya beklenmeyen çalışma zamanı davranışı dahil öngörülemeyen davranışlara neden olabilir. Aşağıdaki kod Visual Studio 2015 ' de derlenir, ancak Visual Studio 2017 ' de bir hata oluşturur.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>İfade-SFıNAE

İfade-SFINAE 'yi desteklemek için, artık **`decltype`** şablon örneği oluşturulması yerine bir şekilde bildirildiği zaman bağımsız değişkenleri ayrıştırır. Bu nedenle, decltype bağımsız değişkeninde bağımlı olmayan bir özelleştirme bulunursa, örnek oluşturma zaman ertelenir. Anında işlenir ve bu sırada ortaya çıkan hatalar tanılandı.

Aşağıdaki örnekte, bildirim noktasında oluşan bir derleyici hatası gösterilmektedir:

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

### <a name="classes-declared-in-anonymous-namespaces"></a>Anonim ad alanlarında belirtilen sınıflar

C++ standardına göre, anonim bir ad alanı içinde belirtilen bir sınıfın iç bağlantısı vardır ve bu, verilemeyeceği anlamına gelir. Visual Studio 2015 ve önceki sürümlerde bu kural zorlanmaz. Visual Studio 2017 ' de kural kısmen zorlanır. Visual Studio 2017 ' de aşağıdaki örnek hata C2201 oluşturuyor:

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} };
  // C2201 const anonymous namespace::S1::vftable: must have external linkage
  // in order to be exported/imported.
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Değer sınıfı üyeleri için varsayılan başlatıcılar (C++/CLı)

Visual Studio 2015 ve önceki sürümlerde, derleyici bir değer sınıfının üyesi için varsayılan üye başlatıcısını (ancak yok sayılır) izin verilir. Değer sınıfının varsayılan başlatması her zaman sıfır-üyeleri başlatır. Varsayılan bir oluşturucuya izin verilmez. Visual Studio 2017 ' de, varsayılan üye başlatıcıları aşağıdaki örnekte gösterildiği gibi bir derleyici hatası yükseltir:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Varsayılan Dizin oluşturucular (C++/CLı)

Visual Studio 2015 ve önceki sürümlerde, bazı durumlarda derleyici varsayılan bir dizin oluşturucu olarak varsayılan bir özelliği yanlış tanımladı. Bu özelliğe erişmek için tanımlayıcıyı kullanarak soruna geçici bir çözüm olabilir **`default`** . Geçici çözüm, **`default`** c++ 11 ' de bir anahtar sözcük olarak sunulduktan sonra sorunlu hale geldi. Visual Studio 2017 ' de, geçici çözümü gerektiren hatalar düzeltildi. Derleyici artık **`default`** bir sınıf için varsayılan özelliğe erişmek üzere kullanıldığında bir hata oluşturur.

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

Visual Studio 2017 ' de, her iki değer özelliklerine adlarıyla erişebilirsiniz:

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="conformance-improvements-in-153"></a><a name="improvements_153"></a> 15,3 sürümündeki uyumluluk geliştirmeleri

### <a name="constexpr-lambdas"></a>`constexpr` Lambdalar

Lambda ifadeleri artık sabit ifadelerde kullanılabilir. Daha fazla bilgi için bkz. [ `constexpr` C++ ' da lambda ifadeleri](../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>`if constexpr` işlev şablonlarında

Bir işlev şablonu, **`if constexpr`** derleme zamanı dallanmayı etkinleştirmek için deyimler içerebilir. Daha fazla bilgi için bkz. [ `if constexpr` deyimler](../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Başlatıcılarla seçim deyimleri

Bir **`if`** ifade, deyimin kendisi içindeki blok kapsamında bir değişken sunan bir başlatıcı içerebilir. Daha fazla bilgi için bkz. [ `if` Başlatıcı olan deyimler](../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybe_unused-and-nodiscard-attributes"></a>`[[maybe_unused]]` ve `[[nodiscard]]` öznitelikleri

`[[maybe_unused]]`Bir varlık kullanılmazsa yeni öznitelik susturces uyarıları. `[[nodiscard]]`Öznitelik, bir işlev çağrısının dönüş değeri atıldığı takdirde bir uyarı oluşturur. Daha fazla bilgi için bkz. [C++ Içindeki öznitelikler](../cpp/attributes.md).

### <a name="using-attribute-namespaces-without-repetition"></a>Öznitelik ad alanlarını tekrarsız kullanma

Öznitelik listesinde yalnızca tek bir ad alanı tanımlayıcısını etkinleştirmek için yeni sözdizimi. Daha fazla bilgi için bkz. [C++ Içindeki öznitelikler](../cpp/attributes.md).

### <a name="structured-bindings"></a>Yapılandırılmış bağlamalar

Tek bir bildirimde, bir değeri bir dizi, ya da veya `std::tuple` `std::pair` tüm ortak statik olmayan veri üyelerine sahip olduğu durumlarda, bileşenleri için bağımsız adlarla bir değer depolamak için de mümkündür. Daha fazla bilgi için bkz. [P0144R0-Structured bağlamaları](https://wg21.link/p0144r0) ve [bir işlevden birden çok değer döndürme](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Değerler için yapım kuralları `enum class`

Artık daraltma olmayan kapsamlı Numaralandırmalar için örtük bir dönüştürme vardır. Kapsamlı bir numaralandırmanın temel alınan türünden numaralandırmanın kendisine dönüştürür. Dönüştürme, tanımı bir Numaralandırıcı oluşturmazsa ve kaynak bir liste başlatma söz dizimi kullandığında kullanılabilir. Daha fazla bilgi için bkz. değerler ve [numaralandırmalar](../cpp/enumerations-cpp.md#no_enumerators) [Için P0138R2-yapım kuralları `enum class` ](https://wg21.link/p0138r2) .

### <a name="capturing-this-by-value"></a>`*this`Değere göre yakalama

**`*this`** Lambda ifadesindeki nesne artık değere göre yakalanamaz. Bu değişiklik, özellikle daha yeni makine mimarilerinde, lambda 'nin paralel ve zaman uyumsuz işlemlerde çağrıldığı senaryolara izin vermez. Daha fazla bilgi için, bkz. [P0018R3-Lambda \* bu değere göre değer \[ =, \* Bu \] ](https://wg21.link/p0018r3).

### <a name="removing-operator-for-bool"></a>`operator++`İçin kaldırılıyor`bool`

`operator++` türler üzerinde artık desteklenmez **`bool`** . Daha fazla bilgi için bkz. [P0002R1-Remove işleci + + (bool)](https://wg21.link/p0002r1).

### <a name="removing-deprecated-register-keyword"></a>Kullanım dışı bırakılan `register` anahtar sözcüğü kaldırılıyor

**`register`** Daha önce kullanım dışı olan (ve derleyici tarafından yoksayılan) anahtar sözcüğü artık dilden kaldırılmıştır. Daha fazla bilgi için bkz. [P0001R1- `register` anahtar sözcüğünün kullanım dışı kullanımını kaldır](https://wg21.link/p0001r1).

### <a name="calls-to-deleted-member-templates"></a>Silinen üye şablonlarına yapılan çağrılar

Visual Studio 'nun önceki sürümlerinde, bazı durumlarda derleyici, silinen üye şablonuna yönelik hatalı biçimlendirilmiş çağrılar için bir hata yaymayabilir. Bu çağrılar, çalışma zamanında kilitlenmelere neden olabilir. Aşağıdaki kod artık C2280 üretir:

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail with
// C2280: 'int S<int>::f<int>(void)': attempting to reference a deleted function
}
```

Hatayı onarmak için `i` olarak bildirin **`int`** .

### <a name="pre-condition-checks-for-type-traits"></a>Tür nitelikleri için koşul öncesi denetimler

Visual Studio 2017 sürüm 15,3, standart bir şekilde izlemek için tür nitelikleri için koşul öncesi denetimleri geliştirir. Bu tür bir denetim atanabilir içindir. Aşağıdaki kod, Visual Studio 2017 sürüm 15,3 ' de C2139 üretir:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yeni derleyici uyarısı ve çalışma zamanı, yerel-yönetilen sıralamaya göre denetler

Yönetilen işlevlerden yerel işlevlere çağırma sıralama gerektirir. CLR sıralama yapar, ancak C++ semantiğini anlamaz. Bir yerel nesneyi değere göre geçirirseniz, CLR nesnenin kopya oluşturucusunu veya kullanımını çağırır `BitBlt` , bu da çalışma zamanında tanımsız davranışlara neden olabilir.

Derleyici, derleme zamanında bu hatayı bulursa bir uyarı yayar: silinen kopya ctor ile yerel bir nesne, değere göre yerel ve yönetilen sınır arasında geçirilir. Derleyicinin derleme zamanında tanımadığı bu durumlar için, `std::terminate` hatalı oluşturulmuş bir sıralama gerçekleştiğinde programın hemen çağırması için bir çalışma zamanı denetimi çıkarır. Visual Studio 2017 sürüm 15,3 ' de, aşağıdaki kod C4606 uyarısını üretir:

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
    // This call from managed to native requires marshaling. The CLR doesn't
    // understand C++ and uses BitBlt, which results in a double-free later.
    f(A()); // C4606 'A': passing argument by value across native and managed
    // boundary requires valid copy constructor. Otherwise, the runtime
    // behavior is undefined.`
}
```

Hatayı onarmak için, `#pragma managed` çağrıyı yapana yerel olarak işaretleme ve sıralama yapmaktan kaçının yönergesini kaldırın.

### <a name="experimental-api-warning-for-winrt"></a>WinRT için deneysel API uyarısı

Deneme ve geri bildirim için yayımlanan WinRT API 'Leri ile birlikte tasarlanmıştır `Windows.Foundation.Metadata.ExperimentalAttribute` . Visual Studio 2017 sürüm 15,3 ' de, derleyici bu öznitelik için uyarı C4698 oluşturur. Önceki Windows SDK sürümlerinden birkaç API zaten özniteliğiyle birlikte tasarlanmıştır ve bu API 'lere yapılan çağrılar artık bu derleyici uyarısını tetikler. Daha yeni Windows SDK 'Ları, tüm sevk edilen türlerden kaldırılan özniteliğe sahiptir. Daha eski bir SDK kullanıyorsanız, sevk edilen türlere yapılan tüm çağrılar için bu uyarıları bastırmak zorunda olacaksınız.

Aşağıdaki kod, C4698 uyarısını üretir:

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); // C4698
// 'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' is for
// evaluation purposes only and is subject to change or removal in future updates
```

Uyarıyı devre dışı bırakmak için #pragma ekleyin:

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Şablon üye işlevinin satır dışı tanımı

Visual Studio 2017 sürüm 15,3, sınıfında bildirilmeyen bir şablon üye işlevinin satır dışı tanımı için bir hata oluşturur. Aşağıdaki kod artık C2039 hatasını veriyor:

```cpp
struct S {};

template <typename T>
void S::f(T t) {} // C2039: 'f': is not a member of 'S'
```

Hatayı düzeltemedi, sınıfa bir bildirim ekleyin:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>İşaretçinin adresini alma girişimi `this`

C++ ' da, **`this`** X için işaretçi türünde bir prvalue olamaz. Adresini alamaz **`this`** veya bir lvalue başvurusuna bağlayamazsınız. Visual Studio 'nun önceki sürümlerinde derleyici, bu kısıtlamayı bir cast kullanarak atlatmayı sağlar. Visual Studio 2017 sürüm 15,3 ' de, derleyici C2664 hatasını üretir.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemeyen bir taban sınıfına dönüştürme

Visual Studio 2017 sürüm 15,3, bir türü erişilemeyen temel sınıfa dönüştürmeye çalıştığınızda bir hata üretir. Aşağıdaki kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Derleyici artık aşağıdakine benzer bir kod gördüğünde C2243 üretir:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243: 'type cast': conversion from 'D *' to 'B *' exists, but is inaccessible

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>Üye işlevlerinin satır dışı tanımlarında varsayılan bağımsız değişkenlere izin verilmez

Şablon sınıflarındaki üye işlevlerinin satır dışı tanımlarında varsayılan bağımsız değişkenlere izin verilmez. Derleyici, altında bir uyarı **`/permissive`** ve altında bir sabit hata verecek [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

Visual Studio 'nun önceki sürümlerinde, aşağıdaki hatalı oluşturulmuş kod, çalışma zamanı kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3, uyarı C5034 üretir:

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034: 'A<T>::f': an out-of-line definition of a member of a class template cannot have default arguments
{
    // ...
}
```

Hatayı onarmak için `= false` Varsayılan bağımsız değişkeni kaldırın.

### <a name="use-of-offsetof-with-compound-member-designator"></a>`offsetof`Bileşik üye göstergesi ile kullanımı

Visual Studio 2017 sürüm 15,3 ' de, `offsetof(T, m)` "bileşik üye göstergesi" *olarak kullanıldığında* , seçeneğiyle derlerken bir uyarı oluşur **`/Wall`** . Aşağıdaki kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3, uyarı C4841 üretir:

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Kodu onarmak için, bir pragma ile uyarıyı devre dışı bırakın ya da kodu kullanmayan olarak değiştirin `offsetof` :

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>`offsetof`Statik veri üyesi veya üye işlevi ile kullanma

Visual Studio 2017 sürüm 15,3 ' de `offsetof(T, m)` bir statik  veri üyesine veya üye işleve başvuran bir hata ile sonuçlanır. Aşağıdaki kod C4597 hatasını üretir:

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);  // C4597: undefined behavior: offsetof applied to member function 'A::ten'
constexpr auto off2 = offsetof(A, two); // C4597: undefined behavior: offsetof applied to static data member 'A::two'
```

Bu kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Hatayı onarmak için kodu artık tanımsız davranışı çağırmayacak şekilde değiştirin. C++ standardı tarafından izin verilmeyen taşınabilir olmayan kod.

### <a name="new-warning-on-__declspec-attributes"></a><a name="declspec"></a>Özniteliklerde yeni uyarı `__declspec`

Visual Studio 2017 sürüm 15,3 ' de, `__declspec(...)` bağlantı belirtiminden önce uygulanmışsa derleyici artık öznitelikleri yok saymaz `extern "C"` . Daha önce derleyici, çalışma zamanı etkilerine sahip olabilecek özniteliğini yoksayacaktır. **`/Wall`** Ve **`/WX`** seçenekleri ayarlandığında, aşağıdaki kod C4768 uyarısını üretir:

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall // C4768: __declspec attributes before linkage specification are ignored
```

Uyarıyı onarmak için, önce şunu yerleştirin `extern "C"` :

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı, varsayılan olarak 15,3 ' de, ancak varsayılan olarak 15,5 ' de kullanılır ve yalnızca ile derlenen kodu etkiler  **`/Wall`** **`/WX`** .

### <a name="decltype-and-calls-to-deleted-destructors"></a>`decltype` ve silinen yıkıcıları için çağrılar

Visual Studio 'nun önceki sürümlerinde derleyici, ile ilişkili ifade bağlamında silinmiş yok edicinin bir çağrısının gerçekleştiğini algılamadım **`decltype`** . Visual Studio 2017 sürüm 15,3 ' de aşağıdaki kod C2280 hatasını üretir:

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
   g(42); // C2280: 'A<T>::~A(void)': attempting to reference a deleted function
}
```

### <a name="uninitialized-const-variables"></a>Başlatılmamış const değişkenleri

Visual Studio 2017 RTW sürümünde gerileme vardı: C++ derleyicisi başlatılmamış bir değişken için tanılama yayınlamadığı **`const`** . Bu gerileme, Visual Studio 2017 sürüm 15,3 ' de düzeltildi. Aşağıdaki kod artık uyarı C4132 üretir:

```cpp
const int Value; // C4132: 'Value': const object should be initialized
```

Hatayı onarmak için bir değer atayın `Value` .

### <a name="empty-declarations"></a>Boş bildirimler

Visual Studio 2017 sürüm 15,3 artık yalnızca yerleşik türler değil, tüm türlerin boş bildirimlerinde uyarır. Aşağıdaki kod şu anda dört bildirim için bir düzey 2 C4091 uyarısı üretir:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Uyarıları kaldırmak için, yorum yapın veya boş bildirimleri kaldırın. Adlandırılmamış nesnenin bir yan etkisi olması amaçlanan durumlarda (örneğin, rampa), bir ad verilmelidir.

Uyarı düzeyi W2 altında, uyarı altında tutulur **`/Wv:18`** ve varsayılan olarak açık olur.

### <a name="stdis_convertible-for-array-types"></a>`std::is_convertible` dizi türleri için

Derleyicinin önceki sürümleri dizi türleri için yanlış sonuçlar verdi [`std::is_convertible`](../standard-library/is-convertible-class.md) . Bu gerekli kitaplık yazarları, nitelik türü kullanılırken Microsoft C++ derleyicisine özel durum verebilir `std::is_convertible<...>` . Aşağıdaki örnekte, statik onaylar Visual Studio 'nun önceki sürümlerinde geçer ancak Visual Studio 2017 sürüm 15,3 ' de başarısız olur:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>` , bir sanal işlev tanımının düzgün biçimlendirilmiş olup olmadığını denetleyerek hesaplanır:

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdis_constructible"></a>Özel Yıkıcılar ve `std::is_constructible`

Önceki derleyicinin sürümleri, sonucu saptarken bir yıkıcının özel olup olmadığını yoksaydı [`std::is_constructible`](../standard-library/is-constructible-class.md) . Artık bunları dikkate alır. Aşağıdaki örnekte, statik onaylar Visual Studio 'nun önceki sürümlerinde geçer ancak Visual Studio 2017 sürüm 15,3 ' de başarısız olur:

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

Özel Yıkıcılar bir türün oluşturulabilir olmayan şekilde oluşmasına neden olur. `std::is_constructible<T, Args...>` , aşağıdaki bildirim yazıldığı gibi hesaplanır:

```cpp
   T obj(std::declval<Args>()...)
```

Bu çağrı bir yıkıcı çağrısını gösterir.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: belirsiz aşırı yükleme çözümü

Derleyicinin önceki sürümleri bazen birden fazla aday ve bağımsız değişkene bağlı arama aracılığıyla birden çok aday bulmadığı zaman belirsizliğe neden olmuş olabilir. Bu hata, seçilen yanlış aşırı yüklemeye ve beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3 doğru C2668 yükseltir:

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
   f(s1, s2); // C2668: 'f': ambiguous call to overloaded function
}
```

Kodu onarmak için, `N::f` çağrısını amaçlıyorsanız using ifadesini kaldırın `::f()` .

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişkene bağlı arama

Yerel işlev bildirimleri kapsayan kapsamdaki işlev bildirimini gizler ve bağımsız değişkene bağımlı aramayı devre dışı bırakır. Derleyicinin önceki sürümleri her zaman bağımsız değişkene bağlı arama, bu durumda. Derleyici yanlış bir aşırı yüklemeyi seçtiyse, beklenmeyen çalışma zamanı davranışına neden olabilir. Genellikle, hata yerel işlev bildiriminin hatalı imzası nedeniyle oluşur. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3 doğru C2660 yükseltir:

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

Sorunu gidermek için `f(S)` imzayı değiştirin ya da kaldırın.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: Başlatıcı listelerinde başlatma sırası

Sınıf üyeleri, başlatıldıkları sırada başlatılır, başlatıcı listelerinde göründükleri sırada değildir. Önceki derleyicinin sürümleri, başlatıcı listesinin sırası bildirim sırasına göre farklıydı. Bu sorun, bir üyenin başlatması zaten başlatılmış başka bir üyeye bağımlıında, tanımsız çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3 (ile), **`/Wall`** Uyarı C5038 oluşturur:

```cpp
struct A
{    // Initialized in reverse, y reused
    A(int a) : y(a), x(y) {} // C5038: data member 'A::y' will be initialized after data member 'A::x'
    int x;
    int y;
};
```

Sorunu gidermek için, başlatıcı listesini bildirimlerle aynı sırada olacak şekilde düzenleyin. Bir veya her iki Başlatıcı de temel sınıf üyelerine başvururken benzer bir uyarı tetiklenir.

Bu uyarı varsayılan olarak kapalıdır ve yalnızca ile derlenen kodu etkiler **`/Wall`** .

## <a name="conformance-improvements-in-155"></a><a name="improvements_155"></a> 15,5 sürümündeki uyumluluk geliştirmeleri

14 ile işaretlenen Özellikler \[ , modunda bile koşullu olarak kullanılabilir **`/std:c++14`** .

### <a name="new-compiler-switch-for-extern-constexpr"></a>İçin yeni derleyici anahtarı `extern constexpr`

Visual Studio 'nun önceki sürümlerinde derleyici, **`constexpr`** değişken işaretlenmiş olsa bile her zaman iç bağlantı verdi **`extern`** . Visual Studio 2017 sürüm 15,5 ' de, yeni bir derleyici anahtarı, [`/Zc:externConstexpr`](../build/reference/zc-externconstexpr.md) doğru ve standartlara uygun davranışı mümkün bir şekilde sunar. Daha fazla bilgi için bkz. [ `extern constexpr` bağlantı](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimleri kaldırılıyor

[P0003R5](https://wg21.link/p0003r5) Dinamik özel durum belirtimleri C++ 11 ' de kullanımdan kaldırılmıştır. Özellik C++ 17 ' den kaldırılır, ancak (hala) kullanım dışı olan `throw()` Belirtim tamamen bir diğer ad olarak tutulur `noexcept(true)` . Daha fazla bilgi için bkz. [dinamik özel durum belirtimi `noexcept` kaldırma ve ](#noexcept_removal).

### `not_fn()`

[P0005R4](https://wg21.link/p0005r4) `not_fn` , ve ' nin yerini alır `not1` `not2` .

### <a name="rewording-enable_shared_from_this"></a>Yeniden ifade `enable_shared_from_this`

[P0033R1](https://wg21.link/p0033r1) `enable_shared_from_this` , C++ 11 ' ye eklenmiştir. C++ 17 standardı, belirli köşe durumlarını daha iyi işlemek için belirtimi güncelleştirir. \[May

### <a name="splicing-maps-and-sets"></a>Haritalar ve kümeler ile ayarlama

[P0083R3](https://wg21.link/p0083r3) Bu özellik, `map` `set` `unordered_map` `unordered_set` daha sonra değiştirilebilecek ve aynı kapsayıcıya veya aynı düğüm türünü kullanan farklı bir kapsayıcıya eklenebilen, ilişkili kapsayıcılardan (,,,,) düğümlerin ayıklanmasını mümkün hale gelir. (Yaygın kullanım örneği, bir düğümü bir öğesinden ayıklamak `std::map` , anahtarı değiştirmek ve yeniden eklemek için kullanılır.)

### <a name="deprecating-vestigial-library-parts"></a>Kalıntı kitaplık parçalarını kullanımdan kaldırma

[P0174R2](https://wg21.link/p0174r2) C++ standart kitaplığı 'nın birkaç özelliği, yıllar üzerinde yeni özelliklerden değiştirilmiştir veya başka bir yöntem bulunamadı veya sorunlu. Bu özellikler, C++ 17 ' de resmi kullanım dışı bırakılmıştır.

### <a name="removing-allocator-support-in-stdfunction"></a>İçindeki ayırıcı desteği kaldırılıyor `std::function`

[P0302R1](https://wg21.link/p0302r1) C++ 17 ' den önce, Sınıf şablonunda `std::function` ayırıcı bağımsız değişkeni alan birkaç Oluşturucu vardı. Bununla birlikte, bu bağlamdaki ayırıcıların kullanımı sorunlu ve semantik anlaşılır değildi. Sorun bu sorundan kaldırılmıştır.

### <a name="fixes-for-not_fn"></a>İçin düzeltmeler `not_fn()`

[P0358R1](https://wg21.link/p0358r1) İçin yeni ifade, `std::not_fn` sarmalayıcı çağrısında kullanıldığında değer kategorisinin yayılmasının desteğini sağlar.

### <a name="shared_ptrt-shared_ptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](https://wg21.link/p0414r2) `shared_ptr` Kitaplık temellerinde bulunan değişiklikleri c++ 17 ' ye birleştirme. \[May

### <a name="fixing-shared_ptr-for-arrays"></a>`shared_ptr`Diziler için düzeltme

[P0497R0](https://wg21.link/p0497r0) Diziler için shared_ptr desteğine yönelik düzeltmeler. \[May

### <a name="clarifying-insert_return_type"></a>Netleştirerek `insert_return_type`

[P0508R0](https://wg21.link/p0508r0) Benzersiz anahtarlarla ilişkilendirilebilir kapsayıcılar ve benzersiz anahtarlarla birlikte sıralanmamış kapsayıcılar, `insert` iç içe bir tür döndüren bir üye işlevine sahiptir `insert_return_type` . Bu dönüş türü artık yineleyici ve kapsayıcının NodeType üzerinde parametreli olan bir türün özelleştirmesi olarak tanımlanmıştır.

### <a name="inline-variables-for-the-standard-library"></a>Standart Kitaplık için satır içi değişkenler

[P0607R0](https://wg21.link/p0607r0)için, standart kitaplıkta belirtilen birkaç ortak değişken satır içi olarak bildirilmiştir.

### <a name="annex-d-features-deprecated"></a>Ek D özellikleri kullanım dışı

C++ standardının ek D,, ve dahil olmak üzere kullanım dışı bırakılmış tüm özellikleri içerir `shared_ptr::unique()` `<codecvt>` `namespace std::tr1` . **`/std:c++17`** Derleyici anahtarı ayarlandığında, ek D içindeki standart kitaplık özelliklerinin neredeyse tamamı kullanım dışı olarak işaretlenir. Daha fazla bilgi için bkz. [Ek D Içindeki standart kitaplık özellikleri kullanım dışı olarak işaretlendi](#annex_d).

`std::tr2::sys`' Deki ad alanı `<experimental/filesystem>` artık varsayılan olarak altında kullanımdan kaldırma uyarısı yayar **`/std:c++14`** ve **`/std:c++17`** Varsayılan olarak altında kaldırılır.

`<iostream>`Standart olmayan bir uzantıyı önleyerek ' de geliştirilmiş uyumluluk (sınıf içi açık uzmanlık).

Standart kitaplık artık değişken şablonları dahili olarak kullanmaktadır.

Standart Kitaplık, C++ 17 derleyici değişikliklerine yanıt olarak güncelleştirildi. Güncelleştirmeler, **`noexcept`** tür sistemine ekleme ve dinamik özel durum belirtimlerinin kaldırılması içerir.

### <a name="partial-ordering-change"></a>Kısmi sıralama değişikliği

Derleyici artık aşağıdaki kodu doğru şekilde reddeder ve doğru hata iletisini verir:

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

Yukarıdaki örnekte yer alan sorun, türlerde iki fark vardır (const ve const olmayan ve Pack ve Pack olmayan). Derleyici hatasını ortadan kaldırmak için farklardan birini kaldırın. Daha sonra derleyici, işlevleri kesin bir şekilde sıraya alabilir.

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

Dizi veya işlev türüne başvuru işleyicileri hiçbir bir özel durum nesnesi için hiçbir şekilde eşleşmez. Derleyici artık bu kurala göre doğru şekilde uyarın ve 4. düzey bir uyarı oluşturur. Ayrıca `char*` `wchar_t*` , kullanıldığı zaman bir veya bir dize sabiti ile eşleşmez **`/Zc:strictStrings`** .

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

Aşağıdaki kod hatayı önler:

```cpp
catch (int (*)[1]) {}
```

### <a name="stdtr1-namespace-is-deprecated"></a><a name="tr1"></a>`std::tr1`ad alanı kullanım dışı

Standart olmayan `std::tr1` ad alanı artık hem c++ 14 hem de c++ 17 modlarında kullanım dışı olarak işaretlenir. Visual Studio 2017 sürüm 15,5 ' de aşağıdaki kod C4996 yükseltilir:

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
warning C4996: 'std::tr1': warning STL4002: The non-standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

Hatayı onarmak için `tr1` ad alanına başvuruyu kaldırın:

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

### <a name="standard-library-features-in-annex-d-are-marked-as-deprecated"></a><a name="annex_d"></a> Ek D içindeki standart kitaplık özellikleri kullanım dışı olarak işaretlendi

**`/std:c++17`** Mod derleyici anahtarı ayarlandığında, ek D içindeki neredeyse tüm standart kitaplık özellikleri kullanım dışı olarak işaretlenir.

Visual Studio 2017 sürüm 15,5 ' de aşağıdaki kod C4996 yükseltilir:

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
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

Hatayı onarmak için aşağıdaki kodda gösterildiği gibi, uyarı metnindeki yönergeleri izleyin:

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

Visual Studio 15,5 ' de, uyarı C4189 aşağıdaki kodda gösterildiği gibi daha fazla durumda yayınlanır:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Hatayı onarmak için kullanılmayan değişkeni kaldırın.

### <a name="single-line-comments"></a>Tek satır açıklamaları

Visual Studio 2017 sürüm 15,5 ' de, uyarılar C4001 ve C4179 artık C derleyicisi tarafından yayılmayacaktır. Daha önce bunlar yalnızca derleyici anahtarı altında yer alırlar **`/Za`** .  Tek satır açıklamaları C99 sonrasında C standardının bir parçası olduğundan, uyarılar artık gerekli değildir.

```cpp
/* C only */
#pragma warning(disable:4001) // C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

Kodun geriye dönük olarak uyumlu olması gerekmiyorsa, C4001 ve C4179 gizlemesini kaldırarak uyarıyı önleyin. Kodun geriye dönük olarak uyumlu olması gerekiyorsa yalnızca C4619 ' ı gizleyin.

```C
/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="__declspec-attributes-with-extern-c-linkage"></a>`__declspec`bağlantısı olan öznitelikler `extern "C"`

Visual Studio 'nun önceki sürümlerinde, derleyici, `__declspec(...)` `__declspec(...)` bağlantı belirtiminden önce uygulandığında yoksayılan öznitelikleri yok sayılır `extern "C"` . Bu davranış, olası çalışma zamanı etkilerine karşı kullanıcının istememiş kodu oluşturulmasına neden oldu. Uyarı Visual Studio sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak etkindir.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall // C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Hatayı onarmak için, bağlantı belirtimini __declspec özniteliği önüne yerleştirin:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu yeni uyarı C4768, Visual Studio 2017 15,3 veya daha eski bir sürümü (örneğin, RS2 SDK olarak da bilinir) ile birlikte gelen bazı Windows SDK üstbilgilerinde verilmiştir. Ancak, daha sonraki Windows SDK üstbilgileri (özellikle, ShlObj. h ve ShlObj_core. h) sürümleri uyarı üretmedikleri için düzeltildi. Windows SDK başlıklarından gelen bu uyarıyı gördüğünüzde, bu eylemleri gerçekleştirebilirsiniz:

1. Visual Studio 2017 sürüm 15,5 sürümüyle birlikte gelen en son Windows SDK geçin.

1. Windows SDK Header ifadesinin #include etrafında uyarıyı kapat:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern-constexpr-linkage"></a><a name="extern_linkage"></a>`extern constexpr`bağlantı

Visual Studio 'nun önceki sürümlerinde, derleyici her zaman **`constexpr`** değişken işaretlenmiş olsa bile iç bağlantı değişkeni verdi **`extern`** . Visual Studio 2017 sürüm 15,5 ' de, yeni bir derleyici anahtarı ( **`/Zc:externConstexpr`** ), doğru, standartlara uygun bir davranış sunar. Sonuç olarak bu davranış varsayılan olur.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Bir üst bilgi dosyası, tanımlanmış bir değişken içeriyorsa **`extern constexpr`** , `__declspec(selectany)` yinelenen bildirimlerinin doğru şekilde birleştirilmek üzere işaretlenmesi gerekir:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>`typeid` tamamlanmamış sınıf türünde kullanılamaz

Visual Studio 'nun önceki sürümlerinde, derleyici aşağıdaki koda yanlış izin verdiği için hatalı tür bilgisi oluşmasına neden olur. Visual Studio 2017 sürüm 15,5 ' de, derleyici doğru bir hata oluşturur:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdis_convertible-target-type"></a>`std::is_convertible` hedef türü

`std::is_convertible` hedef türün geçerli bir dönüş türü olmasını gerektirir. Visual Studio 'nun önceki sürümlerinde, derleyici yanlış bir aşırı yükleme çözümüne ve istenmeyen çalışma zamanı davranışına neden olabilecek soyut türlere yanlış izin verebilir.  Aşağıdaki kod artık C2338 öğesini doğru şekilde yükseltir:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Hatanın önüne geçmek için, `is_convertible` bir tür soyut olduğunda işaretçi türü olmayan bir karşılaştırma başarısız olabileceğinden işaretçi türlerini karşılaştırmalısınız.

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="dynamic-exception-specification-removal-and-noexcept"></a><a name="noexcept_removal"></a> Dinamik özel durum belirtimi kaldırma ve `noexcept`

C++ 17 ' de, `throw()` için bir diğer addır ve **`noexcept`** `throw(<type list>)` `throw(...)` kaldırılır ve belirli türler dahil olabilir **`noexcept`** . Bu değişiklik, C++ 14 veya daha önceki bir sürümüyle uyumlu kodla kaynak uyumluluk sorunlarına neden olabilir. **`/Zc:noexceptTypes-`** Anahtar, **`noexcept`** genel olarak c++ 17 modu kullanılırken c++ 14 sürümüne dönmek için kullanılabilir. Bu `throw()` , tüm kodunuzu aynı anda yeniden yazmak zorunda kalmadan, kaynak kodunuzu c++ 17 ' ye uyacak şekilde güncelleştirmenizi sağlar.

Derleyici Ayrıca C++ 17 modundaki bildirimlerde veya yeni uyarı C5043 ile birlikte, artık eşleşmeyen özel durum belirtimlerini de tanılar [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

Aşağıdaki kod, anahtar uygulandığında Visual Studio 2017 sürüm 15,5 ' de C5043 ve C5040 üretir **`/std:c++17`** :

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

Hala kullanırken hataları kaldırmak için **`/std:c++17`** , **`/Zc:noexceptTypes-`** anahtarı komut satırına ekleyin ya da **`noexcept`** Aşağıdaki örnekte gösterildiği gibi kodunuzu kullanmak üzere güncelleştirin:

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

Statik **`constexpr`** veri üyeleri artık örtük olarak yapılır **`inline`** , bu da bir sınıftaki bildiriminin artık tanımıyla olduğu anlamına gelir. Veri üyesi için satır dışı bir tanım kullanmak **`static constexpr`** gereksizdir ve artık kullanım dışıdır. Visual Studio 2017 sürüm 15,5 ' de, **`/std:c++17`** anahtar uygulandığında aşağıdaki kod artık uyarı C5041 üretir:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041: 'size': out-of-line definition for constexpr static data member is not needed and is deprecated in C++17
```

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)` Uyarı C4768 Şu anda varsayılan olarak açık

Uyarı Visual Studio 2017 sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak açık olur. Daha fazla bilgi için bkz. [ `__declspec` özniteliklerde yeni uyarı](#declspec).

### <a name="defaulted-functions-and-__declspecnothrow"></a>Varsayılan işlevler ve `__declspec(nothrow)`

Derleyici, `__declspec(nothrow)` karşılık gelen temel/üye işlevleri için özel durumlara izin verildiğinde, önceden ayarlanmış işlevlerin ile bildirilmesine izin verilir. Bu davranış, C++ standardının aksine, çalışma zamanında tanımsız davranışlara neden olabilir. Özel durum belirtimi uyumsuzluğu varsa, standart bu tür işlevlerin silinmiş olarak tanımlanmasını gerektirir.  **`/std:c++17`** Aşağıdaki kod, C2280 başlatır:

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
    b2 = b1; // error C2280: attempting to reference a deleted function.
             // Function was implicitly deleted because the explicit exception
             // specification is incompatible with that of the implicit declaration.
}
```

Bu kodu düzeltmek için, varsayılan işlevden __declspec (nothrow) öğesini kaldırın ya da `= default` gerekli özel durum işlemeyle birlikte işlev için bir tanım sağlayın:

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

### <a name="noexcept-and-partial-specializations"></a>`noexcept` ve kısmi uzmanlık

**`noexcept`** Tür sisteminde, belirli "çağrılabilir" türler için kısmi özelleşmeler derlenmeyebilir veya,-noexcept işlevleri için eksik bir kısmi özelleştirme nedeniyle birincil şablonu seçemeyebilir.

Bu gibi durumlarda, **`noexcept`** işlev işaretçilerini ve üye işlevlerine işaretçiler işlemek için daha fazla kısmi uzmanlık eklemeniz gerekebilir **`noexcept`** . Bu aşırı yüklemeler yalnızca modda geçerlidir **`/std:c++17`** . C++ 14 ile geriye dönük uyumluluk korunuyorsa ve başkalarının kullandığı kodu yazıyorsanız, bu yeni aşırı yüklemeleri yönergeler içinde korumalısınız `#ifdef` . Kendi kendine içerilen bir modülde çalışıyorsanız, koruma kullanmak yerine `#ifdef` yalnızca anahtarla derleme yapabilirsiniz **`/Zc:noexceptTypes-`** .

Aşağıdaki kod, altında derlenir **`/std:c++14`** ancak **`/std:c++17`** hata C2027 ile başarısız olur:

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
    return g(&f) ? 0 : 1; // C2027: use of undefined type 'A<T>'
}
```

Aşağıdaki kod, **`/std:c++17`** derleyici yeni kısmi özelleşme seçtiği için altında başarılı olur `A<void (*)() noexcept>` :

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

## <a name="conformance-improvements-in-156"></a><a name="improvements_156"></a> 15,6 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-library-fundamentals-v1"></a>C++ 17 kitaplık temelleri v1

[P0220R1](https://wg21.link/p0220r1) c++ 17 Için kitaplık temelleri teknik belirtimini standart olarak içerir. ,,,,,,, Ve için güncelleştirmeleri içerir \<experimental/tuple> \<experimental/optional> \<experimental/functional> \<experimental/any> \<experimental/string_view> \<experimental/memory> \<experimental/memory_resource> \<experimental/algorithm> .

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++ 17: standart kitaplık için sınıf şablonu bağımsız değişken kesintiyi geliştirme

[P0739R0](https://wg21.link/p0739r0) `adopt_lock_t` `scoped_lock` Uygulamasının tutarlı kullanımını etkinleştirmek için için parametre listesinin önüne geçin `scoped_lock` . `std::variant`Oluşturucuyu kopyalama atamasını etkinleştirmek için, daha fazla durumda oluşturucunun aşırı yükleme çözümüne katılmasına izin verin.

## <a name="conformance-improvements-in-157"></a><a name="improvements_157"></a> 15,7 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-rewording-inheriting-constructors"></a>C++ 17: Reifade devralan oluşturucular

[P0136R1](https://wg21.link/p0136r1) **`using`** bir oluşturucuyu isimlendiremeyen bir bildirimin, ilgili temel sınıf oluşturucuların daha fazla türetilmiş sınıf Oluşturucu bildirmek yerine, türetilen sınıfın başlatmaları için görünür olduğunu belirtir. Bu reifade, C++ 14 ' ten bir değişiklik. Visual Studio 2017 sürüm 15,7 ve sonraki sürümlerinde, **`/std:c++17`** modunda c++ 14 ' te geçerli olan ve devralan oluşturucular kullanan kod geçerli olmayabilir veya farklı anlamlarına sahip olabilir.

Aşağıdaki örnek C++ 14 davranışını gösterir:

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

Aşağıdaki örnekte, **`/std:c++17`** Visual Studio 15,7 davranışı gösterilmektedir:

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

Daha fazla bilgi için bkz. [oluşturucular](../cpp/constructors-cpp.md#inheriting_constructors).

### <a name="c17-extended-aggregate-initialization"></a>C++ 17: genişletilmiş toplu başlatma

[P0017R1](https://wg21.link/p0017r1)

Bir temel sınıfın Oluşturucusu genel olmayan, ancak türetilmiş bir sınıf tarafından erişilebiliyorsa, **`/std:c++17`** Visual Studio 2017 sürüm 15,7 ' de mod altında, türetilmiş türdeki bir nesneyi başlatmak için artık boş küme ayraçları kullanamazsınız.
Aşağıdaki örnekte C++ 14 uyumlu davranış gösterilmektedir:

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

C++ 17 ' de `Derived` artık bir toplam türü olarak kabul edilir. Bu, `Base` özel varsayılan oluşturucu aracılığıyla başlatmanın, genişletilmiş toplama başlatma kuralının bir parçası olarak doğrudan gerçekleşir anlamına gelir. Daha önce, `Base` özel Oluşturucu Oluşturucu aracılığıyla çağrılıydı `Derived` ve arkadaş bildirimi nedeniyle başarılı oldu.
Aşağıdaki örnekte, Visual Studio sürüm 15,7 ' deki C++ 17 davranışı **`/std:c++17`** modda gösterilmektedir:

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

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++ 17: otomatik olarak tür olmayan şablon parametreleri bildirme

[P0127R2](https://wg21.link/p0127r2)

**`/std:c++17`** Modunda, derleyici artık ile belirtilen tür olmayan bir şablon bağımsız değişkeninin türünü verebilir **`auto`** :

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Bu yeni özelliğin bir etkisi geçerli C++ 14 kodunun geçerli olmaması veya farklı anlambilime sahip olması olabilir. Örneğin, daha önce geçersiz olan bazı aşırı yüklemeler artık geçerlidir. Aşağıdaki örnek, ' a ' çağrısı olduğu için derlenen C++ 14 kodunu gösterir `example(p)` `example(void*);` . Visual Studio 2017 sürüm 15,7 ' de **`/std:c++17`** modunda, `example` işlev şablonu en iyi eşleşmedir.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

Aşağıdaki örnekte, modunda Visual Studio 15,7 ' de C++ 17 kodu gösterilmektedir **`/std:c++17`** :

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*);

void example(void *);

void sample(A<0> *p)
{
    example(p); // C2280: 'int example<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++ 17: Elemensel dize dönüştürmeleri (kısmi)

[P0067R5](https://wg21.link/p0067r5) Tamsayılar ve dizeler arasında ve kayan noktalı sayılar ve dizeler arasındaki dönüşümler için alt düzey, yerel ayara bağımsız işlevler.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++ 20: gereksiz Decay 'yi önleme (kısmi)

[P0777R1](https://wg21.link/p0777r1) "Decay" kavramı arasına farklılaşmayı ekler ve yalnızca const veya başvuru niteleyicilerini kaldırmaktır.  Yeni tür nitelik `remove_reference_t` `decay_t` bazı bağlamlarda yerini alır. Desteği `remove_cvref_t` Visual Studio 2019 ' de uygulanır.

### <a name="c17-parallel-algorithms"></a>C++ 17: paralel algoritmalar

[P0024R2](https://wg21.link/p0024r2) Paralellik, küçük değişikliklerle standart olarak birleştirilir.

### <a name="c17-hypotx-y-z"></a>C++ 17: `hypot(x, y, z)`

[P0030R1](https://wg21.link/p0030r1) , `std::hypot` **`float`** **`double`** Ve **`long double`** her birinin üç giriş parametresi bulunan türleri için için üç yeni aşırı yükleme ekler.

### <a name="c17-filesystem"></a>C++ 17: \<filesystem>

[P0218R1](https://wg21.link/p0218r1) Birkaç ifade değişikliği ile dosya sistemini standart olarak benimseme.

### <a name="c17-mathematical-special-functions"></a>C++ 17: matematik özel işlevleri

[P0226R1](https://wg21.link/p0220r1) Matematik özel Işlevleri için önceki teknik belirtimleri standart üstbilgiye benimseme \<cmath> .

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++ 17: standart kitaplık için kesinti Kılavuzu

[P0433R2](https://wg21.link/p0433r2) STL 'ye güncelleştirme, sınıf şablonu bağımsız değişkeni için destek ekleyen [P0091R3](https://wg21.link/p0091r3)'in c++ 17 benimseme özelliğinden faydalanmak için.

### <a name="c17-repairing-elementary-string-conversions"></a>C++ 17: elemensel dize dönüşümlerini onarma

[P0682R1](https://wg21.link/p0682r1) Yeni elemensel dize dönüştürme işlevlerini P0067R5 ' dan yeni bir üstbilgiye taşıyın \<charconv> ve yerine kullanılacak hata işlemeyi değiştirme de dahil olmak üzere diğer iyileştirmeler yapın `std::errc` `std::error_code` .

### <a name="c17-constexpr-for-char_traits-partial"></a>C++ 17: `constexpr` for `char_traits` (kısmi)

[P0426R1](https://wg21.link/p0426r1) `std::traits_type` `length` `compare` `find` Sabit ifadelerde kullanılabilir hale getirmek için, ve üye `std::string_view` işlevlerindeki değişiklikler. (Visual Studio 2017 sürüm 15,6 ' de yalnızca Clang/LLVM için desteklenir. Sürüm 15,7 Preview 2 ' de, destek, ClXX için neredeyse tamamlanmıştır.)

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++ 17: birincil Sınıf şablonunda varsayılan bağımsız değişken

Bu davranış değişikliği, [sınıf şablonları Için P0091R3-Template bağımsız değişken kesintisi](https://wg21.link/p0091r3)için bir önkoşuludur.

Daha önce, derleyici birincil Sınıf şablonunda varsayılan bağımsız değişkeni yok sayıldı:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

**`/std:c++17`** Visual Studio 2017 sürüm 15,7 ' deki modda varsayılan bağımsız değişken yok sayılır:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Bağımlı ad çözümlemesi

Bu davranış değişikliği, [sınıf şablonları Için P0091R3-Template bağımsız değişken kesintisi](https://wg21.link/p0091r3)için bir önkoşuludur.

Aşağıdaki örnekte, Visual Studio 15,6 ve önceki sürümlerde derleyici, `D::type` `B<T>::type` birincil Sınıf şablonunda olarak çözümleniyor.

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

Visual Studio 2017 sürüm 15,7, **`/std:c++17`** modunda, **`typename`** D içindeki ifadesinde anahtar sözcüğü gerektirir **`using`** . Olmadan **`typename`** , derleyici uyarı C4346: `'B<T*>::type': dependent name is not a type` ve hata C2061: `syntax error: identifier 'type'` :

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

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++ 17: `[[nodiscard]]` öznitelik-uyarı düzeyi artış

Visual Studio 2017 sürüm 15,7 **`/std:c++17`** modunda, C4834 uyarı düzeyi, W3 'Den W1 'e yükseltilir. Bir cast ile **`void`** veya derleyiciye geçirerek uyarıyı devre dışı bırakabilirsiniz **`/wd:4834`**

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning C4834: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Değişken bağımsız değişken şablon Oluşturucusu temel sınıf başlatma listesi

Visual Studio 'nun önceki sürümlerinde, şablon bağımsız değişkenleri eksik olan bir bağımsız değişken şablon Oluşturucu temel sınıf başlatma listesine hatasız olarak izin veriliyor. Visual Studio 2017 sürüm 15,7 ' de bir derleyici hatası tetiklenir.

Visual Studio 2017 sürüm 15,7 ' de aşağıdaki kod örneği C2614 hatasını yükseltir:

```cpp
template<typename T>
struct B {};

template<typename T>
struct D : B<T>
{

    template<typename ...C>
    D() : B() {} // C2614: D<int>: illegal member initialization: 'B' is not a base or member
};

D<int> d;
```

Hatayı onarmak için B () ifadesini B \<T> () olarak değiştirin.

### <a name="constexpr-aggregate-initialization"></a>`constexpr` toplu başlatma

C++ derleyicisinin önceki sürümleri, toplu başlatmayı yanlış bir şekilde işledi **`constexpr`** . Derleyici, toplama-init listesinde çok fazla öğe olduğu ve kendisi için hatalı nesne kodu üreten geçersiz kodu kabul etti. Aşağıdaki kod bu kodun bir örneğidir:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = { // C2078: too many initializers
        { 1, 2 },
        { 3, 4 }
    };
    return 0;
}
```

Visual Studio 2017 sürüm 15,7 güncelleştirme 3 ve sonraki sürümlerde, önceki örnek artık C2078 ' u yükseltir. Aşağıdaki örnek, kodun nasıl düzeltileceğini gösterir. `std::array`İç içe yerleştirilmiş küme ayracı-init-listeleriyle, iç diziye kendi kendine açılan bir liste verin:

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

## <a name="conformance-improvements-in-158"></a><a name="update_158"></a> 15,8 sürümündeki uyumluluk geliştirmeleri

### <a name="typename-on-unqualified-identifiers"></a>`typename` Nitelenmemiş tanımlayıcıda

[`/permissive-`](../build/reference/permissive-standards-conformance.md)Modunda, **`typename`** diğer ad şablonu tanımlarında nitelenmemiş tanımlayıcılarda bulunan spurerkeywords anahtar sözcükleri artık derleyici tarafından kabul edilmez. Aşağıdaki kod artık C7511 üretir:

```cpp
template <typename T>
using  X = typename T; // C7511: 'T': 'typename' keyword must be 
                       // followed by a qualified name
```

Hatayı onarmak için ikinci satırı olarak değiştirin `using  X = T;` .

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()` diğer ad şablonu tanımlarının sağ tarafında

[`__declspec`](../cpp/declspec.md) Artık diğer ad şablon tanımının sağ tarafında izin verilmez. Daha önce derleyici kabul etti ancak bu kodu yok sayıldı. Diğer ad kullanıldığında, hiçbir zaman kullanımdan kaldırma uyarısı oluşmasına neden olmaz.

Bunun yerine standart C++ özniteliği [`[[deprecated]]`](../cpp/attributes.md) kullanılabilir ve Visual Studio 2017 sürüm 15,6 ' de yer alabilir. Aşağıdaki kod artık C2760 üretir:

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T; // C2760: syntax error:
                                           // unexpected token '__declspec',
                                           // expected 'type specifier'`
```

Hatayı onarmak için, koda (diğer ad tanımının ' = ' önüne yerleştirilmiş özniteliği) aşağıdaki gibi değiştirin:

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>İki aşamalı ad arama tanılaması

İki aşamalı ad arama, şablon gövdelerinde kullanılan bağımlı olmayan adların, tanım zamanında şablona görünür olması gerekir. Daha önce, Microsoft C++ derleyicisi, bulunmayan bir adı, örnekleme zamanına kadar aranmaz olarak bırakır. Şimdi, bağımlı olmayan adların şablon gövdesine bağlı olmasını gerektirir.

Bu şekilde bildirimde bulunan tek bir yöntem, bağımlı temel sınıflara aramalardır. Daha önce, derleyici bağımlı temel sınıflarda tanımlanmış adların kullanılmasına izin verilir. Bunun nedeni, tüm türlerin çözümlenme zamanı sırasında örnekleme sırasında aranmaları. Artık bu kod bir hata olarak kabul edilir. Bu durumlarda, değişkeni temel sınıf türü ile niteleyerek veya bir işaretçi ekleyerek buna bağımlı hale getirerek, örneği örnekleme zamanına göre aranmaya zorlayabilirsiniz `this->` .

[`/permissive-`](../build/reference/permissive-standards-conformance.md)Modda aşağıdaki kod artık C3861 ' u yükseltir:

```cpp
template <class T>
struct Base {
    int base_value = 42;
};

template <class T>
struct S : Base<T> {
    int f() {
        return base_value; // C3861: 'base_value': identifier not found
    }
};
```

Hatayı onarmak için, **`return`** ifadesini olarak değiştirin `return this->base_value;` .

> [!NOTE]
> 1,70 'den önceki Boost. Python kitaplık sürümlerinde, içindeki bir şablon iletme bildirimi için MSVC özgü bir geçici çözüm vardır [`unwind_type.hpp`](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp) . [`/permissive-`](../build/reference/permissive-standards-conformance.md)Visual Studio 2017 sürüm 15,8 () ' den başlayan mod altında `_MSC_VER==1915` MSVC derleyicisi, bağımsız değişkene bağımlı ad araması (adl) doğru şekilde yapar. Artık diğer derleyicilerle tutarlıdır, bu geçici çözüm koruma gereksiz hale gelir. Hata C3861: ' ı kullanmaktan kaçınmak için `'unwind_type': identifier not found` , Boost. Python kitaplığınızı güncelleştirin.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>ad alanındaki iletme bildirimleri ve tanımları `std`

C++ standardı, bir kullanıcının ad alanına iletme bildirimleri veya tanımları eklemesine izin vermez `std` . Ad alanına veya ad alanı içindeki bir ad alanına bildirim veya tanım eklemek `std` `std` artık tanımsız davranışa neden olur.

Daha sonra, Microsoft, bazı standart kitaplık türlerinin tanımlandığı konumu taşıyacaktır. Bu değişiklik, ad alanına iletme bildirimleri ekleyen mevcut kodu keser `std` . Yeni bir uyarı olan C4643, bu tür kaynak sorunları belirlemenize yardımcı olur. Uyarı **`/default`** modda etkindir ve varsayılan olarak kapalıdır. , Veya ile derlenen programları etkiler **`/Wall`** **`/WX`** .

Aşağıdaki kod artık C4643 ' i yükseltir:

```cpp
namespace std {
    template<typename T> class vector;  // C4643: Forward declaring 'vector'
                                        // in namespace std is not permitted
                                        // by the C++ Standard`
}
```

Hatayı onarmak için, **`#include`** iletme bildirimi yerine bir yönerge kullanın:

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>Kendilerine temsilci olan oluşturucular

C++ standardı, bir derleyicinin kendi kendine temsilci Oluşturucu temsilcisi olarak bir tanı yaymayı önerir. Ve modlarında Microsoft C++ derleyicisi [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) artık C7535 ' i başlatır.

Bu hata olmadan, aşağıdaki program derlenir ancak sonsuz bir döngü oluşturacak:

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){} // C7535: 'X::X': delegating constructor calls itself
};
```

Sonsuz döngüyü önlemek için farklı bir oluşturucuya temsilci seçin:

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>`offsetof` Sabit ifadelerle

[`offsetof`](../c-runtime-library/reference/offsetof-macro.md) , geleneksel olarak, gerektiren bir makro kullanılarak uygulanmıştır [`reinterpret_cast`](../cpp/reinterpret-cast-operator.md) . Bu kullanım, sabit bir ifade gerektiren bağlamlarda geçersizdir, ancak Microsoft C++ derleyicisinde geleneksel olarak izin verilir. `offsetof`Standart kitaplığın bir parçası olarak gönderilen makro bir derleyici iç ( **`__builtin_offsetof`** ) kullanır, ancak pek çok kişi makro eli kullanarak kendi kendilerini tanımlar `offsetof` .

Visual Studio 2017 sürüm 15,8 ' de, derleyici, **`reinterpret_cast`** Standart C++ davranışına uyum sağlamak için bu işleçlerin varsayılan modda görünebilen alanı kısıtlar. Altında [`/permissive-`](../build/reference/permissive-standards-conformance.md) kısıtlamalar bile daha sıkı bir şekilde yapılır. `offsetof`Sabit ifadeler gerektiren bir konum sonucunun kullanılması, uyarı C4644 veya C2975 veren koda neden olabilir.

Aşağıdaki kod **`/default`** , C4644 ve modlarını ve **`/std:c++17`** C2975 in [`/permissive-`](../build/reference/permissive-standards-conformance.md) Mode:

```cpp
struct Data {
    int x;
};

// Common pattern of user-defined offsetof
#define MY_OFFSET(T, m) (unsigned long long)(&(((T*)nullptr)->m))

int main()

{
    switch (0) {
    case MY_OFFSET(Data, x): return 0; // C4644: usage of the
        // macro-based offsetof pattern in constant expressions
        // is non-standard; use offsetof defined in the C++
        // standard library instead
        // OR
        // C2975: invalid template argument, expected
        // compile-time constant expression

    default: return 1;
    }
}
```

Hatayı onarmak için şunu kullanarak `offsetof` tanımlandığı şekilde kullanın \<cstddef> :

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

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>paket genişletmesine tabi olan temel sınıflarda CV niteleyicileri

Microsoft C++ derleyicisinin önceki sürümleri, paket genişletmesi için de bir temel sınıfta CV niteleyicileri olduğunu algılamamıştı.

Visual Studio 2017 sürüm 15,8 ' de [`/permissive-`](../build/reference/permissive-standards-conformance.md) modda aşağıdaki kod C3770 yükseltilir:

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x; // C3770: 'const S': is not a valid base class
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>`template` anahtar sözcük ve iç içe ad-tanımlayıcılar

[`/permissive-`](../build/reference/permissive-standards-conformance.md)Modunda, derleyici artık, **`template`** bağımlı bir iç içe ad belirleyicisi sonrasında olduğunda bir şablon adının önüne geçmek için anahtar sözcüğü gerektirir.

Aşağıdaki modda aşağıdaki kod [`/permissive-`](../build/reference/permissive-standards-conformance.md) artık C7510 ' a yükseltilir:

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        Base<T>::example<int>(); // C7510: 'example': use of dependent
            // template name must be prefixed with 'template'
            // note: see reference to class template instantiation
            // 'X<T>' being compiled
    }
};
```

Hatayı onarmak için **`template`** `Base<T>::example<int>();` Aşağıdaki örnekte gösterildiği gibi ifadeye anahtar sözcüğünü ekleyin:

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        // Add template keyword here:
        Base<T>::template example<int>();
    }
};
```

## <a name="conformance-improvements-in-159"></a><a name="improvements_159"></a> 15,9 sürümündeki uyumluluk geliştirmeleri

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>İşleçler `->*` , `[]` , `>>` ve için soldan sağa değerlendirme sırası `<<`

C++ 17 ' den başlayarak,,, ve işleçlerinin `->*` işlenenleri `[]` `>>` `<<` soldan sağa sırada değerlendirilmelidir. Derleyicinin bu sırayı garanti edemediği iki durum vardır:

- işlenen ifadelerinden biri, değer ile geçirilen bir nesne veya değer tarafından geçirilen bir nesne içeriyorsa veya

- kullanılarak derlendiğinde **`/clr`** ve işlenenlerinden biri bir nesnenin veya dizi öğesinin bir alanıdır.

Derleyici, soldan sağa değerlendirmeyi garanti edemediği zaman uyarı [C4866](../error-messages/compiler-warnings/c4866.md) yayar. Derleyici, bu **`/std:c++17`** operatörlerin soldan sağa sırası gereksinimi c++ 17 ' de tanıtıldığından, bu uyarıyı yalnızca veya daha sonra belirtilmişse oluşturur.

Bu uyarıyı çözmek için öncelikle işlenenlerin sol-sağ değerlendirmesinin gerekli olup olmadığını göz önünde bulundurun. Örneğin, işlenenlerin değerlendirmesi sırasıyla sipariş bağımlı yan etkiler üretemedi, bu gerekli olabilir. İşlenenlerinin değerlendirildiği sıranın birçok durumda herhangi bir observable etkisi yoktur. Değerlendirme sırası soldan sağa doğru olmalıdır. bunun yerine işlenenleri const başvuruya göre mi geçiremeyeceğinizi düşünün. Bu değişiklik aşağıdaki kod örneğindeki uyarıyı ortadan kaldırır:

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

### <a name="identifiers-in-member-alias-templates"></a>Üye diğer ad şablonlarındaki tanımlayıcılar

Üye diğer ad şablonu tanımında kullanılan tanımlayıcı kullanılmadan önce bildirilmelidir.

Derleyicinin önceki sürümlerinde, aşağıdaki koda izin verilir. Visual Studio 2017 sürüm 15,9 ' de, [`/permissive-`](../build/reference/permissive-standards-conformance.md) modda derleyici C3861 ' u yükseltir:

```cpp
template <typename... Ts>
struct A
{
  public:
    template <typename U>
    using from_template_t = decltype(from_template(A<U>{})); // C3861:
        // 'from_template': identifier not found

  private:
    template <template <typename...> typename Type, typename... Args>
    static constexpr A<Args...> from_template(A<Type<Args...>>);
};

A<>::from_template_t<A<int>> a;
```

Hatayı onarmak için, önce bildirimini `from_template` yapın `from_template_t` .

### <a name="modules-changes"></a>Modül değişiklikleri

Visual Studio 2017, sürüm 15,9 ' de, modüller için komut satırı seçenekleri modül oluşturma ve modül tüketim tarafları arasında tutarlı olmadığı zaman derleyici C5050 ' u yükseltir. Aşağıdaki örnekte, iki sorun vardır:

- Tüketim tarafında (Main. cpp), seçenek **`/EHsc`** belirtilmez.

- C++ sürümü **`/std:c++17`** oluşturma tarafında ve **`/std:c++14`** Tüketim tarafında bulunur.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Derleyici, bu iki durum için C5050 başlatır:

```Output
warning C5050: Possible incompatible environment while
importing module 'm': mismatched C++ versions.
Current "201402" module version "201703"`.
```

Derleyici Ayrıca, dosya üzerinde oynanmış her seferinde C7536 de yükseltilir *`.ifc`* . Modül arabiriminin üstbilgisi, altındaki içeriklerin SHA2 karmasını içerir. İçeri aktarma işleminde, *`.ifc`* dosya karma hale getirilir ve üst bilgide belirtilen karmayla denetlenir. Bunlar eşleşmiyorsa, hata C7536 tetiklenir:

```Output
error C7536: ifc failed integrity checks.
Expected SHA2: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'
```

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Diğer adlar ve çıkarılamayan bağlamlarla ilgili Kısmi sıralama

Çıkarılamayan bağlamlardaki diğer adları içeren kısmi sıralama kurallarında uygulamalar birbirinden ayrılan uygulamalardır. Aşağıdaki örnekte, GCC ve Microsoft C++ derleyicisi ( [`/permissive-`](../build/reference/permissive-standards-conformance.md) modunda), Clang kodu kabul ettiğinde bir hata yükseltir.

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

Önceki örnekte C2668 yükseltilir:

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

Uygulama ayrılmış gösterimi, C++ standart ifadesi içindeki bir gerileme nedeniyle oluşur. Çekirdek soruna çözüm 2235, bu aşırı yüklemelerin sıralanabilmesi için bazı metinlerin kaldırılmasını sağlar. Geçerli C++ standardı, bu işlevleri kısmen sıralamak için belirsiz olarak kabul edilmeyen bir mekanizma sağlamaz.

Geçici bir çözüm olarak, bu sorunu çözmek için kısmi sıralamaya güvenmemelisiniz. Bunun yerine, belirli aşırı yüklemeleri kaldırmak için SFıNAE kullanın. Aşağıdaki örnekte, `IsA` öğesinin bir özelleştirmesi olduğunda ilk tekrar yüklemeyi kaldırmak için bir yardımcı sınıfı kullanıyoruz `Alloc` `A` :

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

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>Şablonlu işlev tanımlarında geçersiz ifadeler ve değişmez değer olmayan türler

Geçersiz ifadeler ve sabit olmayan türler artık açıkça özelleştirilmiş şablonlu işlevlerin tanımlarında doğru bir şekilde tanılanıyor. Daha önce, bu tür hatalar işlev tanımı için yayılmadı. Ancak, sabit bir ifadenin bir parçası olarak değerlendiriliyorsa geçersiz ifade veya değişmez değer olmayan tür yine de tanılanıyor.

Visual Studio 'nun önceki sürümlerinde, aşağıdaki kod uyarı vermeden derlenir:

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

Visual Studio 2017 sürüm 15,9 ' de, kod bu hatayı oluşturur:

```Output
error C3615: constexpr function 'S<int>::f' cannot result in a constant expression.
note: failure was caused by call of undefined function or one not declared 'constexpr'
note: see usage of 'g'.
```

Hatayı önlemek için, **`constexpr`** niteleyiciyi işlevin açık örneklemesi ' nden kaldırın `f()` .

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft C++ dil uygunluğu tablosu](visual-cpp-language-conformance.md)
