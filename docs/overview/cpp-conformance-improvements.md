---
title: C++ uygunluk iyileştirmeleri
ms.date: 03/16/2020
description: Visual Studio'daki Microsoft C++ C++20 dil standardına tam uyumluluk yolunda ilerliyor.
ms.technology: cpp-language
ms.openlocfilehash: 2309e79acb4784cd2e79b4f3f6fffb29e8d5dea8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353533"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Visual Studio 2017’deki C++ uyumluluk geliştirmeleri

Microsoft C++ her sürümde uyumluluk geliştirmeleri ve hata düzeltmeleri yapar. Bu makalede, büyük sürüm, daha sonra sürümü tarafından iyileştirmeler listeler. Ayrıca, sürüme göre büyük hata düzeltmelerini listeler. Belirli bir sürümün değişikliklerine doğrudan atlamak için **bu makaledeki listeyi** kullanın.

::: moniker range="vs-2019"

## <a name="conformance-improvements-in-visual-studio-2019-rtw-version-160"></a><a name="improvements_160"></a>Visual Studio 2019 RTW'de uygunluk iyileştirmeleri (sürüm 16.0)

Visual Studio 2019 RTW, Microsoft C++ derleyicisinde (MSVC) aşağıdaki uyumluluk geliştirmelerini, hata düzeltmelerini ve davranış değişikliklerini içerir

**Not:** C++20 özellikleri hem derleyici hem de IntelliSense için C++20 uygulaması tamamlanana kadar modda `/std:c++latest` kullanıma sunulacaktır. O zaman, `/std:c++20` derleyici modu tanıtılır.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modül desteği

Modüller artık resmi olarak C++20 standardındadır. Visual Studio 2017 sürüm 15.9'a geliştirilmiş destek eklendi. Daha fazla bilgi için, [MSVC 2017 sürüm 15.9 ile C++ Modüllerinde daha iyi şablon desteği ve hata algılama](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/)bilgisine bakın.

### <a name="modified-specification-of-aggregate-type"></a>Agrega türünün değiştirilmiş belirtimi

Toplam türünün belirtimi C++20'de değiştirildi (bkz. [kullanıcı tarafından bildirilen yapıcılarla toplamaları yasakla).](https://wg21.link/p1008r1) Visual Studio `/std:c++latest`2019'da, kullanıcı tarafından bildirilen herhangi bir oluşturucuya sahip bir `= default` `= delete`sınıf (örneğin, bildirilen bir oluşturucu dahil veya) bir toplam değildir. Önceden, yalnızca kullanıcı tarafından sağlanan oluşturucular bir sınıfı toplam olmaktan diskalifiye ederdi. Bu değişiklik, bu tür türlerin nasıl baş harfe alınabileceği konusunda ek kısıtlamalar getirir.

Aşağıdaki kod Visual Studio 2017'de hatasız derlenmiştir ancak Visual Studio 2019'da C2280 ve C2440 hatalarını gündeme `/std:c++latest`getirmektedir:

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

### <a name="partial-support-for-operator-"></a>Kısmi destek için`operator <=>`

[P0515R3](https://wg21.link/p0515r3) C++20, "uzay gemisi işleci" olarak da bilinen `<=>` üç yönlü karşılaştırma işlecisini tanıtır. Visual Studio 2019 modunda `/std:c++latest` şimdi izin verilmeyen sözdizimi için hataları yükselterek operatör için kısmi destek tanıtır. Örneğin, Aşağıdaki kod Visual Studio 2017'de hatasız derler ancak Visual Studio `/std:c++latest`2019'da aşağıdaki gibi birçok hata yı karşılar:

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

Hataları önlemek için, son açı ayracından önce rahatsız edici `U<&S::operator<= > u;`satıra bir boşluk ekleyin: .

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Eşleşmemiş cv niteleyicileri olan türlere başvurular

Daha önce, MSVC üst düzeyin altında uyumsuz cv elemeleri ile bir tür bir referans doğrudan bağlama izin verdi. Bu bağlama, başvuru tarafından atıfta bulunulan sözde const verilerin değiştirilmesine izin verebilir. Derleyici şimdi standart tarafından gerekli olarak, geçici bir oluşturur. Visual Studio 2017'de aşağıdaki kod uyarı yapılmadan derlenmiştir. Visual Studio 2019'da derleyici *C4172 \<uyarısını gündemePData@X getiriyor: func:#1 "? @@QBEABQBXXZ"> yerel değişken veya geçici dönen adresi*.

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

### <a name="reinterpret_cast-from-an-overloaded-function"></a>`reinterpret_cast`aşırı yüklü bir fonksiyondan

Bağımsız değişken, aşırı yüklenen bir işlevin adresine izin verilen bağlamlardan biri `reinterpret_cast` değildir. Aşağıdaki kod Visual Studio 2017'de hatasız olarak derlenir, ancak Visual Studio 2019'da *C2440'ı yükseltir: 'aşırı yüklü işlev'den 'fp'ye dönüştüremez:*

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

Hatayı önlemek için, bu senaryo için izin verilen bir döküm kullanın:

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>Lambda kapakları

C++14'te lambda kapatma türleri edebi değildir. Bu kuralın birincil sonucu bir lambda bir **constexpr** değişken atanmamış olabilir. Aşağıdaki kod Visual Studio 2017'de hatasız olarak derlenmiştir, ancak Visual Studio 2019'da *C2127'yi yükseltir: 'l': 'constexpr' varlığının sürekli olmayan bir ifadeyle yasa dışı olarak başlatılması:*

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Hatayı önlemek için **constexpr** niteleyicisini kaldırın veya uygunluk modunu 'da ' olarak `/std:c++17`değiştirin

### <a name="stdcreate_directory-failure-codes"></a>`std::create_directory`hata kodları

[P1164'](https://wg21.link/p1164r1) ün C++20' den koşulsuz olarak uygulanması. Bu, `std::create_directory` hedefin zaten bir hata dizini olup olmadığını denetlemek için değişir. Önceden, tüm ERROR_ALREADY_EXISTS türü hataları başarı ama-directory-değil oluşturulan kodlar dönüştürüldü.

### `operator<<(std::ostream, nullptr_t)`

Başına [LWG 2221](https://cplusplus.github.io/LWG/issue2221), akışları nullptrs yazmak için eklendi. `operator<<(std::ostream, nullptr_t)`

### <a name="additional-parallel-algorithms"></a>Ek paralel algoritmalar

Yeni paralel `is_sorted`versiyonları `is_partitioned` `set_difference`, `set_intersection` `is_sorted_until` `is_heap`, `is_heap_until`, , , ve .

### <a name="atomic-initialization"></a>atomik başlatma

[P0883 "Atomik başlatmayı düzeltme"](https://wg21.link/p0883r1) varsayılan olarak başlatılması yerine içerdiği T'yi değer-initialize etmek için değişir. `std::atomic` Düzeltme, Microsoft standart kitaplığı yla Clang/LLVM kullanırken etkinleştirilir. Şu anda **Constexpr** işleme bir hata için geçici çözüm olarak, Microsoft C++ derleyicisi için devre dışı bırakılır.

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` ve `remove_cvref_t`

`remove_cvref` `remove_cvref_t` [P0550'den](https://wg21.link/p0550r2)uygulanan ve tip özellikleri uygulanmıştır. Bunlar, işlevleri ve dizileri işaretçilere (aksine ve) `std::decay` bozmadan bir `std::decay_t`türden referans-lık ve cv niteliğini kaldırır.

### <a name="feature-test-macros"></a>Özellik testi makroları

[P0941R2 - özellik test makroları](https://wg21.link/p0941r2) tamamlandı, `__has_cpp_attribute`destek ile . Özellik testi makroları tüm standart modlarda desteklenir.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Kullanıcı tarafından bildirilen yapıcılarla toplamaları yasaklama

[C++20 P1008R1 - kullanıcı tarafından bildirilen yapıcılarla agregaların yasaklanması](https://wg21.link/p1008r1) tamamlandı.

## <a name="conformance-improvements-in-161"></a><a name="improvements_161"></a>16.1'deki uygunluk iyileştirmeleri

### <a name="char8_t"></a>char8_t

[P0482r6](https://wg21.link/p0482r6). C++20, UTF-8 kod birimlerini temsil etmek için kullanılan yeni bir karakter türü ekler. `u8`C++20'deki string literals'in türü `const char8_t[N]` `const char[N]`, daha önce olduğu gibi. Benzer değişiklikler [N2231](https://wg14.link/n2231)C standardı için önerilmiştir. `char8_t` [P1423r3'te](https://wg21.link/p1423r3)geriye dönük uyumluluk düzeltmesi için öneriler verilmiştir. Microsoft C++ derleyicisi, `char8_t` **/Zc:char8_t** derleyici seçeneğini belirttiğiniz zaman Visual Studio 2019 sürüm 16.1 için destek ekler. Gelecekte **/Zc:char8_t-** ile C++17 davranışına döndürülebilen [/std:c++en son](../build/reference/std-specify-language-standard-version.md)ile desteklenecektir. IntelliSense'e güç veren EDG derleyicisi henüz desteklemez, bu nedenle gerçek derlemeyi etkilemeyen sahte IntelliSense yalnızca hatalar görürsünüz.

#### <a name="example"></a>Örnek

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>std::type_identity metafonksiyon ve std::identity function object

[P0887R1 type_identity](https://wg21.link/p0887r1). Amortismana alınan `std::identity` sınıf şablonu uzantısı kaldırıldı ve C++20 `std::type_identity` metaişlev `std::identity` ve işlev nesnesi ile değiştirildi. Her ikisi de yalnızca [/std:c++en son](../build/reference/std-specify-language-standard-version.md)altında mevcuttur.

Aşağıdaki örnek, Visual Studio 2017'de `std::identity` \<(type_traits> tanımlanan) için amortisman uyarısı C4996'yı üretir:

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

Aşağıdaki örnek, yeni `std::identity` \< `std::type_identity`ile birlikte yeni (işlevsel> tanımlanan) nasıl kullanılacağını gösterir:

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Jenerik lambdas için sözdizimi denetimleri

Yeni lambda işlemci genel lambdas bazı uygunluk modu sözdizimi kontrolleri sağlar, altında [/ std:c++son](../build/reference/std-specify-language-standard-version.md) veya başka bir dil modu altında **/ deneysel:newLambdaProcessor**.

Visual Studio 2017'de bu kod uyarı olmadan derlenmiştir, ancak Visual Studio 2019'da hata *C2760 sözdizimi hatası üretir: beklenmeyen belirteç '\<id-expr>', beklenen 'id-expression'*:

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

Aşağıdaki örnek, şimdi derleyici tarafından zorlanan doğru sözdizimini gösterir:

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>Işlev çağrıları için bağımsız değişkene bağımlı arama

[P0846R0](https://wg21.link/p0846r0) (C++20) Açık şablon bağımsız değişkenleri olan işlev çağrı ifadeleri için bağımsız lığa bağlı arama yoluyla işlev şablonlarını bulma yeteneği artırıldı. Gerektirir **/std:c++son**.

### <a name="designated-initialization"></a>Atanmış başlatma

[P0329R4](https://wg21.link/p0329r4) (C++20) Atanmış başlatma, `Type t { .member = expr }` sözdizimi kullanılarak belirli üyelerin toplu başlatmada seçilmesini sağlar. Gerektirir **/std:c++son**.

### <a name="new-and-updated-standard-library-functions-c20"></a>Yeni ve güncelleştirilmiş standart kitaplık işlevleri (C++20)

- `starts_with()`ve `ends_with()` `basic_string` için `basic_string_view`ve .
- İlişkili kapsayıcılar için `contains()`.
- `list` ve `forward_list` için `remove()`, `remove_if()` ve `unique()` artık `size_type` değerini döndürüyor.
- `shift_left()`ve `shift_right()` algoritma \<ya eklendi>.

## <a name="conformance-improvements-in-162"></a><a name="improvements_162"></a>16.2'deki uygunluk iyileştirmeleri

### <a name="noexcept-constexpr-functions"></a>nostexpr fonksiyonları hariç

Constexpr işlevleri artık sabit bir ifadede kullanıldığında varsayılan olarak **önemsiz** olarak kabul edilir. Bu davranış değişikliği [CWG 1351](https://wg21.link/cwg1351) çözünürlüğünden gelir ve [/izin-](../build/reference/permissive-standards-conformance.md). Aşağıdaki örnek Visual Studio 2019 sürüm 16.1 ve daha önceki sürümde derlenmiştir, ancak Visual Studio 2019 sürüm 16.2'de C2338 üretir:

```cpp
constexpr int f() { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept"); // C2338 in 16.2
}
```

Hatayı düzeltmek için işlev bildirimine **noexcept** ifadesini ekleyin:

```cpp
constexpr int f() noexcept { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept");
}
```

### <a name="binary-expressions-with-different-enum-types"></a>Farklı enum tipleri ne sahip ikili ifadeler

Her zamanki aritmetik dönüşümleri biri numaralandırma tipinde, diğerinin farklı numaralandırma türünde veya kayan nokta türünde olan operandlara uygulayabilme yeteneği C++20 'de[(P1120R0)](https://wg21.link/p1120r0)amortismana tabidir. Visual Studio 2019 sürüm 16.2 ve sonraki sürümlerinde, [/std:c++en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkinleştirildiğinde aşağıdaki kod düzey 4 uyarısı üretir:

```cpp
enum E1 { a };
enum E2 { b };
int main() {
    int i = a | b; // warning C5054: operator '|': deprecated between enumerations of different types
}
```

Uyarıyı önlemek için, ikinci operand'ı dönüştürmek için [static_cast](../cpp/static-cast-operator.md) kullanın:

```cpp
enum E1 { a };
enum E2 { b };
int main() {
  int i = a | static_cast<int>(b);
}
```

### <a name="binary-expressions-with-enumeration-and-floating-point-types"></a>Numaralandırma ve kayan nokta tipleri ile ikili ifadeler

Her zamanki aritmetik dönüşümleri biri numaralandırma tipinde, diğerinin farklı numaralandırma türünde veya kayan nokta türünde olan operandlara uygulayabilme yeteneği C++20 'de[(P1120R0)](https://wg21.link/p1120r0)amortismana tabidir. Başka bir deyişle, numaralandırma ve kayan nokta türü arasında ikili bir işlem kullanmak, [/std:c++en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkinleştirildiğinde artık bir uyarıdır:

```cpp
enum E1 { a };
int main() {
  double i = a * 1.1;
}
```

Uyarıyı önlemek için, ikinci operand'ı dönüştürmek için [static_cast](../cpp/static-cast-operator.md) kullanın:

```cpp
enum E1 { a };
int main() {
   double i = static_cast<int>(a) * 1.1;
}
```

### <a name="equality-and-relational-comparisons-of-arrays"></a>Dizilerin eşitlik ve ilişkisel karşılaştırmaları

C++20 'de[(P1120R0)](https://wg21.link/p1120r0)dizi tipiiki operand arasındaki eşitlik ve ilişkisel karşılaştırmalar amortismana alınır. Başka bir deyişle, iki dizi (rütbe ve kapsam benzerlikleri ne olursa olsun) arasında bir karşılaştırma işlemi artık bir uyarıdır. Visual Studio 2019 sürüm 16.2'den başlayarak, aşağıdaki kod *C5056'yı üretir:* [/std:c++en son](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkinleştirildiğinde dizi türleri için amortismana uyrur:

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

İki dizinin içeriğinin eşit olup olmadığını belirlemek için [std::equal](../standard-library/algorithm-functions.md#equal) işlevini kullanın:

```cpp
std::equal(std::begin(a), std::end(a), std::begin(b), std::end(b));
```

### <a name="effect-of-defining-spaceship-operator-on--and-"></a>Uzay gemisi işlecinin == ve != üzerindeki etkisi

Uzay gemisi işlecinin**<=>** tanımı ( ) tek başına, **==** uzay gemisi işleci[(P1185R2)](https://wg21.link/p1185r2)olarak `= default` işaretlenmediği sürece, içeren ifadeleri veya **!=** ifadeleri yeniden yazmayacaktır. Aşağıdaki örnek Visual Studio 2019 RTW ve sürüm 16.1'de derlenmiştir, ancak Visual Studio 2019 sürüm 16.2'de C2678 üretir:

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

Hatayı önlemek için işleci== tanımlayın veya varsayılan olarak bildirin:

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

### <a name="standard-library-improvements"></a>Standart Kütüphane geliştirmeleri

- \<charconv `to_chars()` sabit/ bilimsel hassasiyetle>. (Genel hassasiyet şu anda 16,4 için planlanmaktadır.)
- [P0020R6](https://wg21.link/p0020r6):\<atomik şamandıra>, atomik\<çift>, atomik\<uzun çift>
- [P0463R1](https://wg21.link/p0463r1): endian
- [P0482R6](https://wg21.link/p0482r6): char8_t için kütüphane desteği
- [P0600R1](https://wg21.link/p0600r1):\[[ nodiscard]] STL için, Bölüm 1
- [P0653R2](https://wg21.link/p0653r2): to_address()
- [P0754R2](https://wg21.link/p0754r2) \<: sürüm>
- [P0771R1](https://wg21.link/p0771r1): noexcept Std için::fonksiyonun hareket yapıcı

## <a name="conformance-improvements-in-visual-studio-2019-version-163"></a><a name="improvements_163"></a>Visual Studio 2019 sürüm 16.3'te uygunluk iyileştirmeleri

### <a name="stream-extraction-operators-for-char-removed"></a>Char* için akış çıkarma operatörleri kaldırıldı

İşaretçi-karakterler için akış çıkarma işleçleri kaldırıldı ve karakter dizisi için çıkarma işleçleri ile değiştirildi [(P0487R1](https://wg21.link/p0487r1)başına). WG21, kaldırılan aşırı yüklerin güvenli değil olduğunu kabul eder. [/std:c++son](../build/reference/std-specify-language-standard-version.md) modda, aşağıdaki örnek şimdi *C2679 üretir: ikili '>>':\*'char' tipinin sağ el operand'ını alan hiçbir işleç bulunamadı (veya kabul edilebilir bir dönüştürme yoktur)*:

```cpp
   char x[42];
   char* p = x;
   std::cin >> std::setw(42);
   std::cin >> p;
```

Hatayı önlemek için, char[] değişkeni olan ekstraksiyon işleci kullanın:

```cpp
char x[42];
std::cin >> x;
```

### <a name="new-keywords-requires-and-concept"></a>Yeni anahtar kelimeler **gerektirir** ve **kavram**

Microsoft C++ derleyicisine yeni anahtar kelimeler **ve** **kavram** eklendi. [/std:c++son](../build/reference/std-specify-language-standard-version.md) modda tanımlayıcı olarak birini kullanmaya çalışırsanız, derleyici *C2059'u yükseltir: sözdizimi hatası*.

### <a name="constructors-as-type-names-disallowed"></a>Tür adları olarak yapıcılar izin verilmiyor

Oluşturucu adlar, sınıf şablonu uzmanlığına bir takma addan sonra nitelikli bir adla göründüklerinde artık enjekte edilen sınıf adları olarak kabul edilmiştir. Bu daha önce diğer varlıkları bildirmek için bir tür adı olarak yapıcıların kullanımına izin verdi. Aşağıdaki örnek şimdi *C3646 üretir: 'TotalDuration': bilinmeyen geçersiz kılma belirtimi:*

```cpp
#include <chrono>

class Foo {
   std::chrono::milliseconds::duration TotalDuration{};
};

```

Hatayı önlemek için, `TotalDuration` burada gösterildiği gibi bildirin:

```cpp
#include <chrono>

class Foo {
  std::chrono::milliseconds TotalDuration {};
};
```

### <a name="stricter-checking-of-extern-c-functions"></a>Extern "C" fonksiyonlarının daha sıkı kontrolü

Bir **extern "C"** işlevi farklı ad alanlarında bildirilmişse, Microsoft C++ derleyicisinin önceki sürümleri bildirimlerin uyumlu olup olmadığını denetlememiştir. Visual Studio 2019 sürüm 16.3'te derleyici böyle bir denetim gerçekleştirir. [/izin modunda,](../build/reference/permissive-standards-conformance.md) aşağıdaki kod *C2371* üretir : yeniden tanımlama; farklı temel türleri ve *C2733 C bağlantısı ile bir işlevi aşırı yükleyemezsiniz:*

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

Önceki örnekteki hataları önlemek için, her iki bildirimde de sürekli olarak **BOOL** yerine `f` **bool** kullanın.

### <a name="standard-library-improvements"></a>Standart Kütüphane geliştirmeleri

Standart olmayan başlıklar \<stdexcpt.h \<> ve typeinfo.h> kaldırıldı. Bunları içeren kod, bunun yerine \<standart üstbilgiler özel durum> ve \<typeinfo>, sırasıyla içermelidir.

## <a name="conformance-improvements-in-visual-studio-2019-version-164"></a><a name="improvements_164"></a>Visual Studio 2019 sürüm 16.4'te uygunluk iyileştirmeleri

### <a name="better-enforcement-of-two-phase-name-lookup-for-qualified-ids-in-permissive-"></a>/izin li- id'ler için iki aşamalı ad aramasının daha iyi uygulanması

İki aşamalı ad araması, şablon gövdelerinde kullanılan bağımlı olmayan adların tanım zamanında şablontarafından görünür olmasını gerektirir. Daha önce, şablon anında yapıldığında bu tür adlar bulunmuş olabilir. Bu değişiklik, [/izin veren](../build/reference/permissive-standards-conformance.md) bayrak altında MSVC'de taşınabilir, uygun kod yazmayı kolaylaştırır.

Visual Studio 2019 sürüm 16.4'te **,/izin veren** bayrak kümesiyle, `N::f` `f<T>` şablon tanımlandığında görünmez olduğundan aşağıdaki örnekte bir hata üretir:

```cpp
template <class T>
int f() {
    return N::f() + T{}; // error C2039: 'f': is not a member of 'N'
}

namespace N {
    int f() { return 42; }
}
```

Genellikle, bu aşağıdaki örnekte gösterildiği gibi eksik üstbilgi veya ileri bildiren işlevler veya değişkenler dahil edilerek düzeltilebilir:

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

### <a name="implicit-conversion-of-integral-constant-expressions-to-null-pointer"></a>İntegral sabit ifadelerin null işaretçisine örtülü dönüşümü

MSVC derleyicisi artık [CWG Issue 903'ü](https://wg21.link/cwg903) uygunluk modunda (/izin verme modunda-) uygular. Bu kural, integral sabit ifadelerin (tamsayı literal '0' hariç) null işaretçi sabitlerine örtülü dönüşümüne izin verir. Aşağıdaki örnek, uygunluk modunda C2440 üretir:

```cpp
int* f(bool* p) {
    p = false; // error C2440: '=': cannot convert from 'bool' to 'bool *'
    p = 0; // OK
    return false; // error C2440: 'return': cannot convert from 'bool' to 'int *'
}
```

Hatayı düzeltmek **için, false**yerine **nullptr** kullanın. Gerçek 0'a hala izin verildiğini unutmayın:

```cpp
int* f(bool* p) {
    p = nullptr; // OK
    p = 0; // OK
    return nullptr; // OK
}
```

### <a name="standard-rules-for-types-of-integer-literals"></a>Tümseci edebi türleri için standart kurallar

Uygunluk modunda [(/izin verilen)](../build/reference/permissive-standards-conformance.md)MSVC, tümseci edebi türleri için standart kuralları kullanır. Daha önce, imzalı bir 'int' sığmayacak kadar büyük ondalık literal'lere 'imzasız int' türü verilirdi. Şimdi bu tür literals sonraki en büyük imzalı tamsayı türü, 'uzun uzun' verilir. Ayrıca, imzalı bir türe sığmayacak kadar büyük olan 'll' sonekine sahip literal'lere 'imzasız uzun uzun' türü verilir.

Bu farklı uyarı tanılama oluşturulan ve edebi üzerinde gerçekleştirilen aritmetik işlemler için davranış farklılıkları yol açabilir.

Aşağıdaki örnek, Visual Studio 2019 sürüm 16.4'teki yeni davranışı göstermektedir. `i` Değişken türü **imzasız int** ve bu nedenle uyarı yükseltilir. Değişkenin `j` yüksek sıralı bitleri 0 olarak ayarlanır.

```cpp
void f(int r) {
    int i = 2964557531; // warning C4309: truncation of constant value
    long long j = 0x8000000000000000ll >> r; // literal is now unsigned, shift will fill high-order bits with 0
}
```

Aşağıdaki örnek, eski davranışın nasıl saklanıp uyarılardan ve çalışma süresi davranış değişikliğinden kaçınılmayı gösterir:

```cpp
void f(int r) {
int i = 2964557531u; // OK
long long j = (long long)0x8000000000000000ll >> r; // shift will keep high-order bits
}
```

### <a name="function-parameters-that-shadow-template-parameters"></a>Şablon parametrelerini gölgeleyen işlev parametreleri

MsVC derleyicisi, işlev parametresi şablon parametresini gölgelediğinde hata kaldırır:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T(&buffer)[Size], int& Size) // error C7576: declaration of 'Size' shadows a template parameter
{
    return f(buffer, Size, Size);
}
```

Hatayı düzeltmek için parametrelerden birinin adını değiştirin:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T (&buffer)[Size], int& size_read)
{
    return f(buffer, Size, size_read);
}
```

### <a name="user-provided-specializations-of-type-traits"></a>Tür özelliklerinin kullanıcı tarafından sağlanan uzmanlıkları

Standardın *meta.rqmts* alt maddesine uygun olarak, MSVC derleyicisi `type_traits` `std` artık ad alanında belirtilen şablonlardan birinin kullanıcı tanımlı uzmanlığıyla karşılaştığında bir hata yükseltir. Aksi belirtilmedikçe, bu tür uzmanlıklar tanımlanmamış davranışlara neden olur. Aşağıdaki örnek, kuralı ihlal ettiği için tanımlanmamış `static_assert` bir davranışa sahiptir ve **c2338**hatası ile başarısız olur.

```cpp
#include <type_traits>
struct S;

template<>
struct std::is_fundamental<S> : std::true_type {};

static_assert(std::is_fundamental<S>::value, "fail");
```

Hatayı önlemek için, tercih edilenden `type_trait`devralan bir yapı tanımlayın ve aşağıdakileri uzmanlanın:

```cpp
#include <type_traits>

struct S;

template<typename T>
struct my_is_fundamental : std::is_fundamental<T> {};

template<>
struct my_is_fundamental<S> : std::true_type { };

static_assert(my_is_fundamental<S>::value, "fail");
```

### <a name="changes-to-compiler-provided-comparison-operators"></a>Derleyici tarafından sağlanan karşılaştırma işleçleri değişiklikleri

MSVC derleyicisi şimdi [/std:c++en son](../build/reference/std-specify-language-standard-version.md) seçeneği etkinleştirildiğinde [P1630R1](https://wg21.link/p1630r1) başına karşılaştırma işleçlerinde aşağıdaki değişiklikleri uygular:

Derleyici artık **bool**olmayan `operator==` bir dönüş türü içeriyorsa kullanarak ifadeleri yeniden yazmaz. Aşağıdaki kod şimdi *hata C2088 üretir: '!=': yapı için yasadışı:*

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

Hatayı önlemek için, gerekli işleci açıkça tanımlamanız gerekir:

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

Derleyici, birleşim benzeri bir sınıfın üyesiyse artık varsayılan bir karşılaştırma işleci tanımlamaz. Aşağıdaki örnek şimdi *C2120 üretir: 'void' her türlü yasadışı:*

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

Derleyici, sınıf bir referans üye içeriyorsa artık varsayılan bir karşılaştırma işleci tanımlamaz. Aşağıdaki kod şimdi *hata C2120 üretir: 'void' tüm türleri ile yasadışı:*

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

## <a name="conformance-improvements-in-visual-studio-2019-version-165"></a><a name="improvements_165"></a>Visual Studio 2019 sürüm 16.5'te uygunluk iyileştirmeleri

### <a name="explicit-specialization-declaration-without-an-initializer-is-not-a-definition"></a>Bir baş harfi olmadan açık uzmanlık beyanı bir tanım değildir

Altında, `/permissive-`MSVC şimdi açık uzmanlık bildirimleri başlatma olmadan tanımları değildir standart bir kural uygular. Daha önce, bildirim varsayılan bir baş harfe sahip bir tanım olarak kabul edilirdi. Bu davranışa bağlı bir program artık çözülmemiş sembollere sahip olabileceğinden, bağlantı zamanında etki gözlemlenebilir. Bu örnek şimdi bir hata ile sonuçlanır:

```cpp
template <typename> struct S {
    static int a;
};

// In permissive-, this declaration is not a definition and the program will not link.
template <> int S<char>::a;

int main() {
    return S<char>::a;
}
```

```Output
error LNK2019: unresolved external symbol "public: static int S<char>::a" (?a@?$S@D@@2HA) referenced in function _main
at link time.
```

Sorunu gidermek için bir baş harf ekleyin:

```cpp
template <typename> struct S {
    static int a;
};

// Add an initializer for the declaration to be a definition.
template <> int S<char>::a{};

int main() {
    return S<char>::a;
}
```

### <a name="preprocessor-output-preserves-newlines"></a>Önişlemci çıkışı yeni satırları korur

Deneysel önişlemci artık kullanırken `/P` veya `/E` . `/experimental:preprocessor` Bu değişiklik kullanarak `/d1experimental:preprocessor:oldWhitespace`devre dışı tutulabilir.

Bu örnek kaynak göz önüne alındığında,

```cpp
#define m()
line m(
) line
```

Önceki çıktı `/E` sı:

```Output
line line
#line 2
```

Yeni çıktı `/E` şimdi:

```Output
line
 line
```

### <a name="import-and-module-keywords-are-context-dependent"></a>'alma' ve 'modül' anahtar kelimeleri içeriğe bağlıdır

P1857R1 başına, içe aktarma ve modül önişlemci yönergeleri sözdizimi üzerinde ek kısıtlamalar vardır. Bu örnek artık derlemez:

```cpp
import // Invalid
m;
```

Aşağıdaki hata iletisini üretir:

```Output
error C2146: syntax error: missing ';' before identifier 'm'
```

Sorunu gidermek için, alma işlemi aynı satırda tutun:

```cpp
import m; // OK
```

### <a name="removal-of-stdweak_equality-and-stdstrong_equality"></a>Std kaldırılması::weak_equality ve std::strong_equality

P1959R0'un birleştirilmesi, derleyicinin davranışı ve `std::weak_equality` `std::strong_equality` türleri ve türlerine yapılan başvuruları kaldırmasını gerektirir.

Bu örnekteki kod artık derlemez:

```cpp
#include <compare>

struct S {
    std::strong_equality operator<=>(const S&) const = default;
};

void f() {
    nullptr<=>nullptr;
    &f <=> &f;
    &S::operator<=> <=> &S::operator<=>;
}
```

Örnek şimdi bu hatalara yol açar:

```Output
error C2039: 'strong_equality': is not a member of 'std'
error C2143: syntax error: missing ';' before '<=>'
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C7546: binary operator '<=>': unsupported operand types 'nullptr' and 'nullptr'
error C7546: binary operator '<=>': unsupported operand types 'void (__cdecl *)(void)' and 'void (__cdecl *)(void)'
error C7546: binary operator '<=>': unsupported operand types 'int (__thiscall S::* )(const S &) const' and 'int (__thiscall S::* )(const S &) const'
```

Sorunu gidermek için, yerleşik ilişkisel işleçleri tercih etmek ve kaldırılan türleri değiştirmek için güncelleştirin:

```cpp
#include <compare>

struct S {
    std::strong_ordering operator<=>(const S&) const = default; // prefer 'std::strong_ordering'
};

void f() {
    nullptr != nullptr; // use pre-existing builtin operator != or ==.
    &f != &f;
    &S::operator<=> != &S::operator<=>;
}
```

### <a name="tls-guard-changes"></a>TLS Guard değişiklikleri

Daha önce, DLL'lerde iş parçacığı yerel değişkenler, DLL yüklenen iş parçacığı dışında, DLL yüklenmeden önce var olan iş parçacıkları üzerinde ilk kullanımlarından önce doğru bir şekilde başharfe çevrilmemişti. Bu kusur şimdi düzeltildi.
Böyle bir DLL'deki iş parçacığı yerel değişkenleri, bu tür iş parçacıkları üzerinde ilk kullanımlarından hemen önce baş harflere para yla verilir.

İş parçacığı yerel değişkenlerin kullanımı üzerinde başlatma için test bu yeni `/Zc:tlsGuards-` davranış derleyici anahtarı kullanılarak devre dışı olabilir. Veya, belirli `[[msvc:no_tls_guard]]` iş parçacığı yerel değişkenlere öznitelik ekleyerek.

### <a name="better-diagnosis-of-call-to-deleted-functions"></a>Silinen işlevlere çağrının daha iyi tanısı

Derleyicimiz daha önce silinen işlevlere yapılan aramalar konusunda daha müsamahakârdı. Örneğin, aramalar bir şablon gövdesi bağlamında gerçekleştiyse, aramayı tanılamayız. Ayrıca, silinen işlevlere birden çok çağrı örneği olsaydı, yalnızca bir tanılama yayımlardık. Şimdi her biri için bir teşhis yayınlıyoruz.

Yeni davranışın bir sonucu küçük bir kırılma değişikliği üretebilir: Silinmiş işlev olarak adlandırılan kod, kod oluşturma için hiç gerekmediyse tanı konulmaz. Şimdi ön teşhis koyacağız.

Bu örnekte, şimdi bir hata üreten kod gösterilmektedir:

```cpp
struct S {
  S() = delete;
  S(int) { }
};

struct U {
  U() = delete;
  U(int i): s{ i } { }

  S s{};
};

U u{ 0 };
```

```Output
error C2280: 'S::S(void)': attempting to reference a deleted function
note: see declaration of 'S::S'
note: 'S::S(void)': function was explicitly deleted
```

Sorunu gidermek için, silinen işlevlere yapılan çağrıları kaldırın:

```cpp
struct S {
  S() = delete;
  S(int) { }
};

struct U {
  U() = delete;
  U(int i): s{ i } { }

  S s;  // Do not call the deleted ctor of 'S'.
};

U u{ 0 };
```

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019"></a><a name="update_160"></a>Visual Studio 2019'da hata düzeltmeleri ve davranış değişiklikleri

### <a name="reinterpret_cast-in-a-constexpr-function"></a>Reinterpret_cast bir constexpr fonksiyonu

**Bir reinterpret_cast** bir **constexpr** fonksiyonu yasadışıdır. Microsoft C++ derleyicisi daha önce **reinterpret_cast** yalnızca **constexpr** bağlamında kullanıldığında reddeder. Visual Studio 2019'da, tüm dil standartları modlarında **derleyici, bir constexpr** fonksiyonunun tanımında **bir reinterpret_cast** doğru bir şekilde tanılar. Aşağıdaki kod şimdi *C3615 üretir: constexpr fonksiyonu 'f' sabit bir ifade ile sonuçlanamaz.*

```cpp
long long i = 0;
constexpr void f() {
    int* a = reinterpret_cast<int*>(i);
}
```

Hatayı önlemek **için, constexpr** değiştiriciyi işlev bildiriminden çıkarın.

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>basic_string aralığı oluşturucu için doğru tanılama

Visual Studio `basic_string` 2019'da, aralık yapıcı artık derleyici `static_cast`tanılamayı . Aşağıdaki kod Visual Studio 2017'de uyarı olmadan derlenmiştir, `wchar_t` ancak baş `out`harfe doğru **char'a** kadar olası veri kaybına rağmen:

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 doğru *C4244 yükseltir: 'argüman': 'wchar_t' 'const _Elem' dönüşüm, veri olası kaybı*. Uyarıyı önlemek için, bu örnekte gösterildiği gibi std:string'i başolarak alabilirsiniz:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>/clr veya /ZW altında += ve -= yanlış çağrılar artık doğru bir şekilde algılandı

Visual Studio 2017'de derleyicinin hataları sessizce yok sayması ve geçersiz çağrılar için += ve `/clr` -= altında veya `/ZW`altında kod oluşturmaması için bir hata sunuldu. Aşağıdaki kod Visual Studio 2017'de hatasız derlenmiştir ancak Visual Studio 2019'da hata yı doğru bir şekilde yükseltir *C2845: 'Sistem::String ^': işaretçi aritmetiğine izin verilmez:*

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Bu örnekteki hatayı önlemek için, ToString() yöntemiyle `s += E::e.ToString();`işleci kullanın: .

### <a name="initializers-for-inline-static-data-members"></a>Satır lı statik veri üyeleri için başlangıçlayıcılar

Geçersiz üye **inline** ve **statik constexpr** initializers içinde erişir şimdi doğru algılanır. Aşağıdaki örnek Visual Studio 2017'de hatasız olarak derlenmiştir, `/std:c++17` ancak Visual Studio 2019 modunda *C2248 hatasını yükseltir: 'X' sınıfında beyan edilen özel üyeye erişemez.*

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

### <a name="c4800-reinstated"></a>C4800 geri

MSVC **bool**örtülü dönüşüm hakkında bir performans uyarısı C4800 için kullanılır. Çok gürültülüydü ve bastırılamadı, bu da Visual Studio 2017'de kaldırmamıza yol açtı. Ancak Visual Studio 2017'nin yaşam döngüsü boyunca, çözdüğün yararlı vakalar hakkında çok fazla geri bildirim aldık. Visual Studio 2019'da açıklayıcı C4165 ile birlikte özenle uyarlanmış bir C4800'ü geri getiriyoruz. Bu uyarıların her ikisi de açık bir döküm veya uygun tür0 0 ile karşılaştırıldığında kolayca bastırılabilir. C4800 bir off-by-default düzey 4 uyarı ve C4165 bir off-by-varsayılan düzey 3 uyarıdır. Her ikisi de `/Wall` derleyici seçeneği kullanılarak keşfedilebilir.

Aşağıdaki örnek altında `/Wall`C4800 ve C4165 yükseltir:

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

Önceki örnekteki uyarıları önlemek için kodu aşağıdaki gibi yazabilirsiniz:

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>Yerel sınıf üye işlevinin bir gövdesi yok

Visual Studio 2017, *C4822: Yerel sınıf üye işlevi* bir gövde ye `/w14822` sahip değildir, yalnızca derleyici seçeneği açıkça ayarlandığında yükseltilir; ile `/Wall`gösterilmez. Visual Studio 2019'da C4822, varsayılan olmayan bir uyarıdır ve `/Wall` bu uyarı, açıkça ayarlamak `/w14822` zorunda kalmadan altında keşfedilebilir hale getirir.

```cpp
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>If ostexpr içeren işlev şablonu gövdeleri if deyimleri

Constexpr deyimleri bazı [/izin veren-](../build/reference/permissive-standards-conformance.md) ayrıştma ile ilgili denetimleri **etkinleştirilmişse** şablon işlev gövdeleri. Örneğin, Visual Studio 2017'de aşağıdaki kod *C7510 üretir: 'Tür': bağımlı tür adının kullanımı* yalnızca **/izin verme** seçeneği ayarlanmıyorsa 'tür adı' ile önceden belirlenmiş olmalıdır. Visual Studio 2019'da aynı kod **/izin-** seçeneği ayarlandığında bile hataları yükseltir:

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

Hatayı önlemek için, aşağıdakileri bildirgeye tür `a` `typename T::Type a;`**adı** anahtar sözcüğü ekleyin.

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Satır daşifre kodu lambda ifadesinde desteklenmez

Microsoft C++ ekibi, yakın zamanda bir lambda içinde sıralı assembler kullanımının `ebp` çalışma zamanında (iade adresi kaydı) bozulmasına yol açabileceği bir güvenlik sorunu hakkında bilgi sahibi oldu. Kötü amaçlı bir saldırgan bu senaryodan yararlanabilir. Sorunun doğası göz önüne alındığında, satır içi assembler sadece x86 desteklenen gerçeği ve inline assembler ve derleyici geri kalanı arasındaki kötü etkileşim, bu soruna en güvenli çözüm bir lambda ifade içinde inline assembler izin vermek oldu.

'Vahşi' bulduğumuz bir lambda ifadesi içinde sıralı assembler tek kullanımı dönüş adresi yakalamak oldu. Bu senaryoda, sadece bir derleyici içsel `_ReturnAddress()`kullanarak tüm platformlarda dönüş adresini yakalayabilirsiniz.

Aşağıdaki kod *C7552 üretir: inline assembler* visual studio 2017 15.9 ve Visual Studio 2019 hem de bir lambda desteklenmez:

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

Hatayı önlemek için derleme kodunu aşağıdaki örnekte gösterildiği gibi adlandırılmış bir işleve taşıyın:

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

### <a name="iterator-debugging-and-stdmove_iterator"></a>Bueratör hata ayıklama ve`std::move_iterator`

Yineleyici hata ayıklama özelliği düzgün açmak `std::move_iterator`için öğretilmiştir. Örneğin, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` şimdi `memcpy` hızlı yol meşgul olabilir.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>anahtar kelime \<zorlama> xkeycheck.h için düzeltmeler

Standart kitaplığın makro bir anahtar kelime \<zorlama xkeycheck.h yerine> genel bir ileti yerine algılanan gerçek sorun anahtar kelime yaksiletmek için sabittir. Ayrıca C++20 anahtar kelimelerini destekler ve IntelliSense'i rastgele anahtar kelimelerin makro olduğunu söylemesi için kandırmaktan kaçınır.

### <a name="allocator-types-no-longer-deprecated"></a>Allocator türleri artık amortismana

`std::allocator<void>`, `std::allocator::size_type`ve `std::allocator::difference_type` artık amortismana lı değildir.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Dize dönüşümlerini daraltma için doğru uyarı

Yanlışlıkla C4244 daraltma uyarıları bastırılmış standart tarafından çağrılan `static_cast` bir sahte `std::string`kaldırıldı . Aramaya `std::string::string(const wchar_t*, const wchar_t*)` çalışmak artık düzgün bir şekilde *C4244 yatacak "bir wchar_t bir char'a daraltmak."*

### <a name="various-filesystem-correctness-fixes"></a>Çeşitli \<dosya sistemi> düzeltmeleri

- Bir `std::filesystem::last_write_time` dizinin son yazma süresini değiştirmeye çalışırken başarısız olması düzeltildi.
- Oluşturucu `std::filesystem::directory_entry` şimdi, var olmayan bir hedef yolu sağlandığında bir özel durum oluşturmak yerine başarısız bir sonuç depolar.
- `std::filesystem::create_directory` 2-parametre sürümü, temel `CreateDirectoryExW` işlevin bir symlink `copy_symlink` `existing_p` iken kullanacağı gibi, 1-parametre sürümü aramak için değiştirildi.
- `std::filesystem::directory_iterator`kırık bir symlink bulunduğunda artık başarısız olur.
- `std::filesystem::space`şimdi göreli yolları kabul eder.
- `std::filesystem::path::lexically_relative`[lwg 3096](https://cplusplus.github.io/LWG/issue3096)olarak bildirilen, artık kesikler izleyerek karıştırılmamalıdır.
- İleri `CreateSymbolicLinkW` kesikler ile yolları reddetme `std::filesystem::create_symlink`etrafında çalıştı.
- Windows 10 LTSB `delete` 1609'da var olan ancak dosyaları silemeden POSIX silme modu işlevi etrafında çalıştı.
- `std::boyer_moore_searcher`ve `std::boyer_moore_horspool_searcher`'kopya yapıcılar ve kopyalama atama operatörleri şimdi aslında şeyler kopyalayın.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 ve sonraki paralel algoritmalar

Paralel algoritmalar kitaplığı artık her `WaitOnAddress` zaman Windows 7 ve önceki sahte sürümleri ni kullanmak yerine, Windows 8 ve sonraki sürümlerde gerçek aileyi düzgün bir şekilde kullanır.

### <a name="stdsystem_categorymessage-whitespace"></a>`std::system_category::message()`Boşluk

`std::system_category::message()`şimdi döndürülen iletiden beyaz boşluğu izler.

### <a name="stdlinear_congruential_engine-divide-by-zero"></a>`std::linear_congruential_engine`sıfıra böl

0'a bölmeyi tetiklemeye neden `std::linear_congruential_engine` olacak bazı koşullar düzeltildi.

### <a name="fixes-for-iterator-unwrapping"></a>Yineleyici açma düzeltmeleri

Visual Studio 2017 15.8'de programcı-kullanıcı entegrasyonu için ilk kez ortaya çıkarılan, [VS 2017 1017 15.8'deki](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/)C++ Team Blog makalesi STL Özellikleri ve Düzeltmeleri'nde açıklandığı gibi, standart kütüphane yineleyicilerinden türetilen yinelemeleri açmaz. Örneğin, davranışı türleyen `std::vector<int>::iterator` ve özelleştirmeye çalışan bir kullanıcı, artık işaretçi davranışı yerine standart kitaplık algoritmalarını ararken özelleştirilmiş davranışlarını alır.

LWG `reserve` [2156'da](https://cplusplus.github.io/LWG/issue2156)açıklandığı gibi, sırasız konteyner işlevi artık aslında N elementleri için rezervler.

### <a name="time-handling"></a>Zaman işleme

- Daha önce, eşzamanlılık kitaplığına geçirilen bazı zaman değerleri, örneğin `condition_variable::wait_for(seconds::max())`taşardı. Şimdi sabit, taşmalar görünüşte rasgele 29 günlük döngüsü (uint32_t milisaniye altta yatan Win32 API'ler tarafından kabul davranışı değişti taşmış).

- \<Ctime> üstbilgi, bunları `timespec` genel `timespec_get` ad `std` alanında bildirmenin yanı sıra doğru bir şekilde bildirir ve ad alanında da bildirir.

### <a name="various-fixes-for-containers"></a>Kapsayıcılar için çeşitli düzeltmeler

- Birçok standart kütüphane dahili kapsayıcı işlevleri geliştirilmiş bir IntelliSense deneyimi için özel hale getirilmiştir. MSVC'nin sonraki sürümlerinde üyeleri özel olarak işaretlemek için ek düzeltmeler beklenmektedir.

- Özel durum güvenlik doğruluğu sorunları, düğüm tabanlı `list` `map`kaplar `unordered_map` gibi , , , ve bozuk olacak sabit oldu. Bir `propagate_on_container_copy_assignment` veya `propagate_on_container_move_assignment` yeniden atama işlemi sırasında, konteynerin sentinel düğümini eski ayırıcıyla serbest bırakıp, eski tahsisatçı üzerinde POCCA/POCMA ataması yapar ve sonra sentinel düğümünyeni ayırıcıdan elde etmeye çalışırız. Bu ayırma başarısız olduysa, sentinel düğüm sahibi bir sabit veri yapısı değişmez olduğu için kapsayıcı bozuk ve hatta yok edilememiş. Bu kod, varolan sentinel düğümü yok etmeden önce kaynak kapsayıcının ayırıcısından yeni sentinel düğüm ayırmak için düzeltildi.

- Konteynerler, `propagate_on_container_copy_assignment`beyan `propagate_on_container_move_assignment` `propagate_on_container_swap` `is_always_equal`edilen tahsisörler için bile , ve hatta , göre her zaman kopyalama /taşıma /takas allocators sabitedildi .

- [P0083 "Splicing Maps And Sets"](https://wg21.link/p0083r3) başına rvalue kapsayıcıları kabul konteyner birleştirme ve ayıklama üye işlevleri için aşırı yükler eklendi

### <a name="stdbasic_istreamread-processing-of-rn--n"></a>`std::basic_istream::read`r\\ \\n = \\> n işleme

`std::basic_istream::read`r \\\\n => \\n işleminin bir parçası olarak geçici olarak verilen arabelleğe yazılmayacak şekilde sabitlenmiştir. Bu değişiklik, Visual Studio 2017 15.8'de 4K boyutundan büyük okumalar için kazanılan performans avantajının bir kısmını verir. Ancak, karakter başına üç sanal çağrıdan kaçınma verimlilik iyileştirmeleri hala mevcuttur.

### <a name="stdbitset-constructor"></a>`std::bitset`Oluşturucu

Oluşturucu `std::bitset` artık büyük bit kümeleri için ters sırada birler ve sıfırları okumaz.

### <a name="stdpairoperator-regression"></a>`std::pair::operator=`Regresyon

`std::pair` [LWG 2729 "Std'de Eksik SFINAE::pair::operator=";](https://cplusplus.github.io/LWG/issue2729)uygularken tanıtılan atama operatöründeki bir gerileme düzeltildi. Şimdi doğru `std::pair` tekrar dönüştürülebilir türleri kabul eder.

### <a name="non-deduced-contexts-for-add_const_t"></a>Için çıkarılmayan bağlamlar`add_const_t`

Küçük tür özellikleri hata, `add_const_t` nerede ve ilgili işlevleri olmayan bir çıkarılmış bağlam olması gerekiyordu düzeltildi. Başka bir `add_const_t` deyişle, bir `typename add_const<T>::type`takma ad `const T`olmalıdır, değil.

## <a name="bug-fixes-and-behavior-changes-in-162"></a><a name="update_162"></a>Hata düzeltmeleri ve davranış değişiklikleri 16.2

### <a name="const-comparators-for-associative-containers"></a>Bağşancı kaplar için const karşıtlaştırıcılar

[Kümedeki](../standard-library/set-class.md)arama ve ekleme kodu, [harita,](../standard-library/map-class.md) [çok ayarlı](../standard-library/multiset-class.md)ve [çoklu harita](../standard-library/multimap-class.md) azaltılmış kod boyutu için birleştirilmiştir. Ekleme işlemleri artık, arama işlemlerinin daha önce yaptığı gibi, **const** karşılaştırma functor'da daha az karşılaştırma yı çağırır. Aşağıdaki kod Visual Studio 2019 sürüm 16.1 ve daha önce derler, ancak Visual Studio 2019 sürümü 16.2 C3848 yükseltir:

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

Hatayı önlemek için, karşılaştırma işleci **const**olun:

```cpp
struct Comparer  {
   bool operator() (K a, K b) const {
      return a.a < b.a;
   }
};

```

::: moniker-end

::: moniker range="vs-2017"

## <a name="conformance-improvements-in-visual-studio-2017-rtw-version-150"></a><a name="improvements_150"></a>Visual Studio 2017 RTW'de uygunluk iyileştirmeleri (sürüm 15.0)

Genelleştirilmiş **constexpr** ve non-statik veri üye başlatma (NSDMI) için destek ile Visual Studio 2017 Microsoft C++ derleyicisi artık C++14 standardına eklenen özellikler için tamamlandı. Ancak derleyici, C++11 ve C++98 standartlarından birkaç özellikten hala yoksundur. Derleyicinin geçerli durumunu gösteren bir tablo için [Microsoft C++ dil uygunluk tablosuna](../visual-cpp-language-conformance.md) bakın.

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++11: Daha fazla kütüphanede Ifade SFINAE desteği

Derleyici, şablon bağımsız değişken iksiyonu ve **decltype** ve **constexpr** ifadelerinin şablon parametreleri olarak görünebileceği ikame için gerekli olan SFINAE ifadesine yönelik desteğini geliştirmeye devam eder. Daha fazla bilgi için [Visual Studio 2017 RC'deki Expression SFINAE geliştirmelerine](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3)bakın.

### <a name="c14-nsdmi-for-aggregates"></a>C++14: Agregalar için NSDMI

Toplam, kullanıcı tarafından sağlanan oluşturucu, özel veya korumalı statik olmayan veri üyesi, temel sınıf ve sanal işlev içermeyen bir dizi veya sınıftır. C++14'ten başlayarak agregalar üye harfler içerebilir. Daha fazla bilgi için [Üye başlangıç bilgileri ve agregalara](https://wg21.link/n3605)bakın.

### <a name="c14-extended-constexpr"></a>C++14: Genişletilmiş **constexpr**

**Constexpr** olarak bildirilen ifadeler artık belirli türde bildirimleri içermesine izin verilir, eğer ve geçiş ifadeleri, döngü deyimleri, ve yaşam ömrü constexpr ifade değerlendirmesi içinde başlayan nesnelerin mutasyonu. Ayrıca, artık bir **constexpr** statik olmayan üye işlevin örtülü **olarak const**olması gerekir bir gereklilik yoktur. Daha fazla bilgi için, [constexpr işlevleri üzerinde Rahatlatıcı kısıtlamalar](https://wg21.link/n3652)abakın.

### <a name="c17-terse-static_assert"></a>C++17: Terse`static_assert`

için `static_assert` ileti parametresi isteğe bağlıdır. Daha fazla bilgi için bkz: [Genişletme static_assert, v2](https://wg21.link/n3928).

### <a name="c17-fallthrough-attribute"></a>C++17: `[[fallthrough]]` öznitelik

**/std:c++17** modunda, `[[fallthrough]]` öznitelik anahtar ifadeleri bağlamında, düşme davranışının amaçlandığına dair derleyiciye bir ipucu olarak kullanılabilir. Bu öznitelik, derleyicinin bu gibi durumlarda uyarı vermesini engeller. Daha fazla bilgi [için \[ \[fallthrough\] \] özniteliği için Wording'e](https://wg21.link/p0188r0)bakın.

### <a name="generalized-range-based-for-loops"></a>Döngüler için genelleştirilmiş aralık tabanlı

Döngüler için aralık tabanlı artık `begin()` `end()` bunu gerektirmez ve aynı türdeki nesneleri döndürür. Bu değişiklik, `end()` [range-v3](https://github.com/ericniebler/range-v3) aralıkları ve tamamlanmış ama tam olarak yayınlanmamış Aralıklar Teknik Belirtimi'nde kullanılan bir sentinel'i döndürmeyi sağlar. Daha fazla bilgi için, [Aralık Tabanlı Döngü Için Genelleme'ye](https://wg21.link/p0184r0)bakın.

## <a name="conformance-improvements-in-153"></a><a name="improvements_153"></a>15.3'teki uygunluk iyileştirmeleri

### <a name="constexpr-lambdas"></a>constexpr lambdas

Lambda ifadeleri artık sabit ifadelerde kullanılabilir. Daha fazla bilgi için [C++'daki constexpr lambda ifadelerine](../cpp/lambda-expressions-constexpr.md)bakın.

### <a name="if-constexpr-in-function-templates"></a>işlev şablonlarında **constexpr ise**

Derleme zamanı dallandırmayı etkinleştirmek için **constexpr** deyimleri varsa bir işlev şablonu içerebilir. Daha fazla bilgi için, [constexpr ifadeleri bakın.](../cpp/if-else-statement-cpp.md#if_constexpr)

### <a name="selection-statements-with-initializers"></a>Baş harflerle seçim ifadeleri

**If** deyimi, deyimin kendisi içinde blok kapsamında bir değişken tanıtan bir başlatıcı içerebilir. Daha fazla bilgi için, [baş harfli ifadeler olup olmadığını](../cpp/if-else-statement-cpp.md#if_with_init)görün.

### <a name="maybe_unused-and-nodiscard-attributes"></a>`[[maybe_unused]]`ve `[[nodiscard]]` öznitelikleri

Yeni öznitelik, `[[maybe_unused]]` bir varlık kullanılmadığında uyarıları susturuyor. Bir `[[nodiscard]]` işlev çağrısının geri dönüş değeri atılırsa öznitelik bir uyarı oluşturur. Daha fazla bilgi için [C++'daki Özniteliklere](../cpp/attributes.md)bakın.

### <a name="using-attribute-namespaces-without-repetition"></a>Yineleme olmadan öznitelik ad boşluklarını kullanma

Öznitelik listesinde yalnızca tek bir ad alanı tanımlayıcısını etkinleştirmek için yeni sözdizimi. Daha fazla bilgi için [C++'daki Özniteliklere](../cpp/attributes.md)bakın.

### <a name="structured-bindings"></a>Yapılandırılmış ciltler

Artık tek bir bildirimde, değeri bir dizi, bir `std::tuple` veya `std::pair`, veya tüm ortak statik olmayan veri üyeleri olduğunda, bileşenleri için tek tek adlarla bir değer depolamak mümkündür. Daha fazla bilgi için bkz: [Yapılandırılmış Bağlamalar](https://wg21.link/p0144r0) ve [bir işlevden birden çok değer döndürme.](../cpp/functions-cpp.md#multi_val)

### <a name="construction-rules-for-enum-class-values"></a>**Enum sınıfı** değerleri için inşaat kuralları

Artık, tanımı nda numaralandırma olmadığı ve kaynak bir liste başlatma sözdizimi kullandığında, kapsamlı numaralandırmanın temel türünden, kapsamlı numaralandırmanın altında yatan türe kadar örtük/daraltma olmayan bir dönüştürme vardır. Daha fazla bilgi [için, enum sınıfı Değerleri](https://wg21.link/p0138r2) ve [Tümumerasyonlar](../cpp/enumerations-cpp.md#no_enumerators)için Yapı Kuralları'na bakın.

### <a name="capturing-this-by-value"></a>Değere `*this` göre yakalama

Lambda `*this` ifadesindeki nesne artık değertarafından yakalanabilir. Bu değişiklik, lambda'nın paralel ve eşzamanlı işlemlerde, özellikle de yeni makine mimarilerinde çağrıldığı senaryoları mümkün kılar. Daha fazla bilgi için [lambda \*Capture \[this\*by\]This by Value olarak =, bu](https://wg21.link/p0018r3).

### <a name="removing-operator-for-bool"></a>`operator++` **Bool** için çıkarma

`operator++`**artık bool** tipleri desteklenmez. Daha fazla bilgi için bkz: [Amortismana Alınan operatörü kaldırın++(bool)](https://wg21.link/p0002r1).

### <a name="removing-deprecated-register-keyword"></a>Amortismana kaydı anahtar **register** sözcüğü kaldırma

Daha önce amortismana kaldırılmış (ve derleyici tarafından göz ardı **edilen) kayıt** anahtar kelimesi artık dilden kaldırılır. Daha fazla bilgi için [bkz.](https://wg21.link/p0001r1)

## <a name="conformance-improvements-in-155"></a><a name="improvements_155"></a>15,5'teki uygunluk iyileştirmeleri

14] \[ile işaretlenmiş özellikler **/std:c++14** modunda bile koşulsuz olarak kullanılabilir.

### <a name="new-compiler-switch-for-extern-constexpr"></a>**Extern constexpr** için yeni derleyici anahtarı

Visual Studio önceki sürümlerinde, derleyici her zaman bir **constexpr** değişken iç bağlantı bile değişken **extern**işaretlenmiştir verdi. Visual Studio 2017 sürüm 15.5'te yeni bir derleyici anahtarı, [/Zc:externConstexpr,](../build/reference/zc-externconstexpr.md)doğru standartlara uygun davranış sağlar. Daha fazla bilgi için [extern constexpr bağlantısına](#extern_linkage)bakın.

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimlerini kaldırma

[P0003R5](https://wg21.link/p0003r5) Dinamik özel durum özellikleri C++11'de amortismana kattı. özelliği C++17'den kaldırılır, ancak (hala) amortismana alınmış `throw()` belirtimi `noexcept(true)`kesinlikle . Daha fazla bilgi için Dinamik [özel durum belirtimi kaldırma ve noexcept](#noexcept_removal)bakın.

### `not_fn()`

[P0005R4](https://wg21.link/p0005r4) `not_fn` ve bir `not1` `not2`yedektir.

### <a name="rewording-enable_shared_from_this"></a>Yeniden İfade`enable_shared_from_this`

C++11'e [P0033R1](https://wg21.link/p0033r1) `enable_shared_from_this` eklendi. C++17 standardı, belirli köşe durumlarını daha iyi işlemek için belirtimi güncelleştirir. [14]

### <a name="splicing-maps-and-sets"></a>Haritaları ve setleri birleştirme

[P0083R3](https://wg21.link/p0083r3) `map`Bu özellik, `set` `unordered_map` `unordered_set`daha sonra değiştirilebilir ve aynı kap veya aynı düğüm türünü kullanan farklı bir kapsayıcı ya da geri takılabilir bağdaştırıcı kaplardan düğümlerin çıkarılmasını sağlar. (Yaygın kullanım örneği, bir `std::map`düğüm ayıklamak için, anahtarı değiştirmek ve yeniden eklemek.)

### <a name="deprecating-vestigial-library-parts"></a>Amortismana neden olan kütüphane parçaları

[P0174R2](https://wg21.link/p0174r2) C++ standart kitaplığı'nın çeşitli özellikleri yıllar içinde yeni özelliklertarafından yerini almış veya yararlı veya sorunlu bulunmamıştır. Bu özellikler C++17'de resmen amortismana alınır.

### <a name="removing-allocator-support-in-stdfunction"></a>Tahsis atadesteğinin kaldırılması`std::function`

[P0302R1](https://wg21.link/p0302r1) C++17'den önce, `std::function` sınıf şablonunda ayırıcı bağımsız değişkeni alan birkaç oluşturucu vardı. Ancak, bu bağlamda ayırıcıların kullanımı sorunlu ve anlambilim belirsizdi. Sorun konstrüktörler kaldırıldı.

### <a name="fixes-for-not_fn"></a>Için düzeltmeler`not_fn()`

[P0358R1](https://wg21.link/p0358r1) Sarmalayıcı çağırmasında kullanıldığında değer kategorisinin yayılmasını destekleyen yeni ifadeler. `std::not_fn`

### <a name="shared_ptrt-shared_ptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](https://wg21.link/p0414r2) Kitaplık `shared_ptr` Temelleri'nden C++17'ye değişiklikleri birleştirme. [14]

### <a name="fixing-shared_ptr-for-arrays"></a>Diziler için sabitleme `shared_ptr`

[P0497R0](https://wg21.link/p0497r0) Diziler için destek shared_ptr için düzeltmeler. [14]

### <a name="clarifying-insert_return_type"></a>Netleştirme`insert_return_type`

[P0508R0](https://wg21.link/p0508r0) Benzersiz anahtarlara sahip bağdaştırıcı kapsayıcılar ve benzersiz anahtarlara `insert` sahip sıralanmamış kapsayıcılar iç içe bir türü `insert_return_type`döndüren bir üye işlevine sahiptir. Bu iade türü şimdi kapsayıcının Yineleyici ve Düğüm Tipi üzerinde parametreli bir tür uzmanlık olarak tanımlanır.

### <a name="inline-variables-for-the-standard-library"></a>Standart kitaplık için satır satır değişkenleri

[P0607R0](https://wg21.link/p0607r0)

### <a name="annex-d-features-deprecated"></a>Ek D özellikleri amortismana

C++ standardının Ek D'si, `shared_ptr::unique()` `<codecvt>`" ve `namespace std::tr1`. **/std:c++17** derleyici anahtarı ayarlandığında, Ek D'deki hemen hemen tüm standart kitaplık özellikleri amortismana ermiş olarak işaretlenir. Daha fazla bilgi için, [Ek D'deki Standart kitaplık özelliklerine bakın amortismanlı olarak işaretlenmiştir.](#annex_d)

Şimdiki `std::tr2::sys` `<experimental/filesystem>` ad alanı varsayılan olarak **/std:c++14** altında bir değer çıkarma uyarısı yayır ve şimdi varsayılan olarak **/std:c++17** altında kaldırılır.

Standart olmayan `<iostream>` bir uzantıdan (sınıf içi açık uzmanlıklar) kaçınarak daha iyi uyumluluk.

Standart kitaplık artık değişken şablonları dahili olarak kullanır.

Standart kitaplık, c++17 derleyici söyici değişikliklerine yanıt olarak, tür sistemine **noexcept** eklenmesi ve dinamik özel durum belirtimlerinin kaldırılması da dahil olmak üzere güncelleştirildi.

## <a name="conformance-improvements-in-156"></a><a name="improvements_156"></a>15,6'daki uygunluk iyileştirmeleri

### <a name="c17-library-fundamentals-v1"></a>C++17 Kütüphane Temelleri V1

[P0220R1,](https://wg21.link/p0220r1) C++17 için Kütüphane Temelteknik Şartnamesini standart olarak içerir. \<Deneysel/tuple \<>, deneysel/isteğe bağlı \<>, deneysel/fonksiyonel>, \< \<deneysel/>, \<deneysel/string_view \<>, deneysel/memory_resource \<>, deneysel/memory_resource> ve deneysel/algoritma> güncellemelerini kapsar.

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++17: Standart kitaplık için sınıf şablonu bağımsız değişken tümlemesi iyileştirilmesi

[P0739R0](https://wg21.link/p0739r0) Tutarlı `adopt_lock_t` kullanımını etkinleştirmek için `scoped_lock` parametre listesinin `scoped_lock`önüne geçin. Kopya `std::variant` atamasını etkinleştirmek için, oluşturucunun daha fazla durumda aşırı yük çözümüne katılmasına izin verin.

## <a name="conformance-improvements-in-157"></a><a name="improvements_157"></a>15,7'deki uygunluk iyileştirmeleri

### <a name="c17-rewording-inheriting-constructors"></a>C++17: Devralan yapıcıları yeniden ifade etme

[P0136R1,](https://wg21.link/p0136r1) bir oluşturucunun adlarını veren bir deklarasyonun, ek türemiş sınıf oluşturucuları bildirmek yerine, türemiş sınıfın başharflerine karşılık gelen taban sınıf oluşturucuları görünür hale geldiğini belirtir. **using** Bu yeniden ifade C++14'ten bir değişikliktir. Visual Studio 2017 sürüm 15.7 ve sonraki sürümlerde **,/std:c++17** modunda, C++14'te geçerli olan ve kalıtsal yapıcılar kullanan kod geçerli olmayabilir veya farklı anlambilime sahip olabilir.

Aşağıdaki örnek, C++14 davranışını gösterir:

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

Aşağıdaki örnek, Visual Studio 15.7'de **/std:c++17** davranışını gösterir:

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

Daha fazla bilgi için [Constructors'a](../cpp/constructors-cpp.md#inheriting_constructors)bakın.

### <a name="c17-extended-aggregate-initialization"></a>C++17: Genişletilmiş toplam başlatma

[P0017R1](https://wg21.link/p0017r1)

Bir taban sınıfın oluşturucusu ortak değil, ancak türemiş bir sınıf için erişilebilirse, Visual Studio 2017 sürüm 15.7'deki **/std:c++17** modu altında, türetilmiş türdeki bir nesneyi başlatmak için artık boş ayraçkullanamazsınız.
Aşağıdaki örnek, C++14 konforman davranışını gösterir:

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

C++17'de `Derived` artık toplam bir tür olarak kabul edilir. Bu, genişletilmiş toplam `Base` başlatma kuralının bir parçası olarak, özel varsayılan oluşturucu aracılığıyla başlatılmasının doğrudan gerçekleştiği anlamına gelir. Daha önce, `Base` özel yapıcı `Derived` yapıcı aracılığıyla çağrıldı ve arkadaş bildirimi nedeniyle başarılı oldu.
Aşağıdaki örnek, Visual Studio sürüm 15.7'de **/std:c++17** modunda C++17 davranışını gösterir:

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

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++17: Tür tipi olmayan şablon parametrelerinin otomatik olarak belirtilmesi

[P0127R2](https://wg21.link/p0127r2)

**/std:c++17** modunda, derleyici artık **otomatik**olarak bildirilen tür dışı şablon bağımsız değişkeninin türünü anlayabilir:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Bu yeni özelliğin bir etkisi geçerli C++14 kodu geçerli olmayabilir veya farklı semantik olabilir. Örneğin, daha önce geçersiz olan bazı aşırı yüklemeler artık geçerlidir. Aşağıdaki örnekte, çağrı `example(p)` ya `example(void*);`da . Visual Studio 2017 sürüm 15.7'de, **/std:c++17** modunda, `example` işlev şablonu en iyi eşleşmedir.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

Aşağıdaki örnek, Visual Studio 15.7'de **/std:c++17** modunda C++17 kodunu gösterir:

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*);

void example(void *);

void sample(A<0> *p)
{
    example(p); // C2280: 'int example<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++17: Temel dize dönüşümleri (kısmi)

[P0067R5](https://wg21.link/p0067r5) Ortalisans ve dizeleri arasında ve kayan nokta numaraları ve dizeleri arasında dönüşümler için düşük düzeyli, yerel bağımsız işlevler.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++20: Gereksiz çürümeden kaçınma (kısmi)

[P0777R1](https://wg21.link/p0777r1) "Çürüme" kavramı ile sadece const veya referans niteleyicileri kaldırma kavramı arasında ayrım ekler.  Yeni tür `remove_reference_t` özelliği `decay_t` bazı bağlamlarda yerini alır. Destek, `remove_cvref_t` Visual Studio 2019'da uygulanmaktadır.

### <a name="c17-parallel-algorithms"></a>C++17: Paralel algoritmalar

[P0024R2](https://wg21.link/p0024r2) Paralellik TS standart içine dahil edilir, küçük değişiklikler ile.

### <a name="c17-hypotx-y-z"></a>C++17:`hypot(x, y, z)`

[P0030R1](https://wg21.link/p0030r1) Üç yeni overloads `std::hypot`ekler , türleri **için float**, **çift**, ve **uzun çift**, her biri üç giriş parametreleri vardır.

### <a name="c17-filesystem"></a>C++17: \<dosya sistemi>

[P0218R1](https://wg21.link/p0218r1) Birkaç ifade değişikliği yle Dosya Sistemi TS'yi standart olarak benimser.

### <a name="c17-mathematical-special-functions"></a>C++17: Matematiksel özel fonksiyonlar

[P0226R1](https://wg21.link/p0220r1) Matematiksel Özel Fonksiyonlar için önceki teknik \<özellikleri standart cmath> üstbilgisine benimser.

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++17: Standart kitaplık için tümdengelim kılavuzları

[P0433R2](https://wg21.link/p0433r2) Sınıf şablonu bağımsız değişken çıkarımı için destek ekleyen [P0091R3'ün](https://wg21.link/p0091r3)C++17 benimsenmesi için STL'ye yapılan güncelleştirmeler.

### <a name="c17-repairing-elementary-string-conversions"></a>C++17: Temel dize dönüşümlerini onarmak

[P0682R1](https://wg21.link/p0682r1) P0067R5'ten yeni bir temel dize dönüştürme \<işlevlerini yeni bir başlık charconv> taşıyın `std::errc` ve `std::error_code`hata işlemeyi değiştirmek yerine kullanmak üzere değiştirme de dahil olmak üzere diğer iyileştirmeler yapın.

### <a name="c17-constexpr-for-char_traits-partial"></a>C++17: **constexpr** for `char_traits` (kısmi)

[P0426R1](https://wg21.link/p0426r1) Üye `std::traits_type` işlevlerde `length` `compare`yapılan `find` değişiklikler `std::string_view` ve sürekli ifadelerde kullanılabilir hale getirmek. (Visual Studio 2017 sürüm 15.6, sadece Clang/LLVM için desteklenir. Sürüm 15.7 Önizleme 2, destek clxx için de neredeyse tamamlandı.)

## <a name="conformance-improvements-in-159"></a><a name="improvements_159"></a>15,9'da uygunluk iyileştirmeleri

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>Operatörler `->*`için soldan sağa değerlendirme `[]` `>>`sırası , , ve`<<`

C++17'den başlayarak, `->*`işleçlerin operandları , `[]`, `>>`ve `<<` soldan sağa sırayla değerlendirilmelidir. Derleyicinin bu siparişi garanti edemediği iki durum vardır:

- operand ifadelerinden biri değer tarafından geçirilen bir nesne olduğunda veya değer tarafından geçirilen bir nesne içeriyorsa veya

- **/clr**kullanılarak derlendiğinde ve operandlardan biri bir nesnenin veya dizi elemanının alanıdır.

Derleyici, soldan sağa değerlendirmeyi garanti edemediğinde [C4866](https://docs.microsoft.com/cpp/error-messages/compiler-warnings/c4866?view=vs-2017) uyarısı yayır. Derleyici bu uyarıyı yalnızca **/std:c++17** veya daha sonra belirtildiğinde oluşturur, çünkü bu işleçlerin soldan sağa sıra gereksinimi C++17'de tanıtıldı.

Bu uyarıyı çözmek için, önce operandların soldan sağa değerlendirilmesinin gerekli olup olmadığını düşünün, örneğin operandların değerlendirilmesi nin isme bağlı yan etkilere yol açabileceği zaman. Çoğu durumda, operandların değerlendirilme sırasının gözlemlenebilir bir etkisi yoktur. Değerlendirme sırası soldan sağa olması gerekiyorsa, bunun yerine const referans la operands geçirip geçiremeyeceğinigöz önünde bulundurun. Bu değişiklik, aşağıdaki kod örneğindeki uyarıyı ortadan kaldırır:

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

## <a name="bug-fixes-in-visual-studio-2017-rtw-version-150"></a><a name="update_150"></a>Visual Studio 2017 RTW'de hata düzeltmeleri (sürüm 15.0)

### <a name="copy-list-initialization"></a>Kopya-liste-başlatma

Visual Studio 2017, Visual Studio 2015'te yakalanmayan başharf listelerini kullanarak nesne oluşturmayla ilgili derleyici hatalarını doğru bir şekilde yükseltir ve çökmelere veya tanımlanmamış çalışma zamanı davranışına yol açabilir. N4594 13.3.1.7p1 uyarınca, kopya-liste başlatmada, derleyicinin aşırı yük çözümü için açık bir oluşturucuyu dikkate alması gerekir, ancak bu aşırı yük seçilirse hata yükseltmesi gerekir.

Aşağıdaki iki örnek Visual Studio 2015'te derlenmiştir, ancak Visual Studio 2017'de derlenmiştir.

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

Hatayı düzeltmek için doğrudan başlatmayı kullanın:

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015'te derleyici, kopya-liste başlatmayı normal kopya-başlatma yla aynı şekilde hatalı bir şekilde ele aldı; sadece aşırı yük çözümü için yapıcıları dönüştürmeyi kabul eder. Aşağıdaki örnekte, Visual Studio 2015 MyInt(23) seçer ancak Visual Studio 2017 doğru hatayı yükseltir.

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

Bu örnek öncekine benzer, ancak farklı bir hata yükseltir. Visual Studio 2015'te başarılı olur ve C2668 ile Visual Studio 2017'de başarısız olur.

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

### <a name="deprecated-typedefs"></a>Amortismana ait typedefs

Visual Studio 2017 şimdi bir sınıf veya yapı olarak bildirilen amortismana kalımlı typedef'ler için doğru uyarıyı yayınlar. Aşağıdaki örnek Visual Studio 2015'te uyarı olmadan derlenmiştir ancak Visual Studio 2017'de C4996 üretir.

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

Visual Studio 2017, koşullu olarak değerlendirilen bir işlemin sol operand'ı constexpr bağlamında geçerli olmadığında hatayı doğru bir şekilde yükseltir. Aşağıdaki kod Visual Studio 2015'te derlenmiştir, ancak Visual Studio 2017'de derlenemez (C3615 constexpr fonksiyonu 'f' sabit bir ifadeyle sonuçlanamaz):

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

Hatayı `array::size()` düzeltmek için, işlevi **constexpr** olarak bildirin veya **constexpr** niteleyicisini `f`kaldırın.

### <a name="class-types-passed-to-variadic-functions"></a>Variadik fonksiyonlara geçen sınıf türleri

Visual Studio 2017'de printf gibi değişken bir işleve aktarılan sınıflar veya structs önemsiz bir şekilde kopyalanabilir olmalıdır. Bu tür nesneleri geçerken, derleyici sadece bitwise kopya yapar ve yapıcı veya yıkıcı aramaz.

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

Hatayı düzeltmek için, önemsiz bir şekilde kopyalanabilir bir tür döndüren bir üye işlev çağırabilirsiniz,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

veya başka bir aktarmadan önce nesneyi dönüştürmek için statik bir döküm kullanın:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

CString kullanılarak oluşturulmuş ve yönetilen dizeleri için, sağlanan `operator LPCTSTR()` biçim dizesi tarafından beklenen C işaretçisine bir CString nesnesi döküm için kullanılmalıdır.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>Sınıf yapımında Cv elemeleri

Visual Studio 2015'te derleyici, bir oluşturucu çağrı aracılığıyla bir sınıf nesnesi oluştururken bazen cv elemeyi yanlış olarak yok sayar. Bu sorun, bir kilitlenme veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnek Visual Studio 2015'te derlenmiştir ancak Visual Studio 2017'de derleyici hatası ortaya çıkarır:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Hatayı düzeltmek için `operator int()` **const**olarak bildirin.

### <a name="access-checking-on-qualified-names-in-templates"></a>Şablonlarda nitelikli adları denetleme

Derleyicinin önceki sürümleri, bazı şablon bağlamlarında nitelikli adlara erişimi denetlemedi. Bu sorun, bir ismin erişilemezliği nedeniyle ikame başarısız olması beklenen SFINAE davranışı ile engelleyebilir. Derleyici yanlışlıkla işleç yanlış aşırı çağırdı, çünkü çalışma zamanında bir kilitlenme veya beklenmeyen davranışa neden olabilir. Visual Studio 2017'de derleyici hatası ortaya çıkmıştır. Belirli hata değişebilir, ancak genellikle "C2672 hiçbir eşleşen aşırı yükleme işlevi bulunamadı". Aşağıdaki kod Visual Studio 2015'te derler ancak Visual Studio 2017'de bir hata ortaya çıkarır:

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

Visual Studio 2015 ve daha önceki dönemde, derleyici, şablon varsayılan şablon bağımsız değişkeninin veya tür tipi olmayan şablon parametresinin bir parçası olarak şablon parametre listesinde göründüğünde eksik şablon bağımsız değişken listelerini tanılamadı. Bu sorun, derleyici çökmeleri veya beklenmeyen çalışma zamanı davranışı da dahil olmak üzere öngörülemeyen davranışlara neden olabilir. Aşağıdaki kod Visual Studio 2015'te derlenmiştir, ancak Visual Studio 2017'de bir hata üretir.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>İfade-SFINAE

Expression-SFINAE'yi desteklemek için derleyici, şablonlar anlık olarak değil dejenere olduğunda bağımsız **değişkenleri** ayrışdırır. Sonuç olarak, decltype argümanında bağımlı olmayan bir uzmanlık bulunursa, anlık çalışma süresine ertelenmez. Hemen işlenir ve ortaya çıkan hatalar o anda teşhis edilir.

Aşağıdaki örnek, bildirim noktasında ortaya çıkan böyle bir derleyici hatasını gösterir:

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

### <a name="classes-declared-in-anonymous-namespaces"></a>Anonim ad alanlarında bildirilen sınıflar

C++ standardına göre, anonim bir ad alanı içinde bildirilen bir sınıfın iç bağlantısı vardır ve bu da dışa aktarılaamayacağı anlamına gelir. Visual Studio 2015 ve daha önce, bu kural uygulanmadı. Visual Studio 2017'de kural kısmen uygulanır. Aşağıdaki örnek Visual Studio 2017'de bu hatayı yükseltir: "hata C2201: const anonim ad alanı::S1::vftable: dış bağlantının dış bağlantıya sahip olması gerekir/ içe aktarılmak."

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Değer sınıfı üyeleri için varsayılan başlangıçlayıcılar (C++/CLI)

Visual Studio 2015 ve daha önceki durumlarda, derleyici bir değer sınıfının bir üyesi için varsayılan bir üye başlatılmasına izin verdi (ancak yok sayıldı). Bir değer sınıfının varsayılan başlatması her zaman üyeleri sıfır başharfe indirir. Varsayılan bir oluşturucuya izin verilmez. Visual Studio 2017'de varsayılan üye baş harfleri, bu örnekte gösterildiği gibi derleyici hatalarını yükseltir:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Varsayılan dizin oluşturma (C++/CLI)

Visual Studio 2015 ve daha önceki durumlarda, derleyici varsayılan bir özelliği varsayılan dizinleyici olarak yanlış tanımlayabıdır. Özelliğe erişmek için tanımlayıcı **varsayılanını** kullanarak sorunu çözmek mümkündü. Varsayılan **olarak** C++11'de anahtar kelime olarak tanıtıldıktan sonra geçici çözüm sorunlu hale geldi. Visual Studio 2017'de, geçici çözüm gerektiren hatalar giderildi ve derleyici, bir sınıfın varsayılan özelliğine erişmek için **varsayılan** özellik kullanıldığında şimdi bir hata ortaya çıkarıyor.

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

Visual Studio 2017'de her iki Değer özelliğine de adlarıyla erişebilirsiniz:

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="bug-fixes-in-153"></a><a name="update_153"></a>15.3 hata düzeltmeleri

### <a name="calls-to-deleted-member-templates"></a>Silinen üye şablonlarına yapılan aramalar

Visual Studio'nun önceki sürümlerinde, bazı durumlarda derleyici, silinmiş bir üye şablonuna yanlış biçimlendirilmiş aramalar için bir hata yakılmayır ve bu hata zamanında çökmelere neden olabilir. Aşağıdaki kod şimdi C2280 üretir, "'int S\<\<int>::f int>(void)': silinmiş bir işleve başvurmaya çalışmak":

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

Hatayı düzeltmek için `i` **int**olarak bildirin.

### <a name="pre-condition-checks-for-type-traits"></a>Ön koşul türü özellikleri için denetler

Visual Studio 2017 sürüm 15.3, standartta daha sıkı bir şekilde uymak için tip özellikleri için ön koşul kontrollerini geliştirir. Böyle bir denetim atanabilir içindir. Aşağıdaki kod Visual Studio 2017 sürüm 15.3 C2139 üretir:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yerelden yönetilen mareşallikte yeni derleyici uyarısı ve çalışma zamanı denetimleri

Yönetilen işlevlerden yerel işlevlere çağrı yapmak, mareşallik gerektirir. CLR mareşallik yapar, ancak C++ semantik anlamıyor. Yerel bir nesneyi değere göre geçirirseniz, CLR nesnenin kopya `BitBlt`oluşturucuyu çağırır veya çalışma zamanında tanımlanmamış davranışlara neden olabilecek kullanır.

Şimdi derleyici, silinmiş kopya ctor'una sahip yerel bir nesnenin yerel ve yönetilen sınır arasında değere göre geçirildiğini derleyerek biliyorsa bir uyarı yayar. Derleyicinin derleme zamanında bilmediği durumlar için, bir çalışma zamanı denetimi enjekte eder, böylece `std::terminate` kötü biçimlendirilmiş bir mareşallik gerçekleştiğinde program hemen çağırır. Visual Studio 2017 sürüm 15.3'te, aşağıdaki kod C4606 "'A': bağımsız değişkeni yerel ve yönetilen sınır lar arasında değere göre geçirmek geçerli kopya oluşturucu gerektirir. Aksi takdirde, çalışma zamanı davranışı tanımsız.

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

Hatayı düzeltmek için, `#pragma managed` arayanın yerel olarak işaretlemesi ve mareşallik ten kaçınmak için yönergeyi kaldırın.

### <a name="experimental-api-warning-for-winrt"></a>WinRT için deneysel API uyarısı

Deneme ve geri bildirim için yayımlanan WinRT API'leri ile `Windows.Foundation.Metadata.ExperimentalAttribute`dekore edilmiştir. Visual Studio 2017 sürüm 15.3'te derleyici, öznitelikile karşılaştığında C4698 uyarısı üretir. Windows SDK'nın önceki sürümlerindeki birkaç API zaten öznitelik ile dekore edilmiştir ve bu API'lere yapılan çağrılar artık bu derleyici uyarısını tetikletir. Yeni Windows SDK'lar özniteliği tüm sevk türlerinden kaldırıldı, ancak eski bir SDK kullanıyorsanız, sevk türlerine yapılan tüm aramalar için bu uyarıları bastırmanız gerekir.

Aşağıdaki kod Uyarı C4698 üretir: "'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' sadece değerlendirme amaçlıdır ve gelecekteki güncelleştirmelerde değişiklik veya kaldırma tabidir":

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Uyarıyı devre dışı katmak için bir #pragma ekleyin:

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Şablon üye işlevinin satır dışı tanımı

Visual Studio 2017 sürüm 15.3, sınıfta belirtilmemiş bir şablon üye işlevinin satır dışı tanımıyla karşılaştığında bir hata üretir. Aşağıdaki kod şimdi hata C2039 üretir: 'f': 'S' üyesi değildir:

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Hatayı düzeltmek için sınıfa bir bildirim ekleyin:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>**Bu** işaretçinin adresini almaya çalışma

C++'da **bu,** X'e ait tür işaretçisinin değeridir. **Bunun** adresini alamaz veya bir lvalue başvurusuna bağlayamazsınız. Visual Studio'nun önceki sürümlerinde derleyici, bir döküm kullanarak bu kısıtlamayı aşmanızı sağlar. Visual Studio 2017 sürüm 15.3'te derleyici C2664 hatası üretir.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemeyen bir taban sınıfa dönüştürme

Visual Studio 2017 sürüm 15.3, bir türü erişilemeyen bir taban sınıfa dönüştürmeye çalıştığınızda bir hata üretir. Derleyici şimdi "hata C2243: 'tip döküm': 'D *' den 'B *' dönüştürme var, ancak erişilemez" yükseltir. Aşağıdaki kod yanlış oluşturulmuştur ve çalışma zamanında bir kilitlenme nin oluşmasına neden olabilir. Derleyici şimdi bu gibi kod karşılaştığında C2243 üretir:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>Varsayılan bağımsız değişkenlere üye işlevlerin satır tanımları dışında izin verilmez

Varsayılan bağımsız değişkenlere şablon sınıflarında üye işlevlerin satır dışı tanımlarında izin verilmez. Derleyici **/ izin altında**bir uyarı ve / izin altında sabit bir hata yayınlayacak- . [/permissive-](../build/reference/permissive-standards-conformance.md)

Visual Studio'nun önceki sürümlerinde, aşağıdaki yanlış biçimlendirilmiş kod çalışma zamanı çökmesine neden olabilir. Visual Studio 2017 sürüm 15.3 uyarı C5034 üretir: 'Bir\<T>::f': bir sınıf şablonu üyesinin satır dışı tanımı varsayılan bağımsız değişkenlere sahip olamaz:

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

Hatayı düzeltmek için varsayılan `= false` bağımsız değişkeni kaldırın.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Bileşik `offsetof` üye tasnörü ile kullanımı

Visual Studio 2017 sürüm 15.3'te, `offsetof(T, m)` *m'nin* "bileşik üye atası" olduğu yerde **kullanmak/ Duvar** seçeneğiyle derlediğinizde bir uyarı yla sonuçlanır. Aşağıdaki kod yanlış biçimlendirilmiştir ve çalışma zamanında bir çökmeye neden olabilir. Visual Studio 2017 sürüm 15.3 "uyarı C4841: standart dışı uzantısı kullanılır: offsetof bileşik üye atama" üretir:

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Kodu düzeltmek için, uyarıyı pragma ile devre dışı ya da `offsetof`kodu kullanmamak için değiştirin:

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Statik `offsetof` veri üyesi veya üye işlevi ile kullanma

Visual Studio 2017 sürüm 15.3'te, `offsetof(T, m)` *m'nin* statik bir veri üyesine veya bir üye işlevine atıfta bulunduğu yerde kullanılması bir hatayla sonuçlanır. Aşağıdaki kod "hata C4597: tanımlanmamış davranış: üye işlev 'örnek' ve "hata C4597 uygulanan ofsetof: tanımsız davranış: statik veri üyesi 'örnek' uygulanan ofset:

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

Bu kod yanlış biçimlendirilmiştir ve çalışma zamanında bir çökmeye neden olabilir. Hatayı düzeltmek için, kodu artık tanımlanmamış davranışı çağırmak için değiştirin. C++ standardı tarafından izin verilmeyen taşınabilir olmayan koddur.

### <a name="new-warning-on-__declspec-attributes"></a><a name="declspec"></a>Özniteliklerhakkında `__declspec` yeni uyarı

Visual Studio 2017 sürüm 15.3'te derleyici, `__declspec(...)` bağlantı belirtiminderden önce `extern "C"` uygulandığında öznitelikleri artık göz ardı etmez. Daha önce, derleyici çalışma zamanı etkileri olabilir öznitelik, yoksayardı. **/Wall** ve **/WX** seçenekleri ayarlandığında, aşağıdaki kod "uyarı C4768: bağlantı belirtimi göz ardı edilmeden önce __declspec öznitelikleri" üretir:

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarıyı düzeltmek için `extern "C"` önce:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı varsayılan olarak 15.3'te kapalıdır, ancak varsayılan olarak 15.5'te dir ve yalnızca **/Wall** **/WX**ile derlenen kodu etkiler.

### <a name="decltype-and-calls-to-deleted-destructors"></a>silinen yıkıcılara **decltype** ve aramalar

Visual Studio'nun önceki sürümlerinde derleyici, silinmiş bir yıkıcıya yapılan bir çağrının **decltype**ile ilişkili ifade bağlamında gerçekleştiğini algılamadı. Visual Studio 2017 sürüm 15.3'te aşağıdaki kod "hata C2280: 'A\<T>::~A(void)': silinmiş bir işleve başvurmaya çalışmak" kodu üretir:

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

### <a name="uninitialized-const-variables"></a>Başlatlanmamış const değişkenler

Visual Studio 2017 RTW sürümünde, **const** değişken başharfe başlaltımadığı takdirde C++ derleyicisinin tanısal olarak yayınlanmayacağı bir gerileme vardı. Bu gerileme Visual Studio 2017 sürüm 15.3'te sabitlenmiştir. Aşağıdaki kod şimdi "uyarı C4132: 'Değer': const nesne başharfe getirilmelidir" üretir:

```cpp
const int Value; //C4132
```

Hatayı düzeltmek için, 'ye `Value`bir değer atayın

### <a name="empty-declarations"></a>Boş bildirimler

Visual Studio 2017 sürüm 15.3 artık sadece yerleşik türleri değil, tüm türleri için boş bildirimleri konusunda uyarır. Aşağıdaki kod şimdi dört bildirimleri için bir düzey 2 C4091 uyarı üretir:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Uyarıları kaldırmak için, yorum yapmak veya boş bildirimleri kaldırmak için. Adsız nesnenin yan etkisi olması amaçlandığı durumlarda (RAII gibi), bir ad verilmelidir.

Uyarı **/Wv:18** altında dışlanır ve varsayılan olarak Uyarı düzeyi W2 altında dır.

### <a name="stdis_convertible-for-array-types"></a>`std::is_convertible`dizi türleri için

Derleyicinin önceki sürümleri std için yanlış sonuçlar [verdi::dizi](../standard-library/is-convertible-class.md) türleri için is_convertible. Bu, kitaplık yazarlarının tür özelliğini kullanırken `std::is_convertible<...>` Microsoft C++ derleyicisini özel olarak kullanmalarını zorunlu kılır. Aşağıdaki örnekte, statik asserts Visual Studio önceki sürümlerinde geçmek ama Visual Studio 2017 sürümü 15.3 başarısız:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>`hayali bir işlev tanımının iyi oluşmuş olup olmadığını kontrol ederek hesaplanır:

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdis_constructible"></a>Özel yıkıcılar ve`std::is_constructible`

Derleyicinin önceki sürümleri std sonucuna karar verirken bir yıkıcı özel olup olmadığını göz [ardı::is_constructible](../standard-library/is-constructible-class.md). Şimdi onları düşünüyor. Aşağıdaki örnekte, statik asserts Visual Studio önceki sürümlerinde geçmek ama Visual Studio 2017 sürümü 15.3 başarısız:

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

Özel yıkıcılar bir türün yapılamayabilir hale alınmasına neden olur. `std::is_constructible<T, Args...>`aşağıdaki beyan yazılmış gibi hesaplanır:

```cpp
   T obj(std::declval<Args>()...)
```

Bu çağrı bir yıkıcı çağrı anlamına gelir.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: Belirsiz aşırı yük çözünürlüğü

Derleyicinin önceki sürümleri, hem bildirimleri hem de bağımsız değişkene bağımlı arama yoluyla birden fazla aday bulduğunda bazen belirsizliği algılayamamış olur. Bu hata, yanlış aşırı yüklemenin seçilmesine ve beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 doğru C2668 'f' yükseltir: aşırı yüklü fonksiyon belirsiz çağrı:

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

Kodu düzeltmek için, aramayı `N::f` `::f()`planlıyorsanız kullanarak ifadeyi kaldırın.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişkene bağımlı arama

Yerel işlev bildirimleri işlev bildirimini çevreleyen kapsamda gizler ve bağımsız değişkene bağımlı aramaya bağımlı aramayı devre dışı kılabilir. Ancak, derleyicinin önceki sürümleri bu durumda bağımsız değişkene bağımlı arama gerçekleştirmiş ve bu da yanlış aşırı yüklemenin seçilmesine ve beklenmeyen çalışma zamanı davranışına yol açmaktadır. Genellikle, hata yerel işlev bildiriminin yanlış imza nedeniyle. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 doğru C2660 'f' yükseltir: fonksiyon iki bağımsız değişken almaz:

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

Sorunu gidermek için, imzayı değiştirin `f(S)` veya kaldırın.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: başharf listelerinde başlatma sırası

Sınıf üyeleri, başharf listelerinde göründükleri sırayla değil, beyan edildikleri sırada başharfe fişlenir. Derleyicinin önceki sürümleri, baş harf listesinin sırası bildirim sırasına göre farklı olduğunda uyarmadı. Bir üyenin başlatılması zaten başlatılan listedeki başka bir üyeye bağlıysa, bu sorun tanımlanmamış çalışma zamanı davranışına yol açabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 **(/Wall**ile) "uyarı C5038: veri üyesi 'A::y' veri üyesi 'A::x'" sonra baş harfe çevrilecektir yükseltir:

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Sorunu gidermek için, baş harf listesini bildirimlerle aynı sıraya sahip olacak şekilde düzenleyin. Benzer bir uyarı, bir veya her iki başlatma cılızlayıcılar taban sınıf üyelerine atıfta bulunduğunda yükseltilir.

Bu uyarı varsayılan olarak kapalıdır ve yalnızca **/Wall**ile derlenen kodu etkiler.

## <a name="bug-fixes-and-other-behavior-changes-in-155"></a><a name="update_155"></a>Hata düzeltmeleri ve diğer davranış değişiklikleri 15.5

### <a name="partial-ordering-change"></a>Kısmi sipariş değişikliği

Derleyici şimdi doğru aşağıdaki kodu reddeder ve doğru hata iletisi verir:

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

Yukarıdaki örnekte sorun türleri (const vs non-const ve pack vs non-pack) iki fark olmasıdır. Derleyici hatasını ortadan kaldırmak için farklardan birini kaldırın. Bu, derleyicinin işlevleri kesin olarak sipariş etmesini sağlar.

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

Dizi veya işlev türüne başvuru handleyicis hiçbir zaman herhangi bir özel durum nesnesi için eşleşmiyor. Derleyici şimdi bu kuralı doğru bir şekilde yerine getirir ve düzey 4 uyarısını yükseltir. Ayrıca, **/Zc:strictStrings** `wchar_t*` kullanıldığında, artık bir dize `char*` gerçek veya bir dize gerçek eşleşir.

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

### <a name="stdtr1-namespace-is-deprecated"></a><a name="tr1"></a>`std::tr1` namespace amortismana uğradı

Standart `std::tr1` olmayan ad alanı artık hem C++14 hem de C++17 modlarında amortismana ermiş olarak işaretlenmiştir. Visual Studio 2017 sürüm 15.5'te aşağıdaki kod C4996'yı yükseltir:

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

Hatayı düzeltmek için, `tr1` başvuruyu ad alanına kaldırın:

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

### <a name="standard-library-features-in-annex-d-are-marked-as-deprecated"></a><a name="annex_d"></a>Ek D'deki standart kütüphane özellikleri amortismana ermiş olarak işaretlenir

**/std:c++17** mod derleyici anahtarı ayarlandığında, Ek D'deki hemen hemen tüm standart kitaplık özellikleri amortismana ermiş olarak işaretlenir.

Visual Studio 2017 sürüm 15.5'te aşağıdaki kod C4996'yı yükseltir:

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

Hatayı düzeltmek için, aşağıdaki kodda gösterildiği gibi uyarı metnindeki yönergeleri izleyin:

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

### <a name="unreferenced-local-variables"></a>Başvurulmamış yerel değişkenler

Visual Studio 15.5'te, Aşağıdaki kodda gösterildiği gibi, C4189 uyarısı daha fazla durumda yayılır:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Hatayı düzeltmek için kullanılmayan değişkeni kaldırın.

### <a name="single-line-comments"></a>Tek satırlık açıklamalar

Visual Studio 2017 sürüm 15.5'te C4001 ve C4179 uyarıları artık C derleyicisi tarafından yayılmadı. Daha önce, sadece **/ Za** derleyici anahtarı altında yayılan edildi.  Tek satırlı yorumlar C99'dan beri C standardının bir parçası olduğundan uyarılara artık gerek yoktur.

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

Kodun geriye dönük uyumlu olması gerekmiyorsa, C4001/C4179 bastırmayı kaldırarak uyarıyı önleyebilirsiniz. Kodun geriye dönük uyumlu olması gerekiyorsa, yalnızca C4619'u bastırın.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="__declspec-attributes-with-extern-c-linkage"></a>`__declspec`bağlantı `extern "C"` ile öznitelikleri

Visual Studio'nun önceki sürümlerinde, `__declspec(...)` derleyici `__declspec(...)` `extern "C"` bağlantı belirtiminden önce uygulandığında öznitelikleri göz ardı etti. Bu davranış, olası çalışma zamanı etkileriyle, kullanıcının istemediği kodun oluşturulmasına neden oldu. Uyarı Visual Studio sürüm 15.3 eklendi, ancak varsayılan olarak kapalıydı. Visual Studio 2017 sürüm 15.5'te uyarı varsayılan olarak etkinleştirilir.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Hatayı düzeltmek için bağlantı belirtimini __declspec özniteliğinden önce yerleştirin:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu yeni uyarı C4768 Visual Studio 2017 15.3 veya daha büyük (örneğin: sürüm 10.0.15063.0, ayrıca RS2 SDK olarak da bilinir) ile sevk edildi bazı Windows SDK başlıkları verilir. Ancak, Windows SDK üstbilgilerinin sonraki sürümleri (özellikle ShlObj.h ve ShlObj_core.h) uyarıyı üretmeyecek şekilde düzeltildi. Windows SDK üstbilgilerinden gelen bu uyarıyı gördüğünüzde, şu eylemleri yapabilirsiniz:

1. Visual Studio 2017 sürüm 15.5 sürümüyle birlikte gelen en son Windows SDK sürümüne geçin.

1. Windows SDK başlık bildiriminin #include etrafındaki uyarıyı kapatın:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern-constexpr-linkage"></a><a name="extern_linkage"></a>Extern constexpr bağlantı

Visual Studio önceki sürümlerinde, derleyici her zaman bir **constexpr** değişken iç bağlantı bile değişken **extern**işaretlenmiştir verdi. Visual Studio 2017 sürüm 15.5'te, yeni bir derleyici anahtarı **(/Zc:externConstexpr)** doğru standartlara uygun davranışlar sağlar. Sonunda bu davranış varsayılan olur.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Üstbilgi dosyası, ekstremite **constexpr**olarak bildirilen bir `__declspec(selectany)` değişken içeriyorsa, yinelenen bildirimlerinin doğru bir şekilde birleştirilmesi için işaretlemesi gerekir:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>**typeid** eksik sınıf türünde kullanılamaz

Visual Studio'nun önceki sürümlerinde derleyici aşağıdaki koda yanlış izin vererek yanlış tür bilgilerine neden oldu. Visual Studio 2017 sürüm 15.5'te derleyici doğru bir hata ortaya çıkarır:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdis_convertible-target-type"></a>`std::is_convertible`hedef türü

`std::is_convertible`hedef türün geçerli bir iade türü olmasını gerektirir. Visual Studio'nun önceki sürümlerinde derleyici, yanlış aşırı yük çözünürlüğü ve istenmeyen çalışma zamanı davranışına yol açabilecek soyut türlere yanlış izin verebilmiştir.  Aşağıdaki kod şimdi doğru C2338 yükseltir:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Hatayı önlemek için, `is_convertible` bir tür soyutsa işaretçi türü olmayan bir karşılaştırma başarısız olabileceğinden, işaretçi türlerini karşılaştırmanız gerekir:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="dynamic-exception-specification-removal-and-noexcept"></a><a name="noexcept_removal"></a>Dinamik özel durum belirtimi kaldırma ve **noexcept**

`throw()` C++17'de, **noexcept**için bir `throw(<type list>)` `throw(...)` diğer addır ve kaldırılır ve bazı türler **noexcept**içerebilir. Bu değişiklik, C++14 veya daha önce uyumlu kod ile kaynak uyumluluk sorunlarına neden olabilir. **/Zc:noexceptTypes-** anahtarı, genel olarak C++17 modunu kullanırken **noexcept'un** C++14 sürümüne dönmek için kullanılabilir. Tüm kodunuzu aynı anda yeniden yazmak zorunda kalmadan C++17'ye uyacak şekilde kaynak kodunuzu güncelleştirmenizi `throw()` sağlar.

Derleyici ayrıca artık C++17 modundaki bildirimlerde veya [/izin li](../build/reference/permissive-standards-conformance.md) yeni uyarı C5043 ile daha uyumsuz özel durum belirtimlerini tanılar.

Visual Studio 2017 sürümü 15.5'te **/std:c++17** anahtarı uygulandığında aşağıdaki kod C5043 ve C5040'ı oluşturur:

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

**/std:c++17'yi**kullanmaya devam ederken hataları kaldırmak için , komut satırına **/Zc:noexceptTypes-** anahtarını ekleyin veya kodunuzu aşağıdaki örnekte gösterildiği gibi **noexcept**kullanmak üzere güncelleştirin:

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

### <a name="inline-variables"></a>Satır dışı değişkenler

Statik constexpr veri üyeleri artık dolaylı olarak satır içidir, bu da bir sınıf içindeki bildirimlerinin artık onların tanımı olduğu anlamına gelir. Statik bir constexpr veri üyesi için satır dışı bir tanım kullanmak gereksizdir ve şimdi amortismana hazırdır. Visual Studio 2017 sürüm 15.5'te **/std:c++17** anahtarı uygulandığında aşağıdaki kod artık uyarı C5041 *'boyut' üretir: constexpr statik veri üyesi için out-of-line tanımı gerekli değildir ve C++17'de amortismana uygulanır*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)`uyarı C4768 şimdi varsayılan olarak

Uyarı Visual Studio 2017 sürüm 15.3 eklendi, ancak varsayılan olarak kapalıydı. Visual Studio 2017 sürüm 15.5'te uyarı varsayılan olarak açıktır. Daha fazla bilgi için, [declspec \_ \_öznitelikleri yeni uyarı](#declspec)bakın.

### <a name="defaulted-functions-and-__declspecnothrow"></a>Varsayılan işlevler ve`__declspec(nothrow)`

Derleyici daha önce varsayılan işlevlerin, `__declspec(nothrow)` ilgili temel/üye işlevlerinin özel durumlara izin verdiğinde bildirilmesine izin verebilmiştir. Bu davranış C++ standardına aykırıdır ve çalışma zamanında tanımlanmamış davranışlara neden olabilir. Standart, özel durum belirtimi uyuşmazlığı varsa, bu tür işlevlerin silinmiş olarak tanımlanmasını gerektirir.  **/std:c++17**altında, *silinmiş bir işleve başvurmaya çalışırken c2280'i aşağıdaki kod yükseltir. Açık özel durum belirtimi örtük bildiriminkiyle uyumsuz olduğundan işlev örtülü olarak silindi.*

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

Bu kodu düzeltmek için, varsayılan işlevden __declspec(nothrow) `= default` kaldırın veya gerekli özel durum işleme ile birlikte işlev için bir tanım kaldırın ve sağlayın:

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

### <a name="noexcept-and-partial-specializations"></a>**noexcept** ve kısmi uzmanlıklar

Tür sisteminde **ki noexcept** ile, belirli "çağrılabilir" türleri eşleştirmek için kısmi uzmanlıklar, işaretçilerden düğümlü işlevlere yönelik eksik kısmi uzmanlık nedeniyle birincil şablonu derlemeyi veya seçemeyebilir.

Bu gibi durumlarda, üye işlevlere **noexcept** işlev işaretçileri ve **noexcept** işaretçileri işlemek için ek kısmi uzmanlıklar eklemeniz gerekebilir. Bu aşırı yüklemeler yalnızca **/std:c++17** modunda yasaldır. C++14 ile geriye dönük uyumluluk sağlanmalıdır ve başkalarının tükettiği kodlar yazıyorsanız, bu yeni `#ifdef` aşırı yüklemeleri yönergeler içinde korumanız gerekir. Bağımsız bir modülde çalışıyorsanız, korumaları kullanmak `#ifdef` yerine **/Zc:noexceptTypes-** anahtarıyla derleyebilirsiniz.

Aşağıdaki kod **/std:c++14** altında derlenmiştir ancak **/std:c++17** altında "hata C2027:tanımlanmamış tür 'A\<T>' kullanımı" ile başarısız olur:

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

Derleyici yeni kısmi uzmanlık `A<void (*)() noexcept>`seçer, çünkü aşağıdaki kod **/std:c++17** altında başarılı:

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

## <a name="bug-fixes-and-other-behavior-changes-in-157"></a><a name="update_157"></a>Hata düzeltmeleri ve diğer davranış değişiklikleri 15.7

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++17: İlksınıf şablonundaki varsayılan bağımsız değişken

Bu davranış değişikliği sınıf şablonları için Şablon bağımsız değişken çıkarımı için bir ön koşuldur [- P0091R3](https://wg21.link/p0091r3).

Daha önce, derleyici birincil sınıf şablonundaki varsayılan bağımsız değişkeni yoksaydı:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

Visual Studio 2017 sürüm 15.7'de **/std:c++17** modunda varsayılan bağımsız değişken göz ardı edilmez:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Bağımlı ad çözümü

Bu davranış değişikliği sınıf şablonları için Şablon bağımsız değişken çıkarımı için bir ön koşuldur [- P0091R3](https://wg21.link/p0091r3).

Aşağıdaki örnekte, Visual Studio 15.6 ve önceki `D::type` derleyici sinif `B<T>::type` şablonuna göre çözülür.

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

Visual Studio 2017 sürüm 15.7, **in /std:c++17** modunda, D'deki **kullanarak** ifadedeki**tür adı** anahtar sözcüğü gerektirir. **Tür adı**olmadan, derleyici uyarı C4346 yükseltir: *'B<T\*>::type': bağımlı ad bir tür* ve hata C2061 değildir: *sözdizimi hatası: tanımlayıcı 'türü'*:

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

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++17: `[[nodiscard]]` öznitelik - uyarı düzeyi artışı

Visual Studio 2017 sürüm 15.7 in **/std:c++17** modunda, C4834 uyarı düzeyi ("'nodiscard' özniteliği ile fonksiyonun geri dönüş değeri") W3'ten W1'e yükseltilir. Uyarıyı **geçersiz**kılmak için bir dökümle veya **/wd:4834'ü** derleyiciye geçirerek devre dışı kullanabilirsiniz

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Variadic şablon oluşturucu taban sınıf başlatma listesi

Visual Studio'nun önceki sürümlerinde, şablon bağımsız değişkenleri eksik olan variadic şablon oluşturucu taban sınıf başlatma listesi hatalı bir şekilde hatasız olarak izin verildi. Visual Studio 2017 sürüm 15.7'de derleyici hatası ortaya çıkmıştır.

Visual Studio 2017 sürüm 15.7'deki aşağıdaki kod örneği *C2614 hatasını yükseltir: D\<int>: yasadışı üye başlatma: 'B' bir üs veya üye değildir*

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

Hatayı düzeltmek için B() ifadesini B\<T>() olarak değiştirin.

### <a name="constexpr-aggregate-initialization"></a>**constexpr** toplu başlatma

C++ derleyicisinin önceki sürümleri nde **constexpr** toplam başlatma yanlış işlenir; toplam init-list çok fazla öğe vardı geçersiz kod kabul etti ve bunun için kötü codegen üretti. Aşağıdaki kod bu kodun bir örneğidir:

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

Visual Studio 2017 sürüm 15.7 güncelleme 3 ve sonrası, önceki örnek şimdi *C2078 çok fazla başlatılması*yükseltir. Aşağıdaki örnek, kodun nasıl düzeltileni gösterir. İç içe `std::array` geçme listeleri içeren bir adizibaşlangıç yaparken, iç diziye kendi ayraçlı bir listesini verin:

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

## <a name="bug-fixes-and-behavior-changes-in-158"></a><a name="update_158"></a>Hata düzeltmeleri ve davranış değişiklikleri 15.8

Visual Studio 2017 sürüm 15.8'deki derleyici değişikliklerinin tümü hata düzeltmeleri ve davranış değişiklikleri kategorisine girer ve aşağıda listelenmiştir:

### <a name="typename-on-unqualified-identifiers"></a>niteliksiz tanımlayıcılarda **yazı adı**

[/izin verme](../build/reference/permissive-standards-conformance.md) modunda, diğer ad şablontanımlarında niteliksiz tanımlayıcılarda sahte**ad adları** anahtar kelimeler artık derleyici tarafından kabul edilmez. Aşağıdaki kod şimdi C7511 *'T' üretir: 'typename' anahtar kelime nitelikli bir ad takip edilmelidir:*

```cpp
template <typename T>
using  X = typename T;
```

Hatayı düzeltmek için ikinci satırı `using  X = T;`' da ' olarak değiştirin

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()`diğer ad şablon tanımlarının sağ tarafında

[__declspec](../cpp/declspec.md) artık bir diğer ad şablontanımının sağ tarafında izin verilmez. Bu kod daha önce kabul edilmiş, ancak derleyici tarafından yoksayılmış ve takma ad kullanıldığında hiçbir zaman bir amortisman uyarısı ile sonuçlanmaz.

Bunun [ \[ \[yerine, amortismana konan\] ](../cpp/attributes.md) standart C++ özniteliği kullanılabilir ve Visual Studio 2017 sürüm 15.6'da saygı duyulur. Aşağıdaki kod şimdi C2760 *sözdizimi hatası üretir: beklenmeyen belirteç '__declspec', beklenen 'tür belirteç':*

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

Hatayı düzeltmek için koda aşağıdaki şekilde değiştirin (diğer ad tanımının '=' önce söyleğe yerleştirilen özniteliği ile):

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>İki aşamalı ad arama tanılama

İki aşamalı ad araması, şablon gövdelerinde kullanılan bağımlı olmayan adların tanım zamanında şablontarafından görünür olmasını gerektirir. Daha önce, Microsoft C++ derleyicisi anlık bir zamana kadar aranmayan bir ad bırakırdı. Şimdi, bağımlı olmayan adların şablon gövdesine bağlanmasını gerektirir.

Bunun ortaya çıkabildiği bir yol, bağımlı taban sınıflarına aramadır. Daha önce derleyici, tüm türler çözüldüğünde anlık kullanım sırasında aranacaklarından, bağımlı temel sınıflarda tanımlanan adların kullanılmasına izin veremişti. Şimdi bu kod bir hata olarak kabul edilir. Bu gibi durumlarda, değişkeni taban sınıf türüyle niteleyerek veya örneğin bir `this->` işaretçi ekleyerek bağımlı hale getirerek anında bakmaya zorlayabilirsiniz.

[/izin verme](../build/reference/permissive-standards-conformance.md) modunda, aşağıdaki kod şimdi C3861 yükseltir: *'base_value': tanımlayıcı bulunamadı:*

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

Hatayı düzeltmek için deyimi `return` ' `return this->base_value;`yi ' olarak değiştirin

**Not:** Boost python kitaplığında, [unwind_type.hpp'deki](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp)şablon iletme bildirimi için msvc'ye özgü bir geçici çözüm uzun zamandır vardır. Visual Studio 2017 sürüm 15.8 (_MSC_VER=1915) ile başlayan [/izin verme modu](../build/reference/permissive-standards-conformance.md) altında, MSVC derleyicisi bağımsız değişkene bağımlı ad aramasını (ADL) doğru yapar ve diğer derleyicilerle tutarlıdır, bu geçici çözüm korumasını gereksiz kılar. C3861 hatasını önlemek *için: 'unwind_type': tanımlayıcı bulunamadı,* üstbilgi dosyasını güncelleştirmek için Boost repo'sunda [PR 229'a](https://github.com/boostorg/python/pull/229) bakın. [VCPKG](../build/vcpkg.md) Boost paketini zaten yamaladık, bu nedenle Boost kaynaklarınızı vcpkg'dan alır veya yükseltirseniz, yamanızı ayrı olarak uygulamanız gerekmez.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>iletme bildirimleri ve ad alanında tanımlar`std`

C++ standardı, kullanıcının ad alanına `std`iletme bildirimleri veya tanımları eklemesine izin vermez. Ad alanına veya ad alanı `std` `std` içindeki ad alanına bildirimler veya tanımlar eklemek artık tanımlanmamış davranışlarla sonuçlanır.

Gelecekte microsoft, bazı standart kitaplık türlerinin tanımlandığı konumu taşır. Bu değişiklik, ad alanına `std`ek açıklamalar ekleyen varolan kodu kıracak. Yeni bir uyarı, C4643, bu tür kaynak sorunları belirlemenize yardımcı olur. Uyarı **/varsayılan** modda etkinleştirilir ve varsayılan olarak kapalıdır. **/Wall** veya **/WX**ile derlenen programları etkileyecektir.

Aşağıdaki kod şimdi C4643 yükseltir: *İleri ad alanı std 'vektör' bildiren C++ Standart tarafından izin verilmez.*

```cpp
namespace std {
    template<typename T> class vector;
}
```

Hatayı gidermek için, iletme bildirimi yerine **bir dahil** yönergesi kullanın:

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>Kendilerine temsilci veren yapıcılar

C++ standardı, bir derleyicinin, bir kurucu nun kendisine yetki verirken bir tanı yayışmasını önerir. [/std:c++17](../build/reference/std-specify-language-standard-version.md) ve [/std:c++son](../build/reference/std-specify-language-standard-version.md) modlarında Microsoft C++ derleyicisi c7535'i şimdi yükseltir: *'X::X': kurucu nun kendisini adlandırdığı nı çağırır.*

Bu hata olmadan, aşağıdaki program derlenir, ancak sonsuz bir döngü oluşturur:

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
};
```

Sonsuz döngüden kaçınmak için, farklı bir oluşturucuya temsilci:

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>`offsetof`sabit ifadelerle

[offsetof](../c-runtime-library/reference/offsetof-macro.md) geleneksel bir [reinterpret_cast](../cpp/reinterpret-cast-operator.md)gerektiren bir makro kullanılarak uygulanmıştır. Bu kullanım, sürekli ifade gerektiren bağlamlarda yasa dışıdır, ancak Microsoft C++ derleyicisi geleneksel olarak buna izin verilmiştir. Standart `offsetof` kitaplığın bir parçası olarak gönderilen makro doğru bir derleyici içsel **(__builtin_offsetof)** kullanır, ancak birçok `offsetof`kişi kendi tanımlamak için makro hile kullandık.

Visual Studio 2017 sürüm 15.8'de derleyici, kodun standart C++ davranışına uymasına yardımcı olmak için bu `reinterpret_cast` işleçlerin varsayılan modda görünebileceği alanları kısıtlar. [/izin altında-](../build/reference/permissive-standards-conformance.md), kısıtlamalar daha da katıdır. Sabit ifadeler gerektiren `offsetof` yerlerde bir sonucu kullanarak sabit ifadelerde desen makro tabanlı ofset c4644 kullanımı uyarı kodları sorunları kod neden olabilir *standart dışıdır; c++ standart kitaplık yerine tanımlanan ofset veya* C2975 *geçersiz şablon argümanı, beklenen derleme zamanı sabit ifade*.

Aşağıdaki kod C4644'ü **/default** ve **/std:c++17** modlarında ve C2975'i [/izin li modda](../build/reference/permissive-standards-conformance.md) yükseltir:

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

Hatayı düzeltmek için, `offsetof` cstddef> yoluyla \<tanımlandığı şekilde kullanın:

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

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>paket genişletmetabi temel sınıflarda cv-elemeleri

Microsoft C++ derleyicisinin önceki sürümlerinde, paket genişletmesine tabi olan bir taban sınıf cv niteleyicisi olduğu algılamadı.

Visual Studio 2017 sürüm 15.8, [/izin-](../build/reference/permissive-standards-conformance.md) modunda aşağıdaki kod C3770 *'const S'i yükseltir: geçerli bir taban sınıf değildir:*

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>**şablon** anahtar kelime ve iç içe-ad-belirteçleri

[/izin verme](../build/reference/permissive-standards-conformance.md) modunda, derleyici artık **şablon** anahtar kelimesinin, bağımlı iç içe geçmiş bir ad belirticiden sonra geldiğinde bir şablon adından önce olmasını gerektirir.

[/izin verme modundaki](../build/reference/permissive-standards-conformance.md) aşağıdaki kod artık C7510'u yükseltir: *'örnek': bağımlı şablon adının kullanımı 'template' ile önceden belirlenmiş olmalıdır. not: sınıf şablonu anlık 'X\<T>' derleniyor referans bakın:*

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

Hatayı düzeltmek için, aşağıdaki örnekte `Base<T>::example<int>();` gösterildiği **gibi, şablon** anahtar sözcük ifadesini ifadeye ekleyin:

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

## <a name="bug-fixes-and-behavior-changes-in-159"></a><a name="update_159"></a>Hata düzeltmeleri ve davranış değişiklikleri 15.9

### <a name="identifiers-in-member-alias-templates"></a>Üye takma ad şablonlarında tanımlayıcılar

Üye diğer ad şablonu tanımında kullanılan bir tanımlayıcı, kullanılmadan önce bildirilmelidir.

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

Visual Studio 2017 sürüm 15.9'da, [/izin verme](../build/reference/permissive-standards-conformance.md) modunda, derleyici C3861'i yükseltir: *'from_template': tanımlayıcı bulunamadı*.

Hatayı düzeltmek için, `from_template` `from_template_t`önce bildirin.

### <a name="modules-changes"></a>Modüller değişir

Visual Studio 2017 sürüm 15.9'da derleyici, modüller için komut satırı seçenekleri modül oluşturma ve modül tüketim tarafları arasında tutarlı olmadığında C5050'yi yükseltir. Aşağıdaki örnekte, iki sorun vardır:

- Tüketim tarafında (main.cpp), **/EHsc** seçeneği belirtilmemiş.

- C++ sürümü oluşturma tarafında **/std:c++17,** tüketim tarafında **ise /std:c++14'dür.**

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Derleyici, bu durumların her ikisi için de C5050'yi yükseltir: *C5050'yi uyarmak: Modül 'm'i alırken olası uyumsuz ortam: uyumsuz C++ sürümleri.  Geçerli "201402" modül sürümü "201703"*.

Derleyici ayrıca .ifc dosyası nın kurcalandığı zaman C7536'yı da yükseltir. Modül arabiriminin üstbilgisi, altındaki içeriğin SHA2 karmasını içerir. Alma da ,.ifc dosyası aynı şekilde ele alınır ve üstbilgide sağlanan karma ile karşılaştırılır. Bunlar eşleşmiyorsa, hata C7536 yükseltilir: *ifc başarısız bütünlük denetler.  Beklenen SHA2: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'*.

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Takma adlar ve çıkarılmayan bağlamları içeren kısmi sıralama

Uygulamalar, çıkarılmamış bağlamlarda diğer adları içeren kısmi sıralama kurallarında farklılaşır. Aşağıdaki örnekte, GCC ve Microsoft C++ derleyicisi [(/izin modunda)](../build/reference/permissive-standards-conformance.md) bir hata yükseltirken, Clang kodu kabul eder.

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

Önceki örnek, C2668'i yükseltir:

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

Uygulama farklılığı, C++ standart ifadelerindeki bir gerilemeden kaynaklanır. Temel sorun 2235'in çözümü, bu aşırı yüklemelerin sipariş edilmesine izin veren bazı metinleri kaldırdı. Geçerli C++ standardı bu işlevleri kısmen sipariş etmek için bir mekanizma sağlamaz, bu nedenle belirsiz olarak kabul edilirler.

Geçici çözüm olarak, bu sorunu çözmek için kısmi sıralamaya güvenmemenizi tavsiye ettik. Bunun yerine, belirli aşırı yüklemeleri kaldırmak için SFINAE'yi kullanın. Aşağıdaki örnekte, aşağıdakilerin uzmanlık `IsA` alanı olduğunda `Alloc` ilk aşırı yüklemeyi kaldırmak `A`için bir yardımcı sınıf kullanırız:

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

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>Şablonlu işlev tanımlarında yasadışı ifadeler ve gerçek olmayan türler

Yasa dışı ifadeler ve edebi olmayan türler artık açıkça özelleştirilmiş şablonlu işlevlerin tanımlarında doğru tanılanır. Daha önce, bu tür hatalar işlev tanımı için yayımlanmadı. Ancak, sürekli bir ifadenin parçası olarak değerlendirildiğinde, yasa dışı ifade veya gerçek olmayan tür yine de teşhis edilmiş olurdu.

Visual Studio'nun önceki sürümlerinde aşağıdaki kod uyarı olmadan derlenmiştir:

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

Visual Studio 2017 sürüm 15.9'da kod şu hatayı ortaya çıkarır:

```Output
error C3615: constexpr function 'S<int>::f' cannot result in a constant expression.
note: failure was caused by call of undefined function or one not declared 'constexpr'
note: see usage of 'g'.
```

Hatayı önlemek için, **constexpr** niteleyicisini işlevin `f()`açık anlık tantanasından kaldırın.

::: moniker-end

::: moniker range="vs-2015"

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>Visual Studio 2015'te C++ uyumluluk iyileştirmeleri

Visual Studio 2015 Update 3'teki uyumluluk geliştirmelerinin tam listesi için [Visual C++ What's New 2003-2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015)bölümüne bakın.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft C++ dil uygunluk tablosu](../visual-cpp-language-conformance.md)
