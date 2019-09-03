---
title: C++uyumluluk geliştirmeleri
ms.date: 08/30/2019
description: Visual C++ Studio 'da Microsoft, c++ 20 dil standardı ile tam uygunluğu doğru ilerliyor.
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: aeaaab704706bee575e3ae44726522cd04c17433
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222308"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Visual Studio 2017’deki C++ uyumluluk geliştirmeleri

Microsoft C++ , her yayında uygunluk geliştirmeleri ve hata düzeltmeleri yapar. Bu makalede, ana sürüme ve ardından sürüme göre iyileştirmeler listelenmektedir. Ayrıca, sürüme göre önemli hata düzeltmelerini de listeler. Belirli bir sürümdeki değişikliklere doğrudan geçmek için **Bu makale** listesinde öğesini kullanın.

::: moniker range="vs-2019"

## <a name="improvements_160"></a>Visual Studio 2019 RTW (sürüm 16,0) ile uyumluluk geliştirmeleri

Visual Studio 2019 RTW, Microsoft C++ derleyicisindeki aşağıdaki uygunluk geliştirmelerini, hata düzeltmelerini ve davranış değişikliklerini IÇERIR (MSVC)

**Not:** C++ 20 uygulamasının her ikisi de derleyici ve `/std:c++latest` IntelliSense için, c++ 20 uygulama tamamlanana kadar modunda kullanılabilir hale getirilir. Bu sırada, `/std:c++20` derleyici modu tanıtılacaktır.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modüller desteği

Modüller artık C++ 20 standardında resmi olarak bulunur. Visual Studio 2017 sürüm 15,9 ' ye geliştirilmiş destek eklenmiştir. Daha fazla bilgi için bkz. [MSVC 2017 sürüm 15,9 C++ Ile modüllerde daha iyi şablon desteği ve hata algılama](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Toplu türün değiştirilmiş belirtimi

C++ 20 ' de bir toplama türünün belirtimi değişmiştir (bkz. [Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla](https://wg21.link/p1008r1)). Visual Studio 2019 ' de, `/std:c++latest`altında, Kullanıcı tarafından tanımlanmış bir oluşturucuya sahip bir sınıf (örneğin, bir `= default` Oluşturucu veya `= delete`) bir toplama değildir. Daha önce, yalnızca Kullanıcı tarafından sunulan oluşturucular bir sınıfın bir toplama olmasını eledi. Bu değişiklik, bu tür türlerin nasıl başlatıladığıyla ilgili ek kısıtlamalar getirir.

Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak şu Visual Studio 2019 `/std:c++latest`' de C2280 ve C2440 hataları oluşturur:

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>İçin kısmi destek`operator <=>`

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C++ 20, " `<=>` Spaceship işleci" olarak da bilinen üç yönlü karşılaştırma işlecini tanıtır. Visual Studio 2019 `/std:c++latest` , artık izin verilmeyen sözdizimi için hataları yükselterek operatör için kısmi destek sunar. Örneğin, aşağıdaki kod Visual Studio 2017 hatası olmadan derlenir, ancak altında `/std:c++latest`Visual Studio 2019 ' de birden çok hata oluşturuyor:

```cpp
struct S
{
    bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };

int main(int argc, char** argv)
{
    U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

Hataları önlemek için, son açı ayracından önce sorunlu satıra bir boşluk ekleyin: `U<&S::operator<= > u;`.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Eşleşmeyen CV niteleyicileri olan türlere başvurular

Daha önce, MSVC, en üst düzeyin altında eşleşmeyen CV niteleyicilerine sahip bir türden başvurunun doğrudan bağlamasını izin verilir. Bu bağlama, başvuruya göre başvuruda bulunulan düzgün const verileri değişikliğine izin verebilir. Derleyici artık standart tarafından gerekli olduğu gibi geçici bir durum oluşturur. Visual Studio 2017 ' de, aşağıdaki kod uyarılar olmadan derlenir. Visual Studio 2019 ' de, derleyici *Uyarı C4172: \<Func: #1PData@X "? @@QBEABQBXXZ"> yerel değişkenin adresini veya geçici durumunu döndürüyor*.

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```

### <a name="reinterpret_cast-from-an-overloaded-function"></a>`reinterpret_cast`aşırı yüklenmiş bir işlevden

İçin `reinterpret_cast` bağımsız değişken, aşırı yüklenmiş bir işlevin adresine izin verilen bağlamların değil. Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019 C2440 tarafından yükseltilir *: ' aşırı yüklenmiş-işlev ' iken ' FP ' olarak dönüştürülemez*:

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

Hatayı önlemek için, bu senaryo için izin verilen bir dönüştürme kullanın:

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>Lambda kapanışları

C++ 14 ' te lambda kapatma türleri değişmez değer değildir. Bu kuralın birincil sonucu bir Lambda `constexpr` değişkenine atanmayabilir. Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019 *C2127: ' l ': sabit olmayan bir ifadeyle ' constexpr ' varlığının geçersiz şekilde başlatılması*:

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Hatayı önlemek için, `constexpr` niteleyiciyi kaldırın ya da uyumluluk modunu olarak `/std:c++17`değiştirin.

### <a name="stdcreate_directory-failure-codes"></a>`std::create_directory`hata kodları

C++ 20 ' den koşullu [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) uygulandı. Bu, `std::create_directory` hedefin hata durumunda zaten bir dizin olup olmadığını denetlemek için değişir. Daha önce tüm ERROR_ALREADY_EXISTS tür hataları başarılı oldu-ancak Dizin oluşturulmamış kodlara açıldı.

### `operator<<(std::ostream, nullptr_t)`

Her [LWG 2221](https://cplusplus.github.io/LWG/issue2221)için, `operator<<(std::ostream, nullptr_t)` akışlara nullptrs yazmak için eklenmiştir.

### <a name="additional-parallel-algorithms"></a>Ek paralel algoritmalar

`is_sorted` ,`is_sorted_until` ,,`is_heap_until`,, Ve ' nin yeni paralel sürümleri. `is_partitioned` `set_difference` `set_intersection` `is_heap`

### <a name="atomic-initialization"></a>Atomik başlatma

[P0883 "atomik başlatma düzeltme"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) `std::atomic` değeri değeri, varsayılan olarak başlatmak yerine içerilen T 'yi başlatın. Microsoft standart kitaplığı ile Clang/LLVM kullanılırken bu çözüm etkinleştirilir. Şu anda Microsoft C++ derleyicisi için, `constexpr` işlemekte olan bir hata için geçici bir çözüm olarak devre dışı bırakılmıştır.

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` ve `remove_cvref_t`

`remove_cvref_t` [P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)öğesinden ve tür nitelikleri uygulandı `remove_cvref` . Bunlar, bir türden başvuru ve CV nitelemesini kaldırma işlevleri ve diziler (ve ' `std::decay` `std::decay_t`nin aksine) olmadan bir türden kaldırır.

### <a name="feature-test-macros"></a>Özellik testi makroları

[P0941R2-Feature-test makroları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) , desteğiyle `__has_cpp_attribute`birlikte tamamlanmıştır. Özellik testi makroları tüm standart modlarda desteklenir.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla

[C++ 20 P1008R1-Kullanıcı tarafından belirtilen oluşturucularla proyaları toplamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) tamamlanmıştır.

## <a name="improvements_161"></a>16,1 sürümündeki uyumluluk geliştirmeleri

### <a name="char8_t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C++ 20, UTF-8 kod birimlerini temsil etmek için kullanılan yeni bir karakter türü ekler. `u8`c++ 20 `const char8_t[N]` ' deki dize sabit değerleri, yerine `const char[N]`, daha önce gelen bir durumdur. [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm)içinde C standardı için benzer değişiklikler önerilir. Geriye dönük `char8_t` uyumluluk düzeltme için öneriler [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html)içinde verilmiştir. Microsoft C++ derleyicisi, `char8_t` **/Zc: char8_t** derleyici seçeneğini belirttiğinizde Visual Studio 2019 sürüm 16,1 ' ye yönelik destek ekler. Gelecekte, [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)ile desteklenecek ve **/Zc: Char8_t-** aracılığıyla c++ 17 davranışına geri döndürülecektir. IntelliSense 'i destekleyen EDG derleyicisi henüz desteklemez, bu nedenle yalnızca gerçek derlemeyi etkilemeden yalnızca IntelliSense 'e sahip olan hataları görürsünüz.

#### <a name="example"></a>Örnek

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>std:: type_identity programlayıcılarına ve std:: Identity işlevi nesnesi

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). Kullanım dışı `std::identity` bırakılan sınıf şablonu uzantısı kaldırılmıştır ve c++ 20 `std::type_identity` programlayıcılarına ve `std::identity` Function nesnesiyle değiştirilmiştir. Her ikisi de yalnızca [/std: c + + en son](../build/reference/std-specify-language-standard-version.md)altında kullanılabilir.

Aşağıdaki örnek, Visual Studio 2017 ' de için `std::identity` kullanımdan kaldırma Uyarısı \<C4996 (type_traits > içinde tanımlanmıştır) üretir:

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

Aşağıdaki örnek, New `std::identity` (işlevsel > 'de \<tanımlanır `std::type_identity`) ile birlikte yeni bir nasıl kullanılacağını gösterir:

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Genel Lambdalar için söz dizimi denetimleri

Yeni lambda işlemcisi, [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) altında veya **/deneysel: newLambdaProcessor**ile herhangi bir dil modu altında genel Lambdalar içinde bazı uyumluluk modu sözdizimsel denetimleri sunar.

Visual Studio 2017 ' de, bu kod uyarı olmadan derlenir, ancak Visual Studio 2019 içinde hata *C2760 sözdizimi hatası oluştu: beklenmeyen belirteç '\<id-Expr > ', beklenen ' ID-Expression '* :

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

Aşağıdaki örnek, artık derleyici tarafından zorlanan doğru söz dizimini göstermektedir:

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>İşlev çağrıları için bağımsız değişkene bağlı arama

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html) (C++ 20) Açık şablon bağımsız değişkenleriyle işlev çağrısı ifadeleri için bağımsız değişkene bağlı arama aracılığıyla işlev şablonlarını bulma özelliği arttı. **/Std: c + + en son**gerektirir.

### <a name="designated-initialization"></a>Belirlenmiş başlatma

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf) (C++ 20) Belirlenen başlatma, `Type t { .member = expr }` söz dizimi kullanılarak toplu başlatma işleminde belirli üyelerin seçili olmasına izin verir. **/Std: c + + en son**gerektirir.

### <a name="new-and-updated-standard-library-functions-c20"></a>Yeni ve güncelleştirilmiş standart kitaplık işlevleri (C++ 20)

- `starts_with()`ve `ends_with()` `basic_string` için. `basic_string_view`
- İlişkili kapsayıcılar için `contains()`.
- `list` ve `forward_list` için `remove()`, `remove_if()` ve `unique()` artık `size_type` değerini döndürüyor.
- `shift_left()`ve `shift_right()` > \<algoritmasına eklenmiştir.


## <a name="improvements_162"></a>16,2 sürümündeki uyumluluk geliştirmeleri

### <a name="noexcept-constexpr-functions"></a>noexcept constexpr işlevleri

Constexpr işlevleri, sabit bir ifadede `noexcept` kullanıldığında artık varsayılan olarak değerlendirilmez. Bu davranış değişikliği [CWG 1351](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html#1351) çözünürlükten gelir ve [/Permissive-](../build/reference/permissive-standards-conformance.md)' de etkinleştirilmiştir. Aşağıdaki örnek Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' te C2338 üretir:

```cpp
constexpr int f() { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept"); // C2338 in 16.2
}
```

Hatayı onarmak için `noexcept` ifadeyi işlev bildirimine ekleyin:

```cpp
constexpr int f() noexcept { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept");
}
```

### <a name="binary-expressions-with-different-enum-types"></a>Farklı enum türlerine sahip ikili ifadeler

Tek bir numaralandırma türü olan ve diğeri farklı bir numaralandırma türü olan ve diğer bir kayan nokta türünde olan işlenenler üzerinde her zamanki aritmetik dönüştürmeleri uygulama özelliği C++ 20 ' de ([P1120R0](http://wg21.link/p1120r0)) kullanım dışıdır. Visual Studio 2019 sürüm 16,2 ve sonraki sürümlerde, [/std: c + + latest](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkin olduğunda aşağıdaki kod bir düzey 4 uyarısı üretir:

```cpp
enum E1 { a };
enum E2 { b };
int main() {
    int i = a | b; // warning C5054: operator '|': deprecated between enumerations of different types
}
```

Uyarıyı önlemek için, ikinci işleneni dönüştürmek üzere [static_cast](../cpp/static-cast-operator.md) kullanın:

```cpp
enum E1 { a };
enum E2 { b };
int main() {
  int i = a | static_cast<int>(b);
}
```

### <a name="binary-expressions-with-enumeration-and-floating-point-types"></a>Numaralandırma ve kayan nokta türleri ile ikili ifadeler

Tek bir numaralandırma türü olan ve diğeri farklı bir numaralandırma türü olan ve diğer bir kayan nokta türünde olan işlenenler üzerinde her zamanki aritmetik dönüştürmeleri uygulama özelliği C++ 20 ' de ([P1120R0](http://wg21.link/p1120r0)) kullanım dışıdır. Diğer bir deyişle, bir numaralandırma ve kayan nokta türü arasındaki ikili bir işlemin kullanılması artık [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkin olduğunda bir uyarıdır:

```cpp
enum E1 { a };
int main() {
  double i = a * 1.1;
}
```

Uyarıyı önlemek için, ikinci işleneni dönüştürmek üzere [static_cast](../cpp/static-cast-operator.md) kullanın:

```cpp
enum E1 { a };
int main() {
   double i = static_cast<int>(a) * 1.1;
}
```

### <a name="equality-and-relational-comparisons-of-arrays"></a>Dizilerin eşitlik ve ilişkisel karşılaştırmaları

Dizi türünün iki işleneni arasındaki eşitlik ve ilişkisel karşılaştırmalar, C++ 20 ' de ([P1120R0](http://wg21.link/p1120r0)) kullanım dışıdır. Diğer bir deyişle, iki dizi arasındaki karşılaştırma işlemi (derecelendirmeden ve ölçüde benzerlikleri ne olursa olsun) artık bir uyarıdır. Visual Studio 2019 sürüm 16,2 ' den başlayarak, aşağıdaki kod *C5056: operator ' = = ':* [/std: c + + latest](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkin olduğunda dizi türleri için kullanım dışı bırakıldı:

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (a == b) { return 1; }
}
```

Uyarıyı önlemek için, ilk öğelerin adreslerini karşılaştırabilirsiniz:

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (&a[0] == &b[0]) { return 1; }
}
```

İki dizinin içeriğinin eşit olup olmadığını anlamak için [std:: eşittir](../standard-library/algorithm-functions.md#equal) işlevini kullanın:

```cpp
std::equal(std::begin(a), std::end(a), std::begin(b), std::end(b));
```

### <a name="effect-of-defining-spaceship-operator-on--and-"></a>= = Ve! = üzerinde Spaceship işlecinin tanımlanmasıyla ilgili efekt

Spaceship **<=>** işlecinin () tek başına bir tanımı, Spaceship işleci ([P1185R2](https://wg21.link/p1185r2)) olarak `= default` işaretlenmedikçe yalnızca veya **! =** içeren **==** ifadeleri yeniden yazmayacaktır. Aşağıdaki örnek Visual Studio 2019 RTW ve sürüm 16,1 ' de derlenir, ancak Visual Studio 2019 sürüm 16,2 ' te C2678 üretir:

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Hatayı önlemek için = = işlecini tanımlayın veya varsayılan olarak bildirin:

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
  bool operator==(const S&) const = default;
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

### <a name="standard-library-improvements"></a>Standart Kitaplık geliştirmeleri

- \<charconv, `to_chars()` fixed/bilimsel duyarlıkla >. (Genel duyarlık Şu anda 16,4 için planlanmaktadır.)
- [P0020R6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0020r6.html): atomik\<float >, atomik\<çift >, atomik\<uzun çift >
- [P0463R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html): endian
- [P0482R6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html): Char8_t Için kitaplık desteği
- [P0600R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0600r1.pdf): [\[noDiscard]] STL, Bölüm 1
- [P0653R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html): to_address ()
- [P0754R2](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0754r2.pdf): \<sürüm >
- [P0771R1](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0771r1.pdf): noexcept std:: işlevin taşıma Oluşturucusu

## <a name="update_160"></a>Visual Studio 2019 'de hata düzeltmeleri ve davranış değişiklikleri

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>Basic_string Range Oluşturucusu için doğru tanılama

Visual Studio 2019 ' `basic_string` de Aralık Oluşturucusu artık ile `static_cast`derleyici tanılamayı göstermez. Aşağıdaki kod, Visual Studio 2017 ' de uyarılar olmadan derlenir ve bu, başlatma `wchar_t` `char` `out`sırasında veri kaybına neden olabilir:

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 doğru *C4244: ' bağımsız değişken ': ' wchar_t ' değerinden ' const _Eled ' türüne dönüştürme, olası veri kaybı*. Uyarıyı önlemek için std:: String öğesini şu örnekte gösterildiği gibi başlatabilirsiniz:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>/Clr veya/ZW altındaki + = ve-= için yanlış çağrılar artık doğru bir şekilde algılandı

Visual Studio 2017 ' de bir hata ortaya çıkarılmıştır ve derleyicinin hataları sessizce yoksaymasına ve + = ve-= altında `/clr` `/ZW`geçersiz çağrılar için kod üretmesinin nedeni. Aşağıdaki kod Visual Studio 2017 ' de hata olmadan derlenir ancak Visual Studio 2019, C2845 hatasını doğru *şekilde oluşturuyor: ' System:: String ^ ': işaretçi aritmetiğinin bu tür*üzerinde yapılmasına izin verilmiyor:

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Bu örnekteki hatayı önlemek için, işleci ToString () yöntemiyle birlikte kullanın: `s += E::e.ToString();`.

### <a name="initializers-for-inline-static-data-members"></a>Satır içi statik veri üyeleri için başlatıcılar

`inline` Ve`static constexpr` başlatıcıların içindeki geçersiz üye erişimleri artık doğru şekilde algılandı. Aşağıdaki örnek, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019 `/std:c++17` ' de modda *hata C2248: ' X ' sınıfında belirtilen özel üyeye erişilemiyor*.

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

Hatayı önlemek için üyeyi `X::c` korumalı olarak bildirin:

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>C4800 tekrar belirtilmiş

MSVC, öğesine `bool`örtük dönüştürme hakkında bir performans uyarısı C4800 sağlamak için kullanılır. Bu çok gürültülü ve gizlenemedi, bu da Visual Studio 2017 ' de kaldırılması için önde gelir. Bununla birlikte, Visual Studio 2017 yaşam döngüsünün üzerinde çöztiğimiz yararlı durumlar hakkında çok fazla geri bildirim sunuyoruz. Açıklayıcı C4165 ile birlikte Visual Studio 2019 ' ye dikkatlice uyarlanmış bir C4800 geri getiriyoruz. Bu uyarıların her ikisi de açık bir atama ile kolayca gizlenebilir veya uygun türden 0 ' a karşılaştırma yapılabilir. C4800, varsayılan olarak 4. düzey bir uyarıdır ve C4165, varsayılan olarak 1. düzey 3 uyarıdır. Her ikisi de `/Wall` derleyici seçeneği kullanılarak bulunabilir.

Aşağıdaki örnek, altında `/Wall`C4800 ve C4165 ' i yükseltir:

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

Önceki örnekteki uyarılardan kaçınmak için şu şekilde kodu yazabilirsiniz:

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>Yerel sınıf üye işlevinin gövdesi yok

Visual Studio 2017, *C4822: Yerel sınıf üye işlevinin gövdesi* yok ancak derleyici seçeneği `/w14822` açıkça ayarlandığında tetiklenir; ile `/Wall`gösterilmez. Visual Studio 2019 ' de C4822, bu, açık bir uyarıdır. Bu, açıkça ayarlanması `/Wall` `/w14822` gerekmeden altında bulunabilir hale gelir.

```cpp
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>Constexpr if deyimleri içeren işlev şablonu gövdeleri

Deyimleri içeren `if constexpr` şablon işlevi gövdelerinin ayrıştırılmasındaki bazı `/permissive-` denetimler var. Örneğin, Visual Studio 2017 ' de aşağıdaki kod C*7510 ' yi üretir: ' Type ': bağımlı tür adının kullanımı,* `/permissive-` yalnızca seçenek ayarlanmamışsa ' TypeName ' öneki olmalıdır. Visual Studio 2019 ' de, `/permissive-` seçenek ayarlandığında de aynı kod hata oluşturuyor:

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}
```

Hatayı önlemek için, ' `typename` `typename T::Type a;`ın `a`bildirimine anahtar sözcüğünü ekleyin.

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Bir lambda ifadesinde satır içi derleme kodu desteklenmez

Görsel C++ ekip kısa süre önce bir lambda içinde satır içi assembler kullanmanın, çalışma zamanında `ebp` (dönüş Adres kaydı) bozulmasıyla sonuçlanabildiğine yönelik bir güvenlik sorununu bilmiştir. Kötü amaçlı bir saldırgan bu senaryodan faydalanabilir. Sorunun doğası gereği, satır içi derleyicisinin yalnızca x86 'da desteklendiği ve satır içi assembler ve derleyicinin geri kalanı arasındaki kötü etkileşim nedeniyle bu sorunun en güvenli çözümü, bir lambda ifadesinde satır içi derleyicisine izin vermemelidir.

"Joker karakter" bulduğumuz bir lambda ifadesi içinde satır içi assembler 'nun tek kullanımı dönüş adresini yakalamıştı. Bu senaryoda, yalnızca bir derleyici iç `_ReturnAddress()`öğesini kullanarak dönüş adresini tüm platformlarda yakalayabilirsiniz.

Aşağıdaki kod C7552 üretir *: satır içi assembler* hem visual studio 2017 15,9 hem de visual Studio 2019 içinde bir lambda içinde desteklenmez:

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

Hatayı önlemek için, aşağıdaki örnekte gösterildiği gibi, derleme kodunu adlandırılmış bir işleve taşıyın:

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmove_iterator"></a>Yineleyici hata ayıklama ve`std::move_iterator`

Yineleyici hata ayıklama özelliği, düzgün bir şekilde sarmalanmadan `std::move_iterator`daha uygun hale getiriliyor. Örneğin, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` artık `memcpy` hızlı yolu kullanabilir.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>\<Xkeycheck. h > anahtar sözcük zorlaması düzeltmeleri

Standart Kitaplık makrosu, bir genel ileti yerine algılanan \<gerçek sorunlu anahtar sözcüğü göstermek için, bir anahtar sözcük zorlama xkeycheck. h > değiştirme. Ayrıca C++ 20 anahtar sözcüklerini destekler ve IntelliSense 'in rastgele anahtar sözcüklerin makroları olduğunu söylenmesini önler.

### <a name="allocator-types-no-longer-deprecated"></a>Ayırıcı türleri artık kullanım dışı

`std::allocator<void>`, `std::allocator::size_type` ve`std::allocator::difference_type` artık kullanım dışıdır.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Daraltma dizesi dönüştürmeleri için doğru uyarı

Yanlışlıkla gizlenen C4244 daraltma `static_cast` uyarılarını `std::string`kaldırılan standart tarafından bir spurmerak yok. Çağırma `std::string::string(const wchar_t*, const wchar_t*)` girişimi artık *C4244 "bir wchar_t 'yi bir Char 'a daraltma* " olarak doğru olarak yayacaktır.

### <a name="various-filesystem-correctness-fixes"></a>Çeşitli \<FileSystem > doğruluk düzeltmeleri

- Dizinin `std::filesystem::last_write_time` son yazma zamanı değiştirilmeye çalışılırken hata düzeltildi.
- `std::filesystem::directory_entry` Oluşturucu artık varolmayan bir hedef yolu sağlandığı zaman bir özel durum oluşturmak yerine başarısız bir sonucu depolar.
- 2 parametreli sürüm, 1 parametreli sürümü çağırmak üzere değiştirilmiştir ve temel `CreateDirectoryExW` alınan `existing_p` işlev bir symlink olduğunda kullanılır `copy_symlink`. `std::filesystem::create_directory`
- `std::filesystem::directory_iterator`bozuk bir oluşturmaksızın bulunduğunda artık başarısız olmaz.
- `std::filesystem::space`Artık göreli yolları kabul eder.
- `std::filesystem::path::lexically_relative`, [LWG 3096](https://cplusplus.github.io/LWG/issue3096)olarak bildirilen eğik çizgiler tarafından artık karıştırılmamalıdır.
- `CreateSymbolicLinkW` İçindeki`std::filesystem::create_symlink`eğik çizgi ile yolları reddetme
- Windows 10 LTSB 1609 `delete` ' de var olan, ancak dosyaları silebilecek olan POSIX silme modu işlevine geçici bir çözüm olarak çalışmıştır.
- `std::boyer_moore_searcher`ve `std::boyer_moore_horspool_searcher`kopya oluşturucuları ve kopya atama işleçleri artık aslında öğeleri kopyalayamıyorum.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 ve sonraki sürümlerde paralel algoritmalar

Paralel algoritmalar kitaplığı artık Windows 7 ve önceki sahte `WaitOnAddress` sürümlerini kullanmak yerine gerçek aileyi Windows 8 ve üzeri sürümlerde kullanır.

### <a name="stdsystem_categorymessage-whitespace"></a>`std::system_category::message()`boşlu

`std::system_category::message()`Şimdi döndürülen iletiden sondaki boşluğu kırpar.

### <a name="stdlinear_congruential_engine-divide-by-zero"></a>`std::linear_congruential_engine`sıfıra Böl

Tetikleyici 0 olarak bölünmeye `std::linear_congruential_engine` neden olabilecek bazı koşullar düzeltildi.

### <a name="fixes-for-iterator-unwrapping"></a>Yineleyici geri sarma düzeltmeleri

C++ Team Blog makalesi [STL özellikleri ve 15,8 2017 düzeltmeleri](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/)için Visual Studio 2017 15,8 ' de açıklandığı gibi, Visual Studio ' de birinci kez programcı-Kullanıcı tümleştirmesi için kullanıma sunulan Yineleyici, daha önce standart 'dan türetilen yineleyiciler tarafından geri sarılamaz Kitaplık yineleyiciler. Örneğin, öğesinden `std::vector<int>::iterator` türetilen ve özelleştirmeyi denemeyen bir Kullanıcı artık işaretçi davranışı yerine standart kitaplık algoritmalarını çağırırken özelleştirilmiş davranışlarını alıyor.

Sıralanmamış kapsayıcı `reserve` işlevi artık, [LWG 2156](https://cplusplus.github.io/LWG/issue2156)' de açıklandığı gibi N öğeleri için ayrılmış durumda.

### <a name="time-handling"></a>Zaman işleme

- Daha önce, eşzamanlılık kitaplığına geçirilen bazı zaman değerleri, örneğin, `condition_variable::wait_for(seconds::max())`. Şimdi düzeltildi, rastgele 29 günlük bir döngüde (altta yatan Win32 API 'Leri tarafından kabul edilen uint32_t milisaniyesi taştı) değiştirilen taşma

- Üst bilgi, genel ad `timespec` alanında bunları bildirmek `std` için ayrıca ad alanını doğru şekilde bildirir ve `timespec_get` içinde. <ctime>

### <a name="various-fixes-for-containers"></a>Kapsayıcılar için çeşitli düzeltmeler

- Birçok standart kitaplık iç kapsayıcı işlevleri, geliştirilmiş bir IntelliSense deneyimi için özel yapılmıştır. MSVC 'in sonraki sürümlerinde üyeleri özel olarak işaretlemek için ek düzeltmeler beklenmektedir.

- , `list` `map`Ve gibidüğümtabanlıkapsayıcılardakibozukhalegelebileceğiözeldurumgüvenliğidoğruluksorunlarıdüzeltildi.`unordered_map` `propagate_on_container_copy_assignment` Veya`propagate_on_container_move_assignment` yeniden atama işlemi sırasında, kapsayıcının Sentinel düğümünü eski ayırıcıyla boşalttık, eski ayırıcı üzerinde pocca/pocma atamasını yapar ve ardından yeni ayırıcıdan Sentinel düğümünü edinmeye çalışırsınız. Bu ayırma başarısız olduysa, kapsayıcı bozulur ve bir Sentinel düğümü sabit veri yapısı sabiti olduğu için bile yok edilmez. Bu kod, mevcut Sentinel düğümünü yok etmeden önce, kaynak kapsayıcısının ayırıcısından yeni Sentinel düğümünü ayırmak için düzeltildi.

- Kapsayıcılar, belirtilen `propagate_on_container_copy_assignment` `propagate_on_container_swap` `propagate_on_container_move_assignment` ayrıcılar`is_always_equal`için bile, ve ' a göre ayırıcıları her zaman kopyalamak/taşımak/değiştirmek için düzeltildi.

- Kapsayıcı birleştirme için aşırı yüklemeler eklendi ve P0083 başına rvalue kapsayıcıları kabul eden üye işlevleri Ayıkla [ve kümeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) "

### <a name="stdbasic_istreamread-processing-of-rn--n"></a>`std::basic_istream::read`r n işleme = > \\n \\\\

`std::basic_istream::read`, r \\\\n = > \\n işleme parçası olarak, sağlanan arabelleğin bölümlerine geçici olarak yazılmadığından düzeltildi. Bu değişiklik, Visual Studio 2017 15,8 ' de en fazla 4K boyutunda daha büyük okumalar için kazanılan performans avantajlarından bazılarını sağlar. Bununla birlikte, karakter başına üç sanal çağrının önünden kaçınmanın verimlilik geliştirmeleri hala mevcuttur.

### <a name="stdbitset-constructor"></a>`std::bitset`constructor

`std::bitset` Oluşturucu artık büyük bit kümelerine ait olanları ve sıfırları ters sırayla okumamaktadır.

### <a name="stdpairoperator-regression"></a>`std::pair::operator=`regresyon

Bir gerileme, `std::pair` [LWG 2729 "eksik sfinae: std::p AIR:: operator =";](https://cplusplus.github.io/LWG/issue2729) Artık, ' a dönüştürülebilir `std::pair` türleri doğru şekilde kabul eder.

### <a name="non-deduced-contexts-for-add_const_t"></a>İçin çıkarılamayan bağlamlar`add_const_t`

Küçük tür nitelikleri hatası düzeltildi, burada `add_const_t` ve ilgili işlevlerin çıkarılamayan bir bağlam olması gerekir. Diğer bir deyişle `add_const_t` , için `typename add_const<T>::type` `const T`bir diğer ad olmalıdır.

## <a name="update_162"></a>16,2 sürümündeki hata düzeltmeleri ve davranış değişiklikleri

### <a name="const-comparators-for-associative-containers"></a>İlişkilendirilebilir kapsayıcılar için const Karşılaştırıcılar

[Küme](../standard-library/set-class.md), [eşleme](../standard-library/map-class.md), [Çoklu küme](../standard-library/multiset-class.md)ve [multimap](../standard-library/multimap-class.md) 'teki arama ve ekleme için kod, daha az kod boyutu için birleştirildi. Ekleme işlemleri artık, arama işlemlerinin daha önce yapıldığı şekilde, `const` bir karşılaştırma funından daha az karşılaştırmayı çağırır. Aşağıdaki kod, Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' C3848 yükseltir:

```cpp
#include <iostream>
#include <map>

using namespace std;

struct K
{
   int a;
   string b = "label";
};

struct Comparer  {
   bool operator() (K a, K b) {
      return a.a < b.a;
   }
};

map<K, double, Comparer> m;

K const s1{1};
K const s2{2};
K const s3{3};

int main() {

   m.emplace(s1, 1.08);
   m.emplace(s2, 3.14);
   m.emplace(s3, 5.21);

}
```

Hatayı önlemek için karşılaştırma işlecini `const`yapın:

```cpp
struct Comparer  {
   bool operator() (K a, K b) const {
      return a.a < b.a;
   }
};

```

::: moniker-end

::: moniker range="vs-2017"

## <a name="improvements_150"></a>Visual Studio 2017 RTW (sürüm 15,0) ile uyumluluk geliştirmeleri

Toplamalarda Genelleştirilmiş `constexpr` ve statik olmayan veri üyesi başlatma (nsdmı) desteğiyle, Visual Studio 2017 ' deki C++ Microsoft derleyicisi artık c++ 14 standardına eklenen özellikler için tamamlanmıştır. Ancak, derleyicinin yine de C++ 11 ve C++ 98 standartlarından birkaç özelliği yoktur. Derleyicinin geçerli durumunu gösteren bir tablo için bkz. [ C++ görsel dil uyumluluğu](../visual-cpp-language-conformance.md) .

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++ 11: Daha fazla kitaplıklarda ifade SFıNAE desteği

Derleyici, şablon bağımsız değişkeni olarak, ve `decltype` `constexpr` ifadelerinin şablon parametreleri olarak görünebileceği konum ve değiştirme için gerekli olan sfinae ifadesi için desteğini iyileştirmeye devam etmektedir. Daha fazla bilgi için bkz. [Visual Studio 2017 RC 'de Expression SFINAE geliştirmeleri](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

### <a name="c14-nsdmi-for-aggregates"></a>C++ 14: Toplamalar için NSDMı

Toplama, Kullanıcı tarafından sağlanmayan bir Oluşturucu olmayan, özel veya korumalı olmayan veri üyeleri olmayan, temel sınıf olmayan ve sanal işlevler içermeyen bir dizidir veya sınıftır. C++ 14 toplamalarda başlayarak üye başlatıcıları bulunabilir. Daha fazla bilgi için bkz. [üye başlatıcıları ve toplamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

### <a name="c14-extended-constexpr"></a>C++ 14: Genişletildiğinde`constexpr`

Olarak `constexpr` belirtilen ifadeler, bazı bildirim türlerini, if ve Switch deyimlerini, Loop deyimlerini ve yaşam sürelerini constexpr ifade değerlendirmesi içinde başlayan nesneler, döngü deyimleri ve mutasyonları içermesine izin verilir. Ayrıca, statik `constexpr` olmayan bir üye işlevin örtük `const`bir şekilde olması gerekmez. Daha fazla bilgi için bkz. [constexpr işlevleri üzerinde kısıtlamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)gevşme.

### <a name="c17-terse-static_assert"></a>C++ 17: Terse`static_assert`

için `static_assert` ileti parametresi isteğe bağlıdır. Daha fazla bilgi için bkz. [genişletme static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

### <a name="c17-fallthrough-attribute"></a>C++ 17: `[[fallthrough]]` özniteliği

**/Std: c++ 17** modunda, `[[fallthrough]]` öznitelik, anahtar deyimlerinin bağlamında, bir derleyicinin bir ipucu olarak, dönüş davranışının istendiği bir ipucu olarak kullanılabilir. Bu öznitelik, derleyicinin bu gibi durumlarda uyarı vermesini engeller. Daha fazla bilgi için bkz. [ \[fallthrough \[\] \] özniteliği için ifade](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

### <a name="generalized-range-based-for-loops"></a>For döngüleri için genelleştirilmiş Aralık tabanlı

Aralık tabanlı for döngüleri artık bunu gerektirmez `begin()` ve `end()` aynı türdeki nesneleri döndürmelidir. Bu değişiklik, `end()` [Range-v3](https://github.com/ericniebler/range-v3) içindeki aralıklar tarafından kullanılan bir Sentinel, ancak tam olarak yayımlanmış olmayan aralıklar teknik belirtiminde dönmesini sağlar. Daha fazla bilgi için bkz. [Aralık tabanlı for döngüsünü Genelleştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a>15,3 sürümündeki uyumluluk geliştirmeleri

### <a name="constexpr-lambdas"></a>constexpr lambdaları

Lambda ifadeleri artık sabit ifadelerde kullanılabilir. Daha fazla bilgi için, bkz. [' de C++constexpr lambda ifadeleri ](../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>`if constexpr`işlev şablonlarında

Bir işlev şablonu, derleme `if constexpr` zamanı dallanmayı etkinleştirmek için deyimler içerebilir. Daha fazla bilgi için bkz. [constexpr deyimleri](../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Başlatıcılarla seçim deyimleri

Bir `if` ifade, deyimin kendisi içindeki blok kapsamında bir değişken sunan bir başlatıcı içerebilir. Daha fazla bilgi için bkz. [Başlatıcı ile IF deyimleri](../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybe_unused-and-nodiscard-attributes"></a>`[[maybe_unused]]`ve `[[nodiscard]]` öznitelikleri

Bir varlık `[[maybe_unused]]` kullanılmazsa yeni öznitelik susturces uyarıları. `[[nodiscard]]` Öznitelik, bir işlev çağrısının dönüş değeri atıldığı takdirde bir uyarı oluşturur. Daha fazla bilgi için bkz. [Içindeki C++öznitelikler ](../cpp/attributes.md).

### <a name="using-attribute-namespaces-without-repetition"></a>Öznitelik ad alanlarını tekrarsız kullanma

Öznitelik listesinde yalnızca tek bir ad alanı tanımlayıcısını etkinleştirmek için yeni sözdizimi. Daha fazla bilgi için bkz. [Içindeki C++öznitelikler ](../cpp/attributes.md).

### <a name="structured-bindings"></a>Yapılandırılmış bağlamalar

Tek bir bildirimde, bir değeri bir dizi `std::tuple` , ya `std::pair`da veya tüm ortak statik olmayan veri üyelerine sahip olduğu durumlarda, bileşenleri için bağımsız adlarla bir değer depolamak için de mümkündür. Daha fazla bilgi için, bkz. [yapılandırılmış bağlamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) ve [bir işlevden birden çok değer döndürme](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Değerler için `enum class` yapım kuralları

Artık kapsamlı bir numaralandırmanın temel alınan türünden numaralandırmanın kendisine örtük/daraltılamayan bir dönüştürme, tanımı Numaralandırıcı olmadığında ve kaynak bir liste başlatma sözdizimi kullandığında. Daha fazla bilgi için bkz. [sabit listesi sınıfı değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) ve [numaralandırmalar](../cpp/enumerations-cpp.md#no_enumerators)için oluşturma kuralları.

### <a name="capturing-this-by-value"></a>Değere `*this` göre yakalama

Lambda `*this` ifadesindeki nesne artık değere göre yakalanamaz. Bu değişiklik, özellikle daha yeni makine mimarilerinde, lambda 'nin paralel ve zaman uyumsuz işlemlerde çağrıldığı senaryolara izin vermez. Daha fazla bilgi için bkz. [ \*bu değere \[göre Lambda yakalama değeri =,\*bu\]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html).

### <a name="removing-operator-for-bool"></a>İçin `operator++` kaldırılıyor`bool`

`operator++`türler üzerinde `bool` artık desteklenmez. Daha fazla bilgi için bkz. [kullanım dışı Işleci Kaldır + + (bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

### <a name="removing-deprecated-register-keyword"></a>Kullanım dışı `register` bırakılan anahtar sözcüğü kaldırılıyor

Daha önce kullanım dışı olan (ve derleyici tarafından yoksayılan) anahtarsözcüğüartıkdildenkaldırılmıştır.`register` Daha fazla bilgi için bkz. [register anahtar sözcüğünün kullanım dışı kullanımını kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

## <a name="improvements_155"></a>15,5 sürümündeki uyumluluk geliştirmeleri

14 ile \[işaretlenen özellikler, **/std: c++ 14** modunda bile koşullu olarak kullanılabilir.

### <a name="new-compiler-switch-for-extern-constexpr"></a>İçin yeni derleyici anahtarı`extern constexpr`

Visual Studio 'nun önceki sürümlerinde, derleyici her zaman değişken işaretlenmiş `constexpr` `extern`olsa bile iç bağlantı değişkeni verdi. Visual Studio 2017 sürüm 15,5 ' de yeni bir derleyici anahtarı olan [/Zc: externConstexpr](../build/reference/zc-externconstexpr.md), standartlara uygun doğru davranışı mümkün bir şekilde sunar. Daha fazla bilgi için bkz. [extern constexpr bağlantısı](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimleri kaldırılıyor

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) Dinamik özel durum belirtimleri C++ 11 ' de kullanımdan kaldırılmıştır. Özellik c++ 17 ' den kaldırılır, ancak (hala) kullanım dışı `throw()` olan belirtim tamamen bir `noexcept(true)`diğer ad olarak tutulur. Daha fazla bilgi için bkz. [dinamik özel durum belirtimi kaldırma ve noexcept](#noexcept_removal).

### `not_fn()`

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) , ve `not1` '`not2`ninyerinialır. `not_fn`

### <a name="rewording-enable_shared_from_this"></a>Yeniden ifade`enable_shared_from_this`

[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this` , c++ 11 ' ye eklenmiştir. C++ 17 standardı, belirli köşe durumlarını daha iyi işlemek için belirtimi güncelleştirir. [14]

### <a name="splicing-maps-and-sets"></a>Haritalar ve kümeler ile ayarlama

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) Bu `map`özellik, `set` `unordered_map` dahasonradeğiştirilebilecekveaynıkapsayıcıyaveyaaynıdüğümükullananfarklıbirkapsayıcıyaeklenebilenilişkilendirilebilirkapsayıcılardan(,,,,,,,,,)düğümlerinayıklanmasını`unordered_set`mümkün hale getirmenizi ister türüyle. (Yaygın kullanım örneği, bir düğümü bir `std::map`öğesinden ayıklamak, anahtarı değiştirmek ve yeniden eklemek için kullanılır.)

### <a name="deprecating-vestigial-library-parts"></a>Kalıntı kitaplık parçalarını kullanımdan kaldırma

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) C++ Standart kitaplığın birkaç özelliği, yıllar üzerinde yeni özelliklerden değiştirilmiştir veya başka bir yöntem bulunamadı veya sorunlu. Bu özellikler, C++ 17 ' de resmi kullanım dışı bırakılmıştır.

### <a name="removing-allocator-support-in-stdfunction"></a>İçindeki ayırıcı desteği kaldırılıyor`std::function`

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) C++ 17 ' den önce, Sınıf şablonunda `std::function` ayırıcı bağımsız değişkeni alan birkaç Oluşturucu vardı. Bununla birlikte, bu bağlamdaki ayırıcıların kullanımı sorunlu ve semantik anlaşılır değildi. Sorun bu sorundan kaldırılmıştır.

### <a name="fixes-for-not_fn"></a>İçin düzeltmeler`not_fn()`

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) İçin `std::not_fn` yeni ifade, sarmalayıcı çağrısında kullanıldığında değer kategorisinin yayılmasının desteğini sağlar.

### <a name="shared_ptrt-shared_ptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) Kitaplık `shared_ptr` temellerinde bulunan değişiklikleri c++ 17 ' ye birleştirme. [14]

### <a name="fixing-shared_ptr-for-arrays"></a>Diziler `shared_ptr` için düzeltme

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) Diziler için shared_ptr desteğini düzeltir. [14]

### <a name="clarifying-insert_return_type"></a>Netleştirerek`insert_return_type`

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) Benzersiz anahtarlarla ilişkilendirilebilir kapsayıcılar ve benzersiz anahtarlarla birlikte sıralanmamış kapsayıcılar, iç içe bir tür `insert` `insert_return_type`döndüren bir üye işlevine sahiptir. Bu dönüş türü artık yineleyici ve kapsayıcının NodeType üzerinde parametreli olan bir türün özelleştirmesi olarak tanımlanmıştır.

### <a name="inline-variables-for-the-standard-library"></a>Standart Kitaplık için satır içi değişkenler

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>Ek D özellikleri kullanım dışı

Standart ek D,, ve `namespace std::tr1`dahil olmak üzere `shared_ptr::unique()` `<codecvt>`kullanım dışı bırakılan tüm özellikleri içerir. C++ **/Std: c++ 17** derleyici anahtarı ayarlandığında, ek D içindeki standart kitaplık özelliklerinin neredeyse tamamı kullanım dışı olarak işaretlenir. Daha fazla bilgi için bkz. [Ek D Içindeki standart kitaplık özellikleri kullanım dışı olarak işaretlendi](#annex_d).

' Deki `std::tr2::sys` `<experimental/filesystem>` ad alanı artık **/std: c++ 14** ' in altında varsayılan olarak kullanımdan kaldırma uyarısı yayar ve varsayılan olarak **/std: c++ 17** altında kaldırılır.

Standart olmayan bir `<iostream>` uzantıyı önleyerek ' de geliştirilmiş uyumluluk (sınıf içi açık uzmanlık).

Standart kitaplık artık değişken şablonları dahili olarak kullanmaktadır.

Standart Kitaplık, tür sistemine ekleme `noexcept` ve dinamik özel durum belirtimlerini kaldırma dahil olmak üzere c++ 17 derleyici değişikliklerine yanıt olarak güncelleştirilmiştir.

## <a name="improvements_156"></a>15,6 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-library-fundamentals-v1"></a>C++ 17 kitaplık temelleri v1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) c++ 17 Için kitaplık temelleri teknik belirtimini standart olarak içerir. Deneysel/tanımlama \<>, \<deneysel/isteğe bağlı >, \<deneysel/işlevsel >, \<deneysel/any >, \<deneysel/string_view > \<içingüncelleştirmeleriiçerirdeneysel/bellek >, \<deneysel/memory_resource > ve \<deneysel/algoritma >.

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++ 17: Standart Kitaplık için sınıf şablonu bağımsız değişken kesintiyi geliştirme

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html) `scoped_lock` Uygulamasının `adopt_lock_t` tutarlı`scoped_lock`kullanımını etkinleştirmek için için parametre listesinin önüne geçin. Oluşturucuyu `std::variant` kopyalama atamasını etkinleştirmek için, daha fazla durumda oluşturucunun aşırı yükleme çözümüne katılmasına izin verin.

## <a name="improvements_157"></a>15,7 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-rewording-inheriting-constructors"></a>C++ 17: Yeniden ifade devralan oluşturucular

[P0136R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html) bir oluşturucuyu isimlendiremeyen bir **using** bildirimi, ilgili temel sınıf oluşturucularının, ek türetilmiş sınıf oluşturucuları bildirmek yerine, türetilen sınıfın başlatmaları görünür hale getiriyor olduğunu belirtir. Bu reifade, C++ 14 ' ten bir değişiklik. Visual Studio 2017 sürüm 15,7 ve üzeri sürümlerde, **/std: c++ 17** modunda, c++ 14 ' te geçerli olan ve devralan oluşturucular kullanan kod geçerli olmayabilir veya farklı anlamlarına sahip olabilir.

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

Aşağıdaki örnekte, Visual Studio 15,7 ' de **/std: c++ 17** davranışı gösterilmektedir:

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

### <a name="c17-extended-aggregate-initialization"></a>C++ 17: Genişletilmiş toplu başlatma

[P0017R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)

Bir temel sınıfın Oluşturucusu genel olmayan, ancak türetilmiş bir sınıf tarafından erişilebilir değilse, **/std: c++ 17** modu altında, Visual Studio sürüm 15,7 ' de, türetilmiş türdeki bir nesneyi başlatmak için artık boş küme ayraçları kullanamazsınız.

Aşağıdaki örnek C++ 14 uyumlu davranışını gösterir:

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

C++ 17 ' `Derived` de artık bir toplam türü olarak kabul edilir. Bu, özel varsayılan Oluşturucu `Base` aracılığıyla başlatmanın, genişletilmiş toplama başlatma kuralının bir parçası olarak doğrudan gerçekleşir anlamına gelir. Daha önce, `Base` özel Oluşturucu `Derived` Oluşturucu aracılığıyla çağrılıydı ve arkadaş bildirimi nedeniyle başarılı oldu.

Aşağıdaki örnekte, **/std: c++ 17** modundaki Visual Studio sürüm 15,7 ' de c++ 17 davranışı gösterilmektedir:

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

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++ 17: Otomatik olarak tür olmayan şablon parametreleri bildirme

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

**/Std: c++ 17** modunda, derleyici artık **Otomatik**olarak belirtilen tür olmayan bir şablon bağımsız değişkeninin türünü verebilir:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Bu yeni özelliğin bir etkisi geçerli C++ 14 kodunun geçerli olmaması veya farklı anlambilime sahip olması olabilir. Örneğin, daha önce geçersiz olan bazı aşırı yüklemeler artık geçerlidir. Aşağıdaki örnek, ' a ' çağrısı `example(p)` `example(void*);`olduğu için derlenen c++ 14 kodunu gösterir. Visual Studio 2017 sürüm 15,7 ' de, **/std: c++ 17** modunda `example` , işlev şablonu en iyi eşleşmedir.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

Aşağıdaki örnekte, **/std: c++ 17** modunda Visual Studio 15,7 ' de c++ 17 kodu gösterilmektedir:

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

[P0067R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html) Tamsayılar ve dizeler arasında ve kayan noktalı sayılar ve dizeler arasındaki dönüşümler için alt düzey, yerel ayara bağımsız işlevler.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++ 20: Gereksiz Decay önleme (kısmi)

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf) "Decay" kavramı arasına farklılaşmayı ekler ve yalnızca const veya başvuru niteleyicilerini kaldırmaktır.  Yeni tür nitelik `remove_reference_t` bazı `decay_t` bağlamlarda yerini alır. `remove_cvref_t` Desteği Visual Studio 2019 ' de uygulanır.

### <a name="c17-parallel-algorithms"></a>C++ 17: Paralel algoritmalar

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html) Paralellik, küçük değişikliklerle standart olarak birleştirilir.

### <a name="c17-hypotx-y-z"></a>C++ 17:`hypot(x, y, z)`

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf) , Her biri üç giriş `std::hypot`parametresine sahip olan **float**, **Double**ve **Long Double**türleri için üç yeni aşırı yükleme ekler.

### <a name="c17-filesystem"></a>C++ 17: \<FileSystem >

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html) Birkaç ifade değişikliği ile dosya sistemini standart olarak benimseme.

### <a name="c17-mathematical-special-functions"></a>C++ 17: Matematik özel işlevleri

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) Matematik özel işlevleri için önceki teknik belirtimleri standart \<cmath > başlığına benimseme.

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++ 17: Standart Kitaplık için kesinti Kılavuzu

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html) STL 'ye güncelleştirme, sınıf şablonu bağımsız değişkeni için destek ekleyen [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)'in c++ 17 benimseme özelliğinden faydalanmak için.

### <a name="c17-repairing-elementary-string-conversions"></a>C++ 17: Elemensel dize dönüşümlerini onarma

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html) Yeni elemensel dize dönüştürme işlevlerini P0067R5 ' dan yeni bir üst bilgi \<charconv > taşıyın ve yerine `std::error_code`kullanılacak `std::errc` hata işlemeyi değiştirme de dahil olmak üzere başka geliştirmeler yapın.

### <a name="c17-constexpr-for-char_traits-partial"></a>C++ 17: `constexpr` for `char_traits` (kısmi)

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) `length` `compare` `find` Sabit ifadelerde kullanılabilir hale getirmek`std::string_view` için, ve üyeişlevlerindekideğişiklikler.`std::traits_type` (Visual Studio 2017 sürüm 15,6 ' de yalnızca Clang/LLVM için desteklenir. Sürüm 15,7 Preview 2 ' de, destek, ClXX için neredeyse tamamlanmıştır.)

## <a name="improvements_159"></a>15,9 sürümündeki uyumluluk geliştirmeleri

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>İşleçler `->*`, `[]`, veiçinsoldansağadeğerlendirmesırası`>>``<<`

C++ 17 ' den başlayarak,, `->*`, ve `<<` işleçlerinin `[]` `>>`işlenenleri soldan sağa sırada değerlendirilmelidir. Derleyicinin bu sırayı garanti edemediği iki durum vardır:

- işlenen ifadelerinden biri, değer ile geçirilen bir nesne veya değer tarafından geçirilen bir nesne içeriyorsa veya

- **/clr**kullanılarak derlendiğinde ve işlenenlerinden biri bir nesnenin veya dizi öğesinin bir alanıdır.

Derleyici, soldan sağa değerlendirmeyi garanti edemediği zaman uyarı [C4866](https://docs.microsoft.com/cpp/error-messages/compiler-warnings/c4866?view=vs-2017) yayar. Derleyici bu uyarıyı yalnızca **/std: c++ 17** veya sonraki bir sürümü belirtilmişse, bu operatörlerin soldan sağa sırası gereksinimi c++ 17 ' de tanıtılmıştır.

Bu uyarıyı çözmek için ilk olarak, işlenenlerin değerlendirilme sırası bağımlı yan etkileri oluşturabilecek gibi işlenenler için soldan sağa değerlendirmesinin gerekip gerekmediğini göz önünde bulundurun. Çoğu durumda, işlenenlerinin değerlendirildiği sıranın hiçbir observable etkisi yoktur. Değerlendirme sırası soldan sağa doğru olmalıdır. bunun yerine işlenenleri const başvuruya göre mi geçiremeyeceğinizi düşünün. Bu değişiklik aşağıdaki kod örneğindeki uyarıyı ortadan kaldırır:

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

## <a name="update_150"></a>Visual Studio 2017 RTW 'de hata düzeltmeleri (sürüm 15,0)

### <a name="copy-list-initialization"></a>Kopya listesini başlatma

Visual Studio 2017, Visual Studio 2015 ' de yakalanmayan başlatıcı listeleri kullanarak nesne oluşturmayla ilgili derleyici hatalarını doğru şekilde oluşturur ve kilitlenmelere veya tanımsız çalışma zamanı davranışına neden olabilir. N4594 13.3.1.7 P1 başına, Copy-List-Initialization öğesinde, derleyici aşırı yükleme çözümlemesi için açık bir Oluşturucu kabul etmek için gereklidir, ancak belirli bir aşırı yükleme seçildiyse bir hata oluşturması gerekir.

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

Visual Studio 2015 ' de, derleyici yanlışlıkla kopyalama-liste başlatmasını düzenli kopya başlatma ile aynı şekilde kabul ediyor; yalnızca aşırı yükleme çözümlemesi için Oluşturucu dönüştürmekte sayılır. Aşağıdaki örnekte, Visual Studio 2015 myInt (23) öğesini seçer ancak Visual Studio 2017 hatayı doğru bir şekilde yükseltir.

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

Visual Studio 2017 artık, bir sınıf veya yapıda tanımlanan kullanım dışı tür tanımları için doğru uyarıyı yayınlar. Aşağıdaki örnek Visual Studio 2015 ' de uyarılar olmadan derlenir ancak Visual Studio 2017 ' de C4996 oluşturur.

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

Bir constexpr bağlamında, koşullu değerlendirme işleminin sol işleneni geçerli olmadığında Visual Studio 2017 doğru bir şekilde hata oluşturur. Aşağıdaki kod Visual Studio 2015 ' de derlenir, ancak Visual Studio 2017 ' de (C3615 constexpr işlevi ' f ' bir sabit ifade ile sonuçlanamaz):

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

Hatayı `array::size()` düzeltmek için, işlevi olarak `constexpr` bildirin `f`ya da `constexpr` belirteci kaldırın.

### <a name="class-types-passed-to-variadic-functions"></a>Değişken bağımsız değişken işlevlere geçirilen sınıf türleri

Visual Studio 2017 ' de, printf gibi bir bağımsız değişken işleve geçirilen sınıflar veya yapılar, Üçlü kopyalanabilir olmalıdır. Bu tür nesneler geçirilirken, derleyici yalnızca bit düzeyinde bir kopya yapar ve oluşturucuyu veya yıkıcıyı çağırmaz.

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

CString kullanılarak oluşturulan ve yönetilen dizeler için, CString nesnesini `operator LPCTSTR()` biçim dizesi tarafından beklenen C işaretçisine dönüştürmek için, belirtilen dize kullanılmalıdır.

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

Hatayı düzeltmek için olarak `operator int()` `const`bildirin.

### <a name="access-checking-on-qualified-names-in-templates"></a>Şablonlarda nitelikli adlar üzerinde erişim denetimi

Derleyicinin önceki sürümleri bazı şablon bağlamlarındaki nitelikli adlara erişimi denetmedi. Bu sorun, bir adın erişilebilirliği nedeniyle değiştirmenin başarısız olması beklenildiği SFıNAE davranışına engel olabilir. Derleyici yanlış bir işlecin aşırı yüklemesini hatalı olarak çağırdığından, çalışma zamanında kilitlenme veya beklenmeyen davranışlara neden olmuş olabilir. Visual Studio 2017 ' de bir derleyici hatası tetiklenir. Belirli hata değişebilir, ancak genellikle "C2672 eşleşen aşırı yüklenmiş işlev bulunamadı" olarak değişir. Aşağıdaki kod Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de bir hata oluşturur:

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

Visual Studio 2015 ve önceki sürümlerde, derleyici şablon parametre listesinde görünerken, örneğin varsayılan bir şablon bağımsız değişkeninin veya tür olmayan bir şablon parametresinin bir parçası olarak eksik şablon bağımsız değişken listelerini tanılamadı. Bu sorun, derleyici kilitlenmeleri veya beklenmeyen çalışma zamanı davranışı dahil öngörülemeyen davranışlara neden olabilir. Aşağıdaki kod Visual Studio 2015 ' de derlenir, ancak Visual Studio 2017 ' de bir hata oluşturur.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>İfade-SFıNAE

İfade-sfinae 'yi desteklemek için, artık şablon örneği `decltype` oluşturulması yerine bir şekilde bildirildiği zaman bağımsız değişkenleri ayrıştırır. Sonuç olarak, decltype bağımsız değişkeninde bağımlı olmayan bir özelleştirme bulunursa, örnekleme zamanına ertelenir. Anında işlenir ve bu sırada ortaya çıkan hatalar tanılandı.

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

C++ Standart olarak, anonim bir ad alanı içinde belirtilen bir sınıf iç bağlantıya sahiptir ve bu, verilemeyeceği anlamına gelir. Visual Studio 2015 ve önceki sürümlerde bu kural zorlanmaz. Visual Studio 2017 ' de kural kısmen zorlanır. Aşağıdaki örnek bu hatayı Visual Studio 2017: "Error C2201: const anonim ad alanı:: S1:: vftable: ' in verilebilmesi/içeri aktarılması için dış bağlantısı olmalıdır."

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Değer sınıfı üyeleri için varsayılan başlatıcılar (C++/CLI)

Visual Studio 2015 ve önceki sürümlerde, derleyici bir değer sınıfının üyesi için varsayılan üye başlatıcısını (ancak yok sayılır) izin verilir. Değer sınıfının varsayılan başlatması her zaman sıfır-üyeleri başlatır. Varsayılan bir oluşturucuya izin verilmez. Visual Studio 2017 ' de, varsayılan üye başlatıcıları aşağıdaki örnekte gösterildiği gibi bir derleyici hatası yükseltir:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Varsayılan Dizin oluşturucularC++(/CLI)

Visual Studio 2015 ve önceki sürümlerde, bazı durumlarda derleyici varsayılan bir dizin oluşturucu olarak varsayılan bir özelliği yanlış tanımladı. Bu özelliğe erişmek için tanımlayıcıyı `default` kullanarak soruna geçici bir çözüm olabilir. Geçici çözüm, c++ 11 ' `default` de bir anahtar sözcük olarak sunulduktan sonra sorunlu hale geldi. Visual Studio 2017 ' de, geçici çözümü gerektiren hatalar düzeltildi ve derleyici, bir sınıf için varsayılan özelliğe erişmek üzere kullanıldığında `default` bir hata oluşturuyor.

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

## <a name="update_153"></a>15,3 sürümündeki hata düzeltmeleri

### <a name="calls-to-deleted-member-templates"></a>Silinen üye şablonlarına yapılan çağrılar

Visual Studio 'nun önceki sürümlerinde, bazı durumlarda derleyici, çalışma zamanında kilitlenmelere neden olabilecek silinmiş üye şablonuna yönelik hatalı oluşturulmuş çağrılar için hata yaymayabilir. Aşağıdaki kod artık C2280 oluşturuyor, "' int S\<int >:: f\<int > (void) ': silinmiş bir işleve başvurulmaya çalışılıyor":

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

Hatayı onarmak için olarak `i` `int`bildirin.

### <a name="pre-condition-checks-for-type-traits"></a>Tür nitelikleri için koşul öncesi denetimler

Visual Studio 2017 sürüm 15,3, standart bir şekilde izlemek için tür nitelikleri için koşul öncesi denetimleri geliştirir. Bu tür bir denetim atanabilir içindir. Aşağıdaki kod, Visual Studio 2017 sürüm 15,3 ' de C2139 üretir:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yeni derleyici uyarısı ve çalışma zamanı, yerel-yönetilen sıralamaya göre denetler

Yönetilen işlevlerden yerel işlevlere çağırma sıralama gerektirir. CLR sıralama yapar, ancak semantiğini anlamıyor C++ . Bir yerel nesneyi değere göre geçirirseniz, clr nesnenin kopya oluşturucusunu veya kullanımını `BitBlt`çağırır, bu da çalışma zamanında tanımsız davranışlara neden olabilir.

Artık derleyici, silinen kopya ctor ile yerel bir nesnenin değere göre yerel ve yönetilen sınır arasında geçtiğini bildiren bir uyarı yayar. Derleyicinin derleme zamanında tanımadığı bu durumlar için, hatalı oluşturulmuş bir sıralama gerçekleştiğinde programın hemen çağırması `std::terminate` için bir çalışma zamanı denetimi çıkarır. Visual Studio 2017 sürüm 15,3 ' de, aşağıdaki kod "' A" uyarı C4606 oluşturur: yerel ve yönetilen sınır içindeki değere göre bağımsız değişken geçirme geçerli bir kopya Oluşturucu gerektirir. Aksi takdirde, çalışma zamanı davranışı tanımsızdır.

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
    f(A()); // This call from managed to native requires marshaling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

Hatayı onarmak için, çağrıyı yapana yerel `#pragma managed` olarak işaretleme ve sıralama yapmaktan kaçının yönergesini kaldırın.

### <a name="experimental-api-warning-for-winrt"></a>WinRT için deneysel API uyarısı

Deneme ve geri bildirim için yayımlanan WinRT API 'Leri ile birlikte `Windows.Foundation.Metadata.ExperimentalAttribute`tasarlanmıştır. Visual Studio 2017 sürüm 15,3 ' de, derleyici özniteliğiyle karşılaştığında uyarı C4698 oluşturur. Önceki Windows SDK sürümlerinden birkaç API zaten özniteliğiyle birlikte tasarlanmıştır ve bu API 'lere yapılan çağrılar artık bu derleyici uyarısını tetikler. Daha yeni Windows SDK 'Ları, tüm sevk edilen türlerden kaldırılan özniteliğe sahiptir, ancak eski bir SDK kullanıyorsanız, sevk edilen türlere yapılan tüm çağrılar için bu uyarıları bastırın.

Aşağıdaki kod C4698 uyarı üretir: "' Windows:: Storage:: IApplicationDataStatics2:: GetForUserAsync ' yalnızca değerlendirme amaçlıdır ve gelecekteki güncelleştirmelerde değiştirilebilir veya kaldırılabilir":

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Uyarıyı devre dışı bırakmak için #pragma ekleyin:

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Şablon üye işlevinin satır dışı tanımı

Visual Studio 2017 sürüm 15,3, sınıfında bildirilmeyen bir şablon üye işlevinin satır dışı tanımıyla karşılaştığında bir hata oluşturur. Aşağıdaki kod şu anda C2039 hatasını veriyor: ' f ': ' ın ' üyesi değil:

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
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

### <a name="attempting-to-take-the-address-of-this-pointer"></a>`this` İşaretçinin adresini alma girişimi

' C++ `this` De, X için işaretçi türünde bir prvalue olamaz. Adresini `this` alamaz veya bir lvalue başvurusuna bağlayamazsınız. Visual Studio 'nun önceki sürümlerinde derleyici, bu kısıtlamayı bir cast kullanarak atlatmayı sağlar. Visual Studio 2017 sürüm 15,3 ' de, derleyici C2664 hatasını üretir.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemeyen bir taban sınıfına dönüştürme

Visual Studio 2017 sürüm 15,3, bir türü erişilemeyen temel sınıfa dönüştürmeye çalıştığınızda bir hata üretir. Derleyici şimdi "Error C2243: ' tür cast ' öğesini başlatır: ' B * ' türünden dönüştürme var, ancak erişilemez". Aşağıdaki kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Derleyici artık şunun gibi kodla karşılaştığında C2243 üretir:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>Üye işlevlerinin satır dışı tanımlarında varsayılan bağımsız değişkenlere izin verilmez

Şablon sınıflarındaki üye işlevlerinin satır dışı tanımlarında varsayılan bağımsız değişkenlere izin verilmez. Derleyici, **/izin**altında bir uyarı verecek ve **/Permissive-** altında bir sabit hata verecek.

Visual Studio 'nun önceki sürümlerinde, aşağıdaki hatalı oluşturulmuş kod, çalışma zamanı kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3, uyarı C5034 üretir: ' A\<T >:: f ': bir sınıf şablonu üyesinin bir satır dışı tanımı varsayılan bağımsız değişkenlere sahip olamaz:

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

Hatayı onarmak için `= false` varsayılan bağımsız değişkeni kaldırın.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Bileşik üye göstergesi ile kullanımı `offsetof`

Visual Studio 2017 sürüm 15,3 ' de, `offsetof(T, m)` *z* 'nin "bileşik üye göstergesi" olarak kullanılması, **/duvar** seçeneğiyle derlerken bir uyarı ile sonuçlanır. Aşağıdaki kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3 "uyarı C4841: standart olmayan uzantı kullanıldı: OffsetOf içinde bileşik üye göstergesi":

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Kodu onarmak için, bir pragma ile uyarıyı devre dışı bırakın ya da kodu kullanmayan `offsetof`olarak değiştirin:

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Statik `offsetof` veri üyesi veya üye işlevi ile kullanma

Visual Studio 2017 sürüm 15,3 ' de bir `offsetof(T, m)` statik veri üyesine veya üye işleve başvuran bir hata ile sonuçlanır. Aşağıdaki kod, "Error C4597: tanımsız davranış: ' example '" ve "Error C4597: tanımsız davranış: ' Sample ' ' örneğine uygulanmış olan ' örnek ' üye işlevine yönelik OffsetOf uygulandı:

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

Bu kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Hatayı onarmak için kodu artık tanımsız davranışı çağırmayacak şekilde değiştirin. Bu, C++ standart tarafından izin verilmeyen taşınabilir olmayan koddur.

### <a name="declspec"></a>`__declspec` Özniteliklerde yeni uyarı

Visual Studio 2017 sürüm 15,3 ' de, bağlantı belirtiminden önce `__declspec(...)` `extern "C"` uygulanmışsa derleyici artık öznitelikleri yok saymaz. Daha önce derleyici, çalışma zamanı etkilerine sahip olabilecek özniteliğini yoksayacaktır. **/Duvar** ve **/WX** seçenekleri ayarlandığında, aşağıdaki kod "uyarı C4768: bağlantı belirtiminin önüne alınmadan önce __declspec öznitelikleri yok sayılır" olarak oluşturulur.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarıyı onarmak için, önce şunu `extern "C"` yerleştirin:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı, varsayılan olarak 15,3 ' de, ancak varsayılan olarak 15,5 ' de kapalıdır ve yalnızca/duvar/WXile derlenen kodu etkiler.

### <a name="decltype-and-calls-to-deleted-destructors"></a>`decltype`ve silinen yıkıcıları için çağrılar

Visual Studio 'nun önceki sürümlerinde derleyici, ile `decltype`ilişkili ifade bağlamında silinmiş yok edicinin bir çağrısının gerçekleştiğini algılamadım. Visual Studio 2017 sürüm 15,3 ' de, aşağıdaki kod "hata C2280: ' A\<T >:: ~ A (void) ': silinmiş bir işleve başvurulmaya çalışılıyor ":

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

Visual Studio 2017 RTW sürümünde, C++ bir `const` değişken başlatılmamışsa derleyicinin tanılama yayınlamadığı bir gerileme vardı. Bu gerileme, Visual Studio 2017 sürüm 15,3 ' de düzeltildi. Aşağıdaki kod artık "Warning C4132: ' Value ': const nesne başlatılmalıdır ":

```cpp
const int Value; //C4132
```

Hatayı onarmak için bir değer `Value`atayın.

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

Uyarı **/WV: 18** altında tutulur ve uyarı düzeyi W2 altında varsayılan olarak açık olur.

### <a name="stdis_convertible-for-array-types"></a>`std::is_convertible`dizi türleri için

Derleyicinin önceki sürümleri, dizi türleri için [std:: is_convertible](../standard-library/is-convertible-class.md) için yanlış sonuçlar verdi. Bu gerekli kitaplık yazarları, nitelik C++ `std::is_convertible<...>` türü kullanılırken Microsoft derleyicisine özel durum verebilir. Aşağıdaki örnekte, statik onaylar Visual Studio 'nun önceki sürümlerinde geçer ancak Visual Studio 2017 sürüm 15,3 ' de başarısız olur:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>`, bir sanal işlev tanımının düzgün biçimlendirilmiş olup olmadığını denetleyerek hesaplanır:

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdis_constructible"></a>Özel Yıkıcılar ve`std::is_constructible`

Önceki derleyicinin sürümleri, [std:: is_constructible](../standard-library/is-constructible-class.md)sonucunu saptarken bir yıkıcının özel olup olmadığını yoksaydı. Artık bunları dikkate alır. Aşağıdaki örnekte, statik onaylar Visual Studio 'nun önceki sürümlerinde geçer ancak Visual Studio 2017 sürüm 15,3 ' de başarısız olur:

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

Özel Yıkıcılar bir türün oluşturulabilir olmayan şekilde oluşmasına neden olur. `std::is_constructible<T, Args...>`, aşağıdaki bildirim yazıldığı gibi hesaplanır:

```cpp
   T obj(std::declval<Args>()...)
```

Bu çağrı bir yıkıcı çağrısını gösterir.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: Belirsiz aşırı yükleme çözümlemesi

Derleyicinin önceki sürümleri bazen birden fazla aday ve bağımsız değişkene bağlı arama aracılığıyla birden çok aday bulmadığı zaman belirsizliğe neden olmuş olabilir. Bu hata, seçilen yanlış aşırı yüklemeye ve beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3, C2668 ' f ' öğesini doğru şekilde yükseltir: aşırı yüklenmiş işleve belirsiz çağrı:

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

Kodu onarmak için, çağrısını `N::f` `::f()`amaçlıyorsanız using ifadesini kaldırın.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişkene bağlı arama

Yerel işlev bildirimleri kapsayan kapsamdaki işlev bildirimini gizler ve bağımsız değişkene bağımlı aramayı devre dışı bırakır. Ancak, derleyicinin önceki sürümleri bu durumda bağımsız değişkene bağlı arama gerçekleştirmekte ve muhtemelen yanlış aşırı yüklemeye ve beklenmeyen çalışma zamanı davranışına neden olmuş olabilir. Genellikle, hata yerel işlev bildiriminin hatalı imzası nedeniyle oluşur. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3, C2660 ' f ' öğesini doğru şekilde yükseltir: işlev iki bağımsız değişken almaz:

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

Sınıf üyeleri,, başlatıcı listelerinde göründükleri sırada değil, bildirildiği sırada başlatılır. Önceki derleyicinin sürümleri, başlatıcı listesinin sırası bildirim sırasına göre farklıydı. Bu sorun, bir üyenin listedeki başka bir üyeye bağımlı olması durumunda tanımsız çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3 ( **/duvar**ile) "uyarı C5038: ' a:: y ' veri üyesi, ' a:: x '" veri üyesinden sonra başlatılacak:

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Sorunu gidermek için, başlatıcı listesini bildirimlerle aynı sırada olacak şekilde düzenleyin. Bir veya her iki Başlatıcı de temel sınıf üyelerine başvururken benzer bir uyarı tetiklenir.

Bu uyarı varsayılan olarak kapalıdır ve yalnızca **/duvar**ile derlenen kodu etkiler.

## <a name="update_155"></a>15,5 sürümündeki hata düzeltmeleri ve diğer davranış değişiklikleri

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

Yukarıdaki örnekte yer alan sorun, türlerde iki fark vardır (const ve const olmayan ve Pack ve Pack olmayan). Derleyici hatasını ortadan kaldırmak için farklardan birini kaldırın. Bu, derleyicinin işlevleri kesin şekilde sıralaması için olanak sağlar.

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

Dizi veya işlev türüne başvuru işleyicileri hiçbir bir özel durum nesnesi için hiçbir şekilde eşleşmez. Derleyici artık bu kurala göre doğru şekilde uyarın ve 4. düzey bir uyarı oluşturur. Ayrıca, `char*` **/Zc: strictStrings** kullanıldığında `wchar_t*` bir veya işleyicisi ile bir dize sabit değeri eşleşmez.

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

### <a name="tr1"></a>`std::tr1` ad alanı kullanım dışı

Standart `std::tr1` olmayan ad alanı artık hem c++ 14 hem de c++ 17 modlarında kullanım dışı olarak işaretlenir. Visual Studio 2017 sürüm 15,5 ' de aşağıdaki kod C4996 yükseltilir:

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

### <a name="annex_d"></a>Ek D içindeki standart kitaplık özellikleri kullanım dışı olarak işaretlendi

**/Std: c++ 17** modu derleyici anahtarı ayarlandığında, ek D içindeki neredeyse tüm standart kitaplık özellikleri kullanım dışı olarak işaretlenir.

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

Visual Studio 2017 sürüm 15,5 ' de, uyarılar C4001 ve C4179 artık C derleyicisi tarafından yayılmayacaktır. Daha önce, yalnızca **/za** derleyici anahtarı altında yayılmıştı.  Tek satır açıklamaları C99 sonrasında C standardının bir parçası olduğundan, uyarılar artık gerekli değildir.

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

Kodun geriye dönük olarak uyumlu olması gerekmiyorsa, C4001/C4179 gizlemesini kaldırarak uyarıdan kaçınabilirsiniz. Kodun geriye dönük olarak uyumlu olması gerekiyorsa yalnızca C4619 ' ı gizleyin.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="__declspec-attributes-with-extern-c-linkage"></a>`__declspec`bağlantısı olan `extern "C"` öznitelikler

Visual Studio 'nun önceki sürümlerinde, derleyici, `__declspec(...)` `extern "C"` bağlantı belirtiminden önce uygulandığında `__declspec(...)` yoksayılan öznitelikleri yok sayılır. Bu davranış, olası çalışma zamanı etkilerine karşı kullanıcının istememiş kodu oluşturulmasına neden oldu. Uyarı Visual Studio sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak etkindir.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Hatayı onarmak için, bağlantı belirtimini __declspec özniteliğiyle önce yerleştirin:

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

### <a name="extern_linkage"></a>Extern constexpr bağlantısı

Visual Studio 'nun önceki sürümlerinde, derleyici her zaman değişken işaretlenmiş `constexpr` `extern`olsa bile iç bağlantı değişkeni verdi. Visual Studio 2017 sürüm 15,5 ' de, yeni bir derleyici anahtarı ( **/Zc: externConstexpr**) standartlara uygun doğru davranışı mümkün bir şekilde sunar. Sonuç olarak bu davranış varsayılan olur.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Bir üst bilgi dosyası, tanımlanmış `extern constexpr`bir değişken içeriyorsa, yinelenen bildirimlerinin doğru şekilde birleştirilmek üzere işaretlenmesi `__declspec(selectany)` gerekir:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>`typeid`tamamlanmamış sınıf türünde kullanılamaz

Visual Studio 'nun önceki sürümlerinde, derleyici aşağıdaki koda yanlış izin verdiği için hatalı tür bilgisi oluşmasına neden olur. Visual Studio 2017 sürüm 15,5 ' de, derleyici doğru bir hata oluşturur:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdis_convertible-target-type"></a>`std::is_convertible`hedef türü

`std::is_convertible`hedef türün geçerli bir dönüş türü olmasını gerektirir. Visual Studio 'nun önceki sürümlerinde, derleyici yanlış bir aşırı yükleme çözümüne ve istenmeyen çalışma zamanı davranışına neden olabilecek soyut türlere yanlış izin verebilir.  Aşağıdaki kod artık C2338 öğesini doğru şekilde yükseltir:

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

### <a name="noexcept_removal"></a>Dinamik özel durum belirtimi kaldırma ve`noexcept`

C++ `throw()` 17 ' de, `throw(<type list>)` için `noexcept` `throw(...)` bir diğer addır ve kaldırılır ve belirli türler dahil `noexcept`olabilir. Bu değişiklik, C++ 14 veya daha önceki bir sürümüyle uyumlu kodla kaynak uyumluluk sorunlarına neden olabilir. **/Zc: noexcepttypes-** Switch, genel olarak c++ 17 modunu kullanırken c++ 14 sürümüne `noexcept` dönmek için kullanılabilir. Bu, tüm `throw()` kodunuzu aynı anda yeniden yazmak zorunda kalmadan, kaynak kodunuzu c++ 17 ' ye uyacak şekilde güncelleştirmenizi sağlar.

Derleyici Ayrıca C++ 17 modundaki bildirimlerde veya New Warning C5043 ile **/Permissive-** ile daha fazla uyuşmayan özel durum belirtimini de tanılar.

Aşağıdaki kod, **/std: c++ 17** sürümü uygulandığında Visual Studio 2017 sürüm 15,5 ' de C5043 ve C5040 üretir:

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

Yine de **/std: c++ 17**kullanırken hataları kaldırmak için, aşağıdaki örnekte gösterildiği gibi **/Zc: noexcepttypes-** anahtarını komut satırına ekleyin ya da kodunuzu kullanmak `noexcept`üzere güncelleştirin:

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

Statik constexpr veri üyeleri artık örtük olarak satır içine alınır. Bu, bir sınıftaki bildiriminin artık tanımıyla olduğu anlamına gelir. Statik constexpr veri üyesi için satır dışı bir tanım kullanmak gereksizdir ve artık kullanım dışıdır. Visual Studio 2017 sürüm 15,5 ' de, **/std: c++ 17** anahtarı uygulandığında şu kod artık uyarı C5041 *' size ' üretir: constexpr statik veri üyesi için satır dışı tanımı gerekli değildir ve c++ 17 ' de kullanımdan kaldırılmıştır*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)`Uyarı C4768 Şu anda varsayılan olarak açık

Uyarı Visual Studio 2017 sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak açık olur. Daha fazla bilgi için bkz. [declspec Attributes \_hakkında \_yeni uyarı](#declspec).

### <a name="defaulted-functions-and-__declspecnothrow"></a>Varsayılan işlevler ve`__declspec(nothrow)`

Derleyici, karşılık gelen temel/üye işlevleri için özel `__declspec(nothrow)` durumlara izin verildiğinde, önceden ayarlanmış işlevlerin ile bildirilmesine izin verilir. Bu davranış, C++ standardının aksine, çalışma zamanında tanımsız davranışlara neden olabilir. Özel durum belirtimi uyumsuzluğu varsa, standart bu tür işlevlerin silinmiş olarak tanımlanmasını gerektirir.  **/Std: c++ 17**' nin altında, aşağıdaki kod, *silinen bir işleve başvuru yapmaya C2280 yayınlar. Açık özel durum belirtimi örtük bildirimdekilerle uyumsuz olduğundan işlev örtük olarak silindi.*

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

Bu kodu düzeltmek için, varsayılan olarak __declspec (nothrow) işlevini kaldırın ya `= default` da gerekli özel durum işlemeyle birlikte işlev için bir tanım sağlayın:

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

### <a name="noexcept-and-partial-specializations"></a>`noexcept`ve kısmi uzmanlık

`noexcept` Tür sisteminde, belirli "çağrılabilir" türlerin eşleşmesi için kısmi uzmanlık, bir veya daha fazla bağımsız işlevler için eksik kısmi bir özelleştirme nedeniyle birincil şablonu derleyemiyor veya seçemeyebilir.

Bu gibi durumlarda, `noexcept` işlev işaretçilerini ve `noexcept` üye işlevlerine işaretçiler işlemek için ek kısmi uzmanlık eklemeniz gerekebilir. Bu aşırı yüklemeler yalnızca **/std: c++ 17** modunda geçerlidir. C++ 14 ile geriye dönük uyumluluk korunuyorsa ve başkalarının kullandığı kodu yazıyorsanız, bu yeni aşırı yüklemeleri yönergeler içinde `#ifdef` korumalısınız. Kendi kendine içerilen bir modülde çalışıyorsanız, koruyucuları kullanmak `#ifdef` yerine **/Zc: noexcepttypes-** Switch ile derlemeniz yeterlidir.

Aşağıdaki kod **/std: c++ 14** altında derlenir, ancak **/std: c++ 17** altında "Error C2027: tanımsız tür kullanımı ' A\<T > '" ile başarısız olur:

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

Aşağıdaki kod **/std: c++ 17** altında başarılı olur, çünkü derleyici yeni kısmi özelleşme `A<void (*)() noexcept>`seçer:

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

## <a name="update_157"></a>15,7 sürümündeki hata düzeltmeleri ve diğer davranış değişiklikleri

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++ 17: Birincil Sınıf şablonunda varsayılan bağımsız değişken

Bu davranış değişikliği, [sınıf şablonları-P0091R3 Için şablon bağımsız değişken kesintisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)için bir önkoşuludur.

Daha önce, derleyici birincil Sınıf şablonunda varsayılan bağımsız değişkeni yok sayıldı:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

Visual Studio 2017 sürüm 15,7 ' de **/std: c++ 17** modunda, varsayılan bağımsız değişken yok sayılır:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Bağımlı ad çözümlemesi

Bu davranış değişikliği, [sınıf şablonları-P0091R3 Için şablon bağımsız değişken kesintisi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)için bir önkoşuludur.

Aşağıdaki örnekte, Visual Studio 15,6 ve önceki sürümlerde derleyici, birincil Sınıf şablonunda `D::type` olarak `B<T>::type` çözümleniyor.

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

Visual Studio 2017 sürüm 15,7, **/std: c++ 17** modunda, D içindeki `typename` `using` ifadesinde anahtar sözcüğü gerektirir. Olmadan `typename`, derleyici uyarı C4346 başlatır: *' B < T\*>:: Type ': bağımlı ad bir tür değil* ve hata C2061: *sözdizimi hatası: tanımlayıcı ' Type '* :

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

**/Std: c++ 17** modunda Visual Studio 2017 sürüm 15,7 ' de, C4834 uyarı düzeyi ("' noDiscard ' özniteliği ile işlevin dönüş değerini atma), W3 'den W1 'e yükseltilir. Bir Cast `void`ile veya derleyiciye **/WD: 4834** geçirerek uyarıyı devre dışı bırakabilirsiniz

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Değişken bağımsız değişken şablon Oluşturucusu temel sınıf başlatma listesi

Visual Studio 'nun önceki sürümlerinde, şablon bağımsız değişkenleri eksik olan bir bağımsız değişken şablon Oluşturucu temel sınıf başlatma listesine hatasız olarak izin veriliyor. Visual Studio 2017 sürüm 15,7 ' de bir derleyici hatası tetiklenir.

Visual Studio 2017 sürüm 15,7 ' de aşağıdaki kod örneği C2614 *hatasını yükseltir: D\<int >: geçersiz üye başlatma: ' B ' bir taban veya üye değil*

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

Hatayı onarmak için b () ifadesini b\<T > () olarak değiştirin.

### <a name="constexpr-aggregate-initialization"></a>`constexpr`toplu başlatma

C++ Derleyicinin önceki sürümleri, toplu başlatmayı yanlış `constexpr` bir şekilde işledi; toplama-init listesinde çok fazla öğe olduğu ve kendisi için hatalı CodeGen üreten geçersiz kodu kabul etti. Aşağıdaki kod bu kodun bir örneğidir:

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

Visual Studio 2017 sürüm 15,7 güncelleştirme 3 ve sonraki sürümlerde, önceki örnek *C2078 çok fazla Başlatıcı*oluşturuyor. Aşağıdaki örnek, kodun nasıl düzeltileceğini gösterir. `std::array` İç içe yerleştirilmiş küme ayracı-init-listeleriyle, iç diziye kendi kendine açılan bir liste verin:

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

## <a name="update_158"></a>15,8 sürümündeki hata düzeltmeleri ve davranış değişiklikleri

Visual Studio 2017 sürüm 15,8 ' de derleyici değişiklikleri, hata düzeltmeleri ve davranış değişiklikleri kategorisinin altına düşmektedir ve aşağıda listelenmiştir:

### <a name="typename-on-unqualified-identifiers"></a>`typename`Nitelenmemiş tanımlayıcıda

[/Permissive-](../build/reference/permissive-standards-conformance.md) modunda, diğer ad şablonu tanımlarında `typename` nitelenmemiş tanımlayıcılarda bulunan spurerkeywords anahtar sözcükleri artık derleyici tarafından kabul edilmez. Aşağıdaki kod şu anda C7511 *'t ': ' TypeName ' anahtar sözcüğünün ardından tam bir ad*gelmelidir:

```cpp
template <typename T>
using  X = typename T;
```

Hatayı onarmak için ikinci satırı olarak `using  X = T;`değiştirin.

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()`diğer ad şablonu tanımlarının sağ tarafında

diğer ad şablonu tanımının sağ tarafında [__declspec](../cpp/declspec.md) 'e artık izin verilmez. Bu kod önceden kabul edildi ancak derleyici tarafından yoksayıldı ve diğer ad kullanıldığında hiçbir zaman kullanımdan kaldırma uyarısı ile sonuçlanmaz.

Bunun yerine C++ standart özniteliği [ \[ \[kullanım dışı\] bırakılmış\] ](../cpp/attributes.md) olabilir ve Visual Studio 2017 sürüm 15,6 ' de kullanılır. Aşağıdaki kod şu anda C2760 *sözdizimi hatası veriyor: beklenmeyen belirteç ' __declspec ', beklenen ' tür belirleyici '* :

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

Hatayı onarmak için, koda (diğer ad tanımının ' = ' önüne yerleştirilmiş özniteliği) aşağıdaki gibi değiştirin:

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>İki aşamalı ad arama tanılaması

İki aşamalı ad arama, şablon gövdelerinde kullanılan bağımlı olmayan adların, tanım zamanında şablona görünür olması gerekir. Daha önce, Microsoft C++ derleyicisi, bulunmayan bir adı örnekleme zamanına kadar aranmaz olarak bırakır. Şimdi, bağımlı olmayan adların şablon gövdesine bağlı olmasını gerektirir.

Bu şekilde bildirimde bulunan tek bir yöntem, bağımlı temel sınıflara aramalardır. Daha önce, derleyici, bağımlı taban sınıflarında tanımlanan adların kullanılmasına izin verdiklerinden, tüm türler çözümlendiğinde örnekleme sırasında aranabilir. Artık bu kod bir hata olarak kabul edilir. Bu durumlarda, değişkeni temel sınıf türü ile niteleyerek veya bir `this->` işaretçi ekleyerek buna bağımlı hale getirerek, örneği örnekleme zamanına göre aranmaya zorlayabilirsiniz.

**/Permissive-** modunda şu kod şu anda C3861: *' base_value ': tanımlayıcı bulunamadı*:

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

Hatayı onarmak için, `return` ifadesini olarak `return this->base_value;`değiştirin.

**Not:** Yükseltme Python kitaplığı 'nda, [unwind_type. hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp)içindeki bir şablon iletme BILDIRIMI için MSVC 'e özgü bir geçici çözüm olan çok uzun süredir. Visual Studio 2017 sürüm 15,8 (_MSC_VER = 1915) ile başlayan [/Permissive-](../build/reference/permissive-standards-conformance.md) modu ' nun altında, MSVC derleyicisi bağımsız değişkene bağımlı ad araması (adl) ve diğer derleyiciler ile tutarlıdır ve bu geçici çözüm koruma gereksiz hale getirir. Hata *C3861: ' unwind_type ': tanımlayıcı bulunamadı*, üst bilgi dosyasını güncelleştirmek için yükseltme deposunda [PR 229](https://github.com/boostorg/python/pull/229) ' a bakın. [Vcpkg](../build/vcpkg.md) Boost paketini zaten geliştirdik. bu nedenle, Boost kaynaklarınızı vcpkg 'dan edinmeniz veya yükseltmeniz durumunda düzeltme ekini ayrı olarak uygulamanız gerekmez.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>ad alanındaki iletme bildirimleri ve tanımları`std`

Standart C++ , bir kullanıcının ad alanına `std`iletme bildirimleri veya tanımları eklemesine izin vermez. Ad alanına `std` veya ad alanı `std` içindeki bir ad alanına bildirim veya tanım eklemek artık tanımsız davranışa neden olur.

Daha sonra, Microsoft, bazı standart kitaplık türlerinin tanımlandığı konumu taşıyacaktır. Bu değişiklik, ad alanına `std`iletme bildirimleri ekleyen mevcut kodu keser. Yeni bir uyarı olan C4643, bu tür kaynak sorunları belirlemenize yardımcı olur. Bu uyarı, **/Default** modunda etkinleştirilir ve varsayılan olarak kapalıdır. **/Duvarveya** **/WX**ile derlenen programları etkileyecektir.

Aşağıdaki kod artık C4643 ' i yükseltir: *Standart ad alanı std ' deki ' vector ' öğesine iletme kullanılmasına izin verilmiyor. C++*

```cpp
namespace std {
    template<typename T> class vector;
}
```

Hatayı onarmak için, iletme bildirimi yerine bir **içerme** yönergesi kullanın:

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>Kendilerine temsilci olan oluşturucular

Standart C++ , bir derleyicinin kendi kendine temsilci Oluşturucu temsilcisinden bir tanı yaymalıdır. C++ [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) ve [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) modlarında Microsoft derleyicisi artık C7535 ' i yükseltir: *' X:: X ': temsilci Oluşturucu kendisini çağırıyor*.

Bu hata olmadan, aşağıdaki program derlenir ancak sonsuz bir döngü oluşturacak:

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
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

### <a name="offsetof-with-constant-expressions"></a>`offsetof`Sabit ifadelerle

[OffsetOf](../c-runtime-library/reference/offsetof-macro.md) , genellikle [reinterpret_cast](../cpp/reinterpret-cast-operator.md)gerektiren bir makro kullanılarak uygulanmıştır. Bu kullanım, sabit bir ifade gerektiren bağlamlarda geçersizdir, ancak Microsoft C++ derleyicisinin geleneksel olarak BT 'ye izin verilir. Standart kitaplığın bir parçası olarak gönderilen `offsetof` makrobirderleyiciiç(__builtin_offsetof)kullanır,ancakpekçokkişimakroelikullanarakkendikendilerinitanımlar.`offsetof`

Visual Studio 2017 sürüm 15,8 ' de derleyici, bu `reinterpret_cast` işleçlerin standart C++ davranışa uyum sağlamak için varsayılan modda görünebilen alanı kısıtlar. [/Permissive-](../build/reference/permissive-standards-conformance.md)altında kısıtlamalar bile daha sıkı bir şekilde yapılır. Sabit ifadeler gerektiren bir konum `offsetof` sonucunun kullanılması, *sabit ifadelerde makro tabanlı OffsetOf deseninin uyarı C4644 kullanımının standart olmayan bir şekilde kullanılmasına neden olabilir; C++ standart olarak tanımlanan OffsetOf kullanın Kitaplık* veya C2975 *geçersiz şablon bağımsız değişkeni; derleme zamanı sabit ifadesi bekleniyor*.

Aşağıdaki kod, **/Default** ve **/std: C++ 17** modlarında C4644 ve **/Permissive-** modunda C2975 ' i başlatır:

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

Hatayı düzeltemedi, cstddef > `offsetof` aracılığıyla \<tanımlanan şekilde kullanın:

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

Microsoft C++ derleyicisinin önceki sürümleri, aynı zamanda paket genişletmesi konusunda bir temel sınıfta CV niteleyicileri olduğunu algılamamıştı.

Visual Studio 2017 sürüm 15,8 ' de, **/Permissive-** modda şu kod C3770 *' const S ': geçerli bir temel sınıf değil*:

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>`template`anahtar sözcük ve iç içe ad-tanımlayıcılar

**/Permissive-** modunda, derleyici artık, bağımlı bir iç `template` içe ad belirleyicisi sonrasında olduğunda bir şablon adından önce anahtar sözcüğü gerektirir.

**/Permissive-** modundaki şu kod artık C7510: *' example ': bağımlı şablon adının kullanılmasına ' Template ' ön eki eklenmelidir. Note: derlenen sınıf şablonu örneği oluşturma ' X<T>' öğesine başvurmak için bkz*:

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
        Base<T>::example<int>();
    }
};
```

Hatayı onarmak için aşağıdaki örnekte gösterildiği gibi `template` `Base<T>::example<int>();` ifadeye anahtar sözcüğünü ekleyin:

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

## <a name="update_159"></a>15,9 sürümündeki hata düzeltmeleri ve davranış değişiklikleri

### <a name="identifiers-in-member-alias-templates"></a>Üye diğer ad şablonlarındaki tanımlayıcılar

Üye diğer ad şablonu tanımında kullanılan tanımlayıcı kullanılmadan önce bildirilmelidir.

Derleyicinin önceki sürümlerinde aşağıdaki koda izin verildi:

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

Visual Studio 2017 sürüm 15,9 ' de, **/Permissive-** modda, derleyici C3861: *' from_template ': tanımlayıcı bulunamadı*.

Hatayı onarmak için, önce `from_template` `from_template_t`bildirimini yapın.

### <a name="modules-changes"></a>Modül değişiklikleri

Visual Studio 2017, sürüm 15,9 ' de, modüller için komut satırı seçenekleri modül oluşturma ve modül tüketim tarafları arasında tutarlı olmadığı zaman derleyici C5050 ' u yükseltir. Aşağıdaki örnekte, iki sorun vardır:

- Tüketim tarafında (Main. cpp), **/EHsc** seçeneği belirtilmez.

- C++ Sürüm, oluşturma tarafında **/std: c++ 17** ve tüketim tarafında **/std: c++ 14** ' dir.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Derleyici, bu durumların her ikisi için C5050 yükseltir: *uyarı C5050: Modül içeri aktarılırken olası uyumsuz ortam ': eşleşmeyen C++ sürümler.  Geçerli "201402" modül sürümü "201703"* .

Derleyici Ayrıca,. ifc dosyası ile oynanmış her seferinde C7536 ' i de yükseltir. Modül arabiriminin üstbilgisi, altındaki içeriklerin SHA2 karmasını içerir. İçeri aktarma işleminde,. ifc dosyası aynı şekilde karma hale getirilir ve üst bilgide belirtilen karmayla denetlenir. Bunlar eşleşmiyorsa hata C7536 tetiklenir: *IFC başarısız bütünlük denetimleri.  Beklenen SHA2: ' 66d5c8154df0c71d4cab7665be4a125c7ce5cb9a401a4d8b461b706ddd771c6 '* .

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Diğer adlar ve çıkarılamayan bağlamlarla ilgili Kısmi sıralama

Çıkarılamayan bağlamlardaki diğer adları içeren kısmi sıralama kurallarında uygulamalar birbirinden ayrılan uygulamalardır. Aşağıdaki örnekte, GCC ve Microsoft C++ derleyicisi ( **/Permissive-** modda), Clang kodu kabul ettiğinde bir hata yükseltir.

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

Uygulama farklılaşması, C++ standart ifade içindeki bir gerileme nedeniyle oluşur. Çekirdek soruna çözüm 2235, bu aşırı yüklemelerin sıralanabilmesi için bazı metinlerin kaldırılmasını sağlar. Geçerli C++ standart bu işlevleri kısmen sıralamak için bir mekanizma sağlamaz, bu nedenle belirsiz olarak değerlendirilir.

Geçici bir çözüm olarak, bu sorunu çözmek için kısmi sıralamaya güvenmemelisiniz. Bunun yerine, belirli aşırı yüklemeleri kaldırmak için SFıNAE kullanın. Aşağıdaki örnekte, öğesinin `IsA` `A`bir özelleştirmesi olduğunda `Alloc` ilk tekrar yüklemeyi kaldırmak için bir yardımcı sınıfı kullanıyoruz:

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

Hatayı önlemek için, `constexpr` niteleyiciyi işlevin `f()`açık örneklemesi ' nden kaldırın.

::: moniker-end

::: moniker range="vs-2015"

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>C++Visual Studio 2015 uyumluluk geliştirmeleri

Visual Studio 2015 güncelleştirme 3 aracılığıyla uyumluluk geliştirmelerinden oluşan tüm liste için bkz. [Visual C++ Studio 'nun yenilikler 2003-2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Görsel C++ dil uyumluluğu](../visual-cpp-language-conformance.md)
