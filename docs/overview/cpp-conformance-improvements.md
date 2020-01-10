---
title: C++uyumluluk geliştirmeleri
ms.date: 12/04/2019
description: Visual C++ Studio 'da Microsoft, c++ 20 dil standardı ile tam uygunluğu doğru ilerliyor.
ms.technology: cpp-language
ms.openlocfilehash: e9c2a69c8d33ea692a76a5642a15b581567c2c63
ms.sourcegitcommit: 5f276064779d90a4cfda758f89e0c0f1e4d1a188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75793849"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Visual Studio 2017’deki C++ uyumluluk geliştirmeleri

Microsoft C++ , her yayında uygunluk geliştirmeleri ve hata düzeltmeleri yapar. Bu makalede, ana sürüme ve ardından sürüme göre iyileştirmeler listelenmektedir. Ayrıca, sürüme göre önemli hata düzeltmelerini de listeler. Belirli bir sürümdeki değişikliklere doğrudan geçmek için **Bu makale** listesinde öğesini kullanın.

::: moniker range="vs-2019"

## <a name="improvements_160"></a>Visual Studio 2019 RTW (sürüm 16,0) ile uyumluluk geliştirmeleri

Visual Studio 2019 RTW, Microsoft C++ derleyicisindeki aşağıdaki uygunluk geliştirmelerini, hata düzeltmelerini ve davranış değişikliklerini IÇERIR (MSVC)

**Note:** C++ 20 uygulama, hem derleyici hem de IntelliSense için tamamlanana kadar `/std:c++latest` modda kullanılabilir hale getirilir. Bu sırada `/std:c++20` derleyici modu sunulacaktır.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modüller desteği

Modüller artık C++ 20 standardında resmi olarak bulunur. Visual Studio 2017 sürüm 15,9 ' ye geliştirilmiş destek eklenmiştir. Daha fazla bilgi için bkz. [MSVC 2017 sürüm 15,9 C++ Ile modüllerde daha iyi şablon desteği ve hata algılama](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Toplu türün değiştirilmiş belirtimi

C++ 20 ' de bir toplama türünün belirtimi değişmiştir (bkz. [Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla](https://wg21.link/p1008r1)). Visual Studio 2019 ' de, `/std:c++latest`altında, Kullanıcı tarafından tanımlanmış bir oluşturucuya sahip bir sınıf (örneğin, `= default` veya `= delete`olarak belirtilen bir Oluşturucu dahil) bir toplama değildir. Daha önce, yalnızca Kullanıcı tarafından sunulan oluşturucular bir sınıfın bir toplama olmasını eledi. Bu değişiklik, bu tür türlerin nasıl başlatıladığıyla ilgili ek kısıtlamalar getirir.

Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak `/std:c++latest`altında Visual Studio 2019 ' de C2280 ve C2440 hataları ortaya çıkarır:

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

### <a name="partial-support-for-operator-"></a>`operator <=>` için kısmi destek

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C++ 20, "Spaceship işleci" olarak da bilinen `<=>` üç yönlü karşılaştırma işlecini tanıtır. `/std:c++latest` modundaki Visual Studio 2019, artık izin verilmeyen sözdizimi için hataları yükselterek operatör için kısmi destek sunuyor. Örneğin, aşağıdaki kod Visual Studio 2017 hatası olmadan derlenir, ancak `/std:c++latest`altında Visual Studio 2019 ' de birden çok hata oluşturuyor:

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

Daha önce, MSVC, en üst düzeyin altında eşleşmeyen CV niteleyicilerine sahip bir türden başvurunun doğrudan bağlamasını izin verilir. Bu bağlama, başvuruya göre başvuruda bulunulan düzgün const verileri değişikliğine izin verebilir. Derleyici artık standart tarafından gerekli olduğu gibi geçici bir durum oluşturur. Visual Studio 2017 ' de, aşağıdaki kod uyarılar olmadan derlenir. Visual Studio 2019 ' de, derleyici *Uyarı C4172: \<Func: #1 "?PData@X@@QBEABQBXXZ"> yerel değişkenin adresini veya geçici durumunu döndürüyor*.

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

### <a name="reinterpret_cast-from-an-overloaded-function"></a>aşırı yüklenmiş bir işlevden `reinterpret_cast`

`reinterpret_cast` bağımsız değişkeni, aşırı yüklenmiş bir işlevin adresine izin verilen bağlamların biri değildir. Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019 C2440 tarafından yükseltilir *: ' aşırı yüklenmiş-işlev ' iken ' FP ' olarak dönüştürülemez*:

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

C++ 14 ' te lambda kapatma türleri değişmez değer değildir. Bu kuralın birincil sonucu, bir lambda 'nin bir **constexpr** değişkenine atanmayabilir. Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019 *C2127: ' l ': sabit olmayan bir ifadeyle ' constexpr ' varlığının geçersiz şekilde başlatılması*:

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Hatayı önlemek için, **constexpr** niteleyiciyi kaldırın ya da uyumluluk modunu `/std:c++17`olarak değiştirin.

### <a name="stdcreate_directory-failure-codes"></a>`std::create_directory` hata kodları

C++ 20 ' den koşullu [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) uygulandı. Bu değişiklikler, hedefin hata durumunda zaten bir dizin olup olmadığını denetlemek için `std::create_directory`. Daha önce, tüm ERROR_ALREADY_EXISTS türü hataları başarılı oldu-ancak Dizin oluşturulmamış kodlara açıldı.

### `operator<<(std::ostream, nullptr_t)`

Her [LWG 2221](https://cplusplus.github.io/LWG/issue2221)için, akışlara nullptrs yazmak üzere `operator<<(std::ostream, nullptr_t)` eklendi.

### <a name="additional-parallel-algorithms"></a>Ek paralel algoritmalar

`is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap`ve `is_heap_until`yeni paralel sürümleri.

### <a name="atomic-initialization"></a>Atomik başlatma

[P0883 "atomik başlatma düzeltme"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) özelliği değeri `std::atomic`, varsayılan olarak başlatmak yerine içerilen t 'yi başlatacak şekilde değişir. Microsoft standart kitaplığı ile Clang/LLVM kullanılırken bu çözüm etkinleştirilir. Şu anda Microsoft C++ derleyicisi için, **constexpr** işlemede hata için geçici bir çözüm olarak devre dışı bırakılmıştır.

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` ve `remove_cvref_t`

[P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf)' dan `remove_cvref` ve `remove_cvref_t` tür nitelikleri uygulandı. Bu, bir türden başvuru ve CV nitelemesini kaldırma (`std::decay` ve `std::decay_t`farklı olarak) ve işaretçiler için işlevler ve diziler olmadan kaldırır.

### <a name="feature-test-macros"></a>Özellik testi makroları

[P0941R2-Feature-test makroları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) , `__has_cpp_attribute`desteğiyle tamamlanmıştır. Özellik testi makroları tüm standart modlarda desteklenir.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla

[C++ 20 P1008R1-Kullanıcı tarafından belirtilen oluşturucularla proyaları toplamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) tamamlanmıştır.

## <a name="improvements_161"></a>16,1 sürümündeki uyumluluk geliştirmeleri

### <a name="char8_t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C++ 20, UTF-8 kod birimlerini temsil etmek için kullanılan yeni bir karakter türü ekler. C++ 20 ' deki `u8` dize sabit değerleri, daha önce olan `const char[N]`değil, tür `const char8_t[N]` sahip. [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm)içinde C standardı için benzer değişiklikler önerilir. Geriye dönük uyumluluk düzeltme `char8_t` için öneriler [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html)içinde verilmiştir. Microsoft C++ derleyicisi, **/zc: char8_t** derleyici seçeneğini belirttiğinizde Visual Studio 2019 sürüm 16,1 ' de `char8_t` için destek ekler. Gelecekte, [/std: c + + latest](../build/reference/std-specify-language-standard-version.md)ile desteklenecek ve **/zc: Char8_t-** aracılığıyla c++ 17 davranışına geri döndürülecektir. IntelliSense 'i destekleyen EDG derleyicisi henüz desteklemez, bu nedenle yalnızca gerçek derlemeyi etkilemeden yalnızca IntelliSense 'e sahip olan hataları görürsünüz.

#### <a name="example"></a>Örnek

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>std:: type_identity programlayıcılarına ve std:: Identity işlevi nesnesi

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). Kullanım dışı `std::identity` sınıf şablonu uzantısı kaldırılmıştır ve c++ 20 `std::type_identity` programlayıcılarına ve `std::identity` Function nesnesiyle değiştirilmiştir. Her ikisi de yalnızca [/std: c + + en son](../build/reference/std-specify-language-standard-version.md)altında kullanılabilir.

Aşağıdaki örnek, Visual Studio 2017 ' de `std::identity` için kullanımdan kaldırma uyarısı C4996 (\<type_traits > olarak tanımlanmıştır) üretir:

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

Aşağıdaki örnek, yeni `std::identity` (\<işlevsel >) yeni `std::type_identity`birlikte nasıl kullanılacağını gösterir:

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

Visual Studio 2017 ' de, bu kod uyarı olmadan derlenir, ancak Visual Studio 2019 içinde hata *C2760 sözdizimi hatası oluştu: beklenmeyen belirteç '\<ID-expr > ', beklenen ' ID-Expression '* :

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

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html) (c++ 20) açık şablon bağımsız değişkenleriyle işlev çağrısı ifadeleri için bağımsız değişkene bağlı arama aracılığıyla işlev şablonlarını bulma özelliği arttı. **/Std: c + + en son**gerektirir.

### <a name="designated-initialization"></a>Belirlenmiş başlatma

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf) (c++ 20) belirtilen başlatma, `Type t { .member = expr }` söz dizimi kullanılarak toplu başlatma işleminde belirli üyelerin seçili olmasına izin verir. **/Std: c + + en son**gerektirir.

### <a name="new-and-updated-standard-library-functions-c20"></a>Yeni ve güncelleştirilmiş standart kitaplık işlevleri (C++ 20)

- `basic_string` ve `basic_string_view`için `starts_with()` ve `ends_with()`.
- İlişkili kapsayıcılar için `contains()`.
- `list` ve `forward_list` için `remove()`, `remove_if()` ve `unique()` artık `size_type` değerini döndürüyor.
- `shift_left()` ve `shift_right()` \<algoritma > eklendi.


## <a name="improvements_162"></a>16,2 sürümündeki uyumluluk geliştirmeleri

### <a name="noexcept-constexpr-functions"></a>noexcept constexpr işlevleri

Constexpr işlevleri artık sabit bir ifadede kullanıldığında varsayılan olarak **noexcept** olarak değerlendirilmez. Bu davranış değişikliği [CWG 1351](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html#1351) çözünürlükten gelir ve [/Permissive-](../build/reference/permissive-standards-conformance.md)' de etkinleştirilmiştir. Aşağıdaki örnek Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' te C2338 üretir:

```cpp
constexpr int f() { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept"); // C2338 in 16.2
}
```

Hatayı onarmak için, Function bildirimine **noexcept** ifadesini ekleyin:

```cpp
constexpr int f() noexcept { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept");
}
```

### <a name="binary-expressions-with-different-enum-types"></a>Farklı enum türlerine sahip ikili ifadeler

Tek bir numaralandırma türü olan ve diğeri farklı bir numaralandırma türü olan ve diğer bir kayan nokta türünde olan işlenenler üzerinde her zamanki aritmetik dönüştürmeleri uygulama özelliği C++ 20 ' de ([P1120R0](https://wg21.link/p1120r0)) kullanım dışıdır. Visual Studio 2019 sürüm 16,2 ve sonraki sürümlerde, [/std: c + + latest](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkin olduğunda aşağıdaki kod bir düzey 4 uyarısı üretir:

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

Tek bir numaralandırma türü olan ve diğeri farklı bir numaralandırma türü olan ve diğer bir kayan nokta türünde olan işlenenler üzerinde her zamanki aritmetik dönüştürmeleri uygulama özelliği C++ 20 ' de ([P1120R0](https://wg21.link/p1120r0)) kullanım dışıdır. Diğer bir deyişle, bir numaralandırma ve kayan nokta türü arasındaki ikili bir işlemin kullanılması artık [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkin olduğunda bir uyarıdır:

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

Dizi türünün iki işleneni arasındaki eşitlik ve ilişkisel karşılaştırmalar, C++ 20 ' de ([P1120R0](https://wg21.link/p1120r0)) kullanım dışıdır. Diğer bir deyişle, iki dizi arasındaki karşılaştırma işlemi (derecelendirmeden ve ölçüde benzerlikleri ne olursa olsun) artık bir uyarıdır. Visual Studio 2019 sürüm 16,2 ' den başlayarak, aşağıdaki kod *C5056: operator ' = = ':* [/std: c + + latest](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkin olduğunda dizi türleri için kullanım dışı bırakıldı:

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

Spaceship işlecinin ( **<=>** ) tek başına bir tanımı artık **==** veya **! =** içeren ifadeleri yeniden yazmayacak ve Spaceship işleci `= default` ([P1185R2](https://wg21.link/p1185r2)) olarak işaretlenmedikçe. Aşağıdaki örnek Visual Studio 2019 RTW ve sürüm 16,1 ' de derlenir, ancak Visual Studio 2019 sürüm 16,2 ' te C2678 üretir:

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

- Fixed/bilimsel duyarlıkla \<charconv > `to_chars()`. (Genel duyarlık Şu anda 16,4 için planlanmaktadır.)
- [P0020R6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0020r6.html): atomik\<kayan >, atomik\<çift >, atomik\<uzun çift >
- [P0463R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0463r1.html): endian
- [P0482R6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html): char8_t Için kitaplık desteği
- [P0600R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0600r1.pdf): [\[noDiscard]] STL, Bölüm 1
- [P0653R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0653r2.html): to_address ()
- [P0754R2](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0754r2.pdf): \<sürümü >
- [P0771R1](http://open-std.org/JTC1/SC22/WG21/docs/papers/2018/p0771r1.pdf): noexcept std:: işlevin taşıma Oluşturucusu

## <a name="improvements_163"></a>Visual Studio 2019 sürüm 16,3 ' de uyumluluk geliştirmeleri

### <a name="stream-extraction-operators-for-char-removed"></a>Char * için akış ayıklama işleçleri kaldırıldı

Karakterlere işaretçi için akış ayıklama işleçleri kaldırıldı ve karakter dizisi ( [P0487R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0487r1.html)başına) için ayıklama işleçleri tarafından değiştirildi. WG21 kaldırılan aşırı yüklemeleri güvensiz kabul eder. [/Std: c + + en son](../build/reference/std-specify-language-standard-version.md) modunda aşağıdaki örnek, *C2679 ' > > ': ' Char\*' türünde sağ bir işlenen alan hiçbir işleç bulunamadı (veya kabul edilebilir dönüştürme yok)* :

```cpp
   char x[42];
   char* p = x;
   std::cin >> std::setw(42);
   std::cin >> p;
```

Hatayı önlemek için, bir Char [] değişkeniyle ayıklama işlecini kullanın:

```cpp
char x[42];
std::cin >> x;
```

### <a name="new-keywords-requires-and-concept"></a>Yeni anahtar sözcükler ve **kavram** **gerektirir**

Yeni anahtar sözcükler, Microsoft C++ derleyicisi için **gereklidir** ve kavram eklenmiştir. [/Std: c + + en son](../build/reference/std-specify-language-standard-version.md) modunda bir tanımlayıcı olarak birini kullanmaya çalışırsanız, derleyici *C2059 oluşturacak: sözdizimi hatası*.

### <a name="constructors-as-type-names-disallowed"></a>Tür adları olarak oluşturucular izin verilmiyor

Oluşturucu adları, bir sınıf şablonu özelleştirmesine bir diğer addan sonra nitelikli bir ada göründükleri zaman eklenen sınıf adları olarak kabul edilmez. Bu, daha önce diğer varlıkları bildirmek için tür adı olarak oluşturucuların kullanılmasına izin verilir. Aşağıdaki örnek şu anda *C3646 üretir: ' TotalDuration ': bilinmeyen geçersiz kılma belirticisi*:

```cpp
#include <chrono>

class Foo {
   std::chrono::milliseconds::duration TotalDuration{};
};

```

Hatayı önlemek için `TotalDuration` aşağıda gösterildiği gibi bildirin:

```cpp
#include <chrono>

class Foo {
  std::chrono::milliseconds TotalDuration {};
};
```

### <a name="stricter-checking-of-extern-c-functions"></a>Extern "C" işlevlerinin daha sıkı şekilde denetlenmesi

Bir **extern "C"** işlevi farklı ad alanlarında bildirilirse, Microsoft C++ derleyicisi 'nin önceki sürümleri bildirimlerin uyumlu olup olmadığını denetmedi. Visual Studio 2019 sürüm 16,3 ' de, derleyici böyle bir denetim gerçekleştirir. [/Permissive-](../build/reference/permissive-standards-conformance.md) modunda, aşağıdaki kod *C2371: yeniden tanımlama; farklı temel türler* ve *C2733 C bağlantısı ile bir işlevi aşırı*yükleyemezsiniz:

```cpp
using BOOL = int;

namespace N
{
   extern "C" void f(int, int, int, bool);
}

void g()
{
   N::f(0, 1, 2, false);
}

extern "C" void f(int, int, int, BOOL){}
```

Önceki örnekteki hataları önlemek için `f`her iki bildiriminde da **bool** yerine **bool** kullanın.

### <a name="standard-library-improvements"></a>Standart Kitaplık geliştirmeleri

Standart olmayan üstbilgiler \<stdexcpt. h > ve \<TypeInfo. h > kaldırılmıştır. Bunun yerine, bunları içeren kod, sırasıyla standart üstbilgileri \<özel durum > ve \<TypeInfo > içermelidir.

## <a name="improvements_164"></a>Visual Studio 2019 sürüm 16,4 ' de uyumluluk geliştirmeleri

### <a name="better-enforcement-of-two-phase-name-lookup-for-qualified-ids-in-permissive-"></a>/Permissive-içinde nitelikli kimlikler için iki aşamalı ad araması daha iyi bir şekilde zorlendi

İki aşamalı ad arama, şablon gövdelerinde kullanılan bağımlı olmayan adların, tanım zamanında şablona görünür olması gerekir. Daha önce, bu tür adlar şablon örneği oluşturulurken bulunmuş olabilir. Bu değişiklik, [/Permissive-](../build/reference/permissive-standards-conformance.md) bayrağı altında MSVC ' de taşınabilir ve uyumlu kod yazmayı kolaylaştırır.

Visual Studio 2019 sürüm 16,4 ' de, **/Permissive-** bayrağı ayarlanmış olarak, aşağıdaki örnek bir hata üretir çünkü `f<T>` şablonu tanımlandığında `N::f` görünür değildir:

```cpp
template <class T>
int f() {
    return N::f() + T{}; // error C2039: 'f': is not a member of 'N'
}

namespace N {
    int f() { return 42; }
}
```

Genellikle, bu, aşağıdaki örnekte gösterildiği gibi eksik üstbilgiler veya iletme bildirimi işlevleri veya değişkenleri eklenerek düzeltilebilir:

```cpp
namespace N {
    int f();
}

template <class T>
int f() {
    return N::f() + T{};
}

namespace N {
    int f() { return 42; }
}
```

### <a name="implicit-conversion-of-integral-constant-expressions-to-null-pointer"></a>İntegral sabit ifadelerin null işaretçisine örtük dönüştürmesi

MSVC derleyicisi artık Uyumluluk modu 'nda (/Permissive-) [CWG sorun 903](http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_defects.html#903) ' i uygular. Bu kural, tam sayı sabiti ifadelerinin örtük dönüştürmelerine izin vermez (' 0 ' tamsayı sabiti hariç), null işaretçi sabitlerine izin vermez. Aşağıdaki örnek uyumluluk modunda C2440 üretir:

```cpp
int* f(bool* p) {
    p = false; // error C2440: '=': cannot convert from 'bool' to 'bool *'
    p = 0; // OK
    return false; // error C2440: 'return': cannot convert from 'bool' to 'int *'
}
```

Hatayı düzeltemedi, **yanlış**yerine **nullptr** kullanın. 0 sabit değerinin hala izin verildiğini unutmayın:

```cpp
int* f(bool* p) {
    p = nullptr; // OK
    p = 0; // OK
    return nullptr; // OK
}
```

### <a name="standard-rules-for-types-of-integer-literals"></a>Tamsayı sabit değerleri türleri için standart kurallar

Uyumluluk modu ' nda ( [/Permissive-](../build/reference/permissive-standards-conformance.md)tarafından etkinleştirilir), MSVC tamsayı sabit değerleri türleri için standart kuralları kullanır. Daha önce, işaretli bir ' int ' öğesine sığmayacak kadar büyük olan ondalık harfler ' unsigned int ' türünde verilmiş. Bu tür sabitlerde, bir sonraki en büyük işaretli tamsayı türü (' Long Long ') verilir. Ayrıca, imzalı bir türe sığmayacak kadar büyük olan değişmez değerleri ' işaretsiz uzun uzun ' türünde.

Bu, farklı uyarı tanılamaları oluşturulmasını ve değişmez değerler üzerinde gerçekleştirilen aritmetik işlemler için davranış farklarını ortaya çıkaracak.

Aşağıdaki örnekte, Visual Studio 2019, sürüm 16,4 ' deki yeni davranış gösterilmektedir. `i` değişkeni **işaretsiz int** türündedir ve bu nedenle uyarı tetiklenir. `j` değişkeninin üst sıra bitleri 0 olarak ayarlanır.

```cpp
void f(int r) {
    int i = 2964557531; // warning C4309: truncation of constant value
    long long j = 0x8000000000000000ll >> r; // literal is now unsigned, shift will fill high-order bits with 0
}
```

Aşağıdaki örnekte, eski davranışın nasıl saklanacağı gösterilmektedir ve bu nedenle uyarı ve çalışma zamanı davranış değişikliğini önleyin:

```cpp
void f(int r) {
int i = 2964557531u; // OK
long long j = (long long)0x8000000000000000ll >> r; // shift will keep high-order bits
}
```

### <a name="function-parameters-that-shadow-template-parameters"></a>Gölge şablon parametrelerinin işlev parametreleri

MSVC derleyicisi artık bir işlev parametresi bir şablon parametresini gölgelerde bir hata oluşturuyor:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T(&buffer)[Size], int& Size) // error C7576: declaration of 'Size' shadows a template parameter
{
    return f(buffer, Size, Size);
}
```

Hatayı onarmak için parametrelerden birinin adını değiştirin:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T (&buffer)[Size], int& size_read)
{
    return f(buffer, Size, size_read);
}
```

### <a name="user-provided-specializations-of-type-traits"></a>Kullanıcı tarafından sunulan özelleştirilmiş tür nitelikleri

Standart 'ın *meta. rqmts* alt yan tümcesiyle uyumlu olarak, MSVC derleyicisi artık, `std` ad alanındaki belirtilen type_traits şablonlarından birinin Kullanıcı tanımlı özelleştirmeyle karşılaştığında bir hata oluşturuyor. Aksi belirtilmediği takdirde, bu tür Uzmanlıklar tanımsız davranışa neden olur. Aşağıdaki örnek, kuralı ihlal ettiğinden tanımsız davranışa sahiptir ve `static_assert` **C2338**hatasıyla başarısız olur.

```cpp
#include <type_traits>
struct S;

template<>
struct std::is_fundamental<S> : std::true_type {};

static_assert(std::is_fundamental<S>::value, "fail");
```

Hatayı önlemek için, istenen type_trait devralan bir yapı tanımlayın ve şunları yapın:

```cpp
#include <type_traits>

struct S;

template<typename T>
struct my_is_fundamental : std::is_fundamental<T> {};

template<>
struct my_is_fundamental<S> : std::true_type { };

static_assert(my_is_fundamental<S>::value, "fail");
```

### <a name="changes-to-compiler-provided-comparison-operators"></a>Derleyici tarafından sağlanmış karşılaştırma işleçleri değişiklikleri

MSVC derleyicisi artık [/std: c + + latest](../build/reference/std-specify-language-standard-version.md) seçeneği etkin olduğunda [P1630R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1630r1.html) başına karşılaştırma işleçleri için aşağıdaki değişiklikleri uygular:

Derleyici, **bool**olmayan bir dönüş türü içeriyorsa `operator==` deyimleri artık yeniden yazmayacaktır. Aşağıdaki kod şu anda *C2088 hatasını veriyor: '! = ': struct için geçersiz*:

```cpp
struct U {
  operator bool() const;
};

struct S {
  U operator==(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
  return lhs != rhs;
}
```

Hatayı önlemek için gerekli işleci açıkça tanımlamanız gerekir:

```cpp
struct U {
    operator bool() const;
};

struct S {
    U operator==(const S&) const;
    U operator!=(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Derleyici artık birleşim benzeri bir sınıfın üyesiyse, varsayılan olarak bir karşılaştırma işleci tanımlamaz. Aşağıdaki örnek şu anda *C2120 üretir: ' void ' tüm türlerle geçersizdir*:

```cpp
#include <compare>

union S {
    int a;
    char b;
    auto operator<=>(const S&) const = default;
};

bool lt(const S& lhs, const S& rhs) {
    return lhs < rhs;
}
```

Hatayı önlemek için işleç için bir gövde tanımlayın:

```cpp
#include <compare>

union S {
  int a;
  char b;
  auto operator<=>(const S&) const { ... }
}; 

bool lt(const S& lhs, const S& rhs) {
  return lhs < rhs;
}
```

Sınıf bir başvuru üyesi içeriyorsa, derleyici artık varsayılan olarak bir karşılaştırma işleci tanımlamaz. Aşağıdaki kod şu anda *C2120 hatasını veriyor: ' void ' tüm türlerle geçersizdir*:

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const = default;
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

Hatayı önlemek için işleç için bir gövde tanımlayın:

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const { ... };
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

## <a name="update_160"></a>Visual Studio 2019 'de hata düzeltmeleri ve davranış değişiklikleri

### <a name="reinterpret_cast-in-a-constexpr-function"></a>Constexpr işlevinde Reinterpret_cast

**Constexpr** işlevinde **reinterpret_cast** geçersizdir. Microsoft C++ derleyicisi daha önce **reinterpret_cast** yalnızca **constexpr** bağlamında kullanılıyorsa daha sonra reddedebilir. Visual Studio 2019 ' de, tüm dil standartları modlarında, derleyici **constexpr** işlevinin tanımındaki bir **reinterpret_cast** doğru bir şekilde tanılar. Aşağıdaki kod artık C3615 oluşturuyor *: constexpr işlevi ' f ' sabit bir ifadeye neden olamaz*.

```cpp
long long i = 0;
constexpr void f() {
    int* a = reinterpret_cast<int*>(i);
}
```

Hatayı önlemek için, işlev bildiriminden **constexpr** değiştiricisini kaldırın.

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>Basic_string Range Oluşturucusu için tanılama doğru

Visual Studio 2019 ' de `basic_string` Range Oluşturucusu artık `static_cast`ile derleyici tanılamayı göstermez. Aşağıdaki kod, Visual Studio 2017 ' de uyarılar olmadan derlenir, çünkü `out`başlatılırken `wchar_t` veri kaybı olabilir.

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 doğru *C4244: ' bağımsız değişken ': ' wchar_t ' değerinden ' const _Elem ' öğesine dönüştürme, olası veri kaybı*. Uyarıyı önlemek için std:: String öğesini şu örnekte gösterildiği gibi başlatabilirsiniz:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>/Clr veya/ZW altındaki + = ve-= için yanlış çağrılar artık doğru bir şekilde algılandı

Visual Studio 2017 ' de, derleyicinin hataları sessizce yoksaymasına ve `/clr` veya `/ZW`altında geçersiz + = ve-= çağrıları için kod üretmesinin nedeni olan bir hata ortaya çıkarılmıştır. Aşağıdaki kod Visual Studio 2017 ' de hatasız derlenir, ancak Visual Studio 2019, C2845 hatasını doğru şekilde oluşturuyor: *' System:: String ^ ': işaretçi aritmetiğinin bu tür üzerinde yapılmasına izin verilmiyor*:

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Bu örnekteki hatayı önlemek için, işleci ToString () yöntemiyle birlikte kullanın: `s += E::e.ToString();`.

### <a name="initializers-for-inline-static-data-members"></a>Satır içi statik veri üyeleri için başlatıcılar

**Satır içi** ve **statik constexpr** başlatıcıları içindeki geçersiz üye erişimleri artık doğru şekilde algılandı. Aşağıdaki örnek, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019 ' de `/std:c++17` modu *' nda hata C2248: ' X ' sınıfında belirtilen özel üyeye erişilemiyor*.

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

Hatayı önlemek için üye `X::c` korumalı olarak bildirin:

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>C4800 tekrar belirtilmiş

MSVC, **bool**'a örtük dönüştürme hakkında bir performans uyarısı C4800 sağlamak için kullanılır. Bu çok gürültülü ve gizlenemedi, bu da Visual Studio 2017 ' de kaldırılması için önde gelir. Bununla birlikte, Visual Studio 2017 yaşam döngüsünün üzerinde çöztiğimiz yararlı durumlar hakkında çok fazla geri bildirim sunuyoruz. Açıklayıcı C4165 ile birlikte Visual Studio 2019 ' ye dikkatlice uyarlanmış bir C4800 geri getiriyoruz. Bu uyarıların her ikisi de açık bir atama ile kolayca gizlenebilir veya uygun türden 0 ' a karşılaştırma yapılabilir. C4800, varsayılan olarak 4. düzey bir uyarıdır ve C4165, varsayılan olarak 1. düzey 3 uyarıdır. Her ikisi de `/Wall` derleyici seçeneği kullanılarak bulunabilir.

Aşağıdaki örnek, `/Wall`altında C4800 ve C4165 ' i yükseltir:

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

Visual Studio 2017, *C4822: Yerel sınıf üyesi işlevinde bir gövde* yalnızca `/w14822` derleyici seçeneği açıkça ayarlandığında tetiklenir; `/Wall`gösterilmiyor. Visual Studio 2019 ' de C4822, varsayılan olarak, `/w14822` açıkça ayarlamak zorunda kalmadan `/Wall` altında bulunabilir hale getiren varsayılan bir uyarıdır.

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

Constexpr deyimlerinin bir [/Permissive-](../build/reference/permissive-standards-conformance.md) ayrıştırmaya ilişkin denetim etkin **olup olmadığını** içeren şablon işlev gövdeleri. Örneğin, Visual Studio 2017 ' de şu kod C7510 oluşturur *: ' Type ': bağımlı tür adının kullanımı yalnızca/Permissive-seçeneği ayarlanmamışsa ' TypeName ' öneki olmalıdır* . Visual Studio 2019 ' de, **/Permissive-** seçeneği ayarlandığında de aynı kod hata oluşturuyor:

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

Hatayı önlemek için**TypeName** anahtar sözcüğünü `a`bildirimine ekleyin: `typename T::Type a;`.

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Bir lambda ifadesinde satır içi derleme kodu desteklenmez

Microsoft C++ ekibi kısa süre önce bir lambda içinde satır içi derleyici kullanmanın, çalışma zamanında `ebp` (dönüş Adres kaydı) bozulmasıyla sonuçlanabildiğine ilişkin bir güvenlik sorununu bilmiştir. Kötü amaçlı bir saldırgan bu senaryodan faydalanabilir. Sorunun doğası gereği, satır içi derleyicisinin yalnızca x86 'da desteklendiği ve satır içi assembler ve derleyicinin geri kalanı arasındaki kötü etkileşim nedeniyle bu sorunun en güvenli çözümü, bir lambda ifadesinde satır içi derleyicisine izin vermemelidir.

"Joker karakter" bulduğumuz bir lambda ifadesi içinde satır içi assembler 'nun tek kullanımı dönüş adresini yakalamıştı. Bu senaryoda, yalnızca bir derleyici iç `_ReturnAddress()`kullanarak dönüş adresini tüm platformlarda yakalayabilirsiniz.

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

### <a name="iterator-debugging-and-stdmove_iterator"></a>Yineleyici hata ayıklama ve `std::move_iterator`

Yineleyici hata ayıklama özelliği, `std::move_iterator`düzgün bir şekilde sarmalama işlemini geri alır. Örneğin, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` artık `memcpy` hızlı yolu kullanabilir.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>\<xkeycheck. h > anahtar sözcük zorlaması düzeltmeleri

Genel bir ileti yerine, algılanan gerçek sorun anahtar sözcüğünü göstermek için, standart kitaplığın \<xkeycheck. h > bir anahtar sözcüğünü değiştirme sorunu düzeltildi. Ayrıca C++ 20 anahtar sözcüklerini destekler ve IntelliSense 'in rastgele anahtar sözcüklerin makroları olduğunu söylenmesini önler.

### <a name="allocator-types-no-longer-deprecated"></a>Ayırıcı türleri artık kullanım dışı

`std::allocator<void>`, `std::allocator::size_type`ve `std::allocator::difference_type` artık kullanım dışıdır.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Daraltma dizesi dönüştürmeleri için doğru uyarı

Yanlışlıkla gizlenen C4244 daraltma uyarıları `std::string`kaldırılmış olan standart tarafından `static_cast` bir spurmerak değil. `std::string::string(const wchar_t*, const wchar_t*)` çağırma girişimi artık *wchar_t "bir karakteri bir Char 'a daraltma"* olarak doğru olarak yayacaktır.

### <a name="various-filesystem-correctness-fixes"></a>Çeşitli \<FileSystem > doğruluk düzeltmeleri

- Bir dizinin son yazma süresini değiştirmeye çalışırken düzeltilen `std::filesystem::last_write_time` başarısız oldu.
- `std::filesystem::directory_entry` Oluşturucusu artık varolmayan bir hedef yolu sağlandığı zaman bir özel durum oluşturmak yerine başarısız bir sonucu depolar.
- `std::filesystem::create_directory` 2 parametresi sürümü, temel alınan `CreateDirectoryExW` işlevi `existing_p` bir symlink olduğunda `copy_symlink` kullanacağından, 1 parametreli sürümü çağırmak üzere değiştirilmiştir.
- bozuk bir oluşturmaksızın bulunduğunda `std::filesystem::directory_iterator` artık başarısız olmaz.
- `std::filesystem::space` artık göreli yolları kabul eder.
- `std::filesystem::path::lexically_relative`, [LWG 3096](https://cplusplus.github.io/LWG/issue3096)olarak bildirilen eğik çizgiler tarafından artık karıştırılmamalıdır.
- `std::filesystem::create_symlink`' de eğik çizgi ile yol reddetme `CreateSymbolicLinkW` geçici olarak çalıştı.
- POSIX silme modu `delete`, Windows 10 LTSB 1609 ' de var olan ancak gerçekten dosyaları silebilecek şekilde çalışır.
- `std::boyer_moore_searcher` ve `std::boyer_moore_horspool_searcher`kopya oluşturucuları ve kopya atama işleçleri artık öğeleri kopyalayamıyorum.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 ve sonraki sürümlerde paralel algoritmalar

Paralel algoritmalar kitaplığı artık Windows 7 ve önceki sahte sürümlerini kullanmak yerine gerçek `WaitOnAddress` ailesini Windows 8 ve üzeri sürümlerde kullanır.

### <a name="stdsystem_categorymessage-whitespace"></a>`std::system_category::message()` boşluk

`std::system_category::message()` artık döndürülen iletiden sondaki boşluğu kırpar.

### <a name="stdlinear_congruential_engine-divide-by-zero"></a>`std::linear_congruential_engine` sıfıra bölme

0 ile bölme tetiklenmesine `std::linear_congruential_engine` neden olan bazı koşullar düzeltildi.

### <a name="fixes-for-iterator-unwrapping"></a>Yineleyici geri sarma düzeltmeleri

Visual Studio 2017 15,8 ' de birinci kez programcı-Kullanıcı tümleştirmesi için sunulan Yineleyici, C++ Team blog makalesinde [STL özellikleri ve düzeltmeleri ve vs 2017 15,8](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/)' te açıklandığı gibi, standart kitaplık yinelemelerinden türetilen yineleyicilerin sarmalarından daha fazla geri sarılamaz. Örneğin, `std::vector<int>::iterator` ve özelleştirmeyi özelleştirmeye izin veren bir Kullanıcı artık işaretçi davranışı yerine standart kitaplık algoritmalarını çağırırken özelleştirilmiş davranışlarını alır.

Sıralanmamış kapsayıcı `reserve` işlevi, [LWG 2156](https://cplusplus.github.io/LWG/issue2156)' de açıklandığı gibi aslında N öğeleri için ayırmıştır.

### <a name="time-handling"></a>Zaman işleme

- Daha önce, eşzamanlılık kitaplığına geçirilen bazı zaman değerleri, örneğin `condition_variable::wait_for(seconds::max())`taşırdı. Şimdi düzeltildi, rastgele 29 günlük bir döngüde (temel alınan Win32 API 'Leri tarafından kabul edilen uint32_t milisaniyelik) değiştirilen taşma

- \<CTime > üst bilgisi artık `timespec` ve `timespec_get` ad alanı `std`, genel ad alanında bildirmek için de doğru şekilde bildiriyor.

### <a name="various-fixes-for-containers"></a>Kapsayıcılar için çeşitli düzeltmeler

- Birçok standart kitaplık iç kapsayıcı işlevleri, geliştirilmiş bir IntelliSense deneyimi için özel yapılmıştır. MSVC 'in sonraki sürümlerinde üyeleri özel olarak işaretlemek için ek düzeltmeler beklenmektedir.

- `list`, `map`ve `unordered_map` gibi düğüm tabanlı kapsayıcılardan oluşan özel durum güvenliği doğruluk sorunları düzeltildi. Bir `propagate_on_container_copy_assignment` veya `propagate_on_container_move_assignment` yeniden atama işlemi sırasında kapsayıcının Sentinel düğümünü eski ayırıcıyla boşalttık, eski ayırıcı üzerinde POCCA/POCMA atamasını yapar ve ardından yeni ayırıcıdan Sentinel düğümünü edinmeyi deneyin. Bu ayırma başarısız olduysa, kapsayıcı bozulur ve bir Sentinel düğümü sabit veri yapısı sabiti olduğu için bile yok edilmez. Bu kod, mevcut Sentinel düğümünü yok etmeden önce, kaynak kapsayıcısının ayırıcısından yeni Sentinel düğümünü ayırmak için düzeltildi.

- Kapsayıcılar, `is_always_equal`olarak belirtilen ayrıcılar için bile `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment`ve `propagate_on_container_swap`göre ayrıcılar kopyalamak/taşımak/değiştirmek için düzeltildi.

- Kapsayıcı birleştirme için aşırı yüklemeler eklendi ve P0083 başına rvalue kapsayıcıları kabul eden üye işlevleri Ayıkla [ve kümeler](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) "

### <a name="stdbasic_istreamread-processing-of-rn--n"></a>\\r\\`std::basic_istream::read` işleme > \\n

`std::basic_istream::read`, \\r\\n = > \\n işleme parçası olarak sağlanan arabelleğin bölümlerine geçici olarak yazılmadığından düzeltildi. Bu değişiklik, Visual Studio 2017 15,8 ' de en fazla 4K boyutunda daha büyük okumalar için kazanılan performans avantajlarından bazılarını sağlar. Bununla birlikte, karakter başına üç sanal çağrının önünden kaçınmanın verimlilik geliştirmeleri hala mevcuttur.

### <a name="stdbitset-constructor"></a>`std::bitset` Oluşturucusu

`std::bitset` Oluşturucu artık büyük bitkümeler için ters sırada olanları ve sıfırları okumaktadır.

### <a name="stdpairoperator-regression"></a>gerileme `std::pair::operator=`

`std::pair`, [LWG 2729 ' de (std::p AIR:: operator = "; üzerinde SFINAE eksik](https://cplusplus.github.io/LWG/issue2729)) bir gerileme düzeltildi. Artık `std::pair` dönüştürülebilir türleri yeniden kabul eder.

### <a name="non-deduced-contexts-for-add_const_t"></a>`add_const_t` için çıkarılamayan bağlamlar

`add_const_t` ve ilgili işlevlerin çıkarılamayan bir bağlam olması beklenen küçük tür nitelikleri hatası düzeltildi. Diğer bir deyişle, `add_const_t` `const T`değil `typename add_const<T>::type`için bir diğer ad olmalıdır.

## <a name="update_162"></a>16,2 sürümündeki hata düzeltmeleri ve davranış değişiklikleri

### <a name="const-comparators-for-associative-containers"></a>İlişkilendirilebilir kapsayıcılar için const Karşılaştırıcılar

[Küme](../standard-library/set-class.md), [eşleme](../standard-library/map-class.md), [Çoklu küme](../standard-library/multiset-class.md)ve [multimap](../standard-library/multimap-class.md) 'teki arama ve ekleme için kod, daha az kod boyutu için birleştirildi. Ekleme işlemleri artık, arama işlemlerinin daha önce yapıldığı şekilde bir **const** karşılaştırma functor üzerinde daha az karşılaştırmayı çağırır. Aşağıdaki kod, Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' C3848 yükseltir:

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

Hatayı önlemek için, karşılaştırma işlecini **const**yapın:

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

Toplamlar için genelleştirilmiş **constexpr** ve statik olmayan veri üyesi başlatma (nsdmı) desteğiyle, Visual Studio 2017 ' deki C++ Microsoft derleyicisi artık c++ 14 standardına eklenen özellikler için tamamlanmıştır. Ancak, derleyicinin yine de C++ 11 ve C++ 98 standartlarından birkaç özelliği yoktur. Derleyicinin geçerli durumunu gösteren bir tablo için bkz. [Microsoft C++ dil uygunluğu tablosu](../visual-cpp-language-conformance.md) .

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++ 11: daha fazla kitaplıklarda Ifade SFıNAE desteği

Derleyici, şablon bağımsız değişken kesintisi ve **decltype** ve **constexpr** ifadelerinin şablon parametreleri olarak görünebileceği değiştirme için gerekli olan SFINAE ifadesi için desteğini iyileştirmeye devam etmektedir. Daha fazla bilgi için bkz. [Visual Studio 2017 RC 'de Expression SFINAE geliştirmeleri](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

### <a name="c14-nsdmi-for-aggregates"></a>C++ 14: toplamalar için NSDMı

Toplama, Kullanıcı tarafından sağlanmayan bir Oluşturucu olmayan, özel veya korumalı olmayan veri üyeleri olmayan, temel sınıf olmayan ve sanal işlevler içermeyen bir dizidir veya sınıftır. C++ 14 toplamalarda başlayarak üye başlatıcıları bulunabilir. Daha fazla bilgi için bkz. [üye başlatıcıları ve toplamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

### <a name="c14-extended-constexpr"></a>C++ 14: genişletilmiş **constexpr**

**Constexpr** olarak belirtilen ifadeler, if ve Switch deyimlerini, Loop deyimlerini ve yaşam süresi constexpr ifade değerlendirmesi içinde başlayan nesneler için bazı tür bildirimleri içermesine izin verilir. Ayrıca, **constexpr** statik olmayan bir üye işlevinin örtük olarak **const**olması gereken bir gereksinim yoktur. Daha fazla bilgi için bkz. [constexpr işlevleri üzerinde kısıtlamaları gevşme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html).

### <a name="c17-terse-static_assert"></a>C++ 17: terse `static_assert`

`static_assert` için ileti parametresi isteğe bağlıdır. Daha fazla bilgi için bkz. [genişletme static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

### <a name="c17-fallthrough-attribute"></a>C++ 17: `[[fallthrough]]` özniteliği

**/Std: c++ 17** modunda, `[[fallthrough]]` özniteliği, anahtar deyimlerinin bağlamında, derleyici için bir ipucu olarak, dönüş davranışının istendiği bir ipucu olarak kullanılabilir. Bu öznitelik, derleyicinin bu gibi durumlarda uyarı vermesini engeller. Daha fazla bilgi için bkz. [\]\] özniteliği aracılığıyla \[\[Fallfor ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

### <a name="generalized-range-based-for-loops"></a>For döngüleri için genelleştirilmiş Aralık tabanlı

Aralık tabanlı for döngüleri artık `begin()` ve `end()` aynı türdeki nesneleri döndürmesini gerektirmez. Bu değişiklik `end()`, [Range-v3](https://github.com/ericniebler/range-v3) içindeki aralıklar tarafından kullanılan bir Sentinel, ancak tam olarak yayımlanmış aralıklar teknik belirtimindeki bir Sentinel döndürmesini sağlar. Daha fazla bilgi için bkz. [Aralık tabanlı for döngüsünü Genelleştirme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a>15,3 sürümündeki uyumluluk geliştirmeleri

### <a name="constexpr-lambdas"></a>constexpr lambdaları

Lambda ifadeleri artık sabit ifadelerde kullanılabilir. Daha fazla bilgi için, bkz. [' de C++constexpr lambda ifadeleri ](../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>işlev şablonlarında **constexpr ise**

Bir işlev şablonu, derleme zamanı dallanmayı etkinleştirmek için **constexpr** deyimleri içerebilir. Daha fazla bilgi için bkz. [constexpr deyimleri](../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Başlatıcılarla seçim deyimleri

**IF** ifadesinde, bir değişkenin kendisi içerisindeki blok kapsamında bir değişken sunan bir başlatıcı bulunabilir. Daha fazla bilgi için bkz. [Başlatıcı ile IF deyimleri](../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybe_unused-and-nodiscard-attributes"></a>`[[maybe_unused]]` ve `[[nodiscard]]` öznitelikleri

Yeni öznitelik bir varlık kullanılmazsa susturces uyarılarını `[[maybe_unused]]`. `[[nodiscard]]` özniteliği, bir işlev çağrısının dönüş değeri atıldığı takdirde bir uyarı oluşturur. Daha fazla bilgi için bkz. [Içindeki C++öznitelikler ](../cpp/attributes.md).

### <a name="using-attribute-namespaces-without-repetition"></a>Öznitelik ad alanlarını tekrarsız kullanma

Öznitelik listesinde yalnızca tek bir ad alanı tanımlayıcısını etkinleştirmek için yeni sözdizimi. Daha fazla bilgi için bkz. [Içindeki C++öznitelikler ](../cpp/attributes.md).

### <a name="structured-bindings"></a>Yapılandırılmış bağlamalar

Tek bir bildirimde bir değeri, bileşenleri için bağımsız adlarla, değer bir dizi, bir `std::tuple` veya `std::pair`veya tüm ortak statik olmayan veri üyelerine sahip olacak şekilde depolamak için de mümkündür. Daha fazla bilgi için, bkz. [yapılandırılmış bağlamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) ve [bir işlevden birden çok değer döndürme](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>**Enum sınıfı** değerleri için oluşturma kuralları

Artık kapsamlı bir numaralandırmanın temel alınan türünden numaralandırmanın kendisine örtük/daraltılamayan bir dönüştürme, tanımı Numaralandırıcı olmadığında ve kaynak bir liste başlatma sözdizimi kullandığında. Daha fazla bilgi için bkz. [sabit listesi sınıfı değerleri](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) ve [numaralandırmalar](../cpp/enumerations-cpp.md#no_enumerators)için oluşturma kuralları.

### <a name="capturing-this-by-value"></a>Değere göre `*this` yakalama

Lambda ifadesindeki `*this` nesnesi artık değere göre yakalanamaz. Bu değişiklik, özellikle daha yeni makine mimarilerinde, lambda 'nin paralel ve zaman uyumsuz işlemlerde çağrıldığı senaryolara izin vermez. Daha fazla bilgi için, bu [\]\*\*\[= bu değere göre Lambda yakalama ](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)bölümüne bakın.

### <a name="removing-operator-for-bool"></a>**Bool** için `operator++` kaldırılıyor

`operator++` artık **bool** türlerinde desteklenmez. Daha fazla bilgi için bkz. [kullanım dışı Işleci Kaldır + + (bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

### <a name="removing-deprecated-register-keyword"></a>Kullanım dışı bırakılan **yazmaç** anahtar sözcüğü kaldırılıyor

Önceden kullanım dışı bırakılmış (ve derleyici tarafından yoksayılan) **yazmaç** anahtar sözcüğü artık dilden kaldırılmıştır. Daha fazla bilgi için bkz. [register anahtar sözcüğünün kullanım dışı kullanımını kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

## <a name="improvements_155"></a>15,5 sürümündeki uyumluluk geliştirmeleri

\[14] ile işaretlenen Özellikler **/std: c++ 14** modunda bile koşullu olarak kullanılabilir.

### <a name="new-compiler-switch-for-extern-constexpr"></a>**Extern constexpr** için yeni derleyici anahtarı

Visual Studio 'nun önceki sürümlerinde derleyici, değişken **extern**olarak işaretlenmiş olsa bile her zaman bir **constexpr** değişkeni iç bağlantısı vermiştir. Visual Studio 2017 sürüm 15,5 ' de yeni bir derleyici anahtarı olan [/Zc: externConstexpr](../build/reference/zc-externconstexpr.md), standartlara uygun doğru davranışı mümkün bir şekilde sunar. Daha fazla bilgi için bkz. [extern constexpr bağlantısı](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimleri kaldırılıyor

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) Dinamik özel durum belirtimleri C++ 11 ' de kullanımdan kaldırılmıştır. Özellik C++ 17 ' den kaldırılmıştır, ancak artık kullanım dışı `throw()` belirtimi, `noexcept(true)`için tamamen bir diğer ad olarak tutulur. Daha fazla bilgi için bkz. [dinamik özel durum belirtimi kaldırma ve noexcept](#noexcept_removal).

### `not_fn()`

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) `not_fn` `not1` ve `not2`' nin yerini alır.

### <a name="rewording-enable_shared_from_this"></a>Reifade `enable_shared_from_this`

[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this`, c++ 11 ' de eklenmiştir. C++ 17 standardı, belirli köşe durumlarını daha iyi işlemek için belirtimi güncelleştirir. [14]

### <a name="splicing-maps-and-sets"></a>Haritalar ve kümeler ile ayarlama

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) Bu özellik, daha sonra değiştirilebilecek ve aynı kapsayıcıya veya aynı düğüm türünü kullanan farklı bir kapsayıcıya eklenebilen ilişkilendirilebilir kapsayıcılardan (diğer bir deyişle, `map`, `set`, `unordered_map`, `unordered_set`) düğümlerin ayıklanmasını mümkün hale gelir. (Yaygın kullanım örneği, bir `std::map`bir düğümü ayıklamaya, anahtarı değiştirmenize ve yeniden ekleyebiliyor.)

### <a name="deprecating-vestigial-library-parts"></a>Kalıntı kitaplık parçalarını kullanımdan kaldırma

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) C++ Standart kitaplığın birkaç özelliği, yıllar üzerinde yeni özelliklerden değiştirilmiştir veya başka bir yöntem bulunamadı veya sorunlu. Bu özellikler, C++ 17 ' de resmi kullanım dışı bırakılmıştır.

### <a name="removing-allocator-support-in-stdfunction"></a>`std::function` ayırıcı desteği kaldırılıyor

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) C++ 17 ' den önce, sınıf şablonu `std::function` ayırıcı bağımsız değişkeni alan çeşitli oluşturuculara sahipti. Bununla birlikte, bu bağlamdaki ayırıcıların kullanımı sorunlu ve semantik anlaşılır değildi. Sorun bu sorundan kaldırılmıştır.

### <a name="fixes-for-not_fn"></a>`not_fn()` düzeltmeleri

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) `std::not_fn` için yeni ifade, sarmalayıcı çağrısında kullanıldığında değer kategorisinin yayılmasının desteğini sağlar.

### <a name="shared_ptrt-shared_ptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) Kitaplık temellerinde C++ 17 ' ye kadar değişiklik birleştirme `shared_ptr`. [14]

### <a name="fixing-shared_ptr-for-arrays"></a>Diziler için `shared_ptr` Düzeltme

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) Diziler için shared_ptr desteğine yönelik düzeltmeler. [14]

### <a name="clarifying-insert_return_type"></a>`insert_return_type` açıklığa kavuşturan

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) Benzersiz anahtarlarla ilişkilendirilebilir kapsayıcılar ve benzersiz anahtarlarla birlikte sıralanmamış kapsayıcılar, iç içe geçmiş bir tür `insert_return_type`döndüren `insert` bir üye işlevine sahiptir. Bu dönüş türü artık yineleyici ve kapsayıcının NodeType üzerinde parametreli olan bir türün özelleştirmesi olarak tanımlanmıştır.

### <a name="inline-variables-for-the-standard-library"></a>Standart Kitaplık için satır içi değişkenler

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>Ek D özellikleri kullanım dışı

C++ Standart ek D, `shared_ptr::unique()`, `<codecvt>`ve `namespace std::tr1`dahil olmak üzere kullanım dışı bırakılmış tüm özellikleri içerir. **/Std: c++ 17** derleyici anahtarı ayarlandığında, ek D içindeki standart kitaplık özelliklerinin neredeyse tamamı kullanım dışı olarak işaretlenir. Daha fazla bilgi için bkz. [Ek D Içindeki standart kitaplık özellikleri kullanım dışı olarak işaretlendi](#annex_d).

`<experimental/filesystem>` `std::tr2::sys` ad alanı artık **/std: c++ 14** ' in altında varsayılan olarak kullanımdan kaldırma uyarısı yayar ve varsayılan olarak **/std: c++ 17** altında kaldırılır.

Standart olmayan bir uzantıyı önleyerek `<iostream>` gelişmiş uyumluluk (sınıf içi açık uzmanlık).

Standart kitaplık artık değişken şablonları dahili olarak kullanmaktadır.

Standart Kitaplık, tür sisteminde **noexcept** ekleme ve dinamik özel durum belirtimlerini kaldırma dahil olmak üzere c++ 17 derleyici değişikliklerine yanıt olarak güncelleştirilmiştir.

## <a name="improvements_156"></a>15,6 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-library-fundamentals-v1"></a>C++ 17 kitaplık temelleri v1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) c++ 17 Için kitaplık temelleri teknik belirtimini standart olarak içerir. Deneysel/tanımlama > \<, deneysel/isteğe bağlı >, \<deneysel/işlevsel >, \<deneysel/any >, \<deneysel/string_view >, \<deneysel/bellek >, \<deneysel/memory_resource > ve \<deneysel/algoritma > \<.

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++ 17: standart kitaplık için sınıf şablonu bağımsız değişken kesintiyi geliştirme

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html) `scoped_lock`tutarlı kullanımını etkinleştirmek için `adopt_lock_t` `scoped_lock` parametre listesinin önüne taşıyın. Kopyalama atamasını etkinleştirmek için `std::variant` oluşturucusunun daha fazla durumda aşırı yükleme çözümüne katılmasına izin verin.

## <a name="improvements_157"></a>15,7 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-rewording-inheriting-constructors"></a>C++ 17: Reifade devralan oluşturucular

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

### <a name="c17-extended-aggregate-initialization"></a>C++ 17: genişletilmiş toplu başlatma

[P0017R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0017r1.html)

Bir temel sınıfın Oluşturucusu genel olmayan, ancak türetilmiş bir sınıf tarafından erişilebilir değilse, **/std: c++ 17** modu altında Visual Studio 2017 sürüm 15,7 ' de, türetilmiş türdeki bir nesneyi başlatmak için artık boş küme ayraçları kullanamazsınız.
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

C++ 17 ' de `Derived` artık toplam bir tür olarak kabul edilir. Bu, özel varsayılan oluşturucu aracılığıyla `Base` başlatmanın doğrudan genişletilmiş toplama başlatma kuralının bir parçası olarak meydana geldiğini gösterir. Daha önce, `Base` özel Oluşturucu `Derived` Oluşturucu aracılığıyla çağırılır ve arkadaş bildirimi nedeniyle başarılı oldu.
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

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++ 17: otomatik olarak tür olmayan şablon parametreleri bildirme

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

**/Std: c++ 17** modunda, derleyici artık **Otomatik**olarak belirtilen tür olmayan bir şablon bağımsız değişkeninin türünü verebilir:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Bu yeni özelliğin bir etkisi geçerli C++ 14 kodunun geçerli olmaması veya farklı anlambilime sahip olması olabilir. Örneğin, daha önce geçersiz olan bazı aşırı yüklemeler artık geçerlidir. Aşağıdaki örnekte, `example(p)` çağrısı `example(void*);`bağlandığı için derlenen C++ 14 kodu gösterilmektedir. Visual Studio 2017 sürüm 15,7 ' de, **/std: c++ 17** modunda, `example` işlevi şablonu en iyi eşleşmedir.

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

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++ 20: gereksiz Decay 'yi önleme (kısmi)

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf) "Decay" kavramı arasına farklılaşmayı ekler ve yalnızca const veya başvuru niteleyicilerini kaldırmaktır.  Yeni tür nitelik `remove_reference_t` bazı bağlamlarda `decay_t` değiştirir. `remove_cvref_t` için destek Visual Studio 2019 ' de uygulanır.

### <a name="c17-parallel-algorithms"></a>C++ 17: paralel algoritmalar

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html) Paralellik, küçük değişikliklerle standart olarak birleştirilir.

### <a name="c17-hypotx-y-z"></a>C++ 17: `hypot(x, y, z)`

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf) Her biri üç giriş parametresine sahip olan **float**, **Double**ve **Long Double**türleri için `std::hypot`üç yeni aşırı yükleme ekler.

### <a name="c17-filesystem"></a>C++ 17: \<dosya sistemi >

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html) Birkaç ifade değişikliği ile dosya sistemini standart olarak benimseme.

### <a name="c17-mathematical-special-functions"></a>C++ 17: matematik özel işlevleri

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) Matematik özel Işlevleri için önceki teknik belirtimleri standart \<cmath > başlığına benimseme.

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++ 17: standart kitaplık için kesinti Kılavuzu

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html) STL 'ye güncelleştirme, sınıf şablonu bağımsız değişkeni için destek ekleyen [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html)'in c++ 17 benimseme özelliğinden faydalanmak için.

### <a name="c17-repairing-elementary-string-conversions"></a>C++ 17: elemensel dize dönüşümlerini onarma

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html) Yeni elemensel dize dönüştürme işlevlerini P0067R5 ' dan yeni bir üstbilgiye \<charconv > taşıyın ve `std::error_code`yerine `std::errc` kullanmak üzere hata işlemeyi değiştirme dahil olmak üzere başka geliştirmeler yapın.

### <a name="c17-constexpr-for-char_traits-partial"></a>C++ 17: `char_traits` için **constexpr** (kısmi)

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) `std::traits_type` üye işlevlerindeki değişiklikler, `std::string_view` sabit ifadelerde kullanılabilir hale getirmek için `length`, `compare`ve `find`. (Visual Studio 2017 sürüm 15,6 ' de yalnızca Clang/LLVM için desteklenir. Sürüm 15,7 Preview 2 ' de, destek, ClXX için neredeyse tamamlanmıştır.)

## <a name="improvements_159"></a>15,9 sürümündeki uyumluluk geliştirmeleri

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>İşleçler `->*`, `[]`, `>>`ve `<<` için soldan sağa değerlendirme sırası

C++ 17 ' den başlayarak, operatörlerin işlenenleri `->*`, `[]`, `>>`ve `<<`, soldan sağa sırada değerlendirilmelidir. Derleyicinin bu sırayı garanti edemediği iki durum vardır:

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

### <a name="constexpr"></a>**constexpr**

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

Hatayı düzeltmek için `array::size()` işlevini **constexpr** olarak bildirin veya `f`**constexpr** niteleyicisi kaldırın.

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

CString kullanılarak oluşturulan ve yönetilen dizeler için, CString nesnesini biçim dizesi tarafından beklenen C işaretçisine dönüştürmek için, belirtilen `operator LPCTSTR()` kullanılmalıdır.

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

Hatayı düzeltmek için `operator int()` **const**olarak bildirin.

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

İfade-SFINAE 'yi desteklemek için, artık şablon örneği oluşturulan şablonlar olarak bildirildiğinde **decltype** bağımsız değişkenlerini ayrıştırır. Sonuç olarak, decltype bağımsız değişkeninde bağımlı olmayan bir özelleştirme bulunursa, örnekleme zamanına ertelenir. Anında işlenir ve bu sırada ortaya çıkan hatalar tanılandı.

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

Visual Studio 2015 ve önceki sürümlerde, bazı durumlarda derleyici varsayılan bir dizin oluşturucu olarak varsayılan bir özelliği yanlış tanımladı. Bu özelliğe erişmek için tanımlayıcıyı **varsayılan** olarak kullanarak soruna geçici bir çözüm olabilir. Geçici çözüm, C++ 11 ' de **varsayılan** anahtar sözcük olarak sunulduktan sonra sorunlu olur. Visual Studio 2017 ' de, geçici çözümü gerektiren hatalar düzeltildi ve **varsayılan** olarak bir sınıf için varsayılan özelliğe erişmek üzere kullanıldığında derleyici bir hata oluşturur.

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

Visual Studio 'nun önceki sürümlerinde, bazı durumlarda derleyici, çalışma zamanında kilitlenmelere neden olabilecek silinmiş üye şablonuna yönelik hatalı oluşturulmuş çağrılar için hata yaymayabilir. Aşağıdaki kod artık C2280 üretir: "' int S\<int >:: f\<int > (void) ': silinmiş bir işleve başvurulmaya çalışılıyor":

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

Hatayı onarmak için `i` **int**olarak bildirin.

### <a name="pre-condition-checks-for-type-traits"></a>Tür nitelikleri için koşul öncesi denetimler

Visual Studio 2017 sürüm 15,3, standart bir şekilde izlemek için tür nitelikleri için koşul öncesi denetimleri geliştirir. Bu tür bir denetim atanabilir içindir. Aşağıdaki kod, Visual Studio 2017 sürüm 15,3 ' de C2139 üretir:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yeni derleyici uyarısı ve çalışma zamanı, yerel-yönetilen sıralamaya göre denetler

Yönetilen işlevlerden yerel işlevlere çağırma sıralama gerektirir. CLR sıralama yapar, ancak semantiğini anlamıyor C++ . Bir yerel nesneyi değere göre geçirirseniz, CLR nesnenin kopya oluşturucusunu çağırır veya `BitBlt`kullanır ve bu da çalışma zamanında tanımsız davranışlara neden olabilir.

Artık derleyici, silinen kopya ctor ile yerel bir nesnenin değere göre yerel ve yönetilen sınır arasında geçtiğini bildiren bir uyarı yayar. Derleyicinin derleme zamanında tanımadığı bu durumlarda, hatalı oluşturulmuş bir sıralama gerçekleştiğinde programın hemen `std::terminate` çağırması için bir çalışma zamanı denetimi çıkarır. Visual Studio 2017 sürüm 15,3 ' de, aşağıdaki kod "' A" uyarı C4606 oluşturur: yerel ve yönetilen sınır içindeki değere göre bağımsız değişken geçirme geçerli bir kopya Oluşturucu gerektirir. Aksi takdirde, çalışma zamanı davranışı tanımsızdır.

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

Hatayı onarmak için `#pragma managed` yönergesini kaldırarak çağıranın yerel olarak işaretlenmesi ve sıralama yapmaktan kaçının.

### <a name="experimental-api-warning-for-winrt"></a>WinRT için deneysel API uyarısı

Deneme ve geri bildirim için yayımlanan WinRT API 'Leri `Windows.Foundation.Metadata.ExperimentalAttribute`ile donatılmış. Visual Studio 2017 sürüm 15,3 ' de, derleyici özniteliğiyle karşılaştığında uyarı C4698 oluşturur. Önceki Windows SDK sürümlerinden birkaç API zaten özniteliğiyle birlikte tasarlanmıştır ve bu API 'lere yapılan çağrılar artık bu derleyici uyarısını tetikler. Daha yeni Windows SDK 'Ları, tüm sevk edilen türlerden kaldırılan özniteliğe sahiptir, ancak eski bir SDK kullanıyorsanız, sevk edilen türlere yapılan tüm çağrılar için bu uyarıları bastırın.

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

### <a name="attempting-to-take-the-address-of-this-pointer"></a>**Bu** işaretçinin adresi alınmaya çalışılıyor

C++ **Bu** , X için işaretçi türünde bir prvalue olamaz. **Bunun** adresini alamaz veya bir lvalue başvurusuna bağlayabilirsiniz. Visual Studio 'nun önceki sürümlerinde derleyici, bu kısıtlamayı bir cast kullanarak atlatmayı sağlar. Visual Studio 2017 sürüm 15,3 ' de, derleyici C2664 hatasını üretir.

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

Şablon sınıflarındaki üye işlevlerinin satır dışı tanımlarında varsayılan bağımsız değişkenlere izin verilmez. Derleyici, **/izin**altında bir uyarı verecek ve [/Permissive-](../build/reference/permissive-standards-conformance.md)altında bir sabit hata verecek.

Visual Studio 'nun önceki sürümlerinde, aşağıdaki hatalı oluşturulmuş kod, çalışma zamanı kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3, uyarı C5034: ' A\<T >:: f ': bir sınıf şablonu üyesinin bir satır dışı tanımı varsayılan bağımsız değişkenlere sahip olamaz:

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

Hatayı onarmak için `= false` varsayılan bağımsız değişkenini kaldırın.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Bileşik üye göstergesi ile `offsetof` kullanımı

Visual Studio 2017 sürüm 15,3 ' de, *a* 'nın "bileşik üye göstergesi" olduğu `offsetof(T, m)` kullanmak, **/duvar** seçeneğiyle derlerken uyarı vererek sonuçlanır. Aşağıdaki kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3 "uyarı C4841: standart olmayan uzantı kullanıldı: OffsetOf içinde bileşik üye göstergesi":

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Kodu onarmak için, uyarıyı bir pragma ile devre dışı bırakın ya da kodu kullanmayın `offsetof`değiştirin:

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Statik veri üyesi veya üye işlevi ile `offsetof` kullanma

Visual Studio 2017 sürüm 15,3 ' de, bir statik veri üyesine veya üye *işleve başvurduğu `offsetof(T, m)`* kullanmak bir hatayla sonuçlanır. Aşağıdaki kod, "Error C4597: tanımsız davranış: ' example '" ve "Error C4597: tanımsız davranış: ' Sample ' ' örneğine uygulanmış olan ' örnek ' üye işlevine yönelik OffsetOf uygulandı:

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

### <a name="declspec"></a>`__declspec` özniteliklerde yeni uyarı

Visual Studio 2017 sürüm 15,3 ' de, `extern "C"` bağlantı belirtiminden önce `__declspec(...)` uygulanmışsa derleyici artık öznitelikleri yok sayar. Daha önce derleyici, çalışma zamanı etkilerine sahip olabilecek özniteliğini yoksayacaktır. **/Duvar** ve **/WX** seçenekleri ayarlandığında, aşağıdaki kod "uyarı C4768: __declspec öznitelikleri bağlantı belirtiminin yoksayılmadan önce":

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarıyı onarmak için önce `extern "C"` yerleştirin:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı, varsayılan olarak 15,3 ' de, ancak varsayılan olarak 15,5 ' de kapalıdır ve yalnızca **/duvar/WX**ile derlenen kodu etkiler.

### <a name="decltype-and-calls-to-deleted-destructors"></a>**decltype** ve silinen yıkıcıları çağrıları

Visual Studio 'nun önceki sürümlerinde, derleme, **decltype**ile ilişkili ifade bağlamında silinmiş yıkıcıya yapılan bir çağrının gerçekleştiği zaman tespit etmedi. Visual Studio 2017 sürüm 15,3 ' de, aşağıdaki kod "hata C2280: ' A\<T >:: ~ A (void) ': silinmiş bir işleve başvurulmaya çalışılıyor":

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

Visual Studio 2017 RTW sürümünde, C++ bir **const** değişkeni başlatılmamışsa derleyicinin tanılama yayınlamadığı bir gerileme vardı. Bu gerileme, Visual Studio 2017 sürüm 15,3 ' de düzeltildi. Aşağıdaki kod şimdi "uyarı C4132: ' Value ': const nesne başlatılmalıdır":

```cpp
const int Value; //C4132
```

Hatayı düzeltemedi `Value`için bir değer atayın.

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

### <a name="stdis_convertible-for-array-types"></a>dizi türleri için `std::is_convertible`

Derleyicinin önceki sürümleri, dizi türleri için [std:: is_convertible](../standard-library/is-convertible-class.md) hatalı sonuçlar verdi. Bu gerekli kitaplık yazarları, Microsoft C++ derleyicisine nitelik `std::is_convertible<...>` türü kullanılırken özel durum sağlar. Aşağıdaki örnekte, statik onaylar Visual Studio 'nun önceki sürümlerinde geçer ancak Visual Studio 2017 sürüm 15,3 ' de başarısız olur:

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

### <a name="private-destructors-and-stdis_constructible"></a>Özel Yıkıcılar ve `std::is_constructible`

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

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: belirsiz aşırı yükleme çözümü

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

Kodu onarmak için, `::f()`çağırmayı amaçlıyorsanız, using `N::f` ifadesini kaldırın.

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

Sorunu gidermek için `f(S)` imzasını değiştirin ya da kaldırın.

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

Dizi veya işlev türüne başvuru işleyicileri hiçbir bir özel durum nesnesi için hiçbir şekilde eşleşmez. Derleyici artık bu kurala göre doğru şekilde uyarın ve 4. düzey bir uyarı oluşturur. Ayrıca, **/Zc: strictStrings** kullanıldığında bir `char*` veya `wchar_t*` işleyicisiyle bir dize değişmez değerine eşleşmez.

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

### <a name="tr1"></a>`std::tr1` ad alanı kullanım dışıdır

Standart olmayan `std::tr1` ad alanı artık hem C++ 14 hem de C++ 17 modlarında kullanım dışı olarak işaretlendi. Visual Studio 2017 sürüm 15,5 ' de aşağıdaki kod C4996 yükseltilir:

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

### <a name="__declspec-attributes-with-extern-c-linkage"></a>`extern "C"` bağlantısı olan öznitelikleri `__declspec`

Visual Studio 'nun önceki sürümlerinde, `extern "C"` bağlantı belirtiminden önce `__declspec(...)` uygulandığında derleyici `__declspec(...)` öznitelikleri yok sayılır. Bu davranış, olası çalışma zamanı etkilerine karşı kullanıcının istememiş kodu oluşturulmasına neden oldu. Uyarı Visual Studio sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak etkindir.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
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

### <a name="extern_linkage"></a>Extern constexpr bağlantısı

Visual Studio 'nun önceki sürümlerinde derleyici, değişken **extern**olarak işaretlenmiş olsa bile her zaman bir **constexpr** değişkeni iç bağlantısı vermiştir. Visual Studio 2017 sürüm 15,5 ' de, yeni bir derleyici anahtarı ( **/Zc: externConstexpr**) standartlara uygun doğru davranışı mümkün bir şekilde sunar. Sonuç olarak bu davranış varsayılan olur.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Üst bilgi dosyası **extern constexpr**olarak tanımlanmış bir değişken içeriyorsa, yinelenen bildirimlerinin doğru şekilde birleştirilmesi için `__declspec(selectany)` işaretlenmesi gerekir:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>**TypeId** , eksik sınıf türünde kullanılamaz

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

`std::is_convertible`, hedef türün geçerli bir dönüş türü olmasını gerektirir. Visual Studio 'nun önceki sürümlerinde, derleyici yanlış bir aşırı yükleme çözümüne ve istenmeyen çalışma zamanı davranışına neden olabilecek soyut türlere yanlış izin verebilir.  Aşağıdaki kod artık C2338 öğesini doğru şekilde yükseltir:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Hatayı önlemek için `is_convertible` kullanırken işaretçi türlerini karşılaştırmanız gerekir, çünkü bir tür soyut ise işaretçi türü olmayan bir karşılaştırma başarısız olabilir:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="noexcept_removal"></a>Dinamik özel durum belirtimi kaldırma ve **noexcept**

C++ 17 ' de `throw()` **noexcept**için bir diğer addır, `throw(<type list>)` ve `throw(...)` kaldırılır ve belirli türler **noexcept**içerebilir. Bu değişiklik, C++ 14 veya daha önceki bir sürümüyle uyumlu kodla kaynak uyumluluk sorunlarına neden olabilir. **/Zc: noexceptTypes-** Switch, genel olarak c++ 17 modu kullanılırken **noexcept** 'nin c++ 14 sürümüne dönmek için kullanılabilir. Bu, tüm `throw()` kodunuzu aynı anda yeniden yazmak zorunda kalmadan, kaynak kodunuzu C++ 17 ' ye uyacak şekilde güncelleştirmenize olanak sağlar.

Derleyici Ayrıca C++ 17 modundaki bildirimlerde veya New Warning C5043 ile [/Permissive-](../build/reference/permissive-standards-conformance.md) ile daha fazla uyuşmayan özel durum belirtimini de tanılar.

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

Yine de **/std: c++ 17**kullanırken hataları kaldırmak için **/Zc: noexceptTypes-** anahtarını komut satırına ekleyin ya da aşağıdaki örnekte gösterildiği gibi kodunuzu **noexcept**kullanacak şekilde güncelleştirin:

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

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)` uyarı C4768 Şu anda varsayılan olarak açık

Uyarı Visual Studio 2017 sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak açık olur. Daha fazla bilgi için, [\_\_declspec öznitelikleri hakkında yeni uyarı](#declspec)bölümüne bakın.

### <a name="defaulted-functions-and-__declspecnothrow"></a>Varsayılan işlevler ve `__declspec(nothrow)`

Derleyici, karşılık gelen temel/üye işlevleri özel durumlara izin verildiğinde, önceden ayarlanmış işlevlerin `__declspec(nothrow)` ile bildirilmesine izin verilir. Bu davranış, C++ standardının aksine, çalışma zamanında tanımsız davranışlara neden olabilir. Özel durum belirtimi uyumsuzluğu varsa, standart bu tür işlevlerin silinmiş olarak tanımlanmasını gerektirir.  **/Std: c++ 17**' nin altında, aşağıdaki kod, *silinen bir Işleve başvuru yapmaya C2280 yayınlar. Açık özel durum belirtimi örtük bildirimdekilerle uyumsuz olduğundan işlev örtük olarak silindi.*

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

Bu kodu düzeltmek için, varsayılan işlevden __declspec (nothrow) ' ı kaldırın ya da `= default` kaldırın ve gerekli özel durum işlemeyle birlikte işlev için bir tanım sağlayın:

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

### <a name="noexcept-and-partial-specializations"></a>**noexcept** ve kısmi uzmanlık

Tür sisteminde **noexcept** ile, belirli "çağrılabilir" türlerin eşleşmesi için kısmi özelleşmeler,-noexcept işlevleri için eksik kısmi bir özelleştirme nedeniyle birincil şablonu derleyip seçemeyebilir.

Bu gibi durumlarda, **noexcept** işlev işaretçilerini ve **noexcept** işaretçilerini üye işlevlerine işlemek için ek kısmi specialler eklemeniz gerekebilir. Bu aşırı yüklemeler yalnızca **/std: c++ 17** modunda geçerlidir. C++ 14 ile geriye dönük uyumluluk korunuyorsa ve başkalarının tükettiği bir kod yazıyorsanız, bu yeni yüklerini `#ifdef` yönergeleri içinde korumalısınız. Bağımsız bir modülde çalışıyorsanız, `#ifdef` koruyucuları kullanmak yerine, **/Zc: noexceptTypes-** Switch ile yalnızca derleme yapabilirsiniz.

Aşağıdaki kod **/std: c++ 14** altında derlenir, ancak **/std: c++ 17** altında "Error C2027: tanımsız tür kullanımı ' A\<t > '" ile başarısız olur:

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

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++ 17: birincil Sınıf şablonunda varsayılan bağımsız değişken

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

Aşağıdaki örnekte, Visual Studio 15,6 ve önceki sürümlerde derleyici, birincil Sınıf şablonunda `B<T>::type` `D::type` çözümleniyor.

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

Visual Studio 2017 sürüm 15,7, **/std: c++ 17** modunda, D içindeki **using** ifadesinde**TypeName** anahtar sözcüğü gerektirir. **TypeName**olmadan, derleyici uyarı C4346: *' B < T\*>:: Type ': bağımlı ad bir tür değil* ve C2061: *sözdizimi hatası: tanımlayıcı ' Type '* :

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

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++ 17: `[[nodiscard]]` özniteliği-uyarı düzeyi artış

**/Std: c++ 17** modunda Visual Studio 2017 sürüm 15,7 ' de, C4834 uyarı düzeyi ("' noDiscard ' özniteliği ile işlevin dönüş değerini atma), W3 'den W1 'e yükseltilir. Bir tür **void**ile veya derleyiciye **/WD: 4834** geçirerek uyarıyı devre dışı bırakabilirsiniz

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Değişken bağımsız değişken şablon Oluşturucusu temel sınıf başlatma listesi

Visual Studio 'nun önceki sürümlerinde, şablon bağımsız değişkenleri eksik olan bir bağımsız değişken şablon Oluşturucu temel sınıf başlatma listesine hatasız olarak izin veriliyor. Visual Studio 2017 sürüm 15,7 ' de bir derleyici hatası tetiklenir.

Visual Studio 2017 sürüm 15,7 ' deki aşağıdaki kod örneği, *C2614: D\<int >: geçersiz üye başlatma: ' B ' bir taban veya üye değil*

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

Hatayı onarmak için B () ifadesini B\<T > () olarak değiştirin.

### <a name="constexpr-aggregate-initialization"></a>**constexpr** toplu başlatma

Derleyicinin önceki sürümleri, C++ **constexpr** toplama başlatması yanlış işlendi; toplama-init listesinde çok fazla öğe olduğu ve kendisi için hatalı CodeGen üreten geçersiz kodu kabul etti. Aşağıdaki kod bu kodun bir örneğidir:

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

Visual Studio 2017 sürüm 15,7 güncelleştirme 3 ve sonraki sürümlerde, önceki örnek *C2078 çok fazla Başlatıcı*oluşturuyor. Aşağıdaki örnek, kodun nasıl düzeltileceğini gösterir. İç içe küme ayracı-init-Lists ile bir `std::array` başlatırken, iç diziye kendi kendine açılan bir liste verin:

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

###<a name="typename-on-unqualified-identifiers"></a>Nitelenmemiş tanımlayıcılardaki **TypeName**

[/Permissive-](../build/reference/permissive-standards-conformance.md) modunda, diğer ad şablonu tanımlarında nitelenmemiş tanımlayıcılarda bulunan spurertypename anahtar sözcükleri artık derleyici tarafından kabul edilmez. Aşağıdaki kod şu anda C7511 *'t ': ' TypeName ' anahtar sözcüğünün ardından tam bir ad*gelmelidir:

```cpp
template <typename T>
using  X = typename T;
```

Hatayı onarmak için ikinci satırı `using  X = T;`değiştirin.

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>diğer ad şablonu tanımlarının sağ tarafında `__declspec()`

diğer ad şablon tanımının sağ tarafında [__declspec](../cpp/declspec.md) artık izin verilmiyor. Bu kod önceden kabul edildi ancak derleyici tarafından yoksayıldı ve diğer ad kullanıldığında hiçbir zaman kullanımdan kaldırma uyarısı ile sonuçlanmaz.

Standart C++ öznitelik [\[kullanım dışı \[\]\]](../cpp/attributes.md) yerine kullanılabilir ve Visual Studio 2017 sürüm 15,6 ' de vardır. Aşağıdaki kod şu anda C2760 *sözdizimi hatası veriyor: beklenmeyen belirteç ' __declspec ', beklenen ' tür belirleyici '* :

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

Bu şekilde bildirimde bulunan tek bir yöntem, bağımlı temel sınıflara aramalardır. Daha önce, derleyici, bağımlı taban sınıflarında tanımlanan adların kullanılmasına izin verdiklerinden, tüm türler çözümlendiğinde örnekleme sırasında aranabilir. Artık bu kod bir hata olarak kabul edilir. Bu durumlarda, değişkeni temel sınıf türü ile niteleyerek veya bir `this->` işaretçisi ekleyerek bağımlı hale getirerek, örneği örnekleme sırasında girmeye zorlayabilirsiniz.

[/Permissive-](../build/reference/permissive-standards-conformance.md) modunda şu kod şu anda C3861: *' base_value ': tanımlayıcı bulunamadı*:

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

Hatayı onarmak için `return` ifadesini `return this->base_value;`olarak değiştirin.

**Note:** Yükseltme Python kitaplığı 'nda [unwind_type. hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp)içindeki şablon iletme BILDIRIMI için MSVC 'e özgü bir geçici çözüm daha vardır. [/Permissive-](../build/reference/permissive-standards-conformance.md) modunun altında, Visual Studio 2017 sürüm 15,8 ' den (_MSC_VER = 1915) başlayarak, MSVC derleyicisi bağımsız değişkene bağımlı ad araması (adl) ve diğer derleyicilerle tutarlıdır, bu geçici çözüm koruma gereksiz hale getirir. Hata *C3861: ' unwind_type ': tanımlayıcı bulunamadı*, üst bilgi dosyasını güncelleştirmek için yükseltme deposunda [PR 229](https://github.com/boostorg/python/pull/229) ' a bakın. [Vcpkg](../build/vcpkg.md) Boost paketini zaten geliştirdik. bu nedenle, Boost kaynaklarınızı vcpkg 'dan edinmeniz veya yükseltmeniz durumunda düzeltme ekini ayrı olarak uygulamanız gerekmez.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>ad alanındaki iletme bildirimleri ve tanımları `std`

Standart C++ , bir kullanıcının ad alanına iletme bildirimleri veya tanımları eklemesine izin vermez `std`. Ad alanı `std` veya ad uzayı `std` içindeki bir ad alanına bildirim veya tanım ekleme artık tanımsız davranışa neden olur.

Daha sonra, Microsoft, bazı standart kitaplık türlerinin tanımlandığı konumu taşıyacaktır. Bu değişiklik, ad alanına iletme bildirimleri ekleyen mevcut kodu keser `std`. Yeni bir uyarı olan C4643, bu tür kaynak sorunları belirlemenize yardımcı olur. Bu uyarı, **/Default** modunda etkinleştirilir ve varsayılan olarak kapalıdır. **/Duvarveya** **/WX**ile derlenen programları etkileyecektir.

Aşağıdaki kod artık C4643 ' i yükseltir: *std ad alanındaki ileri bildirim ' vector ' öğesine C++ standart tarafından izin verilmiyor*.

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

Standart C++ , bir derleyicinin kendi kendine temsilci Oluşturucu temsilcisinden bir tanı yaymalıdır. C++ [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) ve [/std: c + + en son](../build/reference/std-specify-language-standard-version.md) modlarında Microsoft derleyicisi artık C7535: *' X:: X ': temsilci Oluşturucu kendisini çağırır*.

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

### <a name="offsetof-with-constant-expressions"></a>Sabit ifadelerle `offsetof`

[OffsetOf](../c-runtime-library/reference/offsetof-macro.md) , geleneksel olarak [reinterpret_cast](../cpp/reinterpret-cast-operator.md)gerektiren bir makro kullanılarak uygulanmıştır. Bu kullanım, sabit bir ifade gerektiren bağlamlarda geçersizdir, ancak Microsoft C++ derleyicisinin geleneksel olarak BT 'ye izin verilir. Standart kitaplığın bir parçası olarak gönderilen `offsetof` makrosu, bir derleyici iç ( **__builtin_offsetof**) kullanır, ancak pek çok kişi makro eli kullanarak kendi `offsetof`tanımlarlar.

Visual Studio 2017 sürüm 15,8 ' de, derleyici bu `reinterpret_cast` işleçlerinin varsayılan modda görünebilen alanı kısıtlar. Bu, kodun standart C++ davranışa uymasını sağlar. [/Permissive-](../build/reference/permissive-standards-conformance.md)altında kısıtlamalar bile daha sıkı bir şekilde yapılır. Sabit ifadeler gerektiren konumlarda `offsetof` sonucunun kullanılması, *sabit ifadelerde makro tabanlı OffsetOf deseninin uyarı C4644 kullanımı standart değildir; Bunun yerine C++ standart kitaplıkta* veya C2975 geçersiz şablon bağımsız değişkeni olarak tanımlanan OffsetOf kullanın *, derleme zamanı sabit ifadesi bekleniyor*.

Aşağıdaki kod, **/Default** ve **/std: C++ 17** modlarında C4644 ve [/Permissive-](../build/reference/permissive-standards-conformance.md) modunda C2975 ' i başlatır:

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

Hatayı onarmak için, \<cstddef > ile tanımlanan `offsetof` kullanın:

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

Visual Studio 2017 sürüm 15,8 ' de, [/Permissive-](../build/reference/permissive-standards-conformance.md) modda şu kod C3770 *' const S ': geçerli bir temel sınıf değil*:

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>**şablon** anahtar sözcüğü ve iç içe ad tanımlayıcıları

[/Permissive-](../build/reference/permissive-standards-conformance.md) modunda, derleyici artık **şablon** anahtar sözcüğünün, bağımlı bir iç içe-ad belirleyicisi öğesinden sonra geldiği sırada şablon adının önünde olmasını gerektirir.

[/Permissive-](../build/reference/permissive-standards-conformance.md) modundaki şu kod artık C7510: *' example ': bağımlı şablon adının kullanımı ' Template ' önekini almalıdır. Note: derlenen ' X<T>' sınıf şablonu örneklemesine yönelik başvuruya bakın*:

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

Hatayı onarmak için aşağıdaki örnekte gösterildiği gibi, `Base<T>::example<int>();` ifadesine **şablon** anahtar sözcüğünü ekleyin:

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

Visual Studio 2017 sürüm 15,9 ' de, [/Permissive-](../build/reference/permissive-standards-conformance.md) modunda derleyici C3861: *' from_template ': tanımlayıcı bulunamadı*.

Hatayı onarmak için `from_template_t`önce `from_template` bildirin.

### <a name="modules-changes"></a>Modül değişiklikleri

Visual Studio 2017, sürüm 15,9 ' de, modüller için komut satırı seçenekleri modül oluşturma ve modül tüketim tarafları arasında tutarlı olmadığı zaman derleyici C5050 ' u yükseltir. Aşağıdaki örnekte, iki sorun vardır:

- Tüketim tarafında (Main. cpp), **/EHsc** seçeneği belirtilmez.

- C++ Sürüm, oluşturma tarafında **/std: c++ 17** ve tüketim tarafında **/std: c++ 14** ' dir.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Derleyici, bu durumların her ikisi için C5050 yükseltir: *Uyarı C5050: modül içeri aktarılırken olası uyumsuz ortam ': eşleşmeyen C++ sürümler.  Geçerli "201402" modül sürümü "201703"* .

Derleyici Ayrıca,. ifc dosyası ile oynanmış her seferinde C7536 ' i de yükseltir. Modül arabiriminin üstbilgisi, altındaki içeriklerin SHA2 karmasını içerir. İçeri aktarma işleminde,. ifc dosyası aynı şekilde karma hale getirilir ve üst bilgide belirtilen karmayla denetlenir. Bunlar eşleşmiyorsa hata C7536 tetiklenir: *IFC başarısız bütünlük denetimleri.  Beklenen SHA2: ' 66d5c8154df0c71d4cab7665be4a125c7ce5cb9a401a4d8b461b706ddd771c6 '* .

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Diğer adlar ve çıkarılamayan bağlamlarla ilgili Kısmi sıralama

Çıkarılamayan bağlamlardaki diğer adları içeren kısmi sıralama kurallarında uygulamalar birbirinden ayrılan uygulamalardır. Aşağıdaki örnekte, GCC ve Microsoft C++ derleyicisi ( [/Permissive-](../build/reference/permissive-standards-conformance.md) modda), Clang kodu kabul ettiğinde bir hata yükseltir.

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

Geçici bir çözüm olarak, bu sorunu çözmek için kısmi sıralamaya güvenmemelisiniz. Bunun yerine, belirli aşırı yüklemeleri kaldırmak için SFıNAE kullanın. Aşağıdaki örnekte, `Alloc` bir `A`özelleştirmesi olduğunda ilk aşırı yüklemeyi kaldırmak için `IsA` bir yardımcı sınıfı kullanıyoruz:

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

Hatayı önlemek için `f()`işlevin açık örneklemesi olan **constexpr** niteleyicisi kaldırın.

::: moniker-end

::: moniker range="vs-2015"

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>C++Visual Studio 2015 uyumluluk geliştirmeleri

Visual Studio 2015 güncelleştirme 3 aracılığıyla uyumluluk geliştirmelerinden oluşan tüm liste için bkz. [Visual C++ Studio 'nun yenilikler 2003-2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft C++ dil uygunluk tablosu](../visual-cpp-language-conformance.md)
