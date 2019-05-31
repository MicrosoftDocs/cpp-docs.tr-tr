---
title: C++ uyumluluk geliştirmeleri
ms.date: 05/16/2019
description: Microsoft C++ Visual Studio 2019 içinde C ++ 20 dili standardına uyar doğru ilerliyor.
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 02b778f10ad94342c922a4e79a856cc2a7d53076
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451211"
---
# <a name="c-conformance-improvements-in-visual-studio-2019-rtw-and-version-161improvements161"></a>C++Visual Studio 2019 RTW ve sürüm uyumluluğu geliştirmeleri [16.1](#improvements_161)

## <a name="improvements-in-visual-studio-2019-rtw"></a>Visual Studio 2019 RTW yenilikleri

Visual Studio 2019 RTW aşağıdaki uyumluluk geliştirmeleri, hata düzeltmeleri ve Microsoft C++ derleyicisi (MSVC) davranış değişiklikleri içerir.

**Not:** C ++ 20 özellikleri oluşturulacak bulunan `/std:c++latest` derleme ve IntelliSense için C ++ 20 uygulama tamamlanana kadar modu. O zaman `/std:c++20` derleyici modu kullanıma sunulan.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modüller desteği

Modüller C ++ 20 standart resmi olarak sunulmuştur. Visual Studio 2017 sürüm 15.9 için geliştirilmiş destek eklendi. Daha fazla bilgi için [MSVC 2017 sürümü 15.9 ile C++ modüllerinde şablon desteği ve hata algılama daha iyi](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Değiştirilen toplama türü belirtimi

Bir toplama türü belirtimi, C ++ 20 değiştirildi (bkz [engelle kullanıcı bildirilen oluşturuculara sahip toplamalar](https://wg21.link/p1008r1)). Visual Studio 2019 içinde altında `/std:c++latest`, herhangi bir kullanıcı olarak bildirilen oluşturucusuna sahip bir sınıf (örneğin bir oluşturucu dahil olmak üzere bildirilen `= default` veya `= delete`) bir toplama ifadesi değil. Daha önce yalnızca kullanıcı tarafından sağlanan bir oluşturucu, bir sınıfın bir toplama engeller diskalifiye. Bu değişiklik bu türler nasıl başlatılabilir ek kısıtlamalar getirir.

Aşağıdaki kod Visual Studio 2017'de hatasız derlenir, ancak C2280 ve Visual Studio 2019 altında içinde C2440 hataları başlatır `/std:c++latest`:

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

### <a name="partial-support-for-operator-"></a>Kısmi destek <> = işleci

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C ++ 20 tanıtır `<=>` üç yönlü karşılaştırma işleci olarak da bilinen "savaş Gemisi operatörü". İçinde Visual Studio 2019 `/std:c++latest` modu artık izin verilmeyen söz dizimi hatalarını yükselterek işleci için kısmi destek tanıtır. Örneğin, aşağıdaki kod Visual Studio 2017'de hata olmadan derler ancak Visual Studio 2019 altında birden çok hataları başlatır `/std:c++latest`:

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

Hataları önlemek için geçemediğinde son köşeli ayraç önce boşluk ekle: `U<&S::operator<= > u;`.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Başvuru türleri ile eşleşmeyen cv niteleyicileri

MSVC üst düzey daha önce doğrudan bir türüyle eşleşmeyen cv niteleyicileri başvuru bağlamasının izin verilir. Bu, başvuru tarafından başvurulan kullanılmasından const verileri değiştirilmesine izin verebilir ve derleyici artık standart gerektirdiği gibi geçici oluşturur. Visual Studio 2017'de, aşağıdaki kod uyarılar olmadan derler. Visual Studio 2019 ' derleyici başlatır *C4172 Uyarı: \<func: 1 "?PData@X @@QBEABQBXXZ"> yerel değişkenin veya geçici adresini döndürüyor*.

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
### <a name="reinterpretcast-from-an-overloaded-function"></a>`reinterpret_cast` Aşırı yüklenmiş bir işlevden

Bağımsız değişkeni `reinterpret_cast` aşırı yüklenmiş bir işlevin adresini verildiğinden bağlamları biri değil. Aşağıdaki kodu Visual Studio 2017'de hatasız derlenir, ancak Visual Studio 2019 bilmemektedir *C2440: 'fp' için 'aşırı-işlevden' dönüştürülemiyor*:

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

Hatayı önlemek için bu senaryo için izin verilen bir tür dönüştürme kullanın:

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>Lambda kapanışlar

C ++ 14'te, lambda kapanış türleri hazır değil. Bir lambda atanabilir değil, bu kuralın birincil sonucu olan bir `constexpr` değişkeni. Aşağıdaki kod Visual Studio 2017'de ancak Visual Studio 2019 hatasız harekete geçirirse derlendiğinden *C2127: 'l': 'constexpr' varlığı sabit olmayan bir ifadeyle hatalı başlatıldı* :

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Hatayı önlemek için ya da kaldırma `constexpr` niteleyicisi, aksi takdirde değişiklik uyumluluk modu için `/std:c++17`.

### <a name="stdcreatedirectory-failure-codes"></a>Std::create_directory hata kodları

Uygulanan [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) C ++ 20'den koşulsuz. Bu değişiklikleri `std::create_directory` hedef bir dizin başarısız olup olmadığını denetlemek için. Daha önce tüm error_already_exısts türü hata kodlarına başarılı ancak-directory-not-oluşturulan açık olan.

### <a name="operatorstdostream-nullptrt"></a>işleç < <(std::ostream, nullptr_t)

Başına [LWG 2221](https://cplusplus.github.io/LWG/issue2221)eklendi `operator<<(std::ostream, nullptr_t)` nullptrs akışlara yazmak için. 

### <a name="additional-parallel-algorithms"></a>Ek paralel algoritmalar

Yeni paralel sürümlerini `is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap`, ve `is_heap_until`.

### <a name="atomic-initialization"></a>atomik başlatma

[P0883 "Düzeltme atomik başlatma"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) değişiklikleri `std::atomic` için varsayılan-başlatılıyor yerine kapsanan T değeri-başlatılamadı. Düzeltme Clang/LLVM Microsoft Standart kitaplığını kullanırken etkinleştirilir. Microsoft şu anda devre dışı C++ geçici bir çözüm için constexpr işlenirken bir hata olarak derleyici.

### <a name="removecvref-and-removecvreft"></a>remove_cvref ve remove_cvref_t

Uygulanan `remove_cvref` ve `remove_cvref_t` türü nitelikler [P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf). Bu başvuru durumunu ve cv niteliği bir türünden işlevleri ve diziler işaretçilere küçülen olmadan kaldırın (aksine `std::decay` ve `std::decay_t`).

### <a name="feature-test-macros"></a>Özellik testi makroları

[P0941R2 - özellik testi makroları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) desteğiyle tamamlandı `__has_cpp_attribute`. Özellik testi makroları, tüm standart modlarında desteklenir.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Kullanıcı olarak bildirilen oluşturuculara sahip toplamalar engelle

[Kullanıcı olarak bildirilen oluşturuculara sahip toplamalar yasaklanması c ++ 20 P1008R1 -](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) tamamlandı.

## <a name="improvements_161"></a> Visual Studio 2019 sürüm 16.1 geliştirmeleri

### <a name="char8t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C ++ 20 UTF-8 kod birimlerini temsil etmek için kullanılan yeni bir karakter türü ekler. C ++ 20 U8 dize değişmez değerlerine sahip türü `const char8_t[N]` yerine `const char[N]`, olduğu durum daha önce. Benzer değişiklikler önerilen C standardı'için [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm). Char8_t geriye dönük uyumluluk düzeltme önerileri verilmiştir [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html). Microsoft C++ derleyici belirttiğinizde bu char8_t desteği Visual Studio 2019 sürüm 16.1 ekler **/Zc:char8_t** derleyici seçeneği. Gelecekte ile desteklenecektir [/Std: c ++ Son](../../build/reference/std-specify-language-standard-version.md), hangi döndürülebilir C ++ 17 davranışına **/Zc:char8_t-** . Gerçek derleme etkilemez alacaklardır yalnızca IntelliSense hataları göreceğiniz şekilde çalışmasını sağlayan IntelliSense EDG derleyici henüz, desteklemez.

#### <a name="example"></a>Örnek

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtypeidentity-metafunction-and-stdidentity-function-object"></a>Std::type_identity programlayıcılarına ve std::identity işlev nesnesi

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). Kullanım dışı `std::identity` sınıf şablonu uzantısı algıladı kaldırıldı ve C ++ 20 ile değiştirilen `std::type_identity` programlayıcılarına ve `std::identity` işlev nesnesi. Her ikisi de yalnızca altında kullanılabilir [/Std: c ++ Son](../../build/reference/std-specify-language-standard-version.md). 

Aşağıdaki örnek C4996 için uyarı kullanımdan kaldırma üretir `std::identity` (tanımlanan \<type_traits >) Visual Studio 2017'de: 

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

Aşağıdaki örnek yeni kullanmayı gösterir `std::identity` (tanımlanan \<işlevsel >) ile birlikte yeni `std::type_identity`:

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Genel lambda ifadeleri için söz dizimini denetler

Yeni lambda işlemci altında genel lambda ifadeleri, bazı uyumluluk modu söz dizimsel denetimlerinde sağlayan [/Std: c ++ Son](../../build/reference/std-specify-language-standard-version.md) veya diğer bir dil moduyla altında **/ Deneysel: newLambdaProcessor**. 

Visual Studio 2017'de uyarılar olmadan bu kod derlenir, ancak isteğe bağlı olarak Visual Studio 2019 hata üreten *C2760 söz dizimi hatası: beklenmeyen belirteç '\<kimliği-expr >', beklenen 'kimliği-expression'* :

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

Aşağıdaki örnek, derleyici tarafından artık zorlanan doğru söz dizimini gösterir:

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>İşlev çağrısı için bağımsız değişkene bağlı arama

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html) (C ++ 20) bağımsız değişkene bağlı arama aracılığıyla işlev şablonlarının açık şablon bağımsız değişkenleriyle işlev çağrı ifadeleri için bulma özelliğini Artırdık. Gerektirir **/Std: c ++ Son**.

### <a name="designated-initialization"></a>Belirtilen başlatma

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf) (C ++ 20) atanan başlatma sağlar toplama başlatma kullanılarak seçilmesini belirli üyeleri `Type t { .member = expr }` söz dizimi. Gerektirir **/Std: c ++ Son**.

### <a name="new-and-updated-standard-library-functions-c20"></a>Yeni ve güncelleştirilmiş standart kitaplık işlevleri (C ++ 20)

- `starts_with()` ve `ends_with()` için `basic_string` ve `basic_string_view`.
- İlişkili kapsayıcılar için `contains()`.
- `remove()`, `remove_if()`, ve `unique()` için` list` ve `forward_list` artık döndürür `size_type`.
- `shift_left()` ve `shift_right()` eklenen \<algoritma >.

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-rtw"></a>Hata düzeltmeleri ve Visual Studio 2019 RTW davranış değişiklikleri

### <a name="correct-diagnostics-for-basicstring-range-constructor"></a>Basic_string aralık oluşturucu için doğru tanılama

Visual Studio 2019 içinde `basic_string` aralık oluşturucu artık derleyici Tanılaması ile bastırır `static_cast`. Aşağıdaki kod, Visual Studio 2017, uyarılara rağmen olası veri kaybı olmadan derler `wchar_t` için `char` başlatılırken `out`:

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 doğru başlatır *C4244: 'bağımsız değişkeni': 'const _Elem', olası veri kaybı 'wchar_t' dönüştürme*. Bu uyarıyı engellemek için bu örnekte gösterildiği gibi std::string başlatabilirsiniz:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>+= Ve/CLR veya /ZW altında-= yanlış çağrıları artık doğru şekilde algılandığında

Bir hatayı sessizce Hataları yoksay ve += ve altında-= geçersiz çağrıları için kod oluşturmak derleyicinin neden Visual Studio 2017'de kullanılmaya başlanan `/clr` veya `/ZW`. Aşağıdaki kod Visual Studio 2017, ancak Visual Studio doğru şekilde bilmemektedir 2019 hatasız derlenir *hatası C2845: ' System:: String'i ^': işaretçi aritmetik bu türüne izin verilmiyor*:

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Bu örnekte bir hatayı önlemek için ToString() yöntemiyle işlecini kullanın: `s += E::e.ToString();`.

### <a name="initializers-for-inline-static-data-members"></a>Satır içi statik veri üyesi başlatıcıları

Geçersiz üye erişen içinde `inline` ve `static constexpr` başlatıcılar artık doğru şekilde algılandı. Aşağıdaki örnek Visual Studio 2017'de, ancak Visual Studio 2019 altında hata olmadan derler `/std:c++17` bilmemektedir modu *hatası C2248: olamaz erişimi özel üye bildirilen 'X' sınıfında*.

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

Hatadan kaçınmak için üyenin bildirmek `X::c` korumalı olarak:

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>Uzatılamaz C4800

MSVC C4800 çok gürültülü ve insuppressible bool değerine örtülü dönüştürme hakkında uyarı, bize Visual Studio 2017'de kaldırmak için önde gelen bir performans sağlamak için kullanılır. Ancak, Visual Studio 2017 yaşam döngüsü birçok geri bildirim sorunu gidermeye yararlı durumlarını aldık. Biz Visual Studio 2019 dikkatli bir şekilde özel olarak uyarlanmış bir C4800 ikisi için de bir açık tür dönüştürme veya karşılaştırma uygun türde 0 ile kolayca gizlenebilir, eşlik eden C4165 birlikte geri getirin. Kapalı varsayılan düzey 4 uyarısı C4800 olduğu ve C4165 kapalı varsayılan düzey 3 bir uyarıdır. Her ikisini de kullanarak bulunabilirlik `/Wall` derleyici seçeneği.

Aşağıdaki örnek C4800 ve altında C4165 başlatır `/Wall`:

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

Önceki örnekte uyarılarından kaçınmak için aşağıdakine benzer bir kod yazabilirsiniz:

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>Yerel sınıf üyesi işlevinde bir gövde yok

Visual Studio 2017'de *C4822: Yerel sınıf üyesi işlevinde bir gövde yok* tetiklenir yalnızca derleyici seçeneği `/w14822` ile göremiyorsanız açıkça ayarlanmış; `/Wall`. Visual Studio 2019 içinde C4822 altında bulunabilir hale getiren bir kapalı varsayılan olarak, uyarıdır `/Wall` ayarlamak zorunda kalmadan `/w14822` açıkça.

```cpp
void foo()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>İşlev şablonu gövdeleri constexpr içeren deyimleri

Şablonu işlev gövdeleri içeren `if constexpr` deyimleri sahip bazı `/permissive-` ayrıştırma ile ilgili denetimleri etkin. Örneğin, Visual Studio 2017'de C aşağıdaki kodu üretir*7510: 'Type': 'TypeName 'değerine sahip bağımlı tür adı öneki* yalnızca `/permissive-` seçeneği ayarlı değil. Hataları aynı kodu Visual Studio 2019 içinde olup olmadığını başlatır `/permissive-` seçeneği ayarlanır:

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

Hatayı önlemek için ekleyin `typename` anahtar sözcüğü bildirimine `a`: `typename T::Type a;`.

### <a name="inline-assembly-code-is-not-supported-in-a-lambda-expression"></a>Satır içi derleme kodu lambda ifadesinde desteklenmiyor

Visual C++ ekibine yakın zamanda bozulmasını 'ebp' (dönüş adresi register) çalışma zamanında, bir lambda içinde satır içi assembler kullanımına neden olabilir bir güvenlik sorunu farkında yapıldı. Kötü amaçlı bir saldırganın bu senaryo yararlanmak mümkün olabilir. Göz önünde bulundurulduğunda sorunun, satır içi assembler yalnızca x86 üzerinde desteklenir ve bu sorunun çözümü güvenli olduğunu düşünmüştür derleyici geri kalanını satır içi assembler kötü etkileşimi izin vermeyecek bir lambda içinde satır içi assembler olgusu ifade.

Not: yalnızca 'joker' karşılaştık bir lambda ifadesi içinde satır içi assembler kullanımını dönüş adresi yakalamak için amacı olan bir kullanım oluştu. Bu senaryoda, bir iç derleyici kullanarak tüm platformlarda dönüş adresi yakalayabilirsiniz `_ReturnAddress()`.

Aşağıdaki kod üretir *C7552: bir lambda içinde desteklenmeyen satır içi assembler* her iki Visual Studio 2017 15.9 ve Visual Studio 2019:

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

Hatayı önlemek için aşağıdaki örnekte gösterildiği gibi adlandırılmış bir işleve bütünleştirilmiş kodu Taşı:

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

### <a name="iterator-debugging-and-stdmoveiterator"></a>Hata ayıklama Yineleyici ve std::move_iterator

Hata ayıklama özelliği yineleyici düzgün açılacak verilen `std::move_iterator`. Örneğin, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` artık görüşebilirsiniz `memcpy` hızlı yolu.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>İçin düzeltmeler \<xkeycheck.h > anahtar sözcüğü zorlama

Standart kitaplık makrosu ized anahtar sözcüğü zorlama \<xkeycheck.h > yerine genel bir ileti algılanan gerçek sorunu anahtar sözcüğü yaymak için düzeltildi. Ayrıca C ++ 20 anahtar sözcükleri destekler ve IntelliSense makroları rastgele sözcükler belirten içine şekilde kandırma önler.

### <a name="allocator-types-un-deprecated"></a>Allocator türleri beklemediğiniz kullanım dışı

`std::allocator<void>`, `std::allocator::size_type`, ve `std::allocator::difference_type` beklemediğiniz kullanım dışı bırakıldı.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Daraltma dönüştürmeleri dize için doğru Uyarısı

Sahte bir `static_cast` yanlışlıkla C4244 gizlenen standardına göre uyarıları daraltma std::string kaldırıldı için çağrılır değil. Arama girişimi `std::string::string(const wchar_t*, const wchar_t*)` artık düzgün şekilde yayar *C4244 "bir wchar_t bir char daraltma."*

### <a name="various-filesystem-correctness-fixes"></a>Çeşitli \<filesystem > doğruluk düzeltmeleri

- Sabit `std::filesystem::last_write_time` yazma saati son bir dizin değiştirme girişimi sırasında başarısız oluyor.
- `std::filesystem::directory_entry` Oluşturucusu artık var olmayan bir hedef yolu sağlandığında bir özel durum atma yerine başarısız sonucu depolar.
- `std::filesystem::create_directory` 2 parametre sürüm, temel olarak 1 parametre sürüm çağırmak için değiştirildiği `CreateDirectoryExW` işlevi gerçekleştirir `copy_symlink` existing_p bir sembolik bağlantısını ne zaman.
- `std::filesystem::directory_iterator` bozuk bir sembolik bağlantısını karşılaştığınızda artık başarısız olur.
- `std::filesystem::space` artık göreli yolları kabul eder.
- `std::filesystem::path::lexically_relative` artık tarafından olarak bildirilen bir eğik çizgi, sonda karıştırılır [LWG 3096](https://cplusplus.github.io/LWG/issue3096).
- Geçici olarak çalışan `CreateSymbolicLinkW` eğik yollarla reddetme `std::filesystem::create_symlink`.
- POSIX silme modunu geçici olarak çalışan `delete` üzerinde Windows 10 LTSB 1609 var ancak aslında dosyaları silme özelliğine sahip işlev.
- `std::boyer_moore_searcher` ve `std::boyer_moore_horspool_searcher`kullanıcının kopya oluşturucuları ve kopya atama işleçleri artık gerçekten kopyalamak şeyler.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 ve sonraki sürümlerde paralel algoritmalar

Paralel algoritmalar kitaplığını artık düzgün bir şekilde gerçek kullanan `WaitOnAddress` Windows 8 ve sonraki sürümlerde, her zaman Windows 7 ve önceki sahte sürümlerle kullanmak yerine ailesi.

### <a name="stdsystemcategorymessage-whitespace"></a>std::system_category::message() whitespace

`std::system_category::message()` artık döndürülen iletiden sonraki boşlukları kırpar.

### <a name="stdlinearcongruentialengine-divide-by-zero"></a>Std::linear_congruential_engine sıfıra

Neden bazı koşullar `std::linear_congruential_engine` tetiklemek için 0 ile bölme düzeltilmiştir.

### <a name="fixes-for-iterator-unwrapping"></a>Çözülme yineleyici yönelik düzeltmeler

Visual Studio 2017 15,8 Programcı kullanıcı tümleştirmesi için önce kullanıma sunulan makine çözülme yineleyici (açıklandığı https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/ ) artık standart kitaplığı yineleyicilerine türetilmiş yineleyiciler açar. Örneğin, türetilen bir kullanıcı `std::vector<int>::iterator` ve artık davranışını özelleştirmek için çalışır, bir işaretçi davranışını yerine standart kitaplığı algoritmalarıdır çağrılırken özel davranışları alır.
Sırasız kapsayıcı ayırma işlevi artık gerçekten N öğeleri için açıklandığı gibi ayırır [LWG 2156](https://cplusplus.github.io/LWG/issue2156).

### <a name="time-handling"></a>İşleme süresi

- Daha önce eşzamanlılık kitaplığa iletilen bazı saat değerleri, örneğin, taşma oluşturursunuz `condition_variable::wait_for(seconds::max())`. Artık sabit, bu taşıyor, (temel alınan Win32 API'ları tarafından kabul uint32_t milisaniye zaman taştı) görünüşte rastgele 29 gün döngüsünde davranışı değişti.

- <ctime> Üstbilgi artık doğru şekilde bildirir timespec ve ad alanındaki timespec_get std yanı sıra bunları genel ad alanında bildirme.

### <a name="various-fixes-for-containers"></a>Kapsayıcılar için çeşitli düzeltmeleri

- Birçok standart kitaplığı iç kapsayıcı işlevleri için iyileştirilmiş bir IntelliSense deneyimi özel yapıldı. Üyeleri özel olarak işaretlemek için ek düzeltmelere MSVC sonraki sürümlerde beklenmektedir.

- Özel durum güvenliği doğruluk sorunları burada görüntülerle düğüm tabanlı kapsayıcılar gibi `list`, `map`, ve `unordered_map` bozulmuş düzeltilmiştir. Sırasında bir `propagate_on_container_copy_assignment` veya `propagate_on_container_move_assignment` yeniden atama işlemi, biz kapsayıcının sentinel düğümü eski ayırıcı ile ücretsiz, eski ayırıcı POCCA/POCMA atama yapmak ve sonra yeni ayırıcı sentinel düğümünden almayı deneyin. Bu ayırma başarısız olursa, kapsayıcısı bozuk ve bile, sabit bir sabit veri yapısı sentinel düğümüdür sahip olarak yok edilemez. Bu, varolan bir sentinel düğümü yok etme öncesinde kaynak kapsayıcının ayırıcı yeni sentinel düğüm ayrılacak düzeltildi.

- Kapsayıcılara göre her zaman kopyalama/taşıma/takas ayırıcılar için düzeltilen `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment`, ve `propagate_on_container_swap`, hatta ayırıcılar bildirilen `is_always_equal`.

- Kapsayıcı için aşırı birleştirme ve rvalue kapsayıcı başına kabul üye işlevleri eklenen [P0083 "Haritalar ve kümeleri boşluklarına ayıran"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)

### <a name="stdbasicistreamread-processing-of-rn--n"></a>\r\n Std::basic_istream::Read işlenmesini = > \n

`std::basic_istream::read` Belirtilen arabellek parçalara geçici olarak \r\n bir parçası olarak yazamazlar sabit = > \n işleme. Bu Visual Studio 2017 15,8 Okuma boyutu 4 K büyük için elde edilen performans avantajlarından bazıları yukarı sağlar, ancak gelen karakter başına 3 sanal çağrıları önleme, verimlilik geliştirmelerini yine de bulunur.

### <a name="stdbitset-constructor"></a>Std::bitset Oluşturucusu

`std::bitset`ın Oluşturucusu artık olanları okur ve ters sırada için büyük bitsets sıfırlar.

### <a name="stdpairoperator-regression"></a>Std::pair::operator regresyon =

' Teki bir gerileme düzeltildi `std::pair`atama işleci uygularken sunulan kullanıcının [LWG 2729 "eksik SFINAE std::pair::operator üzerinde =";](https://cplusplus.github.io/LWG/issue2729). Artık doğru şekilde türleri dönüştürülebilir kabul ettiği `std::pair` yeniden.

### <a name="non-deduced-contexts-for-addconstt"></a>Add_const_t olmayan atanan bağlamları

Bir alt türü nitelikler hata düzeltildi burada `add_const_t` ve ilgili işlevleri atanan olmayan bir bağlam olması gereken. Diğer bir deyişle, `add_const_t` için bir diğer ad olmalıdır `typename add_const<T>::type`değil `const T`.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 2019 yenilikler](../what-s-new-for-visual-cpp-in-visual-studio.md)