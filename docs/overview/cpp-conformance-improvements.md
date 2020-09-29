---
title: C++ uygunluk iyileştirmeleri
ms.date: 08/04/2020
description: Visual Studio 'da Microsoft C++, C++ 20 dil standardı ile tam uygunluğu doğru ilerliyor.
ms.technology: cpp-language
ms.openlocfilehash: 3cf06b092b79068b22e62dfdbbcfbd2c2cf5ad91
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500250"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Visual Studio 2017’deki C++ uyumluluk geliştirmeleri

Microsoft C++ her sürümde uyumluluk geliştirmeleri ve hata düzeltmeleri yapar. Bu makalede, ana sürüme ve ardından sürüme göre iyileştirmeler listelenmektedir. Ayrıca, sürüme göre önemli hata düzeltmelerini de listeler. Belirli bir sürümdeki değişikliklere doğrudan geçmek için **Bu makale** listesinde öğesini kullanın.

::: moniker range="vs-2019"

## <a name="conformance-improvements-in-visual-studio-2019-rtw-version-160"></a><a name="improvements_160"></a> Visual Studio 2019 RTW (sürüm 16,0) ile uyumluluk geliştirmeleri

Visual Studio 2019 RTW, Microsoft C++ derleyicisinde aşağıdaki uygunluk geliştirmelerini, hata düzeltmelerini ve davranış değişikliklerini içerir (MSVC)

**Note:** C++ 20 **`/std:c++latest`** uygulamasının her ikisi de derleyici ve IntelliSense için, c++ 20 uygulama tamamlanana kadar modunda kullanılabilir hale getirilir. Bu sırada, **`/std:c++20`** derleyici modu tanıtılacaktır.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modüller desteği

Modüller artık C++ 20 standardında resmi olarak bulunur. Visual Studio 2017 sürüm 15,9 ' ye geliştirilmiş destek eklenmiştir. Daha fazla bilgi için bkz. [MSVC 2017 sürüm 15,9 Ile C++ modüllerinde daha iyi şablon desteği ve hata algılama](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Toplu türün değiştirilmiş belirtimi

C++ 20 ' de bir toplama türünün belirtimi değişmiştir (bkz. [Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla](https://wg21.link/p1008r1)). Visual Studio 2019 ' de, altında, **`/std:c++latest`** Kullanıcı tarafından tanımlanmış bir oluşturucuya sahip bir sınıf (örneğin, bir Oluşturucu `= default` veya) bir `= delete` toplama değildir. Daha önce, yalnızca Kullanıcı tarafından sunulan oluşturucular bir sınıfın bir toplama olmasını eledi. Bu değişiklik, bu tür türlerin nasıl başlatıladığıyla ilgili ek kısıtlamalar getirir.

Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak şu Visual Studio 2019 ' de C2280 ve C2440 hataları oluşturur **`/std:c++latest`** :

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

### <a name="partial-support-for-operator-"></a>İçin kısmi destek `operator <=>`

[P0515R3](https://wg21.link/p0515r3) C++ 20, `<=>` "Spaceship işleci" olarak da bilinen üç yönlü karşılaştırma işlecini tanıtır. Visual Studio 2019, **`/std:c++latest`** artık izin verilmeyen sözdizimi için hataları yükselterek operatör için kısmi destek sunar. Örneğin, aşağıdaki kod Visual Studio 2017 hatası olmadan derlenir, ancak altında Visual Studio 2019 ' de birden çok hata oluşturuyor **`/std:c++latest`** :

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

Hataları önlemek için, son açı ayracından önce sorunlu satıra bir boşluk ekleyin: `U<&S::operator<= > u;` .

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Eşleşmeyen CV niteleyicileri olan türlere başvurular

Daha önce, MSVC, en üst düzeyin altında eşleşmeyen CV niteleyicilerine sahip bir türden başvurunun doğrudan bağlamasını izin verilir. Bu bağlama, başvuruya göre başvuruda bulunulan düzgün const verileri değişikliğine izin verebilir. Derleyici artık standart tarafından gerekli olduğu gibi geçici bir durum oluşturur. Visual Studio 2017 ' de, aşağıdaki kod uyarılar olmadan derlenir. Visual Studio 2019 ' de, derleyici uyarı C4172: `<func:#1 "?PData@X@@QBEABQBXXZ"> returning address of local variable or temporary.` :

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

### <a name="reinterpret_cast-from-an-overloaded-function"></a>`reinterpret_cast` aşırı yüklenmiş bir işlevden

İçin bağımsız değişken, **`reinterpret_cast`** aşırı yüklenmiş bir işlevin adresine izin verilen bağlamların değil. Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019, C2440 hatasını oluşturuyor: `cannot convert from 'overloaded-function' to 'fp'` :

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

C++ 14 ' te lambda kapatma türleri değişmez değer değildir. Bu kuralın birincil sonucu bir lambda değişkenine atanmayabilir **`constexpr`** . Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019, C2127 hatasını oluşturuyor: `'l': illegal initialization of 'constexpr' entity with a non-constant expression` :

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Hatayı önlemek için, **`constexpr`** niteleyiciyi kaldırın ya da uyumluluk modunu olarak değiştirin **`/std:c++17`** .

### <a name="stdcreate_directory-failure-codes"></a>`std::create_directory` hata kodları

C++ 20 ' den koşullu [P1164](https://wg21.link/p1164r1) uygulandı. Bu `std::create_directory` , hedefin hata durumunda zaten bir dizin olup olmadığını denetlemek için değişir. Daha önce, tüm ERROR_ALREADY_EXISTS türü hataları başarılı oldu-ancak Dizin oluşturulmamış kodlara açıldı.

### `operator<<(std::ostream, nullptr_t)`

Her [LWG 2221](https://cplusplus.github.io/LWG/issue2221)için, `operator<<(std::ostream, nullptr_t)` akışlara nullptrs yazmak için eklenmiştir.

### <a name="additional-parallel-algorithms"></a>Ek paralel algoritmalar

,,,,, Ve ' nin yeni paralel sürümleri `is_sorted` `is_sorted_until` `is_partitioned` `set_difference` `set_intersection` `is_heap` `is_heap_until` .

### <a name="atomic-initialization"></a>Atomik başlatma

[P0883 "atomik başlatma düzeltme"](https://wg21.link/p0883r1) `std::atomic` değeri değeri, varsayılan olarak başlatmak yerine içerilen T 'yi başlatın. Microsoft standart kitaplığı ile Clang/LLVM kullanılırken bu çözüm etkinleştirilir. İşlem sırasında oluşan bir hata için geçici çözüm olarak, Microsoft C++ derleyicisi için şu anda devre dışı bırakılmıştır **`constexpr`** .

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` ve `remove_cvref_t`

`remove_cvref` `remove_cvref_t` [P0550](https://wg21.link/p0550r2)öğesinden ve tür nitelikleri uygulandı. Bunlar, bir türden başvuru ve CV nitelemesini kaldırma işlevleri ve diziler (ve ' nin aksine) olmadan bir türden kaldırır `std::decay` `std::decay_t` .

### <a name="feature-test-macros"></a>Özellik testi makroları

[P0941R2-Feature-test makroları](https://wg21.link/p0941r2) , desteğiyle birlikte tamamlanmıştır `__has_cpp_attribute` . Özellik testi makroları tüm standart modlarda desteklenir.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla

[C++ 20 P1008R1-Kullanıcı tarafından belirtilen oluşturucularla proyaları toplamalar](https://wg21.link/p1008r1) tamamlanmıştır.

## <a name="conformance-improvements-in-161"></a><a name="improvements_161"></a> 16,1 sürümündeki uyumluluk geliştirmeleri

### <a name="char8_t"></a>char8_t

[P0482r6](https://wg21.link/p0482r6). C++ 20, UTF-8 kod birimlerini temsil etmek için kullanılan yeni bir karakter türü ekler. `u8` C++ 20 ' deki dize sabit değerleri `const char8_t[N]` , yerine `const char[N]` , daha önce gelen bir durumdur. [N2231](https://wg14.link/n2231)içinde C standardı için benzer değişiklikler önerilir. **`char8_t`** Geriye dönük uyumluluk düzeltme için öneriler [P1423r3](https://wg21.link/p1423r3)içinde verilmiştir. Microsoft C++ derleyicisi, **`char8_t`** derleyici seçeneğini belirttiğinizde Visual Studio 2019 sürüm 16,1 ' de destek ekler **`/Zc:char8_t`** . Gelecekte, [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) aracılığıyla c++ 17 davranışına geri döndürülebilmesi ile desteklenecektir **`/Zc:char8_t-`** . IntelliSense 'i destekleyen EDG derleyicisi henüz desteklememektedir. Yalnızca gerçek derlemeyi etkilemeden yalnızca bir IntelliSense ile ilgili hataları görebilirsiniz.

#### <a name="example"></a>Örnek

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>std:: type_identity programlayıcılarına ve std:: Identity işlevi nesnesi

[P0887R1 type_identity](https://wg21.link/p0887r1). Kullanım dışı bırakılan `std::identity` sınıf şablonu uzantısı kaldırılmıştır ve c++ 20 `std::type_identity` programlayıcılarına ve `std::identity` Function nesnesiyle değiştirilmiştir. Her ikisi de yalnızca altında kullanılabilir [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) .

Aşağıdaki örnek, `std::identity` \<type_traits> Visual Studio 2017 ' de için kullanımdan kaldırma uyarısı C4996 (içinde tanımlanmıştır) üretir:

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

Aşağıdaki örnek, New `std::identity` (' de tanımlı) ' nin \<functional> Yeni ile birlikte nasıl kullanılacağını gösterir `std::type_identity` :

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Genel Lambdalar için söz dizimi denetimleri

Yeni lambda işlemcisi, [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) ile diğer dil modunun altında veya altında genel Lambdalar içinde bazı uyumluluk modu sözdizimsel denetimlerine izin verebilir **`/experimental:newLambdaProcessor`** .

Visual Studio 2017 ' de, bu kod uyarılar olmadan derlenir, ancak Visual Studio 2019 ' de hata C2760 hatası veriyor `syntax error: unexpected token '\<id-expr>', expected 'id-expression'` :

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

[P0846R0](https://wg21.link/p0846r0) (c++ 20) açık şablon bağımsız değişkenleriyle işlev çağrısı ifadeleri için bağımsız değişkene bağlı arama aracılığıyla işlev şablonlarını bulma özelliği arttı. Gerektirir **`/std:c++latest`** .

### <a name="designated-initialization"></a>Belirlenmiş başlatma

[P0329R4](https://wg21.link/p0329r4) (c++ 20) *belirtilen başlatma* , söz dizimi kullanılarak toplu başlatma işleminde belirli üyelerin seçili olmasına izin verir `Type t { .member = expr }` . Gerektirir **`/std:c++latest`** .

### <a name="new-and-updated-standard-library-functions-c20"></a>Yeni ve güncelleştirilmiş standart kitaplık işlevleri (C++ 20)

- `starts_with()` ve `ends_with()` için `basic_string` `basic_string_view` .
- İlişkili kapsayıcılar için `contains()`.
- `list` ve `forward_list` için `remove()`, `remove_if()` ve `unique()` artık `size_type` değerini döndürüyor.
- `shift_left()` ve `shift_right()`\<algorithm> üzerine eklendi.

## <a name="conformance-improvements-in-162"></a><a name="improvements_162"></a> 16,2 sürümündeki uyumluluk geliştirmeleri

### <a name="noexcept-constexpr-functions"></a>`noexcept``constexpr`işlevler

**`constexpr`** işlevler, **`noexcept`** sabit bir ifadede kullanıldığında artık varsayılan olarak değerlendirilmez. Bu davranış değişikliği [CWG 1351](https://wg21.link/cwg1351) çözünürlükten gelir ve ' de etkinleştirilir [`/permissive-`](../build/reference/permissive-standards-conformance.md) . Aşağıdaki örnek Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' te C2338 üretir:

```cpp
constexpr int f() { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept"); // C2338 in 16.2
}
```

Hatayı onarmak için **`noexcept`** ifadeyi işlev bildirimine ekleyin:

```cpp
constexpr int f() noexcept { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept");
}
```

### <a name="binary-expressions-with-different-enum-types"></a>Farklı enum türlerine sahip ikili ifadeler

C++ 20, işlenen her zamanki aritmetik dönüştürmeleri kullanım dışı bıraktı, burada:

- Bir işlenen sabit listesi türüdür ve

- diğeri farklı bir numaralandırma türü veya kayan nokta türüdür.

Daha fazla bilgi için bkz. [P1120R0](https://wg21.link/p1120r0).

Visual Studio 2019 sürüm 16,2 ve sonraki sürümlerde, derleyici seçeneği etkinleştirildiğinde aşağıdaki kod bir düzey 4 uyarısı üretir [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) :

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

Bir numaralandırma ve kayan nokta türü arasında ikili bir işlem kullanmak, [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkinleştirildiğinde bir uyarıdır:

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

Dizi türünün iki işleneni arasındaki eşitlik ve ilişkisel karşılaştırmalar, C++ 20 ' de ([P1120R0](https://wg21.link/p1120r0)) kullanım dışıdır. Diğer bir deyişle, iki dizi arasındaki karşılaştırma işlemi (derece ve kapsam benzerlikleri) artık bir uyarıdır. Visual Studio 2019 sürüm 16,2 ' den başlayarak, aşağıdaki kod C5056 oluşturur: `operator '==': deprecated for array types` [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği etkinleştirildiğinde:

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

### <a name="effect-of-defining-spaceship-operator-on--and-"></a>Ve üzerinde Spaceship işlecinin tanımlanmasıyla ilgili efekt `==``!=`

Spaceship işlecinin ( **`<=>`** ) tek başına tanımı, **`==`** **`!=`** Spaceship işleci **`= default`** ([P1185R2](https://wg21.link/p1185r2)) olarak işaretlenmedikçe veya içeren ifadeleri artık yeniden yazmayacaktır. Aşağıdaki örnek Visual Studio 2019 RTW ve sürüm 16,1 ' de derlenir, ancak Visual Studio 2019 sürüm 16,2 ' te C2678 üretir:

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

- \<charconv>`to_chars()`sabit/bilimsel duyarlıkla. (Genel duyarlık Şu anda 16,4 için planlanmaktadır.)
- [P0020R6](https://wg21.link/p0020r6): atomik \<float> , atomik \<double> , atomik\<long double>
- [P0463R1](https://wg21.link/p0463r1): endian
- [P0482R6](https://wg21.link/p0482r6): char8_t Için kitaplık desteği
- [P0600R1](https://wg21.link/p0600r1): [ \[ NODISCARD]] STL, Bölüm 1
- [P0653R2](https://wg21.link/p0653r2): to_address ()
- [P0754R2](https://wg21.link/p0754r2): \<version>
- [P0771R1](https://wg21.link/p0771r1): noexcept std:: işlevin taşıma Oluşturucusu

## <a name="conformance-improvements-in-visual-studio-2019-version-163"></a><a name="improvements_163"></a> Visual Studio 2019 sürüm 16,3 ' de uyumluluk geliştirmeleri

### <a name="stream-extraction-operators-for-char-removed"></a>Char * için akış ayıklama işleçleri kaldırıldı

Karakterlere işaretçi için akış ayıklama işleçleri kaldırıldı ve karakter dizisi ( [P0487R1](https://wg21.link/p0487r1)başına) için ayıklama işleçleri tarafından değiştirildi. WG21 kaldırılan aşırı yüklemeleri güvensiz kabul eder. [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md)Modda aşağıdaki örnek şu şekilde C2679 üretir: `binary '>>': no operator found which takes a right-hand operand of type 'char*' (or there is no acceptable conversion)`

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

### <a name="new-keywords-requires-and-concept"></a>Yeni anahtar sözcükler `requires` ve `concept`

Yeni anahtar sözcükler **`requires`** ve **`concept`** Microsoft C++ derleyicisine eklenmiştir. Modda bir tanımlayıcı olarak birini kullanmayı denerseniz [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) , derleyici C2059: ' i yükseltir `syntax error` .

### <a name="constructors-as-type-names-disallowed"></a>Tür adları olarak oluşturucular izin verilmiyor

Derleyici artık Oluşturucu adlarını bu durumda eklenen sınıf adları olarak kabul eder: bir sınıf şablonu özelleştirmesine bir diğer addan sonra tam ad halinde görüntülendiklerinde. Daha önce, oluşturucular diğer varlıkları bildirmek için bir tür adı olarak kullanılabilir. Aşağıdaki örnek artık C3646 `'TotalDuration': unknown override specifier` üretir:

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

### <a name="stricter-checking-of-extern-c-functions"></a>İşlevlerin daha sıkı denetlenmesi `extern "C"`

Bir **`extern "C"`** işlev farklı ad alanlarında bildirilirse, Microsoft C++ derleyicisinin önceki sürümleri bildirimlerin uyumlu olup olmadığını denetmedi. Visual Studio 2019 sürüm 16,3 ' den başlayarak, derleyici uyumluluğu denetler. [`/permissive-`](../build/reference/permissive-standards-conformance.md)Modunda, aşağıdaki kod C2371 ve C2733 hatalarını üretir `redefinition; different basic types` `you cannot overload a function with C linkage` :

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

Önceki örnekteki hataları önlemek için, **`bool`** her iki bildiriminde tutarlı olarak yerine kullanın `BOOL` `f` .

### <a name="standard-library-improvements"></a>Standart Kitaplık geliştirmeleri

Standart olmayan üstbilgiler \<stdexcpt.h> ve \<typeinfo.h> kaldırılmıştır. Bunun yerine, standart üst bilgileri ve sırasıyla dahil olmak üzere kodu içerir \<exception> \<typeinfo> .

## <a name="conformance-improvements-in-visual-studio-2019-version-164"></a><a name="improvements_164"></a> Visual Studio 2019 sürüm 16,4 ' de uyumluluk geliştirmeleri

### <a name="better-enforcement-of-two-phase-name-lookup-for-qualified-ids-in-permissive-"></a>' Deki tam kimlikler için iki aşamalı ad araması daha iyi zorlanmaktadır `/permissive-`

İki aşamalı ad arama, şablon gövdelerinde kullanılan bağımlı olmayan adların, tanım zamanında şablona görünür olması gerekir. Daha önce, bu tür adlar şablon örneği oluşturulurken bulunmuş olabilir. Bu değişiklik, bayrağın altına MSVC içinde taşınabilir ve uyumlu kod yazmayı kolaylaştırır [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

Visual Studio 2019 sürüm 16,4 ' de **`/permissive-`**  bayrak kümesiyle, aşağıdaki örnek bir hata üretir, çünkü `N::f` `f<T>` şablon tanımlandığında görünür değildir:

```cpp
template <class T>
int f() {
    return N::f() + T{}; // error C2039: 'f': is not a member of 'N'
}

namespace N {
    int f() { return 42; }
}
```

Genellikle, bu hata, aşağıdaki örnekte gösterildiği gibi eksik üstbilgiler veya iletme bildirimi işlevleri veya değişkenleri eklenerek düzeltilebilir:

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

MSVC derleyicisi artık Uyumluluk modu 'nda () [CWG sorun 903](https://wg21.link/cwg903) ' i uygular **`/permissive-`** . Bu kural, tam sayı sabiti ifadelerinin örtük dönüştürmelerine izin vermez (' 0 ' tamsayı sabiti hariç), null işaretçi sabitlerine izin vermez. Aşağıdaki örnek uyumluluk modunda C2440 üretir:

```cpp
int* f(bool* p) {
    p = false; // error C2440: '=': cannot convert from 'bool' to 'bool *'
    p = 0; // OK
    return false; // error C2440: 'return': cannot convert from 'bool' to 'int *'
}
```

Hatayı onarmak için **`nullptr`** yerine kullanın **`false`** . 0 sabit değerine hala izin veriliyor:

```cpp
int* f(bool* p) {
    p = nullptr; // OK
    p = 0; // OK
    return nullptr; // OK
}
```

### <a name="standard-rules-for-types-of-integer-literals"></a>Tamsayı sabit değerleri türleri için standart kurallar

Uyumluluk modunda (tarafından etkinleştirilir [`/permissive-`](../build/reference/permissive-standards-conformance.md) ), MSVC, tam sayı sabit değerleri türleri için standart kuralları kullanır. Ondalık sabit değerleri **`signed int`** daha önce verilen türe sığmayacak kadar büyük **`unsigned int`** . Artık bu tür değişmez değerler bir sonraki en büyük **`signed`** tamsayı türü olarak verilmiştir **`long long`** . Ayrıca, bir türe sığmayacak kadar büyük olan değişmez değerler, **`signed`** türü olarak verilebilir **`unsigned long long`** .

Bu değişiklik, farklı uyarı tanılamaları oluşturulmasını ve değişmez değerler üzerinde aritmetik işlemler için davranış farklılıkları oluşmasına neden olabilir.

Aşağıdaki örnekte, Visual Studio 2019 sürüm 16,4 ' deki yeni davranış gösterilmektedir. `i`Değişken artık türündedir **`unsigned int`** . Uyarının oluşturulma nedeni budur. Değişkenin yüksek sıralı bitleri `j` 0 olarak ayarlanır.

```cpp
void f(int r) {
    int i = 2964557531; // warning C4309: truncation of constant value
    long long j = 0x8000000000000000ll >> r; // literal is now unsigned, shift will fill high-order bits with 0
}
```

Aşağıdaki örnek, eski davranışı nasıl tutacağınızı ve uyarı ve çalışma zamanı davranış değişikliğini nasıl önleyeceğinizi gösterir:

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

Standart 'ın *meta. rqmts* alt yan tümcesiyle uyumlu olarak, MSVC derleyicisi artık ad alanındaki belirtilen şablonlardan birinin Kullanıcı tanımlı özelleştirmesi bulduğunda bir hata oluşturur `type_traits` `std` . Aksi belirtilmediği takdirde, bu tür Uzmanlıklar tanımsız davranışa neden olur. Aşağıdaki örnek, kuralı ihlal ettiğinden tanımsız davranışa sahiptir ve **`static_assert`** hata C2338 hatasıyla başarısız olur.

```cpp
#include <type_traits>
struct S;

template<>
struct std::is_fundamental<S> : std::true_type {};

static_assert(std::is_fundamental<S>::value, "fail");
```

Hatayı önlemek için, tercih edilen öğeden devralan bir yapı tanımlayın `type_trait` ve şunları yapın:

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

MSVC derleyicisi artık seçenek etkinleştirildiğinde [P1630R1](https://wg21.link/p1630r1) başına karşılaştırma işleçleri için aşağıdaki değişiklikleri uygular [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) :

Derleyici artık olmayan bir dönüş türü içeriyorsa kullanarak ifadeleri yeniden yazar `operator==` **`bool`** . Aşağıdaki kod artık C2088 hatasını `'!=': illegal for struct` veriyor:

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

Derleyici artık birleşim benzeri bir sınıfın üyesiyse, varsayılan olarak bir karşılaştırma işleci tanımlamıyor. Aşağıdaki örnek şu anda C2120 hatasını `'void' illegal with all types` üretir:

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

Sınıf bir başvuru üyesi içeriyorsa, derleyici artık varsayılan olarak bir karşılaştırma işleci tanımlamaz. Aşağıdaki kod artık C2120 hatasını `'void' illegal with all types` veriyor:

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

## <a name="conformance-improvements-in-visual-studio-2019-version-165"></a><a name="improvements_165"></a> Visual Studio 2019 sürüm 16,5 ' de uyumluluk geliştirmeleri

### <a name="explicit-specialization-declaration-without-an-initializer-isnt-a-definition"></a>Başlatıcı olmadan açık özelleştirme bildirimi bir tanım değildir

`/permissive-`MSVC artık, başlatıcı olmayan açık özelleştirme bildirimlerinin tanımsız bir standart kuralı uygular. Daha önce, bildirim varsayılan başlatıcısı olan bir tanım olarak kabul edilir. Bu davranışa bağlı bir programın artık çözümlenmemiş sembolleri olabileceği için bağlantı zamanında bu efekt Observable ' dır. Bu örnek şimdi bir hatayla sonuçlanır:

```cpp
template <typename> struct S {
    static int a;
};

// In permissive-, this declaration isn't a definition, and the program won't link.
template <> int S<char>::a;

int main() {
    return S<char>::a;
}
```

```Output
error LNK2019: unresolved external symbol "public: static int S<char>::a" (?a@?$S@D@@2HA) referenced in function _main
at link time.
```

Sorunu çözmek için bir başlatıcı ekleyin:

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

### <a name="preprocessor-output-preserves-newlines"></a>Önişlemci çıktısı newlines 'ı korur

Deneysel ön işlemci artık veya ile kullanılırken newlines ve Whitespace 'i korur **`/P`** **`/E`** **`/experimental:preprocessor`** .

Bu örnek kaynak verildiğinde,

```cpp
#define m()
line m(
) line
```

Önceki çıkış **`/E`** :

```Output
line line
#line 2
```

Yeni çıktısı **`/E`** artık şu şekilde olur:

```Output
line
 line
```

### <a name="import-and-module-keywords-are-context-dependent"></a>' import ' ve ' Module ' anahtar sözcükleri bağlama bağımlıdır

P1857R1 başına, Import ve Module Önişlemci yönergelerinin sözdizimi hakkında ek kısıtlamalar vardır. Bu örnek artık derlenmezse:

```cpp
import // Invalid
m;
```

Aşağıdaki hata iletisini üretir:

```Output
error C2146: syntax error: missing ';' before identifier 'm'
```

Sorunu çözmek için içeri aktarma işlemi aynı satırda kalsın:

```cpp
import m; // OK
```

### <a name="removal-of-stdweak_equality-and-stdstrong_equality"></a>Std:: weak_equality ve std:: strong_equality kaldırılıyor

P1959R0 birleştirmesi, derleyicisinin ve türlerine yönelik davranışı ve başvuruları kaldırmasını gerektirir `std::weak_equality` `std::strong_equality` .

Bu örnekteki kod artık derlenmezse:

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

Örnek şimdi bu hatalara neden oluyor:

```Output
error C2039: 'strong_equality': is not a member of 'std'
error C2143: syntax error: missing ';' before '<=>'
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C7546: binary operator '<=>': unsupported operand types 'nullptr' and 'nullptr'
error C7546: binary operator '<=>': unsupported operand types 'void (__cdecl *)(void)' and 'void (__cdecl *)(void)'
error C7546: binary operator '<=>': unsupported operand types 'int (__thiscall S::* )(const S &) const' and 'int (__thiscall S::* )(const S &) const'
```

Sorunu çözmek için, yerleşik İlişkisel işleçleri tercih etmek ve kaldırılan türleri değiştirmek üzere güncelleştirin:

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

### <a name="tls-guard-changes"></a>TLS koruyucu değişiklikleri

Daha önce, dll 'Lerdeki iş parçacığı yerel değişkenleri doğru başlatılmamış. DLL 'yi yükleyen iş parçacığında dışında, dll yüklenmeden önce var olan iş parçacıklarında ilk kullanılmadan önce başlatılmazlar. Bu hata düzeltildi. Bu tür bir DLL 'de iş parçacığı yerel değişkenleri, bu iş parçacıkları üzerinde ilk kullanılmadan hemen önce başlatılır.

Bu yeni davranış, iş parçacığı yerel değişkenlerinin kullanımları üzerinde başlatma için test etme davranışını derleyici anahtarı kullanılarak devre dışı bırakılabilir **`/Zc:tlsGuards-`** . Ya da `[[msvc:no_tls_guard]]` özniteliği belirli iş parçacığı yerel değişkenlerine ekleyerek.

### <a name="better-diagnosis-of-call-to-deleted-functions"></a>Silinen işlevlere yapılan çağrının daha iyi tanılaması

Derleyicimiz, daha önce silinen işlevlere yapılan çağrılar hakkında daha fazla izne sahiptir. Örneğin, çağrılar bir şablon gövdesi bağlamında gerçekleştiyse, çağrıyı tanılamadık. Ayrıca, silinen işlevlere birden çok çağrı örneği olsaydı yalnızca bir tanılama oluşturacağız. Artık her biri için bir tanılama veriyoruz.

Yeni davranışın bir sonucu küçük bir değişiklik üretebilir: silinen bir işlevi çağıran kod, kod üretimi için hiçbir daha gerekmiyorsa tanıaramamaktadır. Şimdi tanıdık.

Bu örnek, şimdi bir hata üreten kodu gösterir:

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

Sorunu çözmek için silinen işlevlere yapılan çağrıları kaldırın:

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

## <a name="conformance-improvements-in-visual-studio-2019-version-166"></a><a name="improvements_166"></a> Visual Studio 2019 sürüm 16,6 ' de uyumluluk geliştirmeleri

### <a name="standard-library-streams-reject-insertions-of-mis-encoded-character-types"></a>Standart Kitaplık akışları, yanlış kodlanmış karakter türlerinin eklemeleri reddeder

Geleneksel olarak, bir içine bir veya eklemek ya da **`wchar_t`** `std::ostream` ya da **`char16_t`** **`char32_t`** bir veya içine eklemek `std::ostream` `std::wostream` , tam sayı değerini verir. Bu karakter türlerine işaretçiler eklemek işaretçi değerini verir. Programcılar, büyük/küçük harf kullanımı içermez. Genellikle standart kitaplığın karakter veya null ile sonlandırılmış karakter dizesinin kodunu dönüştürmesini ve sonucun çıktısını almayı bekler.

C++ 20 teklifi [P1423R3](https://wg21.link/p1423r3) , bu akış ve karakter ya da karakter işaretçisi türleri birleşimleri için silinen akış ekleme işleci yüklerini ekler. ' Nin altında, **`/std:c++latest`** aşırı yüklemeler Bu eklemeleri, büyük olasılıkla istenmeyen bir şekilde davranması yerine, bu eklemeleri bir arada yapar. Derleyici, bir C2280 hata oluşturur. `_HAS_STREAM_INSERTION_OPERATORS_DELETED_IN_CXX20` `1` Eski davranışı geri yüklemek için "çıkış taraması" makrosunu tanımlayabilirsiniz. (Teklif, için akış ekleme işleçlerini da siler **`char8_t`** . Standart kitaplığımız destek eklendiğinde benzer aşırı yüklemeler uyguladık **`char8_t`** , bu nedenle "yanlış" davranışı için hiçbir zaman kullanılamaz **`char8_t`** .)

Bu örnek, bu değişikliğe sahip davranışı gösterir:

```cpp
#include <iostream>
int main() {
    const wchar_t cw = L'x', *pw = L"meow";
    const char16_t c16 = u'x', *p16 = u"meow";
    const char32_t c32 = U'x', *p32 = U"meow";
    std::cout << cw << ' ' << pw << '\n';
    std::cout << c16 << ' ' << p16 << '\n';
    std::cout << c32 << ' ' << p32 << '\n';
    std::wcout << c16 << ' ' << p16 << '\n';
    std::wcout << c32 << ' ' << p32 << '\n';
}
```

Kod artık şu tanılama iletilerini üretir:

```Output
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,wchar_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,char16_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,char32_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::<<<std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char16_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::<<<std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char32_t)': attempting to reference a deleted function
```

Karakter türlerini **`unsigned int`** veya işaretçiden karakter türlerini öğesine dönüştürerek, tüm dil modlarında eski davranışın etkisini elde edebilirsiniz `const void*` :

```c++
#include <iostream>
int main() {
    const wchar_t cw = L'x', *pw = L"meow";
    const char16_t c16 = u'x', *p16 = u"meow";
    const char32_t c32 = U'x', *p32 = U"meow";
    std::cout << (unsigned)cw << ' ' << (const void*)pw << '\n'; // Outputs "120 0052B1C0"
    std::cout << (unsigned)c16 << ' ' << (const void*)p16 << '\n'; // Outputs "120 0052B1CC"
    std::cout << (unsigned)c32 << ' ' << (const void*)p32 << '\n'; // Outputs "120 0052B1D8"
    std::wcout << (unsigned)c16 << ' ' << (const void*)p16 << '\n'; // Outputs "120 0052B1CC"
    std::wcout << (unsigned)c32 << ' ' << (const void*)p32 << '\n'; // Outputs "120 0052B1D8"
}
```

### <a name="changed-return-type-of-stdpow-for-stdcomplex"></a>İçin dönüş türü değiştirildi `std::pow()``std::complex`

Daha önce, işlev şablonunun dönüş türü için yükseltme kurallarının MSVC uygulanması `std::pow()` hatalıydı. Örneğin, daha önce `pow(complex<float>, int)` döndürüldü `complex<float>` . Artık doğru şekilde döndürülür `complex<double>` . Bu çözüm, Visual Studio 2019 sürüm 16,6 ' deki tüm standartlar modlarında koşullu olarak uygulandı.

Bu değişiklik derleyici hatalarına neden olabilir. Örneğin, daha önce `pow(complex<float>, int)` bir ile çarpmanız gerekir **`float`** . `complex<T> operator*`Aynı türde bağımsız değişkenleri beklediği için aşağıdaki örnek şimdi derleyici hatası C2676: `binary '*': 'std::complex<double>' does not define this operator or a conversion to a type acceptable to the predefined operator` :

```cpp
// pow_error.cpp
// compile by using: cl /EHsc /nologo /W4 pow_error.cpp
#include <complex>

int main() {
    std::complex<float> cf(2.0f, 0.0f);
    (void) (std::pow(cf, -1) * 3.0f);
}
```

Birçok olası düzeltme vardır:

- **`float`** Çoğulun türünü ve ile değiştirin **`double`** . Bu bağımsız değişken `complex<double>` , tarafından döndürülen türle eşleşecek şekilde doğrudan öğesine dönüştürülebilir `pow` .

- Sonucunu `pow` söyleyerek olarak daraltın `complex<float>` `complex<float>{pow(ARG, ARG)}` . Daha sonra bir değerle çarparak devam edebilirsiniz **`float`** .

- **`float`** Yerine olarak geçirin **`int`** `pow` . Bu işlem daha yavaş olabilir.

- Bazı durumlarda tamamen kaçınabilirsiniz `pow` . Örneğin, `pow(cf, -1)` bölüm ile değiştirilebilir.

### <a name="switch-related-warnings-for-c"></a>C için anahtarla ilgili uyarılar

Visual Studio 2019 sürüm 16,6 ' den başlayarak, derleyici C olarak derlenen kod için önceden varolan C++ uyarılarını uygular. Şu uyarılar artık farklı düzeylerde etkinleştirilmiştir: C4060, C4061, C4062, C4063, C4064, C4065, C4808 ve C4809. Uyarılar C4065 ve C4060, C 'de varsayılan olarak devre dışıdır.

Eksik **`case`** deyimler, tanımsız **`enum`** ve hatalı **`bool`** anahtarlar (yani çok fazla durum içeren) üzerinde uyarılar tetiklenir. Örneğin:

```c
#include <stdbool.h>

int main() {
    bool b = true;
    switch (b) {
        case true: break;
        case false: break;
        default: break; // C4809: switch statement has redundant 'default' label;
                        // all possible 'case' labels are given
    }
}
```

Bu kodu onarmak için gereksiz **`default`** durumu kaldırın:

```c
#include <stdbool.h>

int main() {
    bool b = true;
    switch (b) {
        case true: break;
        case false: break;
    }
}
```

### <a name="unnamed-classes-in-typedef-declarations"></a>Bildirimlerde adlandırılmamış sınıflar `typedef`

Visual Studio 2019 sürüm 16,6 ' den başlayarak, bildirimlerin davranışı **`typedef`** [P1766R1](https://wg21.link/P1766R1)ile uyumlu olacak şekilde kısıtlandı. Bu güncelleştirmeyle, bir bildirimde adlandırılmamış sınıfların dışında **`typedef`** hiçbir üye olamaz:

- statik olmayan veri üyeleri,
- üye sınıfları,
- üye numaralandırmalar,
- ve varsayılan üye başlatıcıları.

Aynı kısıtlamalar, her iç içe yerleştirilmiş sınıfa yinelemeli olarak uygulanır. Kısıtlama, bağlantı amaçlarıyla adlara sahip yapıların basitliğini sağlamak için tasarlanmıştır **`typedef`** . Derleyicinin bağlantı adına girmeden önce hiçbir bağlantı hesaplamalarının gerekli olmadığı kadar basit olmaları gerekir **`typedef`** .

Bu değişiklik derleyicinin tüm standartlar modlarını etkiler. Varsayılan ( **`/std:c++14`** ) ve  **`/std:c++17`** modlarında, derleyici uyumsuz kod Için uyarı C5208 yayar. **`/permissive-`** Belirtilmişse, derleyici uyarı C5208 ' ı bir hata olarak yayar **`/std:c++14`** ve altında hata C7626 yayar **`/std:c++17`** . Derleyici, belirtildiğinde, uyumsuz kod için hata C7626 yayar **`/std:c++latest`** .

Aşağıdaki örnek adlandırılmamış yapılarda artık izin verilmeyen yapıları gösterir. Belirtilen standartlar moduna bağlı olarak, C5208 veya C7626 hataları ya da uyarıları yayınlanır:

```cpp
struct B { };
typedef struct : B { // inheriting from 'B'; ill-formed
    void f(); // ill-formed
    static int i; // ill-formed
    struct U {
        void f(); // nested class has non-data member; ill-formed
    };
    int j = 10; // default member initializer; ill-formed
} S;
```

Yukarıdaki kod adlandırılmamış sınıfa bir ad vererek düzeltilebilir:

```cpp
struct B { };
typedef struct S_ : B {
    void f();
    static int i;
    struct U {
        void f();
    };
    int j = 10;
} S;
```

### <a name="default-argument-import-in-ccli"></a>C++/CLı ' da varsayılan bağımsız değişken içeri aktarma

Daha fazla sayıda API 'nin .NET Core 'da varsayılan bağımsız değişkenleri vardır. Bu nedenle artık C++/CLIENDE varsayılan bağımsız değişkeni içeri aktarmayı destekliyoruz. Bu değişiklik, bu örnekte olduğu gibi birden fazla aşırı yüklemenin bildirildiği mevcut kodu bozabilir:

```cpp
public class R {
    public void Func(string s) {}   // overload 1
    public void Func(string s, string s2 = "") {} // overload 2;
}
```

Bu sınıf C++/CLı ' ya aktarıldığında, aşırı yüklerden birine yapılan bir çağrı bir hataya neden olur:

```cpp
    (gcnew R)->Func("abc"); // error C2668: 'R::Func' ambiguous call to overloaded function
```

Her iki aşırı yükleme de bu bağımsız değişken listesiyle eşleştiğinden, derleyici hata C2668 yayar. İkinci aşırı yüklemede ikinci bağımsız değişken varsayılan bağımsız değişken tarafından doldurulur. Bu sorunu geçici olarak çözmek için gereksiz aşırı yüklemeyi (1) silebilirsiniz. Ya da tam bağımsız değişken listesini kullanın ve açıkça varsayılan bağımsız değişkenleri sağlayın.

## <a name="conformance-improvements-in-visual-studio-2019-version-167"></a><a name="improvements_167"></a> Visual Studio 2019 sürüm 16,7 ' de uyumluluk geliştirmeleri

### <a name="definition-of-is-trivially-copyable"></a>Tanımı *, üç kopyalanabilir*

C++ 20 ' nin tanımı, *üç aylık kopyalanabilir olarak*değiştirildi. Bir sınıfta tam tür olan statik olmayan bir veri üyesi olduğunda **`volatile`** , bu, derleyicinin ürettiği kopyalama veya taşıma oluşturucusunun ya da kopyalama ya da taşıma işlecinin önemsiz olmayan bir kopyasına sahip olduğu anlamına gelir. C++ standart Komitesi bu değişikliği bir hata raporu olarak daha etkin bir şekilde uyguladı. MSVC ' de, derleyici davranışı veya gibi farklı dil modlarında değişmez **`/std:c++14`** **`/std:c++latest`** .

Yeni davranışa bir örnek aşağıda verilmiştir:

```cpp
#include <type_traits>

struct S
{
    volatile int m;
};

static_assert(std::is_trivially_copyable_v<S>, "Meow!");
```

Bu kod, Visual Studio 2019 sürüm 16,7 ' den önce MSVC sürümlerinde derlenmez. Bu değişikliği algılamak için kullanabileceğiniz, varsayılan olarak bir derleyici uyarısı vardır. Kullanarak yukarıdaki kodu derlerseniz **`cl /W4 /w45220`** , aşağıdaki uyarıyı görürsünüz:

Uyarı C5220: `'S::m': a non-static data member with a volatile qualified type no longer implies that compiler generated copy/move constructors and copy/move assignment operators are non trivial`

### <a name="pointer-to-member-and-string-literal-conversions-to-bool-are-narrowing"></a>İşaretçiden üyeye ve dize değişmez değer dönüştürmeleri `bool` daraltımı

C++ standart Komitesi, son zamanlarda [P1957R2](https://wg21.link/p1957r2) `T*`  ->  **`bool`** bir daraltma dönüştürmesi olarak niteyen hata raporu P1957R2. MSVC, daha önce daraltma olarak tanılayan, `T*`  ->  **`bool`** ancak bir dize değişmez değeri veya üye işaretçisi dönüştürmesinin tanılamamasına neden olan uygulamada bir hatayı düzeltti **`bool`** **`bool`** .

Aşağıdaki program, Visual Studio 2019 sürüm 16,7 ' de hatalı biçimlendirilmiş:

```cpp
struct X { bool b; };
void f(X);

int main() {
    f(X { "whoops?" }); // error: conversion from 'const char [8]' to 'bool' requires a narrowing conversion

    int (X::* p) = nullptr;
    f(X { p }); // error: conversion from 'int X::*' to 'bool' requires a narrowing conversion
}
```

Bu kodu düzeltmek için, ' a açık karşılaştırmalar ekleyin **`nullptr`** veya daraltma dönüştürmelerinden kaçının hatalı biçimlendirilmiş bağlamlardan kaçının:

```cpp
struct X { bool b; };
void f(X);

int main() {
    f(X { "whoops?" != nullptr }); // Absurd, but OK

    int (X::* p) = nullptr;
    f(X { p != nullptr }); // OK
}
```

### <a name="nullptr_t-is-only-convertible-to-bool-as-a-direct-initialization"></a>`nullptr_t` yalnızca `bool` doğrudan başlatma olarak dönüştürülebilir

C++ 11 ' de, **`nullptr`** yalnızca **`bool`** *doğrudan dönüştürme*olarak dönüştürülebilir; Örneğin, bir **`bool`** örgü Başlatıcı listesi kullanarak bir başlattığınızda. Bu kısıtlama hiçbir şekilde MSVC tarafından zorlanmaz. MSVC artık kuralı uygular [`/permissive-`](../build/reference/permissive-standards-conformance.md) . Örtük dönüştürmeler artık hatalı biçimlendirilmiş olarak tanılanıyor. Öğesine bağlama dönüştürmeye **`bool`** hala izin verilir, çünkü doğrudan başlatma `bool b(nullptr)` geçerli olur.

Çoğu durumda, **`nullptr`** **`false`** Bu örnekte gösterildiği gibi, hatası ile değiştirilerek düzeltilebilir:

```cpp
struct S { bool b; };
void g(bool);
bool h() { return nullptr; } // error, should be 'return false;'

int main() {
    bool b1 = nullptr; // error: cannot convert from 'nullptr' to 'bool'
    S s { nullptr }; // error: cannot convert from 'nullptr' to 'bool'
    g(nullptr); // error: cannot convert argument 1 from 'nullptr' to 'bool'

    bool b2 { nullptr }; // OK: Direct-initialization
    if (!nullptr) {} // OK: Contextual conversion to bool
}
```

### <a name="conforming-initialization-behavior-for-array-initializations-with-missing-initializers"></a>Eksik başlatıcılarla dizi başlatmaları için uyumlu başlatma davranışı

Daha önce MSVC, eksik başlatıcılara sahip dizi başlatmaları için uyumlu olmayan bir davranış yaşadı. MSVC her zaman, başlatıcısı olmayan her bir dizi öğesi için varsayılan oluşturucu olarak adlandırılır. Standart davranış, her bir öğeyi boş bir örgü-Başlatıcı-List () ile başlatmalıdır **`{}`** . Boş bir örgü Başlatıcı listesi için başlatma bağlamı, açık oluşturucuların çağrılarına izin verilmeyen kopya başlatma ' dır. `{}`Başlatmak için kullanılması, varsayılan Oluşturucu yerine bir Oluşturucu çağırmak için, çalışma zamanı farklılıkları da olabilir `std::initializer_list` . Uyumlu davranış altında etkindir [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

Değiştirilen davranışa bir örnek aşağıda verilmiştir:

```cpp
struct B {
    explicit B() {}
};

void f() {
    B b1[1]{}; // Error in /permissive-, because aggregate init calls explicit ctor
    B b2[1]; // OK: calls default ctor for each array element
}
```

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019"></a><a name="update_160"></a> Visual Studio 2019 'de hata düzeltmeleri ve davranış değişiklikleri

### <a name="reinterpret_cast-in-a-constexpr-function"></a>`reinterpret_cast` bir `constexpr` işlevde

Bir **`reinterpret_cast`** **`constexpr`** işlevde geçersizdir. Microsoft C++ derleyicisi, daha önce **`reinterpret_cast`** yalnızca bir bağlamda kullanıldıysa reddedebilirler **`constexpr`** . Visual Studio 2019 ' de, tüm dil standartları modlarında, derleyici bir işlevin tanımında bir öğesini doğru bir şekilde tanılar **`reinterpret_cast`** **`constexpr`** . Aşağıdaki kod artık C3615 üretir: `constexpr function 'f' cannot result in a constant expression` .

```cpp
long long i = 0;
constexpr void f() {
    int* a = reinterpret_cast<int*>(i);
}
```

Hatayı önlemek için, **`constexpr`** işlev bildiriminden değiştiricisini kaldırın.

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>Basic_string Range Oluşturucusu için tanılama doğru

Visual Studio 2019 ' de `basic_string` Aralık Oluşturucusu artık ile derleyici tanılamayı göstermez **`static_cast`** . Aşağıdaki kod, Visual Studio 2017 ' de uyarılar olmadan derlenir ve bu, başlatma sırasında veri kaybına neden olabilir **`wchar_t`** **`char`** `out` :

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 doğru uyarı C4244: `'argument': conversion from 'wchar_t' to 'const _Elem', possible loss of data` . Uyarıyı önlemek için std:: String öğesini şu örnekte gösterildiği gibi başlatabilirsiniz:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>`+=`Veya altına yanlış çağrılar `-=` ve `/clr` `/ZW` artık doğru şekilde algılandı

Visual Studio 2017 ' de, derleyicinin hataları sessizce yoksaymasına ve veya altında geçersiz çağrılar için kod üretmesinin nedeni olan bir hata sunulmuştur **`+=`** **`-=`** **`/clr`** **`/ZW`** . Aşağıdaki kod Visual Studio 2017 ' de hatasız derlenir ancak Visual Studio 2019, C2845 hatasını doğru şekilde oluşturuyor: `'System::String ^': pointer arithmetic not allowed on this type` :

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Bu örnekteki hatayı önlemek için, **`+=`** işleci yöntemi ile kullanın `ToString()` : `s += E::e.ToString();` .

### <a name="initializers-for-inline-static-data-members"></a>Satır içi statik veri üyeleri için başlatıcılar

Ve başlatıcıların içindeki geçersiz üye erişimleri **`inline`** **`static constexpr`** artık doğru şekilde algılandı. Aşağıdaki örnek Visual Studio 2017 ' de hatasız derlenir, ancak Visual Studio 2019 ' de **`/std:c++17`** modda hata C2248: `cannot access private member declared in class 'X'` .

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

MSVC, öğesine örtük dönüştürme hakkında bir performans uyarısı C4800 sağlamak için kullanılır **`bool`** . Bu çok gürültülü ve gizlenemedi, bu da Visual Studio 2017 ' de kaldırılması için önde gelir. Bununla birlikte, Visual Studio 2017 yaşam döngüsünün üzerinde çöztiğimiz yararlı durumlar hakkında çok fazla geri bildirim sunuyoruz. Açıklayıcı C4165 ile birlikte Visual Studio 2019 ' ye dikkatlice uyarlanmış bir C4800 geri getiriyoruz. Bu uyarıların her ikisi de kolayca bastırılır: açık bir tür kullanılarak veya uygun türden 0 ' a kıyasla. C4800, varsayılan olarak 4. düzey bir uyarıdır ve C4165, varsayılan olarak 1. düzey 3 uyarıdır. Her ikisi de **`/Wall`** derleyici seçeneği kullanılarak bulunabilir.

Aşağıdaki örnek, altında C4800 ve C4165 ' i yükseltir **`/Wall`** :

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

Visual Studio 2017 ' de uyarı C4822: `Local class member function doesn't have a body` yalnızca derleyici seçeneği **`/w14822`** açıkça ayarlandığında tetiklenir. İle gösterilmez **`/Wall`** . Visual Studio 2019 ' de C4822, bu, açık bir uyarıdır. Bu, **`/Wall`** açıkça ayarlanması gerekmeden altında bulunabilir hale gelir **`/w14822`** .

```cpp
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-if-constexpr-statements"></a>Deyim içeren işlev şablonu gövdeleri `if constexpr`

Deyimleri içeren şablon işlevi **`if constexpr`** gövdelerinin [`/permissive-`](../build/reference/permissive-standards-conformance.md) ayrıştırılmasındaki bazı denetimler var. Örneğin, Visual Studio 2017 ' de aşağıdaki kod C7510 oluşturur: `'Type': use of dependent type name must be prefixed with 'typename'` yalnızca **`/permissive-`** seçenek ayarlanmamışsa. Visual Studio 2019 ' de, seçenek ayarlandığında de aynı kod hata oluşturuyor **`/permissive-`** :

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

Hatayı önlemek için, ' **`typename`** ın bildirimine anahtar sözcüğünü ekleyin `a` `typename T::Type a;` .

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Bir lambda ifadesinde satır içi derleme kodu desteklenmez

Microsoft C++ ekibi yakın zamanda bir lambda içinde satır içi assembler kullanmanın, `ebp` çalışma zamanında (dönüş Adres kaydı) bozulmasıyla sonuçlanmasına neden olabilecek bir güvenlik sorununu bilmiştir. Kötü amaçlı bir saldırgan bu senaryodan faydalanabilir. Satır içi assembler yalnızca x86 üzerinde desteklenir ve satır içi assembler ve derleyicinin geri kalanı arasındaki etkileşim kötü olur. Bu olgular ve sorunun doğası göz önünde bulundurulduğunda, bu sorunun en güvenli çözümü, bir lambda ifadesinde satır içi derleyiciye izin vermesidir.

"Joker karakter" bulduğumuz bir lambda ifadesi içinde satır içi assembler 'nun tek kullanımı dönüş adresini yakalamıştı. Bu senaryoda, yalnızca bir derleyici iç öğesini kullanarak dönüş adresini tüm platformlarda yakalayabilirsiniz `_ReturnAddress()` .

Aşağıdaki kod C7552 oluşturur: `inline assembler is not supported in a lambda` hem Visual studio 2017 15,9 hem de Visual studio 2019:

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

Yineleyici hata ayıklama özelliği, düzgün bir şekilde sarmalanmadan daha uygun hale getiriliyor `std::move_iterator` . Örneğin, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` artık `memcpy` hızlı yolu kullanabilir.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>\<xkeycheck.h>Anahtar sözcük zorlaması için düzeltmeler

\<xkeycheck.h>Anahtar sözcüğü değiştiren makrolar için standart kitaplığın zorlaması düzeltildi. Kitaplık artık genel bir ileti yerine algılanan gerçek sorunlu anahtar sözcüğü yayar. Ayrıca C++ 20 anahtar sözcüklerini destekler ve IntelliSense 'in rastgele anahtar sözcüklerin makroları olduğunu söylenmesini önler.

### <a name="allocator-types-no-longer-deprecated"></a>Ayırıcı türleri artık kullanım dışı

`std::allocator<void>`, `std::allocator::size_type` ve `std::allocator::difference_type` artık kullanım dışıdır.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Daraltma dizesi dönüştürmeleri için doğru uyarı

**`static_cast`** `std::string` Standart tarafından çağrılmadığı ve yanlışlıkla C4244 daraltma uyarılarını gizlenen bir şekilde kaldırıldı. `std::string::string(const wchar_t*, const wchar_t*)`Artık C4244 yayma denemeleri `narrowing a wchar_t into a char` .

### <a name="various-fixes-for-filesystem-correctness"></a>Doğruluk açısından çeşitli düzeltmeler \<filesystem>

- `std::filesystem::last_write_time`Dizinin son yazma zamanı değiştirilmeye çalışılırken hata düzeltildi.
- `std::filesystem::directory_entry`Oluşturucu artık varolmayan bir hedef yolu sağlandığı zaman bir özel durum oluşturmak yerine başarısız bir sonucu depolar.
- `std::filesystem::create_directory`2 parametreli sürüm, 1 parametreli sürümü çağırmak üzere değiştirilmiştir ve temel alınan `CreateDirectoryExW` işlev `copy_symlink` `existing_p` bir symlink olduğunda kullanılır.
- `std::filesystem::directory_iterator` bozuk bir oluşturmaksızın bulunduğunda artık başarısız olmaz.
- `std::filesystem::space` Artık göreli yolları kabul eder.
- `std::filesystem::path::lexically_relative` , [LWG 3096](https://cplusplus.github.io/LWG/issue3096)olarak bildirilen eğik çizgiler tarafından artık karıştırılmamalıdır.
- İçindeki eğik `CreateSymbolicLinkW` çizgi ile yolları reddetme `std::filesystem::create_symlink`
- `delete`Windows 10 LTSB 1609 ' de var olan, ancak gerçekten dosyaları silmeyen POSIX silme modu işlevine geçici olarak çalıştık.
- `std::boyer_moore_searcher` ve `std::boyer_moore_horspool_searcher` kopya oluşturucuları ve kopya atama işleçleri artık aslında öğeleri kopyalayamıyorum.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 ve sonraki sürümlerde paralel algoritmalar

Paralel algoritmalar kitaplığı artık `WaitOnAddress` Windows 7 ve önceki sahte sürümlerini kullanmak yerine gerçek aileyi Windows 8 ve üzeri sürümlerde kullanır.

### <a name="stdsystem_categorymessage-whitespace"></a>`std::system_category::message()` boşlu

`std::system_category::message()` Şimdi döndürülen iletiden sondaki boşluğu kırpar.

### <a name="stdlinear_congruential_engine-divide-by-zero"></a>`std::linear_congruential_engine` sıfıra Böl

`std::linear_congruential_engine`Tetikleyici 0 olarak bölünmeye neden olabilecek bazı koşullar düzeltildi.

### <a name="fixes-for-iterator-unwrapping"></a>Yineleyici geri sarma düzeltmeleri

Bazı yineleyici-sarmalama makineleri, Visual Studio 2017 15,8 ' de programlayıcı Kullanıcı tümleştirmesi için ilk kez kullanıma sunuldu. C++ ekip blogu makalesi [STL özellikleri ve VS 2017 15,8 ' deki düzeltmeler](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/)bölümünde açıklanmıştı. Bu makine artık standart kitaplık yineleyiciler tarafından türetilen yineleyicilerin sarmalarını geri sarmayacak. Örneğin, öğesinden türetilen `std::vector<int>::iterator` ve özelleştirmeyi denemeyen bir Kullanıcı artık işaretçi davranışı yerine standart kitaplık algoritmalarını çağırırken özelleştirilmiş davranışlarını alıyor.

Sıralanmamış kapsayıcı `reserve` işlevi artık, [lwg 2156](https://cplusplus.github.io/LWG/issue2156)' de açıklandığı gibi N öğeleri için ayrılmış durumda.

### <a name="time-handling"></a>Zaman işleme

- Daha önce, eşzamanlılık kitaplığına geçirilen bazı zaman değerleri, örneğin, `condition_variable::wait_for(seconds::max())` . Şimdi düzeltildi, rastgele 29 günlük bir döngüde (temel alınan Win32 API 'Leri tarafından kabul edilen uint32_t milisaniyelik) değiştirilen taşma

- \<ctime>Üst bilgi artık ad alanını doğru şekilde bildirir ve bu adı `timespec` `timespec_get` `std` genel ad alanında bildirir.

### <a name="various-fixes-for-containers"></a>Kapsayıcılar için çeşitli düzeltmeler

- Birçok standart kitaplık iç kapsayıcı işlevleri, geliştirilmiş bir IntelliSense deneyimi için özel yapılmıştır. MSVC 'in sonraki sürümlerinde üyeleri özel olarak işaretlemek için ek düzeltmeler beklenmektedir.

- , Ve gibi düğüm tabanlı kapsayıcılardaki `list` `map` bozuk hale gelebileceği özel durum güvenliği doğruluk sorunları `unordered_map` düzeltildi. `propagate_on_container_copy_assignment`Veya `propagate_on_container_move_assignment` yeniden atama işlemi sırasında, kapsayıcının Sentinel düğümünü eski ayırıcıyla boşalttık, eski ayırıcı üzerinde POCCA/POCMA atamasını yapar ve ardından yeni ayırıcıdan Sentinel düğümünü edinmeye çalışırsınız. Bu ayırma başarısız olduysa, kapsayıcı bozulmuştur. Bir Sentinel düğümü sabit bir veri yapısı sabiti olduğu için bile yok edilmez. Bu kod, mevcut Sentinel düğümünü yok etmeden önce kaynak kapsayıcısının ayırıcıyı kullanarak yeni Sentinel düğümünü oluşturmak için düzeltildi.

- Kapsayıcılar, `propagate_on_container_copy_assignment` `propagate_on_container_move_assignment` `propagate_on_container_swap` belirtilen ayrıcılar için bile, ve ' a göre ayırıcıları her zaman kopyalamak/taşımak/değiştirmek için düzeltildi `is_always_equal` .

- Kapsayıcı birleştirme için aşırı yüklemeler eklendi ve rvalue kapsayıcılarını kabul eden üye işlevleri ayıklayın. Daha fazla bilgi için bkz. [P0083 "splicing Maps and Sets"](https://wg21.link/p0083r3)

### <a name="stdbasic_istreamread-processing-of-rn-n"></a>`std::basic_istream::read``\r\n`` =>`\n ' işleniyor

`std::basic_istream::read`, işlemin bir parçası olarak sağlanan arabelleğin bölümlerine geçici olarak yazılmadığından düzeltildi `\r\n`  =>  `\n` . Bu değişiklik, Visual Studio 2017 15,8 ' de en fazla 4K boyutunda daha büyük okumalar için kazanılan performans avantajlarından bazılarını sağlar. Bununla birlikte, karakter başına üç sanal çağrının önünden kaçınmanın verimlilik geliştirmeleri hala mevcuttur.

### <a name="stdbitset-constructor"></a>`std::bitset` constructor

`std::bitset`Oluşturucu artık büyük bit kümelerine ait olanları ve sıfırları ters sırayla okumamaktadır.

### <a name="stdpairoperator-regression"></a>`std::pair::operator=` regresyon

Bir gerileme, `std::pair` [lwg 2729 "eksık SFINAE: std::p AIR:: operator =";](https://cplusplus.github.io/LWG/issue2729) Artık, ' a dönüştürülebilir türleri doğru şekilde kabul eder `std::pair` .

### <a name="non-deduced-contexts-for-add_const_t"></a>İçin çıkarılamayan bağlamlar `add_const_t`

Küçük tür nitelikleri hatası düzeltildi, burada `add_const_t` ve ilgili işlevlerin çıkarılamayan bir bağlam olması gerekir. Diğer bir deyişle, `add_const_t` için bir diğer ad olmalıdır `typename add_const<T>::type` `const T` .

## <a name="bug-fixes-and-behavior-changes-in-162"></a><a name="update_162"></a> 16,2 sürümündeki hata düzeltmeleri ve davranış değişiklikleri

### <a name="const-comparators-for-associative-containers"></a>İlişkilendirilebilir kapsayıcılar için const Karşılaştırıcılar

[Küme](../standard-library/set-class.md), [eşleme](../standard-library/map-class.md), [Çoklu küme](../standard-library/multiset-class.md)ve [multimap](../standard-library/multimap-class.md) 'teki arama ve ekleme için kod, daha az kod boyutu için birleştirildi. Ekleme işlemleri artık **`const`** , arama işlemlerinin daha önce yapıldığı şekilde, bir karşılaştırma funından daha az karşılaştırmayı çağırır. Aşağıdaki kod, Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' C3848 yükseltir:

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

Hatayı önlemek için karşılaştırma işlecini yapın **`const`** :

```cpp
struct Comparer  {
   bool operator() (K a, K b) const {
      return a.a < b.a;
   }
};

```

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-version-167"></a><a name="updates_167"></a> Visual Studio 2019 sürüm 16,7 ' de hata düzeltmeleri ve davranış değişiklikleri

### <a name="initialization-of-class-members-with-overloaded-names-is-correctly-sequenced"></a>Aşırı yüklenmiş adlara sahip sınıf üyelerinin başlatılması doğru sıralı

Bir tür adı aynı zamanda veri üyesinin adı olarak aşırı yüklendiğinde, sınıf veri üyelerinde iç gösterimde bir hata belirledik. Bu hata, toplu başlatma ve üye başlatma sırasında tutarsızlıklara neden oldu. Oluşturulan başlatma kodu artık doğrudur. Bununla birlikte, bu değişiklik, bu örnekte olduğu gibi, yanlışlıkla sıralanmış üyelere dayalı olarak, kaynaktaki hatalara veya uyarılara neden olabilir:

```cpp
// Compiling with /w15038 now gives:
// warning C5038: data member 'Outer::Inner' will be initialized after data member 'Outer::v'
struct Outer {
    Outer(int i, int j) : Inner{ i }, v{ j } {}

    struct Inner { int x; };
    int v;
    Inner Inner; // 'Inner' is both a type name and data member name in the same scope
};
```

Önceki sürümlerde, Oluşturucu veri üyesini yanlış bir şekilde veri üyesi olarak başlatır `Inner` `v` . (C++ standardı, üyelerin bildirim sırasıyla aynı olan bir başlatma sırası gerektirir). Oluşturulan kod standart bir şekilde izlediğinden, üye-init-listesi sıra dışında olur. Derleyici bu örnek için bir uyarı oluşturur. Bunu onarmak için, üye başlatıcısı listesini bildirim sırasını yansıtacak şekilde yeniden sıralayın.

### <a name="overload-resolution-involving-integral-overloads-and-long-arguments"></a>İntegral aşırı yüklemeleri ve bağımsız değişkenleri içeren aşırı yükleme çözümlemesi `long`

C++ standardı, bir **`long`** **`int`** Standart dönüştürme olarak bir dönüştürme için sıralama gerektirir. Önceki MSVC derleyicileri, aşırı yükleme çözümlemesi için daha yüksek olan bir integral yükseltme olarak doğru şekilde derecelendirir. Bu sıralama, aşırı yük çözümlemenin belirsiz kabul edilmesi durumunda başarıyla çözümlenmesine neden olabilir.

Derleyici artık sırasıyla modu doğru şekilde değerlendirir [`/permissive-`](../build/reference/permissive-standards-conformance.md) . Şu örnekte olduğu gibi geçersiz kod doğru tanılandı:

```cpp
void f(long long);
void f(int);

int main() {
    long x {};
    f(x); // error: 'f': ambiguous call to overloaded function
    f(static_cast<int>(x)); // OK
}
```

Bu sorunu çeşitli yollarla çözebilirsiniz:

- Çağıran sitede, geçirilen bağımsız değişkenin türünü olarak değiştirin **`int`** . Değişken türünü değiştirebilir ya da çevirebilirsiniz.

- Birçok çağrı sitesi varsa, bağımsız değişken alan başka bir aşırı yükleme ekleyebilirsiniz **`long`** . Bu işlevde, bağımsız değişkenini dönüştürün ve aşırı yüklemeye iletin **`int`** .

### <a name="use-of-undefined-variable-with-internal-linkage"></a>İç bağlantı ile tanımsız değişken kullanımı

Visual Studio 2019 sürüm 16,7 ' den önceki MSVC sürümleri, **`extern`** iç bağlantısı olan ve tanımlanmamış bir değişkenin kabul edilmiş kullanımı. Bu tür değişkenler başka bir çeviri biriminde tanımlanamaz ve geçerli bir program oluşturmamalıdır. Derleyici artık derleme zamanında bu durumu tanılar. Hata, tanımsız statik işlevler için hataya benzer.

```cpp
namespace {
    extern int x; // Not a definition, but has internal linkage because of the anonymous namespace
}

int main()
{
    return x; // Use of 'x' that no other translation unit can possibly define.
}
```

Bu program daha önce yanlış derlenmiş ve bağlanmış, ancak şimdi şunu yayacaktır:

hata C7631: `'anonymous-namespace'::x': variable with internal linkage declared but not defined`

Bu tür değişkenler, içinde kullanıldıkları aynı çeviri biriminde tanımlanmalıdır. Örneğin, açık bir başlatıcı veya ayrı bir tanım sağlayabilirsiniz.

### <a name="type-completeness-and-derived-to-base-pointer-conversions"></a>Tür bütünlüğü ve türetilen taban işaretçisi dönüşümleri

C++ 20 ' den önceki C++ standartları ' nda, türetilmiş bir sınıftan taban sınıfa dönüştürme, türetilmiş sınıfın bir bütün sınıf türü olmasını gerektirmez. C++ standart Komitesi, C++ dilinin tüm sürümleri için geçerli olan geriye dönük etkin bir hata raporu değişikliğini onayladı. Bu değişiklik, `std::is_base_of` türetilmiş sınıfın bir bütün sınıf türü olmasını gerektiren gibi tür nitelikleri ile dönüştürme işlemini hizalar.

Aşağıda bir örnek verilmiştir:

```cpp
template<typename A, typename B>
struct check_derived_from
{
    static A a;
    static constexpr B* p = &a;
};

struct W { };
struct X { };
struct Y { };

// With this change this code will fail as Z1 is not a complete class type
struct Z1 : X, check_derived_from<Z1, X>
{
};

// This code failed before and it will still fail after this change
struct Z2 : check_derived_from<Z2, Y>, Y
{
};

// With this change this code will fail as Z3 is not a complete class type
struct Z3 : W
{
    check_derived_from<Z3, W> cdf;
};
```

Bu davranış değişikliği, yalnızca MSVC 'in tüm C++ dil modları için geçerlidir **`/std:c++latest`** .

### <a name="narrowing-conversions-are-more-consistently-diagnosed"></a>Daraltma dönüştürmeleri daha tutarlı bir şekilde tanılandı

MSVC, yerleşik bir liste başlatıcısındaki dönüştürmeleri daraltmak için bir uyarı yayar. Daha önce, derleyici daha büyük temel alınan türlerden daraltma dönüştürmelerini daha **`enum`** dar integral türlere tanılayamaz. (Derleyici bir dönüştürme yerine bir integral promosyonu yanlış olarak kabul edilir). Daraltma dönüştürmesi bilerek yapılıyorsa, başlatıcı bağımsız değişkeninde bir kullanarak uyarı kullanmaktan kaçınabilirsiniz **`static_cast`** . Ya da daha büyük bir hedef integral türü seçin.

Bu uyarıyı çözmek için açık bir örnek kullanmanın bir örneği aşağıda verilmiştir **`static_cast`** :

```cpp
enum E : long long { e1 };
struct S { int i; };

void f(E e) {
    S s = { e }; // warning: conversion from 'E' to 'int' requires a narrowing conversion
    S s1 = { static_cast<int>(e) }; // Suppress warning with explicit conversion
}
```

::: moniker-end

::: moniker range="vs-2017"

## <a name="conformance-improvements-in-visual-studio-2017-rtw-version-150"></a><a name="improvements_150"></a> Visual Studio 2017 RTW (sürüm 15,0) ile uyumluluk geliştirmeleri

**`constexpr`** Toplamalarda Genelleştirilmiş ve statik olmayan veri üyesi başlatma (NSDMı) desteğiyle, Visual Studio 2017 ' de Microsoft c++ derleyicisi artık C++ 14 standardına eklenen özellikler için tamamlanmıştır. Ancak, derleyicinin yine de C++ 11 ve C++ 98 standartlarından birkaç özelliği yoktur. Derleyicinin geçerli durumunu gösteren bir tablo için bkz. [Microsoft C++ dil uygunluğu tablosu](./visual-cpp-language-conformance.md) .

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++ 11: daha fazla kitaplıklarda Ifade SFıNAE desteği

Derleyici, SFıNAE ifadesi için desteğini iyileştirmeye devam eder. Şablon bağımsız değişken kesintisi ve değiştirme için **`decltype`** ve **`constexpr`** ifadelerin şablon parametreleri olarak görünebileceği bir değer gereklidir. Daha fazla bilgi için bkz. [Visual Studio 2017 RC 'de Expression SFINAE geliştirmeleri](https://devblogs.microsoft.com/cppblog/expression-sfinae-improvements-in-vs-2015-update-3/).

### <a name="c14-nsdmi-for-aggregates"></a>C++ 14: toplamalar için NSDMı

Toplama, bir dizi veya bir sınıftır: Kullanıcı tarafından sağlanmayan Oluşturucu yoktur, özel veya korumalı olmayan statik olmayan veri üyeleri yoktur, temel sınıf yoktur ve hiçbir sanal işlev yoktur. C++ 14 ' ten başlayarak, toplamalar üye başlatıcıları içerebilir. Daha fazla bilgi için bkz. [üye başlatıcıları ve toplamaları](https://wg21.link/n3605).

### <a name="c14-extended-constexpr"></a>C++ 14: genişletilmiş `constexpr`

Olarak belirtilen ifadeler **`constexpr`** , bazı bildirim türlerini, if ve Switch deyimlerini, Loop deyimlerini ve yaşam süresi ifade değerlendirmesi içinde başlayan nesnelerin zaman larını içermesine izin verilir **`constexpr`** . Artık **`constexpr`** statik olmayan bir üye işlevin örtük olarak olması gerekmez **`const`** . Daha fazla bilgi için bkz. [ `constexpr` Işlevlerde kısıtlamaları Gevşlama](https://wg21.link/n3652).

### <a name="c17-terse-static_assert"></a>C++ 17: terse `static_assert`

için ileti parametresi **`static_assert`** isteğe bağlıdır. Daha fazla bilgi için bkz. [genişletme static_assert, v2](https://wg21.link/n3928).

### <a name="c17-fallthrough-attribute"></a>C++ 17: `[[fallthrough]]` özniteliği

**`/std:c++17`** Modunda, öznitelik, `[[fallthrough]]` anahtar deyimlerinin bağlamında, bir derleyicinin bir ipucu olarak, dönüş davranışının istendiği bir ipucu olarak kullanılabilir. Bu öznitelik, derleyicinin bu gibi durumlarda uyarı vermesini engeller. Daha fazla bilgi için bkz. [ `[[fallthrough]]` özniteliğe yönelik ifade](https://wg21.link/p0188r0).

### <a name="generalized-range-based-for-loops"></a>For döngüleri için genelleştirilmiş Aralık tabanlı

Aralık tabanlı for döngüleri artık bunu gerektirmez `begin()` ve `end()` aynı türdeki nesneleri döndürmelidir. Bu değişiklik `end()` , [Range-v3](https://github.com/ericniebler/range-v3) içindeki aralıklar tarafından kullanılan bir Sentinel, ancak tam olarak yayımlanmış olmayan aralıklar teknik belirtiminde dönmesini sağlar. Daha fazla bilgi için bkz. [Aralık tabanlı `for` döngüyü Genelleştirme](https://wg21.link/p0184r0).

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

Tek bir bildirimde, bir değeri bir dizi, ya da veya `std::tuple` `std::pair` tüm ortak statik olmayan veri üyelerine sahip olduğu durumlarda, bileşenleri için bağımsız adlarla bir değer depolamak için de mümkündür. Daha fazla bilgi için, bkz. [yapılandırılmış bağlamalar](https://wg21.link/p0144r0) ve [bir işlevden birden çok değer döndürme](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Değerler için yapım kuralları `enum class`

Artık daraltma olmayan kapsamlı Numaralandırmalar için örtük bir dönüştürme vardır. Kapsamlı bir numaralandırmanın temel alınan türünden numaralandırmanın kendisine dönüştürür. Dönüştürme, tanımı bir Numaralandırıcı oluşturmazsa ve kaynak bir liste başlatma söz dizimi kullandığında kullanılabilir. Daha fazla bilgi için bkz. [sabit listesi sınıfı değerleri](https://wg21.link/p0138r2) ve [numaralandırmalar](../cpp/enumerations-cpp.md#no_enumerators)için oluşturma kuralları.

### <a name="capturing-this-by-value"></a>`*this`Değere göre yakalama

**`*this`** Lambda ifadesindeki nesne artık değere göre yakalanamaz. Bu değişiklik, özellikle daha yeni makine mimarilerinde, lambda 'nin paralel ve zaman uyumsuz işlemlerde çağrıldığı senaryolara izin vermez. Daha fazla bilgi için bkz. [ \* bu değere göre Lambda yakalama değeri \[ =, \* Bu \] ](https://wg21.link/p0018r3).

### <a name="removing-operator-for-bool"></a>`operator++`İçin kaldırılıyor`bool`

`operator++` türler üzerinde artık desteklenmez **`bool`** . Daha fazla bilgi için bkz. [kullanım dışı Işleci Kaldır + + (bool)](https://wg21.link/p0002r1).

### <a name="removing-deprecated-register-keyword"></a>Kullanım dışı bırakılan `register` anahtar sözcüğü kaldırılıyor

**`register`** Daha önce kullanım dışı olan (ve derleyici tarafından yoksayılan) anahtar sözcüğü artık dilden kaldırılmıştır. Daha fazla bilgi için bkz. [ `register` anahtar sözcüğünün kullanım dışı kullanımını kaldırma](https://wg21.link/p0001r1).

## <a name="conformance-improvements-in-155"></a><a name="improvements_155"></a> 15,5 sürümündeki uyumluluk geliştirmeleri

14 ile işaretlenen Özellikler \[ , modunda bile koşullu olarak kullanılabilir **`/std:c++14`** .

### <a name="new-compiler-switch-for-extern-constexpr"></a>İçin yeni derleyici anahtarı `extern constexpr`

Visual Studio 'nun önceki sürümlerinde derleyici, **`constexpr`** değişken işaretlenmiş olsa bile her zaman iç bağlantı verdi **`extern`** . Visual Studio 2017 sürüm 15,5 ' de, yeni bir derleyici anahtarı, [`/Zc:externConstexpr`](../build/reference/zc-externconstexpr.md) doğru ve standartlara uygun davranışı mümkün bir şekilde sunar. Daha fazla bilgi için bkz. [extern constexpr bağlantısı](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimleri kaldırılıyor

[P0003R5](https://wg21.link/p0003r5) Dinamik özel durum belirtimleri C++ 11 ' de kullanımdan kaldırılmıştır. Özellik C++ 17 ' den kaldırılır, ancak (hala) kullanım dışı olan `throw()` Belirtim tamamen bir diğer ad olarak tutulur `noexcept(true)` . Daha fazla bilgi için bkz. [dinamik özel durum belirtimi kaldırma ve noexcept](#noexcept_removal).

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

[P0607R0](https://wg21.link/p0607r0)

### <a name="annex-d-features-deprecated"></a>Ek D özellikleri kullanım dışı

C++ standardının ek D,, ve dahil olmak üzere kullanım dışı bırakılmış tüm özellikleri içerir `shared_ptr::unique()` `<codecvt>` `namespace std::tr1` . **`/std:c++17`** Derleyici anahtarı ayarlandığında, ek D içindeki standart kitaplık özelliklerinin neredeyse tamamı kullanım dışı olarak işaretlenir. Daha fazla bilgi için bkz. [Ek D Içindeki standart kitaplık özellikleri kullanım dışı olarak işaretlendi](#annex_d).

`std::tr2::sys`' Deki ad alanı `<experimental/filesystem>` artık varsayılan olarak altında kullanımdan kaldırma uyarısı yayar **`/std:c++14`** ve **`/std:c++17`** Varsayılan olarak altında kaldırılır.

`<iostream>`Standart olmayan bir uzantıyı önleyerek ' de geliştirilmiş uyumluluk (sınıf içi açık uzmanlık).

Standart kitaplık artık değişken şablonları dahili olarak kullanmaktadır.

Standart Kitaplık, C++ 17 derleyici değişikliklerine yanıt olarak güncelleştirildi. Güncelleştirmeler, **`noexcept`** tür sistemine ekleme ve dinamik özel durum belirtimlerinin kaldırılması içerir.

## <a name="conformance-improvements-in-156"></a><a name="improvements_156"></a> 15,6 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-library-fundamentals-v1"></a>C++ 17 kitaplık temelleri v1

[P0220R1](https://wg21.link/p0220r1) c++ 17 Için kitaplık temelleri teknik belirtimini standart olarak içerir. ,,,,,,, Ve için güncelleştirmeleri içerir \<experimental/tuple> \<experimental/optional> \<experimental/functional> \<experimental/any> \<experimental/string_view> \<experimental/memory> \<experimental/memory_resource> \<experimental/algorithm> .

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++ 17: standart kitaplık için sınıf şablonu bağımsız değişken kesintiyi geliştirme

[P0739R0](https://wg21.link/p0739r0) `adopt_lock_t` `scoped_lock` Uygulamasının tutarlı kullanımını etkinleştirmek için için parametre listesinin önüne geçin `scoped_lock` . `std::variant`Oluşturucuyu kopyalama atamasını etkinleştirmek için, daha fazla durumda oluşturucunun aşırı yükleme çözümüne katılmasına izin verin.

## <a name="conformance-improvements-in-157"></a><a name="improvements_157"></a> 15,7 sürümündeki uyumluluk geliştirmeleri

### <a name="c17-rewording-inheriting-constructors"></a>C++ 17: Reifade devralan oluşturucular

[P0136R1](https://wg21.link/p0136r1) **`using`** bir oluşturucuyu isimlendiremeyen bir bildirimin artık karşılık gelen temel sınıf oluşturucularının, ek türetilmiş sınıf oluşturucuları bildirmek yerine, türetilen sınıfın başlatmaları görünür hale getiriyor olduğunu belirtir. Bu reifade, C++ 14 ' ten bir değişiklik. Visual Studio 2017 sürüm 15,7 ve sonraki sürümlerinde, **`/std:c++17`** modunda c++ 14 ' te geçerli olan ve devralan oluşturucular kullanan kod geçerli olmayabilir veya farklı anlamlarına sahip olabilir.

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

## <a name="bug-fixes-in-visual-studio-2017-rtw-version-150"></a><a name="update_150"></a> Visual Studio 2017 RTW 'de hata düzeltmeleri (sürüm 15,0)

### <a name="copy-list-initialization"></a>Kopya listesini başlatma

Visual Studio 2017, başlatıcı listeleri kullanarak nesne oluşturmayla ilgili derleyici hatalarını doğru şekilde yükseltir. Bu hatalar Visual Studio 2015 ' de yakalanmadı ve kilitlenmelere veya tanımsız çalışma zamanı davranışına neden olabilir. N4594 13.3.1.7 P1 başına, Copy-List-Initialization öğesinde, aşırı yükleme çözümlemesi için açık bir oluşturucuyu göz önünde bulundurmanız gerekir. Ancak, belirli bir aşırı yükleme seçilirse bir hata oluşturması gerekir.

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

Bir constexpr bağlamında, koşullu değerlendirme işleminin sol işleneni geçerli olmadığında Visual Studio 2017 doğru bir şekilde hata oluşturur. Aşağıdaki kod Visual Studio 2015 ' de derlenir, ancak Visual Studio 2017 ' de C3615 `constexpr function 'f' cannot result in a constant expression` .

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

Derleyicinin önceki sürümleri bazı şablon bağlamlarındaki nitelikli adlara erişimi denetmedi. Bu sorun, bir adın erişilebilirliği nedeniyle değiştirme 'nin başarısız olması beklenen SFıNAE davranışına engel olabilir. Derleyici yanlış bir işlecin aşırı yüklemesini hatalı olarak çağırdığından, büyük olasılıkla çalışma zamanında kilitlenme veya beklenmeyen davranışlara neden olmuş olabilir. Visual Studio 2017 ' de bir derleyici hatası tetiklenir. Belirli hata değişebilir, ancak genellikle C2672 `no matching overloaded function found` . Aşağıdaki kod Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de bir hata oluşturur:

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

İfade-SFINAE 'yi desteklemek için, artık **`decltype`** şablon örneği oluşturulması yerine bir şekilde bildirildiği zaman bağımsız değişkenleri ayrıştırır. Sonuç olarak, decltype bağımsız değişkeninde bağımlı olmayan bir özelleştirme bulunursa, örnekleme zamanına ertelenir. Anında işlenir ve bu sırada ortaya çıkan hatalar tanılandı.

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

C++ standardına göre, anonim bir ad alanı içinde belirtilen bir sınıfın iç bağlantısı vardır ve bu, verilemeyeceği anlamına gelir. Visual Studio 2015 ve önceki sürümlerde bu kural zorlanmaz. Visual Studio 2017 ' de kural kısmen zorlanır. Visual Studio 2017 ' de aşağıdaki örnek hata C2201 oluşturuyor: `const anonymous namespace::S1::vftable: must have external linkage in order to be exported/imported.`

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
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

## <a name="bug-fixes-in-153"></a><a name="update_153"></a> 15,3 sürümündeki hata düzeltmeleri

### <a name="calls-to-deleted-member-templates"></a>Silinen üye şablonlarına yapılan çağrılar

Visual Studio 'nun önceki sürümlerinde, bazı durumlarda derleyici, silinen üye şablonuna yönelik hatalı biçimlendirilmiş çağrılar için bir hata yaymayabilir. Bu çağrılar, çalışma zamanında kilitlenmelere neden olabilir. Aşağıdaki kod artık C2280 üretir `'int S<int>::f<int>(void)': attempting to reference a deleted function` :

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

Derleyici, derleme zamanında bu hatayı bulursa bir uyarı yayar: silinen kopya ctor ile yerel bir nesne, değere göre yerel ve yönetilen sınır arasında geçirilir. Derleyicinin derleme zamanında tanımadığı bu durumlar için, `std::terminate` hatalı oluşturulmuş bir sıralama gerçekleştiğinde programın hemen çağırması için bir çalışma zamanı denetimi çıkarır. Visual Studio 2017 sürüm 15,3 ' de, aşağıdaki kod uyarı C4606 oluşturur. `'A': passing argument by value across native and managed boundary requires valid copy constructor. Otherwise, the runtime behavior is undefined.`

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

Hatayı onarmak için, `#pragma managed` çağrıyı yapana yerel olarak işaretleme ve sıralama yapmaktan kaçının yönergesini kaldırın.

### <a name="experimental-api-warning-for-winrt"></a>WinRT için deneysel API uyarısı

Deneme ve geri bildirim için yayımlanan WinRT API 'Leri ile birlikte tasarlanmıştır `Windows.Foundation.Metadata.ExperimentalAttribute` . Visual Studio 2017 sürüm 15,3 ' de, derleyici bu öznitelik için uyarı C4698 oluşturur. Önceki Windows SDK sürümlerinden birkaç API zaten özniteliğiyle birlikte tasarlanmıştır ve bu API 'lere yapılan çağrılar artık bu derleyici uyarısını tetikler. Daha yeni Windows SDK 'Ları, tüm sevk edilen türlerden kaldırılan özniteliğe sahiptir. Daha eski bir SDK kullanıyorsanız, sevk edilen türlere yapılan tüm çağrılar için bu uyarıları bastırmak zorunda olacaksınız.

Aşağıdaki kod, C4698 Uyarı `'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' is for evaluation purposes only and is subject to change or removal in future updates` üretir:

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

Visual Studio 2017 sürüm 15,3, sınıfında bildirilmeyen bir şablon üye işlevinin satır dışı tanımı için bir hata oluşturur. Aşağıdaki kod artık C2039 hatasını `'f': is not a member of 'S'` veriyor:

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

### <a name="attempting-to-take-the-address-of-this-pointer"></a>İşaretçinin adresini alma girişimi `this`

C++ ' da, **`this`** X için işaretçi türünde bir prvalue olamaz. Adresini alamaz **`this`** veya bir lvalue başvurusuna bağlayamazsınız. Visual Studio 'nun önceki sürümlerinde derleyici, bu kısıtlamayı bir cast kullanarak atlatmayı sağlar. Visual Studio 2017 sürüm 15,3 ' de, derleyici C2664 hatasını üretir.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemeyen bir taban sınıfına dönüştürme

Visual Studio 2017 sürüm 15,3, bir türü erişilemeyen temel sınıfa dönüştürmeye çalıştığınızda bir hata üretir. Derleyici şimdi C2243: hatasını oluşturuyor `'type cast': conversion from 'D *' to 'B *' exists, but is inaccessible` . Aşağıdaki kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Derleyici artık aşağıdakine benzer bir kod gördüğünde C2243 üretir:

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

Şablon sınıflarındaki üye işlevlerinin satır dışı tanımlarında varsayılan bağımsız değişkenlere izin verilmez. Derleyici, altında bir uyarı **`/permissive`** ve altında bir sabit hata verecek [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

Visual Studio 'nun önceki sürümlerinde, aşağıdaki hatalı oluşturulmuş kod, çalışma zamanı kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3, uyarı C5034: `'A\<T>::f': an out-of-line definition of a member of a class template cannot have default arguments` :

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

Hatayı onarmak için `= false` Varsayılan bağımsız değişkeni kaldırın.

### <a name="use-of-offsetof-with-compound-member-designator"></a>`offsetof`Bileşik üye göstergesi ile kullanımı

Visual Studio 2017 sürüm 15,3 ' de, `offsetof(T, m)` "bileşik üye göstergesi" *olarak kullanıldığında* , seçeneğiyle derlerken bir uyarı oluşur **`/Wall`** . Aşağıdaki kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Visual Studio 2017 sürüm 15,3, uyarı C4841: `non-standard extension used: compound member designator in offsetof` :

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

Visual Studio 2017 sürüm 15,3 ' de `offsetof(T, m)` bir statik *m* veri üyesine veya üye işleve başvuran bir hata ile sonuçlanır. Aşağıdaki kod C4597 hatasını üretir: `undefined behavior: offsetof applied to member function 'example'` hata C4597: `undefined behavior: offsetof applied to static data member 'sample'` :

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

Bu kod hatalı biçimlendirilmiş ve çalışma zamanında kilitlenmesine neden olabilir. Hatayı onarmak için kodu artık tanımsız davranışı çağırmayacak şekilde değiştirin. C++ standardı tarafından izin verilmeyen taşınabilir olmayan kod.

### <a name="new-warning-on-__declspec-attributes"></a><a name="declspec"></a>Özniteliklerde yeni uyarı `__declspec`

Visual Studio 2017 sürüm 15,3 ' de, `__declspec(...)` bağlantı belirtiminden önce uygulanmışsa derleyici artık öznitelikleri yok saymaz `extern "C"` . Daha önce derleyici, çalışma zamanı etkilerine sahip olabilecek özniteliğini yoksayacaktır. **`/Wall`** Ve **`/WX`** seçenekleri ayarlandığında, aşağıdaki kod C4768 uyarı üretir: `__declspec attributes before linkage specification are ignored`

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarıyı onarmak için, önce şunu yerleştirin `extern "C"` :

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı, varsayılan olarak 15,3 ' de, ancak varsayılan olarak 15,5 ' de kullanılır ve yalnızca ile derlenen kodu etkiler  **`/Wall`** **`/WX`** .

### <a name="decltype-and-calls-to-deleted-destructors"></a>`decltype` ve silinen yıkıcıları için çağrılar

Visual Studio 'nun önceki sürümlerinde derleyici, ile ilişkili ifade bağlamında silinmiş yok edicinin bir çağrısının gerçekleştiğini algılamadım **`decltype`** . Visual Studio 2017 sürüm 15,3 ' de aşağıdaki kod C2280 hatasını `'A<T>::~A(void)': attempting to reference a deleted function` üretir:

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

Visual Studio 2017 RTW sürümünde gerileme vardı: C++ derleyicisi başlatılmamış bir değişken için tanılama yayınlamadığı **`const`** . Bu gerileme, Visual Studio 2017 sürüm 15,3 ' de düzeltildi. Aşağıdaki kod artık uyarı C4132 `'Value': const object should be initialized` üretir:

```cpp
const int Value; //C4132
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

Derleyicinin önceki sürümleri, dizi türleri için [std:: is_convertible](../standard-library/is-convertible-class.md) hatalı sonuçlar verdi. Bu gerekli kitaplık yazarları, nitelik türü kullanılırken Microsoft C++ derleyicisine özel durum verebilir `std::is_convertible<...>` . Aşağıdaki örnekte, statik onaylar Visual Studio 'nun önceki sürümlerinde geçer ancak Visual Studio 2017 sürüm 15,3 ' de başarısız olur:

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

Özel Yıkıcılar bir türün oluşturulabilir olmayan şekilde oluşmasına neden olur. `std::is_constructible<T, Args...>` , aşağıdaki bildirim yazıldığı gibi hesaplanır:

```cpp
   T obj(std::declval<Args>()...)
```

Bu çağrı bir yıkıcı çağrısını gösterir.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: belirsiz aşırı yükleme çözümü

Derleyicinin önceki sürümleri bazen birden fazla aday ve bağımsız değişkene bağlı arama aracılığıyla birden çok aday bulmadığı zaman belirsizliğe neden olmuş olabilir. Bu hata, seçilen yanlış aşırı yüklemeye ve beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3 doğru C2668 yükseltir `'f': ambiguous call to overloaded function` :

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

Kodu onarmak için, `N::f` çağrısını amaçlıyorsanız using ifadesini kaldırın `::f()` .

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişkene bağlı arama

Yerel işlev bildirimleri kapsayan kapsamdaki işlev bildirimini gizler ve bağımsız değişkene bağımlı aramayı devre dışı bırakır. Ancak, derleyicinin önceki sürümleri her zaman bağımsız değişkene bağlı arama, bu durumda. Hatalı aşırı yüklemeye ve beklenmeyen çalışma zamanı davranışına neden olabilir. Genellikle, hata yerel işlev bildiriminin hatalı imzası nedeniyle oluşur. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3 doğru C2660 yükseltir `'f': function does not take two arguments` :

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

Sınıf üyeleri, başlatıldıkları sırada başlatılır, başlatıcı listelerinde göründükleri sırada değildir. Önceki derleyicinin sürümleri, başlatıcı listesinin sırası bildirim sırasına göre farklıydı. Bu sorun, bir üyenin başlatması zaten başlatılmış başka bir üyeye bağımlıında, tanımsız çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15,3 (ile), **`/Wall`** Uyarı C5038: `data member 'A::y' will be initialized after data member 'A::x'` :

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Sorunu gidermek için, başlatıcı listesini bildirimlerle aynı sırada olacak şekilde düzenleyin. Bir veya her iki Başlatıcı de temel sınıf üyelerine başvururken benzer bir uyarı tetiklenir.

Bu uyarı varsayılan olarak kapalıdır ve yalnızca ile derlenen kodu etkiler **`/Wall`** .

## <a name="bug-fixes-and-other-behavior-changes-in-155"></a><a name="update_155"></a> 15,5 sürümündeki hata düzeltmeleri ve diğer davranış değişiklikleri

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

### <a name="__declspec-attributes-with-extern-c-linkage"></a>`__declspec`bağlantısı olan öznitelikler `extern "C"`

Visual Studio 'nun önceki sürümlerinde, derleyici, `__declspec(...)` `__declspec(...)` bağlantı belirtiminden önce uygulandığında yoksayılan öznitelikleri yok sayılır `extern "C"` . Bu davranış, olası çalışma zamanı etkilerine karşı kullanıcının istememiş kodu oluşturulmasına neden oldu. Uyarı Visual Studio sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak etkindir.

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

Statik **`constexpr`** veri üyeleri artık örtük olarak yapılır **`inline`** , bu da bir sınıftaki bildiriminin artık tanımıyla olduğu anlamına gelir. Veri üyesi için satır dışı bir tanım kullanmak **`static constexpr`** gereksizdir ve artık kullanım dışıdır. Visual Studio 2017 sürüm 15,5 ' de, **`/std:c++17`** anahtar uygulandığında aşağıdaki kod artık uyarı C5041 üretir `'size': out-of-line definition for constexpr static data member is not needed and is deprecated in C++17` :

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)` Uyarı C4768 Şu anda varsayılan olarak açık

Uyarı Visual Studio 2017 sürüm 15,3 ' ye eklenmiştir, ancak varsayılan olarak kapalıdır. Visual Studio 2017 sürüm 15,5 ' de, uyarı varsayılan olarak açık olur. Daha fazla bilgi için bkz. [ \_ \_ declspec Attributes hakkında yeni uyarı](#declspec).

### <a name="defaulted-functions-and-__declspecnothrow"></a>Varsayılan işlevler ve `__declspec(nothrow)`

Derleyici, `__declspec(nothrow)` karşılık gelen temel/üye işlevleri için özel durumlara izin verildiğinde, önceden ayarlanmış işlevlerin ile bildirilmesine izin verilir. Bu davranış, C++ standardının aksine, çalışma zamanında tanımsız davranışlara neden olabilir. Özel durum belirtimi uyumsuzluğu varsa, standart bu tür işlevlerin silinmiş olarak tanımlanmasını gerektirir.  **`/std:c++17`** Aşağıdaki kod, C2280 başlatır`attempting to reference a deleted function. Function was implicitly deleted because the explicit exception specification is incompatible with that of the implicit declaration.`

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

Bu gibi durumlarda, **`noexcept`** işlev işaretçilerini ve üye işlevlerine işaretçiler işlemek için ek kısmi uzmanlık eklemeniz gerekebilir **`noexcept`** . Bu aşırı yüklemeler yalnızca modda geçerlidir **`/std:c++17`** . C++ 14 ile geriye dönük uyumluluk korunuyorsa ve başkalarının kullandığı kodu yazıyorsanız, bu yeni aşırı yüklemeleri yönergeler içinde korumalısınız `#ifdef` . Kendi kendine içerilen bir modülde çalışıyorsanız, koruma kullanmak yerine `#ifdef` yalnızca anahtarla derleme yapabilirsiniz **`/Zc:noexceptTypes-`** .

Aşağıdaki kod, altında derlenir **`/std:c++14`** ancak ile altında başarısız olur **`/std:c++17`** `error C2027: use of undefined type 'A<T>'` :

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

## <a name="bug-fixes-and-other-behavior-changes-in-157"></a><a name="update_157"></a> 15,7 sürümündeki hata düzeltmeleri ve diğer davranış değişiklikleri

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++ 17: birincil Sınıf şablonunda varsayılan bağımsız değişken

Bu davranış değişikliği, [sınıf şablonları-P0091R3 Için şablon bağımsız değişken kesintisi](https://wg21.link/p0091r3)için bir önkoşuludur.

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

Bu davranış değişikliği, [sınıf şablonları-P0091R3 Için şablon bağımsız değişken kesintisi](https://wg21.link/p0091r3)için bir önkoşuludur.

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

Visual Studio 2017 sürüm 15,7 **`/std:c++17`** modunda, C4834 uyarı düzeyi, `discarding return value of function with 'nodiscard' attribute` w3 'den W1 'e yükseltilir. Bir cast ile **`void`** veya derleyiciye geçirerek uyarıyı devre dışı bırakabilirsiniz **`/wd:4834`**

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Değişken bağımsız değişken şablon Oluşturucusu temel sınıf başlatma listesi

Visual Studio 'nun önceki sürümlerinde, şablon bağımsız değişkenleri eksik olan bir bağımsız değişken şablon Oluşturucu temel sınıf başlatma listesine hatasız olarak izin veriliyor. Visual Studio 2017 sürüm 15,7 ' de bir derleyici hatası tetiklenir.

Visual Studio 2017 sürüm 15,7 ' de aşağıdaki kod örneği hatası oluşturuyor C2614: `D<int>: illegal member initialization: 'B' is not a base or member` .

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

Hatayı onarmak için B () ifadesini B \<T> () olarak değiştirin.

### <a name="constexpr-aggregate-initialization"></a>`constexpr` toplu başlatma

C++ derleyicisinin önceki sürümleri, toplu başlatmayı yanlış bir şekilde işledi **`constexpr`** . Derleyici, toplama-init listesinde çok fazla öğe olduğu ve kendisi için hatalı CodeGen üreten geçersiz kodu kabul etti. Aşağıdaki kod bu kodun bir örneğidir:

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

Visual Studio 2017 sürüm 15,7 güncelleştirme 3 ve sonraki sürümlerde, önceki örnek artık C2078 ' u yükseltir `too many initializers` . Aşağıdaki örnek, kodun nasıl düzeltileceğini gösterir. `std::array`İç içe yerleştirilmiş küme ayracı-init-listeleriyle, iç diziye kendi kendine açılan bir liste verin:

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

## <a name="bug-fixes-and-behavior-changes-in-158"></a><a name="update_158"></a> 15,8 sürümündeki hata düzeltmeleri ve davranış değişiklikleri

Visual Studio 2017 sürüm 15,8 ' de derleyici değişiklikleri tüm hata düzeltmeleri ve davranış değişikliklerdir. Bunlar aşağıda listelenmiştir:

### <a name="typename-on-unqualified-identifiers"></a>`typename` Nitelenmemiş tanımlayıcıda

[`/permissive-`](../build/reference/permissive-standards-conformance.md)Modunda, **`typename`** diğer ad şablonu tanımlarında nitelenmemiş tanımlayıcılarda bulunan spurerkeywords anahtar sözcükleri artık derleyici tarafından kabul edilmez. Aşağıdaki kod artık C7511 üretir `'T': 'typename' keyword must be followed by a qualified name` :

```cpp
template <typename T>
using  X = typename T;
```

Hatayı onarmak için ikinci satırı olarak değiştirin `using  X = T;` .

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()` diğer ad şablonu tanımlarının sağ tarafında

diğer ad şablon tanımının sağ tarafında [__declspec](../cpp/declspec.md) artık izin verilmiyor. Daha önce derleyici kabul etti ancak bu kodu yok sayıldı. Diğer ad kullanıldığında, hiçbir zaman kullanımdan kaldırma uyarısı oluşmasına neden olmaz.

Bunun yerine standart C++ özniteliği [ \[ \[ kullanım dışı bırakılmış \] \] ](../cpp/attributes.md) olabilir ve Visual Studio 2017 sürüm 15,6 ' de kullanılır. Aşağıdaki kod artık C2760 üretir `syntax error: unexpected token '__declspec', expected 'type specifier'` :

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

İki aşamalı ad arama, şablon gövdelerinde kullanılan bağımlı olmayan adların, tanım zamanında şablona görünür olması gerekir. Daha önce, Microsoft C++ derleyicisi, bulunmayan bir adı, örnekleme zamanına kadar aranmaz olarak bırakır. Şimdi, bağımlı olmayan adların şablon gövdesine bağlı olmasını gerektirir.

Bu şekilde bildirimde bulunan tek bir yöntem, bağımlı temel sınıflara aramalardır. Daha önce, derleyici bağımlı temel sınıflarda tanımlanmış adların kullanılmasına izin verilir. Bunun nedeni, tüm türlerin çözümlenme zamanı sırasında örnekleme sırasında aranmaları. Artık bu kod bir hata olarak kabul edilir. Bu durumlarda, değişkeni temel sınıf türü ile niteleyerek veya bir işaretçi ekleyerek buna bağımlı hale getirerek, örneği örnekleme zamanına göre aranmaya zorlayabilirsiniz `this->` .

[`/permissive-`](../build/reference/permissive-standards-conformance.md)Modda aşağıdaki kod artık C3861 ' u yükseltir: `'base_value': identifier not found`

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

Hatayı onarmak için, **`return`** ifadesini olarak değiştirin `return this->base_value;` .

**Note:** Yükseltme Python kitaplığı 'nda [unwind_type. hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp)içindeki şablon iletme BILDIRIMI için MSVC 'e özgü bir geçici çözüm vardır. [`/permissive-`](../build/reference/permissive-standards-conformance.md)Visual Studio 2017 sürüm 15,8 ' den başlayan mod ( \_ msc \_ ver = 1915) altında, MSVC derleyicisi bağımsız değişkene bağımlı ad araması (adl) doğru şekilde yapar. Artık diğer derleyicilerle tutarlıdır, bu geçici çözüm koruma gereksiz hale gelir. C3861 hatasını önlemek için `'unwind_type': identifier not found` , bir üst bilgi dosyasını güncelleştirmek üzere artırma deposunda [PR 229](https://github.com/boostorg/python/pull/229) ' a bakın. [Vcpkg](../build/vcpkg.md) Boost paketini zaten geliştirdik. bu nedenle, Boost kaynaklarınızı vcpkg 'dan edinmeniz veya yükseltmeniz durumunda düzeltme ekini ayrı olarak uygulamanız gerekmez.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>ad alanındaki iletme bildirimleri ve tanımları `std`

C++ standardı, bir kullanıcının ad alanına iletme bildirimleri veya tanımları eklemesine izin vermez `std` . Ad alanına veya ad alanı içindeki bir ad alanına bildirim veya tanım eklemek `std` `std` artık tanımsız davranışa neden olur.

Daha sonra, Microsoft, bazı standart kitaplık türlerinin tanımlandığı konumu taşıyacaktır. Bu değişiklik, ad alanına iletme bildirimleri ekleyen mevcut kodu keser `std` . Yeni bir uyarı olan C4643, bu tür kaynak sorunları belirlemenize yardımcı olur. Uyarı **`/default`** modda etkindir ve varsayılan olarak kapalıdır. Veya ile derlenen programları etkileyecektir **`/Wall`** **`/WX`** .

Aşağıdaki kod artık C4643 ' i yükseltir: `Forward declaring 'vector' in namespace std is not permitted by the C++ Standard` .

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

C++ standardı, bir derleyicinin kendi kendine temsilci Oluşturucu temsilcisi olarak bir tanı yaymayı önerir. Ve modlarında Microsoft C++ derleyicisi [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) artık C7535 ' i yükseltir: `'X::X': delegating constructor calls itself` .

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

### <a name="offsetof-with-constant-expressions"></a>`offsetof` Sabit ifadelerle

[OffsetOf](../c-runtime-library/reference/offsetof-macro.md) , geleneksel olarak [reinterpret_cast](../cpp/reinterpret-cast-operator.md)gerektiren bir makro kullanılarak uygulanmıştır. Bu kullanım, sabit bir ifade gerektiren bağlamlarda geçersizdir, ancak Microsoft C++ derleyicisinde geleneksel olarak izin verilir. `offsetof`Standart kitaplığın bir parçası olarak gönderilen makro bir derleyici iç (**__builtin_offsetof**) kullanır, ancak pek çok kişi makro eli kullanarak kendi kendilerini tanımlar `offsetof` .

Visual Studio 2017 sürüm 15,8 ' de, derleyici, **`reinterpret_cast`** Standart C++ davranışına uyum sağlamak için bu işleçlerin varsayılan modda görünebilen alanı kısıtlar. Altında [`/permissive-`](../build/reference/permissive-standards-conformance.md) kısıtlamalar bile daha sıkı bir şekilde yapılır. `offsetof`Sabit ifadeler gerektiren bir konum sonucunun kullanılması, uyarı C4644 veya C2975 veren koda neden olabilir `usage of the macro-based offsetof pattern in constant expressions is non-standard; use offsetof defined in the C++ standard library instead` `invalid template argument, expected compile-time constant expression` .

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
    case MY_OFFSET(Data, x): return 0;
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

Visual Studio 2017 sürüm 15,8 ' de [`/permissive-`](../build/reference/permissive-standards-conformance.md) modda aşağıdaki kod C3770 yükseltilir `'const S': is not a valid base class` :

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>`template` anahtar sözcük ve iç içe ad-tanımlayıcılar

[`/permissive-`](../build/reference/permissive-standards-conformance.md)Modunda, derleyici artık, **`template`** bağımlı bir iç içe ad belirleyicisi sonrasında olduğunda bir şablon adının önüne geçmek için anahtar sözcüğü gerektirir.

Aşağıdaki modda aşağıdaki kod [`/permissive-`](../build/reference/permissive-standards-conformance.md) C7510 yükseltilir: `'example': use of dependent template name must be prefixed with 'template'. note: see reference to class template instantiation 'X<T>' being compiled`

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

## <a name="bug-fixes-and-behavior-changes-in-159"></a><a name="update_159"></a> 15,9 sürümündeki hata düzeltmeleri ve davranış değişiklikleri

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

Visual Studio 2017 sürüm 15,9 ' de, [`/permissive-`](../build/reference/permissive-standards-conformance.md) modda derleyici C3861: `'from_template': identifier not found` .

Hatayı onarmak için, önce bildirimini `from_template` yapın `from_template_t` .

### <a name="modules-changes"></a>Modül değişiklikleri

Visual Studio 2017, sürüm 15,9 ' de, modüller için komut satırı seçenekleri modül oluşturma ve modül tüketim tarafları arasında tutarlı olmadığı zaman derleyici C5050 ' u yükseltir. Aşağıdaki örnekte, iki sorun vardır:

- Tüketim tarafında (Main. cpp), seçenek **`/EHsc`** belirtilmez.

- C++ sürümü **`/std:c++17`** oluşturma tarafında ve **`/std:c++14`** Tüketim tarafında bulunur.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Derleyici, bu iki durum için C5050 yükseltir: `warning C5050: Possible incompatible environment while importing module 'm': mismatched C++ versions.  Current "201402" module version "201703"` .

Derleyici Ayrıca,. ifc dosyası ile oynanmış her seferinde C7536 ' i de yükseltir. Modül arabiriminin üstbilgisi, altındaki içeriklerin SHA2 karmasını içerir. İçeri aktarma işleminde,. ifc dosyası karma hale getirilir ve üst bilgide belirtilen karmayla denetlenir. Bunlar eşleşmiyorsa, hata C7536 tetiklenir: `ifc failed integrity checks.  Expected SHA2: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'` .

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

::: moniker-end

::: moniker range="vs-2015"

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>Visual Studio 2015 ' de C++ uyumluluk geliştirmeleri

Visual Studio 2015 güncelleştirme 3 aracılığıyla uyumluluk geliştirmelerinden oluşan kapsamlı bir liste sunuyoruz. Daha fazla bilgi için bkz. yenilikler [2003 ile 2015 arasında Visual C++](../porting/visual-cpp-what-s-new-2003-through-2015.md).

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft C++ dil uygunluğu tablosu](visual-cpp-language-conformance.md)
