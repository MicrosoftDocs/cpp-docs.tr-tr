---
title: C++ uyumluluk geliştirmeleri
ms.date: 06/14/2019
description: Microsoft C++ Visual Studio'da C ++ 20 dili standardına uyar doğru ilerliyor.
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 1652c7ab9a48de65b32123b34c3231a0b06a410a
ms.sourcegitcommit: 0ad35b26e405bbde17dc0bd0141e72f78f0a38fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67194783"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Visual Studio 2017’deki C++ uyumluluk geliştirmeleri

Microsoft C++ uyumluluk geliştirmeleri ve hata düzeltmeleri her sürümde yapar. Bu makalede geliştirmeleri ana yayın tarafından ardından sürüm tarafından listelenir. Ayrıca önemli hata düzeltmeleri sürümü tarafından listelenir. Belirli bir sürümü için değişiklikleri doğrudan atlamak için kullanmak **bu makaledeki** listesi.

::: moniker range=">=vs-2019"

## <a name="improvements_160"></a> Visual Studio 2019 RTW (sürüm 16,0) yenilikleri

Aşağıdaki uyumluluk geliştirmeleri, hata düzeltmeleri ve davranış değişiklikleri Microsoft Visual Studio 2019 RTW içerir C++ derleyici (MSVC).

**Not:** C ++ 20 özellikleri oluşturulacak bulunan `/std:c++latest` derleme ve IntelliSense için C ++ 20 uygulama tamamlanana kadar modu. O zaman `/std:c++20` derleyici modu kullanıma sunulan.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modüller desteği

Modüller C ++ 20 standart resmi olarak sunulmuştur. Visual Studio 2017 sürüm 15.9 için geliştirilmiş destek eklendi. Daha fazla bilgi için [MSVC 2017 sürümü 15.9 ile C++ modüllerinde şablon desteği ve hata algılama daha iyi](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Değiştirilen toplama türü belirtimi

Bir toplama türü belirtimi, C ++ 20 değiştirildi (bkz [engelle kullanıcı bildirilen oluşturuculara sahip toplamalar](https://wg21.link/p1008r1)). Visual Studio 2019 içinde altında `/std:c++latest`, herhangi bir kullanıcı olarak bildirilen oluşturucusuna sahip bir sınıf (örneğin, bir oluşturucu dahil olmak üzere bildirilen `= default` veya `= delete`) bir toplama değildir. Daha önce yalnızca kullanıcı tarafından sağlanan bir oluşturucu, bir sınıfın bir toplama engeller diskalifiye. Bu değişiklik bu türler nasıl başlatılabilir ek kısıtlamalar getirir.

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

### <a name="partial-support-for-operator-"></a>İçin kısmi destek `operator <=>`

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

Hataları önlemek için geçemediğinde son açılı ayraç önce boşluk ekle: `U<&S::operator<= > u;`.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Başvuru türleri ile eşleşmeyen cv niteleyicileri

Daha önce MSVC doğrudan bir türüyle eşleşmeyen cv niteleyicileri başvuru bağlamasının en üst düzeyde izin. Bu bağlama, başvuru tarafından başvurulan kullanılmasından const verileri değiştirilmesine izin verebilir. Derleyici artık standart gerektirdiği gibi geçici bir oluşturur. Visual Studio 2017'de, aşağıdaki kod uyarılar olmadan derler. Visual Studio 2019 ' derleyici başlatır *C4172 Uyarı: \<func: 1 "?PData@X @@QBEABQBXXZ"> yerel değişkenin veya geçici adresini döndürüyor*.

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

C ++ 14'te, lambda kapanış türleri hazır değil. Bir lambda atanabilir değil, bu kuralın birincil sonucu olan bir `constexpr` değişkeni. Aşağıdaki kodu Visual Studio 2017'de hatasız derlenir, ancak Visual Studio 2019 bilmemektedir *C2127: 'l': 'constexpr' varlığı sabit olmayan bir ifadeyle hatalı başlatıldı*:

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Hatayı önlemek için ya da kaldırma `constexpr` niteleyicisi, aksi takdirde değişiklik uyumluluk modu için `/std:c++17`.

### <a name="stdcreatedirectory-failure-codes"></a>`std::create_directory` Hata kodları

Uygulanan [P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) C ++ 20'den koşulsuz. Bu değişiklikleri `std::create_directory` hedef bir dizin başarısız olup olmadığını denetlemek için. Daha önce tüm error_already_exısts türü hata kodlarına başarılı ancak-directory-not-oluşturulan açık olan.

### `operator<<(std::ostream, nullptr_t)`

Başına [LWG 2221](https://cplusplus.github.io/LWG/issue2221)eklendi `operator<<(std::ostream, nullptr_t)` nullptrs akışlara yazmak için.

### <a name="additional-parallel-algorithms"></a>Ek paralel algoritmalar

Yeni paralel sürümlerini `is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap`, ve `is_heap_until`.

### <a name="atomic-initialization"></a>atomik başlatma

[P0883 "Düzeltme atomik başlatma"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) değişiklikleri `std::atomic` için varsayılan-başlatılıyor yerine kapsanan T değeri-başlatılamadı. Düzeltme Clang/LLVM Microsoft Standart kitaplığını kullanırken etkinleştirilir. Microsoft şu anda devre dışı C++ geçici bir hata için bir çözüm olarak, derleyici `constexpr` işleniyor.

### <a name="removecvref-and-removecvreft"></a>`remove_cvref` ve `remove_cvref_t`

Uygulanan `remove_cvref` ve `remove_cvref_t` türü nitelikler [P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf). Bu başvuru durumunu ve cv niteliği bir türünden işlevleri ve diziler işaretçilere küçülen olmadan kaldırın (aksine `std::decay` ve `std::decay_t`).

### <a name="feature-test-macros"></a>Özellik testi makroları

[P0941R2 - özellik testi makroları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) desteğiyle tamamlandı `__has_cpp_attribute`. Özellik testi makroları, tüm standart modlarında desteklenir.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Kullanıcı olarak bildirilen oluşturuculara sahip toplamalar engelle

[Kullanıcı olarak bildirilen oluşturuculara sahip toplamalar yasaklanması c ++ 20 P1008R1 -](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) tamamlandı.

## <a name="improvements_161"></a> Visual Studio 2019 sürüm 16.1 geliştirmeleri

### <a name="char8t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C ++ 20 UTF-8 kod birimlerini temsil etmek için kullanılan yeni bir karakter türü ekler. `u8` C ++ 20 dize değişmez değerlerine sahip türü `const char8_t[N]` yerine `const char[N]`, olduğu durum daha önce. Benzer değişiklikler teklif, standart c [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm). Önerileri `char8_t` geriye dönük uyumluluk düzeltme verilir [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html). Microsoft C++ derleyici için destek ekler `char8_t` Visual Studio 2019 sürüm belirttiğinizde 16.1 içinde **/Zc:char8_t** derleyici seçeneği. Gelecekte ile desteklenecektir [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md), hangi döndürülebilir C ++ 17 davranışına **/Zc:char8_t-** . Gerçek derleme etkisini alacaklardır yalnızca IntelliSense hataları görürsünüz EDG derleyicinin IntelliSense güç katan, henüz desteklemiyor.

#### <a name="example"></a>Örnek

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtypeidentity-metafunction-and-stdidentity-function-object"></a>Std::type_identity programlayıcılarına ve std::identity işlev nesnesi

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). Kullanım dışı `std::identity` sınıf şablonu uzantısı algıladı kaldırıldı ve C ++ 20 ile değiştirilen `std::type_identity` programlayıcılarına ve `std::identity` işlev nesnesi. Her ikisi de yalnızca altında kullanılabilir [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md).

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

Yeni lambda işlemci altında genel lambda ifadeleri, bazı uyumluluk modu söz dizimsel denetimlerinde sağlayan [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md) veya diğer bir dil moduyla altında **/ Deneysel: newLambdaProcessor**.

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

### <a name="new-and-updated-standard-library-functions-c20"></a>Yeni ve güncelleştirilmiş standart kitaplığı işlevleri (C ++ 20)

- `starts_with()` ve `ends_with()` için `basic_string` ve `basic_string_view`.
- İlişkili kapsayıcılar için `contains()`.
- `list` ve `forward_list` için `remove()`, `remove_if()` ve `unique()` artık `size_type` değerini döndürüyor.
- `shift_left()` ve `shift_right()` eklenen \<algoritma >.

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019"></a>Hata düzeltmeleri ve Visual Studio 2019 davranış değişiklikleri

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

MSVC kullanılan C4800 örtük dönüştürme hakkında uyarı bir performans sağlamak için `bool`. Bu çok gürültülü ve, bize Visual Studio 2017'de kaldırmak için önde gelen gizlenemedi. Ancak, Visual Studio 2017 yaşam döngüsü geri bildirim çok sayıda kullanışlı durumlarını sorunu gidermeye aldık. Biz Visual Studio 2019 açıklayıcı C4165 birlikte dikkatli bir şekilde özel olarak uyarlanmış bir C4800 geri getirin. Bu uyarılar her ikisi de kolayca bir açık tür dönüştürme veya karşılaştırma uygun türde 0 ile gizlenebilir. Kapalı varsayılan düzey 4 uyarısı C4800 olduğu ve C4165 kapalı varsayılan düzey 3 bir uyarıdır. Her ikisini de kullanarak bulunabilirlik `/Wall` derleyici seçeneği.

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
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>İşlev şablonu gövdeleri constexpr içeren deyimleri

Şablonu işlev gövdeleri içeren `if constexpr` deyimleri sahip bazı `/permissive-` ayrıştırma ile ilgili denetimleri etkin. Örneğin, Visual Studio 2017'de C aşağıdaki kodu üretir*7510: 'Type': 'TypeName 'değerine sahip bağımlı tür adı öneki* yalnızca `/permissive-` seçeneği ayarlanmamış. Aynı kod harekete geçirirse hataları Visual Studio 2019 bile `/permissive-` seçeneği ayarlanır:

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

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Satır içi derleme kodu lambda ifadesinde desteklenmiyor

Görsel C++ ekibi kısa bir süre önce bir lambda içinde satır içi assembler kullanımını bozulmasına yol açabilir bir güvenlik sorunu farkında yapıldı `ebp` (dönüş adresi register) çalışma zamanında. Kötü amaçlı bir saldırgan, muhtemelen bu senaryoda avantajlarından ele geçirebilir. Göz önünde bulundurulduğunda, satır içi assembler yalnızca üzerinde desteklenen x86 ve satır içi assembler derleyici geri kalanı arasındaki kötü etkileşimi olduğu gerçeği sorunun bir lambda ifadesi içinde satır içi assembler izin vermeyecek şekilde güvenli çözüm bu sorunu oluştu.

Dönüş adresi yakalamak için yalnızca 'yaşamda' bulduk bir lambda ifadesi içinde satır içi assembler kullanımını oluştu. Bu senaryoda, bir iç derleyici kullanarak tüm platformlarda dönüş adresi yakalayabilirsiniz `_ReturnAddress()`.

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

### <a name="iterator-debugging-and-stdmoveiterator"></a>Hata ayıklama Yineleyici ve `std::move_iterator`

Hata ayıklama özelliği yineleyici düzgün açılacak verilen `std::move_iterator`. Örneğin, `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` artık görüşebilirsiniz `memcpy` hızlı yolu.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>İçin düzeltmeler \<xkeycheck.h > anahtar sözcüğü zorlama

Bir anahtar sözcüğü zorlama değiştirme standart kitaplığının makrosu \<xkeycheck.h > yerine genel bir ileti algılanan gerçek sorunu anahtar sözcüğü yaymak için düzeltildi. Ayrıca C ++ 20 anahtar sözcükleri destekler ve IntelliSense makroları rastgele sözcükler belirten içine şekilde kandırma önler.

### <a name="allocator-types-no-longer-deprecated"></a>Allocator türleri artık kullanım dışı

`std::allocator<void>`, `std::allocator::size_type`, ve `std::allocator::difference_type` artık kullanım dışı bırakılmıştır.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Daraltma dönüştürmeleri dize için doğru Uyarısı

Sahte bir `static_cast` yanlışlıkla C4244 gizlenen standardına göre uyarıları daraltma kaldırıldı için çağrılır değil `std::string`. Arama girişimi `std::string::string(const wchar_t*, const wchar_t*)` artık düzgün şekilde yayar *C4244 "bir wchar_t bir char daraltma."*

### <a name="various-filesystem-correctness-fixes"></a>Çeşitli \<filesystem > doğruluk düzeltmeleri

- Sabit `std::filesystem::last_write_time` yazma saati son bir dizin değiştirme girişimi sırasında başarısız oluyor.
- `std::filesystem::directory_entry` Oluşturucusu artık var olmayan bir hedef yolu sağlandığında bir özel durum atma yerine başarısız sonucu depolar.
- `std::filesystem::create_directory` 2 parametre sürüm, temel olarak 1 parametre sürüm çağırmak için değiştirildiği `CreateDirectoryExW` işlevi kullandığınız `copy_symlink` olduğunda `existing_p` bir sembolik bağlantısını oluştu.
- `std::filesystem::directory_iterator` bozuk bir sembolik bağlantısını bulunduğunda artık başarısız olur.
- `std::filesystem::space` artık göreli yolları kabul eder.
- `std::filesystem::path::lexically_relative` artık tarafından olarak bildirilen bir eğik çizgi, sonda karıştırılır [LWG 3096](https://cplusplus.github.io/LWG/issue3096).
- Geçici olarak çalışan `CreateSymbolicLinkW` eğik yollarla reddetme `std::filesystem::create_symlink`.
- POSIX silme modunu geçici olarak çalışan `delete` üzerinde Windows 10 LTSB 1609 var ancak aslında dosyaları silmek için işlev.
- `std::boyer_moore_searcher` ve `std::boyer_moore_horspool_searcher`kullanıcının kopya oluşturucuları ve kopya atama işleçleri artık gerçekten kopyalamak şeyler.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Windows 8 ve sonraki sürümlerde paralel algoritmalar

Paralel algoritmalar kitaplığını artık düzgün bir şekilde gerçek kullanan `WaitOnAddress` Windows 8 ve sonraki sürümlerde, her zaman Windows 7 ve önceki sahte sürümlerle kullanmak yerine ailesi.

### <a name="stdsystemcategorymessage-whitespace"></a>`std::system_category::message()` Boşluk

`std::system_category::message()` artık döndürülen iletiden sonraki boşlukları kırpar.

### <a name="stdlinearcongruentialengine-divide-by-zero"></a>`std::linear_congruential_engine` sıfıra bölme

Neden bazı koşullar `std::linear_congruential_engine` tetiklemek için 0 ile bölme düzeltilmiştir.

### <a name="fixes-for-iterator-unwrapping"></a>Çözülme yineleyici yönelik düzeltmeler

Öncelikle Visual Studio 2017 15,8 Programcı kullanıcı tümleştirmesi için kullanılan makine açıklandığı çözülme yineleyici C++ Team Blog makalesi [STL özellikleri ve VS 2017 15,8 düzeltmeler](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/), artık yineleyiciler açar Standart Kitaplığı yineleyicilerine türetilmiş. Örneğin, türetilen bir kullanıcı `std::vector<int>::iterator` ve artık davranışını özelleştirmek için çalışır, bir işaretçi davranışını yerine standart kitaplığı algoritmalarıdır çağrılırken özel davranışları alır.

Sırasız kapsayıcı `reserve` gerçekten yedekleri, N öğeler için açıklandığı gibi artık işlev [LWG 2156](https://cplusplus.github.io/LWG/issue2156).

### <a name="time-handling"></a>İşleme süresi

- Daha önce eşzamanlılık kitaplığa iletilen bazı saat değerleri, örneğin, taşma oluşturursunuz `condition_variable::wait_for(seconds::max())`. Sabit artık taşıyor (temel alınan Win32 API'ları tarafından kabul uint32_t milisaniye zaman taştı) görünüşte rastgele 29 gün döngüsünde davranışı değişti.

- <ctime> Üstbilgi artık doğru şekilde bildirir `timespec` ve `timespec_get` ad alanında `std` yanı sıra bunları genel ad alanında bildirme.

### <a name="various-fixes-for-containers"></a>Kapsayıcılar için çeşitli düzeltmeleri

- Birçok standart kitaplığı iç kapsayıcı işlevleri için iyileştirilmiş bir IntelliSense deneyimi özel yapıldı. Üyeleri özel olarak işaretlemek için ek düzeltmelere MSVC daha sonraki sürümlerde beklenmektedir.

- Özel durum güvenliği doğruluk sorunları burada görüntülerle düğüm tabanlı kapsayıcılar gibi `list`, `map`, ve `unordered_map` bozulmuş düzeltilmiştir. Sırasında bir `propagate_on_container_copy_assignment` veya `propagate_on_container_move_assignment` yeniden atama işlemi, biz kapsayıcının sentinel düğümü eski ayırıcı ile ücretsiz, eski ayırıcı POCCA/POCMA atama yapmak ve sonra yeni ayırıcı sentinel düğümünden almayı deneyin. Bu ayırma başarısız olursa, kapsayıcısı bozuk ve bile, sabit bir sabit veri yapısı sentinel düğümüdür sahip olarak yok uygulanamadı. Bu kod, mevcut sentinel düğüm yok etme öncesinde kaynak kapsayıcının ayırıcı yeni sentinel düğüm ayrılacak düzeltildi.

- Kapsayıcılara göre her zaman kopyalama/taşıma/takas ayırıcılar için düzeltilen `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment`, ve `propagate_on_container_swap`, hatta ayırıcılar bildirilen `is_always_equal`.

- Kapsayıcı için aşırı birleştirme ve rvalue kapsayıcı başına kabul üye işlevleri eklenen [P0083 "Haritalar ve kümeleri boşluklarına ayıran"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf)

### <a name="stdbasicistreamread-processing-of-rn--n"></a>`std::basic_istream::read` işlenmesi \\r\\n = > \\n

`std::basic_istream::read` Belirtilen arabellek parçalara geçici olarak bir parçası olarak yazamazlar sabit \\r\\n = > \\n işleme. Bu değişiklik Visual Studio 2017 15,8 Okuma boyutu 4 K büyük için elde edilen performans avantajlarından bazıları yedekleme sağlar. Ancak, verimlilik geliştirmelerini karakter başına üç sanal çağrıları önleme gelen yine de bulunur.

### <a name="stdbitset-constructor"></a>`std::bitset` Oluşturucusu

`std::bitset` Oluşturucusu artık olanları okur ve ters sırada için büyük bitsets sıfırlar.

### <a name="stdpairoperator-regression"></a>`std::pair::operator=` Regresyon

' Teki bir gerileme düzeltildi `std::pair`atama işleci uygularken sunulan kullanıcının [LWG 2729 "eksik SFINAE std::pair::operator üzerinde =";](https://cplusplus.github.io/LWG/issue2729). Artık doğru şekilde türleri dönüştürülebilir kabul ettiği `std::pair` yeniden.

### <a name="non-deduced-contexts-for-addconstt"></a>Olmayan atanan bağlamları `add_const_t`

Bir alt türü nitelikler hata düzeltildi burada `add_const_t` ve ilgili işlevleri atanan olmayan bir bağlam olması gereken. Diğer bir deyişle, `add_const_t` için bir diğer ad olmalıdır `typename add_const<T>::type`değil `const T`.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="improvements_150"></a> Visual Studio 2017 RTW (sürüm 15.0) yenilikleri

Desteğiyle genelleştirilmiş için `constexpr` ve statik olmayan veri üyesi başlatma (NSDMI) toplamlar, Microsoft için C++ Visual Studio 2017'de derleyici C ++ 14 sürümünde standart eklenen özellikler için tam sunuldu. Ancak, yine de derleyici C ++ 11 ve C ++ 98 standartlarındaki bazı özellikler eksiktir. Bkz: [Visual C++ dil uyumluluğu](../visual-cpp-language-conformance.md) derleyici geçerli durumunu gösteren bir tablo için.

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++11: Daha fazla kitaplıklarında ifade SFINAE desteği

Derleyici, şablon bağımsız değişkeni kesintisi ve değiştirme için gerekli olan SFINAE ifadesi desteğini geliştirmeye devam ediyor burada `decltype` ve `constexpr` ifadeler, şablon parametreleri olarak görünebilir. Daha fazla bilgi için [ifade SFINAE geliştirmeleri Visual Studio 2017 rc'de](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

### <a name="c14-nsdmi-for-aggregates"></a>C++14: NSDMI

Toplama, bir dizi veya hiçbir kullanıcı tarafından sağlanan oluşturucusu, hiçbir özel veya korumalı statik olmayan veri üyesi, temel olmayan sınıflar ve sanal işlev yok sınıfı ' dir. C ++ 14 toplamalar'den itibaren üye başlatıcılar içerebilir. Daha fazla bilgi için [üye başlatıcılarında ve toplamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

### <a name="c14-extended-constexpr"></a>C++14: Genişletilmiş `constexpr`

İfadeleri olarak bildirilen `constexpr` artık bildirimleri, belirli türde içermesi durumunda izin verilir ve anahtar ifadeleri, döngü ifadeleri ve Mutasyon nesne ömürlerinin içinde constexpr ifade değerlendirme başladı. Ayrıca, artık bir gerekliliği yoktur, bir `constexpr` statik olmayan üye işlev örtük olarak olmalıdır `const`. Daha fazla bilgi için [constexpr işlevlerdeki kısıtlamalar gevşetme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html).

### <a name="c17-terse-staticassert"></a>C++17: Kısa `static_assert`

ileti parametresi için `static_assert` isteğe bağlıdır. Daha fazla bilgi için [genişletme static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

### <a name="c17-fallthrough-attribute"></a>C ++ 17: `[[fallthrough]]` özniteliği

İçinde **/Std: c ++ 17** modu `[[fallthrough]]` özniteliği başarısızlığı davranışı geçmesini derleyici bir ipucu olarak switch deyimleri bağlamında kullanılabilir. Bu öznitelik, derleyici Böyle durumlarda uyarı vermesini engeller. Daha fazla bilgi için [için ifadesi \[ \[fallthrough\] \] özniteliği](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

### <a name="generalized-range-based-for-loops"></a>Aralık tabanlı for döngüleri genelleştirilmiş

Aralık tabanlı döngüler artık gerektiren için `begin()` ve `end()` aynı türe ait nesneleri döndürür. Bunu değiştirmek etkinleştirir `end()` aralıklardaki tarafından kullanılan bir sentinel döndürülecek [aralığı v3](https://github.com/ericniebler/range-v3) ve tamamlandı ancak-not-sessiz-yayımlanmış aralıkları teknik belirtimi. Daha fazla bilgi için [Genelleştiriliyor aralık tabanlı For döngüsü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a> Visual Studio 2017 sürüm 15.3 geliştirmeleri

### <a name="constexpr-lambdas"></a>constexpr lambdas

Lambda ifadeleri artık sabit ifadelerde kullanılabilir. Daha fazla bilgi için [C++ constexpr lambda ifadelerinde](../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>`if constexpr` işlev şablonları

Bir işlev şablonu içerebilir `if constexpr` derleme zamanı dallanma etkinleştirmek için deyimleri. Daha fazla bilgi için [, constexpr deyimleri](../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Başlatıcıları olan seçim deyimleri

Bir `if` deyimi bir değişkene deyimi içinde blok kapsamındaki tanıtan bir başlatıcı içerebilir. Daha fazla bilgi için [varsa deyimleri başlatıcısıyla](../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybeunused-and-nodiscard-attributes"></a>`[[maybe_unused]]` ve `[[nodiscard]]` öznitelikleri

Yeni öznitelik `[[maybe_unused]]` varlığın kullanıldığında olmayan uyarıların susturur. `[[nodiscard]]` Özniteliği işlev çağrısının dönüş değerini atılır değilse bir uyarı oluşturur. Daha fazla bilgi için [c++ öznitelikleri](../cpp/attributes.md).

### <a name="using-attribute-namespaces-without-repetition"></a>Yineleme olmadan öznitelik ad alanlarını kullanma

Bir öznitelik listesinde yalnızca tek bir ad tanımlayıcısı etkinleştirmek için yeni söz dizimi'ı seçin. Daha fazla bilgi için [c++ öznitelikleri](../cpp/attributes.md).

### <a name="structured-bindings"></a>Yapılandırılmış bağlamalar

Artık değeri bir dizi olduğunda, bileşenleri için ayrı ayrı adlara sahip bir değer depolamak için tek bir bildirimde olası bir `std::tuple` veya `std::pair`, ya da tüm ortak statik olmayan veri üyelerine sahip. Daha fazla bilgi için [yapılandırılmış bağlamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) ve [birden çok değer döndüren bir işlevden](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Yapı kuralları için `enum class` değerleri

Aynı zamanda hiçbir Numaralandırıcı, tanımını sunar ve bir liste başlatma söz dizimi kaynak kullanması durumunda şimdi bir örtük/olmayan-daraltma dönüşümü kapsamlı bir sabit listesinin temel alınan türünden numaralandırma kendisi için yoktur. Daha fazla bilgi için [oluşturma kuralları sabit listesi için değerleri sınıfı](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) ve [numaralandırmalar](../cpp/enumerations-cpp.md#no_enumerators).

### <a name="capturing-this-by-value"></a>Yakalama `*this` değere göre

`*this` Lambda ifadesindeki bir nesne artık yakalanıp değere göre. Bu değişiklik, lambda özellikle yeni makine mimarileri üzerinde paralel ve zaman uyumsuz işlemler çağırıldığı senaryolara olanak sağlar. Daha fazla bilgi için [Lambda yakalama, \*bu değeri olarak \[=\*bu\]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html).

### <a name="removing-operator-for-bool"></a>Kaldırma `operator++` için `bool`

`operator++` artık desteklenir `bool` türleri. Daha fazla bilgi için [kullanımdan kaldırma operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

### <a name="removing-deprecated-register-keyword"></a>Kullanımdan kaldırma `register` anahtar sözcüğü

`register` Anahtar sözcüğü, daha önce kullanım (ve derleyici tarafından yok sayılır), artık dilinden kaldırılır. Daha fazla bilgi için [kullanım dışı kullanımı register anahtar sözcüğü Kaldır](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

## <a name="improvements_155"></a> Visual Studio 2017 sürüm 15.5 geliştirmeleri

Özellikleri ile işaretlenen \[14] koşulsuz bile kullanılabilir **/Std: c ++ 14** modu.

### <a name="new-compiler-switch-for-extern-constexpr"></a>İçin yeni derleyici anahtarı `extern constexpr`

Visual Studio'nun önceki sürümlerinde, derleyici her zaman verdiğiniz bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15.5, yeni bir derleyici anahtarı [/ZC: externconstexpr](../build/reference/zc-externconstexpr.md), doğru standartlara uyan davranışını etkinleştirir. Daha fazla bilgi için [extern constexpr bağlantı](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Dinamik özel durum belirtimleri kaldırılıyor

[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) dinamik özel durum belirtimleri C ++ 11'de kullanım dışı. Bu özellik C ++ 17'den kaldırılır, ancak hâlâ kullanım dışı `throw()` belirtimi için bir diğer ad olarak kesinlikle tutulur `noexcept(true)`. Daha fazla bilgi için [dinamik özel durum belirtimi kaldırma ve noexcept](#noexcept_removal).

### `not_fn()`

[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) `not_fn` yerini, `not1` ve `not2`.

### <a name="rewording-enablesharedfromthis"></a>Yeni ifade biçimiyle `enable_shared_from_this`

[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this` C ++ 11'de eklenmiştir. C ++ 17 standardına daha iyi belirli köşe durumlarında belirtimi güncelleştirir. [14]

### <a name="splicing-maps-and-sets"></a>Haritalar ve kümeler ekleniyor

[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) ayıklama düğümlerinin ilişkilendirilebilir kapsayıcılar bu özelliği sağlar (diğer bir deyişle, `map`, `set`, `unordered_map`, `unordered_set`), ardından değiştirilebilir ve geri aynı kapsayıcı ya da farklı bir eklenen kapsayıcı aynı düğüm türü kullanır. (Bir düğümden ayıklamak için yaygın bir kullanım örneği olan bir `std::map`anahtarını değiştirin ve yeniden ekleyin.)

### <a name="deprecating-vestigial-library-parts"></a>İşlevini kaybetmiş kitaplık parçaları kullanımdan kaldırılıyor

[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) çeşitli özelliklerini C++ standart kitaplığı yıllar içinde yeni özellikler tarafından yenisiyle değiştirilmiş, aksi takdirde yararlı ya da sorunlu bulunmamış. Bu özellikler resmi olarak C ++ 17'de kullanım dışı bırakılmıştır.

### <a name="removing-allocator-support-in-stdfunction"></a>Ayırıcı desteği kaldırılıyor `std::function`

[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) C ++ 17 ' sınıf şablonu önce `std::function` ayırıcı bağımsız değişken alan birçok oluşturucuya sahip. Ancak, bu bağlamda ayırıcılar kullanımını sorunlu ve semantiği belirsiz. Sorun yapıcısı kaldırıldı.

### <a name="fixes-for-notfn"></a>İçin düzeltmeler `not_fn()`

[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) için yeni ifade `std::not_fn` sarmalayıcı çağrısında kullanıldığında değeri kategori yayılmasının desteği sağlar.

### <a name="sharedptrt-sharedptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) birleştirme `shared_ptr` Library Fundamentals'dan C ++ 17'ye değiştirir. [14]

### <a name="fixing-sharedptr-for-arrays"></a>Düzeltme `shared_ptr` diziler için

[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) diziler için destek shared_ptr giderir. [14]

### <a name="clarifying-insertreturntype"></a>Açıklığa kavuşturan `insert_return_type`

[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) benzersiz anahtarları olan ilişkili kapsayıcılar ve benzersiz anahtarları sırasız kapsayıcıları bir üye işlevine sahip `insert` iç içe geçmiş bir tür döndüren `insert_return_type`. Bu türü artık Yineleyici ve kapsayıcının NodeType parametreli bir türde bir özelleştirmesi olarak tanımlanan döndürür.

### <a name="inline-variables-for-the-standard-library"></a>Standart kitaplık için satır içi değişkenler

[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

### <a name="annex-d-features-deprecated"></a>Kullanımdan Kaldırılan annex D özellikleri

C++ standart D Annex dahil olmak üzere bırakılmıştır tüm özelliklerini içeren `shared_ptr::unique()`, `<codecvt>`, ve `namespace std::tr1`. Zaman **/Std: c ++ 17** derleyici anahtarı olarak ayarlanmışsa, d Annex neredeyse tüm standart kitaplık özellikleri kullanım dışı olarak işaretlenir. Daha fazla bilgi için [Annex d standart kitaplık özellikleri kullanım dışı olarak işaretlenmiş](#annex_d).

`std::tr2::sys` Ad alanında `<experimental/filesystem>` artık kullanımdan kaldırma Uyarısı altında yayan **/Std: c ++ 14** varsayılan olarak ve altında artık kaldırılır **/Std: c ++ 17** varsayılan olarak.

Geliştirilmiş uyumluluğu `<iostream>` tarafından bir standart olmayan uzantı (sınıfının açık uzmanlık) önleme.

Standart kitaplık artık dahili değişken şablonlar kullanır.

Standart kitaplık eklenmesi de dahil olmak üzere C ++ 17 derleyici değişikliklere, güncelleştirilmiş `noexcept` tür sistemi ve dinamik özel durum belirtimleri kaldırılması.

## <a name="improvements_156"></a> Visual Studio 2017 sürüm 15.6 geliştirmeleri

### <a name="c17-library-fundamentals-v1"></a>C ++ 17 kitaplığı temelleri V1

[P0220R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) Library Fundamentals teknik belirtimi, C ++ 17 standart içerir. Kapsayan güncelleştirmeleri \<Deneysel/tanımlama grubu >, \<Deneysel ve isteğe bağlı >, \<Deneysel/işlev >, \<Deneysel/any >, \<Deneysel/string_view >, \<Deneysel/bellek >, \<Deneysel/memory_resource >, ve \<Deneysel/algoritma >.

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++17: Sınıf şablonu bağımsız değişkeni kesintisi için standart kitaplık geliştirme

[P0739R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0739r0.html) taşıma `adopt_lock_t` için parametre listesinin öne `scoped_lock` tutarlı kullanımını etkinleştirmek için `scoped_lock`. İzin `std::variant` kopya atamasından etkinleştirmek için aşırı yükleme çözünürlüğü içinde daha fazla durumda katılmak için oluşturucu.

## <a name="improvements_157"></a> Visual Studio 2017 sürüm 15.7 geliştirmeleri

### <a name="c17-rewording-inheriting-constructors"></a>C++17: Yeni ifade biçimiyle devralma oluşturucuları

[P0136R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0136r1.html) belirten bir **kullanarak** bir oluşturucu artık adları bildirim yapar temel sınıf oluşturucuları türetilen sınıfın oluşturucusundaki için görünür karşılık gelen, ek türetilmiş yerine bildirme sınıf oluşturucular. Bu yeni ifade biçimiyle C ++ 14 farklıdır. Visual Studio 2017 sürüm 15.7 ve daha sonra **/Std: c ++ 17** modu, C ++ 14 ve oluşturucuların devralınması kullanan geçerli kod geçerli olmayabilir veya farklı semantiklere sahip.

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

Daha fazla bilgi için [oluşturucular](../cpp/constructors-cpp.md#inheriting_constructors).

### <a name="c17-extended-aggregate-initialization"></a>C++17: Genişletilmiş toplu başlatma

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

C ++ 17 ' de `Derived` artık bir toplama türü olarak kabul edilir. Başlatma anlamına `Base` aracılığıyla özel varsayılan oluşturucu genişletilmiş toplama başlatma kuralının bir parçası doğrudan olur. Daha önce `Base` özel Oluşturucu ile çağrıldı `Derived` oluşturucusu ve friend bildirimi nedeniyle başarılı oldu.

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

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++17: Otomatik tür olmayan şablon parametreleri bildirme

[P0127R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0127r2.html)

İçinde **/Std: c ++ 17** modu, derleyici artık türetme ile bildirilen bir tür olmayan şablon bağımsız değişken türünü **otomatik**:

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Geçerli C ++ 14 kod geçerli olmayabilir veya farklı semantiklere sahip, bu yeni özelliğin bir etkisidir. Örneğin, daha önce geçersiz bazı aşırı yüklemeleri artık geçerli değil. Aşağıdaki örnek, çünkü derleyen C ++ 14 kodu gösterir. çağrı `example(p)` bağlı `example(void*);`. Visual Studio 2017 sürüm 15.7, içinde **/Std: c ++ 17** modu `example` işlevi şablonu olarak en iyi eşleşme.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

Aşağıdaki örnek, Visual Studio 15.7 sürümündeki içinde C ++ 17 kodu gösterir. **/Std: c ++ 17** modu:

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*);

void example(void *);

void sample(A<0> *p)
{
    example(p); // C2280: 'int example<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++17: temel dize dönüştürme (kısmi)

[P0067R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0067r5.html) arasında kayan noktalı sayılar ve dizeler ve tamsayılar ve dizelerin arasında dönüştürmeler için alt düzey ve yerel ayarlardan bağımsızdır işlevler.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++20: Gereksiz decay (kısmi) önleme

[P0777R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0777r1.pdf) "decay" kavramını ve, yalnızca const veya başvuru niteleyicileri kaldırmanın arasında ayrım ekler.  Yeni türü niteliğine `remove_reference_t` değiştirir `decay_t` bazı bağlamlarda. Destek `remove_cvref_t` Visual Studio 2019 içinde uygulanır.

### <a name="c17-parallel-algorithms"></a>C++17: Paralel algoritmalar

[P0024R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0024r2.html) paralellik TS küçük değişiklikler ile standart içine dahil.

### <a name="c17-hypotx-y-z"></a>C++17: `hypot(x, y, z)`

[P0030R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0030r1.pdf) için üç yeni yükler ekler `std::hypot`, türleri için **float**, **çift**, ve **uzun çift**, her biri üç giriş parametresi yok.

### <a name="c17-filesystem"></a>C ++ 17: \<filesystem >

[P0218R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0218r1.html) birkaç ifadesi değişiklikler ile standart içine dosya sistemi TS devralır.

### <a name="c17-mathematical-special-functions"></a>C++17: Özel matematik işlevleri

[P0226R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0220r1.html) standart matematiksel özel işlevler için önceki teknik belirtimlerini uyarlar \<cmath > Üstbilgi.

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++17: Standart kitaplık için çıkarım kılavuzları

[P0433R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0433r2.html) C ++ 17 benimsenmesini yararlanmak için STL güncelleştirmeleri [P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html), sınıfın şablon bağımsız değişkeni kesintisi için destek ekler.

### <a name="c17-repairing-elementary-string-conversions"></a>C++17: Temel dize dönüştürme onarılıyor

[P0682R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0682r1.html) yeni temel dize dönüştürme işlevleri P0067R5 yeni üstbilgisine taşıma \<charconv > ve kullanmak için hata işleme değiştirme gibi diğer geliştirmeler yapmaya `std::errc` yerine `std::error_code`.

### <a name="c17-constexpr-for-chartraits-partial"></a>C ++ 17: `constexpr` için `char_traits` (kısmi)

[P0426R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0426r1.html) değişikliklerini `std::traits_type` üye işlevleri `length`, `compare`, ve `find` yapmak `std::string_view` sabit ifadelerde kullanılabilir. (Visual Studio 2017 sürüm 15.6, Clang/LLVM yalnızca desteklenir. Sürüm 15.7 Önizleme 2, destek neredeyse olduğu için ClXX de tamamlayın.)

## <a name="improvements_159"></a> Visual Studio 2017 sürüm 15.9 geliştirmeleri

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>İşleçler için soldan sağa Değerlendirme sırasını `->*`, `[]`, `>>`, ve `<<`

C ++ 17, işlenenler işleç başlangıç `->*`, `[]`, `>>`, ve `<<` soldan sağa doğru sırayla değerlendirilir. Derleyici bu düzeni olmasını garanti etmek mümkün olduğu iki durum vardır:

- işlenen ifadelerden biri bir nesne değer olarak geçilemez veya değere göre geçirilen nesneyi içerdiğinde veya

- kullanılarak derlendiğinde **/CLR**, ve işlenenleri biri bir alan bir nesne veya dizi öğesi.

Derleyici Uyarısı gösterir [C4866](https://docs.microsoft.com/cpp/error-messages/compiler-warnings/c4866?view=vs-2017) zaman bunu garanti etmez soldan sağa değerlendirme. Bu uyarı yalnızca, derleyici oluşturur **/Std: c ++ 17** veya bu işleçler soldan sağa sıralı gereksinimi C ++ 17'de kullanılmaya başlanan olarak daha sonra belirtilir.

Bu uyarıyı çözmek için önce işlenenlerin soldan sağa Değerlendirme sırasını bağımlı yan etkileri işlenenlerin zaman üretebilir gibi gerekli olup olmadığını göz önünde bulundurun. Çoğu durumda, işlenenleri değerlendirilme sırasını gözlemlenebilir etkisi yoktur. Soldan sağa Değerlendirme sırasını olması gerekiyorsa, işlenenleri sabit başvuruya göre bunun yerine geçirebilirsiniz olup olmadığını göz önünde bulundurun. Bu değişiklik, aşağıdaki kod örneği'nde uyarı ortadan kaldırır:

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

## <a name="update_150"></a> Visual Studio 2017 RTW (sürüm 15.0) hata düzeltmeleri

### <a name="copy-list-initialization"></a>Kopya listesi başlatması

Visual Studio 2017, Visual Studio 2015'te yakalanan değil ve için kilitlenmelere neden olabilir, başlatıcı listeleri kullanarak nesne oluşturma ilgili derleyici hataları doğru başlatır veya çalışma zamanı davranışı tanımsız. Kopya listesi başlatması içinde N4594 13.3.1.7p1 göre derleyici açık bir oluşturucu aşırı yükleme çözümlemesi için dikkate alınması gereken gereklidir, ancak belirli aşırı yükleyen seçilirse hata yükseltmeniz gerekir.

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

### `constexpr`

Koşullu olarak değerlendirilmesini işleminin sol işlenen bir constexpr bağlamında geçerli değilken, visual Studio 2017 doğru bir hata oluşturur. Aşağıdaki kod, Visual Studio 2015'te ancak Visual Studio 2017 ('f' constexpr işlevi sabit ifade ile sonuçlanamaz C3615) derler:

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

Visual Studio 2017'de, sınıf ya da printf gibi değişen sayıda bağımsız değişken işleve geçirilen yapının artık önemsiz olarak kopyalanabilir olmalıdır. Bu tür nesneleri geçirirken, derleyicinin yalnızca bit düzeyinde bir kopya oluşturur ve oluşturucu veya yıkıcı çağrısı değil.

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

Aksi takdirde iletmeden önce nesneyi dönüştürmek için bir statik dönüştürme kullanın:

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

Visual Studio 2015'te derleyici bazen yanlışlıkla bir sınıf nesnesi bir oluşturucu çağrısı aracılığıyla oluştururken cv niteleyici yoksayar. Bu sorun büyük olasılıkla bir kilitlenme veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnek, Visual Studio 2015'te derler ancak Visual Studio 2017'de bir derleyici hatası oluşturur:

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

Önceki derleyici sürümleri, bazı şablon bağlamlarında nitelenmiş adlar erişimi denetlemiyordu. Bu sorun, burada değiştirme adının inaccessibility nedeniyle başarısız olması bekleniyor, beklenen SFINAE davranışı etkileyebilir. Derleyici yanlış İşleç aşırı yüklemesi hatalı denir çünkü bu büyük olasılıkla bir kilitlenme veya çalışma zamanında beklenmeyen davranışlara neden olan. Visual Studio 2017'de, bir derleyici hatası oluşturulur. Belirli bir hata gösterebilir, ancak genellikle "C2672 eşleşen aşırı yüklenmiş işlev bulunamadı" olacaktır. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017'de bir hata oluşturur:

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

Şablonu bir şablon parametre listesinde, örneğin, varsayılan şablon bağımsız değişkeni veya bir tür olmayan şablon parametresinin bir parçası olarak görüntülendiğinde Visual Studio 2015 ve önceki sürümlerinde, derleyici şablon bağımsız değişken listesi eksik tanılayın değil. Bu sorun, derleyici kilitlenmeleri dahil, öngörülemeyen davranışlara veya beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki kod, Visual Studio 2015'te derlenir, ancak Visual Studio 2017'de bir hata oluşturur.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>Expression-SFINAE

İfade SFINAE desteği için derleyici artık ayrıştırmak için `decltype` şablonları bildirilen örneği yerine olduğunda bağımsız değişkenler. Decltype bağımsız değişkende bir bağımlı olmayan özelleştirmesi bulunursa, sonuç olarak, bu örnek oluşturma zamanı ertelenir değil. Hemen işlenir ve ortaya çıkan hataları o anda tanı koydu.

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

Şunlara göre C++ standart, anonim bir ad alanı içinde bildirilmiş bir sınıfın iç bağlantısı vardır ve anlamına onu verilemiyor. Bu kural, Visual Studio 2015 ve önceki sürümlerinde, zorunlu değildi. Visual Studio 2017'de bir kural kısmen uygulanır. Aşağıdaki örnek Visual Studio 2017'de bu hata oluşturur: "hatası C2201: const anonim namespace::S1::vftable: dışarı/içeri aktarılmak için dış bağlantıya sahip olması gerekir."

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Varsayılan başlatıcılar değeri için sınıf üyeleri (C++/CLI)

Visual Studio 2015 ve önceki sürümlerinde, derleyici izin verilir (ancak göz ardı) bir değer sınıfının üyesi için varsayılan üye başlatıcıya. Her zaman varsayılan bir değer sınıfının başlatma sıfır-üyeleri başlatır. Varsayılan bir oluşturucu izin değil. Visual Studio 2017'de, bu örnekte gösterildiği gibi varsayılan üye Başlatıcı bir derleyici hatası Yükselt:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Varsayılan dizin oluşturucular (C++/CLI)

Visual Studio 2015 ve önceki sürümlerinde, bazı durumlarda, derleyici varsayılan bir özellik bir varsayılan dizin oluşturucu misidentified. Tanımlayıcısını kullanarak sorunu çözmek mümkün olan `default` özelliğine erişmek için. Çözüm sonra sorunlu hale geldi `default` C ++ 11'de bir anahtar olarak kullanıma sunulmuştur. Visual Studio 2017'de gerekli geçici hatalar düzeltilmiştir ve derleyici artık bir hata oluşturur, `default` bir sınıfının varsayılan özelliğine erişmek için kullanılır.

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

Visual Studio'nun önceki sürümlerinde, derleyicinin bazı durumlarda hatalı oluşturulmuş çağrılar kilitlenmeleri çalışma zamanında neden olabilecek bir silinen üye şablonu için bir hata yaymak başarısız olur. Aşağıdaki kod C2280, artık üretir "'int S\<int >:: f\<int > (void)': silinmiş bir işleve başvurmaya çalışıyor":

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

Hatayı düzeltmek için bildirmek `i` olarak `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Tür özellikleri için ön koşul denetimleri

Visual Studio 2017 sürüm 15.3 daha kesinlikle standarda tür özellikleri için ön koşul denetimleri artırır. Bu tür bir denetimi içindir atanabilir. Aşağıdaki kod, Visual Studio 2017 sürüm 15.3 C2139 üretir:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yönetilen yerel hazırlama üzerinde yeni derleyici uyarı ve çalışma zamanı denetimleri

Yönetilen işlevlerden yerel işlevleri çağırma hazırlama gerektirir. CLR hazırlama desteklemez, ancak bunu anlamıyor C++ semantiği. Yerel bir nesne değeri geçirirseniz, CLR nesnenin Kopyala oluşturucusunu çağırır veya kullanan `BitBlt`, çalışma zamanında davranış tanımsız neden.

Artık, derleme zamanında silinen copy ctor yerel bir nesnesiyle arasında yerel ve yönetilen sınır değeri tarafından geçirilir biliyorsanız, derleyici bir uyarı verir. Böylece programın çağırır, derleyici değil bilmeniz derleme zamanında bu gibi durumlarda, bir çalışma zamanı denetimi eklediği `std::terminate` hemen hatalı oluşturulmuş bir sıralama oluştuğunda. Visual Studio 2017 sürüm 15.3, uyarı C4606 aşağıdaki kodu üretir "'A': yerel ve yönetilen sınırda değere göre bağımsız değişken geçirme, geçerli bir kopya Oluşturucusu gerektirir. Aksi takdirde, çalışma zamanı davranışı tanımsızdır.

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

Hatayı düzeltmek için kaldırma `#pragma managed` çağıran yerel olarak işaretlemek ve hazırlama önlemek için yönergesi.

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

Bir sınıfta bildirilen değildi bir şablon üye işlev satır dışı tanımı karşılaştığında visual Studio 2017 sürüm 15.3, bir hata oluşturur. Aşağıdaki kod hatası C2039 artık oluşturur: 'f': bir üyesi değil. kullanıcının ':

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

### <a name="attempting-to-take-the-address-of-this-pointer"></a>Adresi alınamaz çalışılıyor `this` işaretçi

İçinde C++ `this` işaretçi türüne X bir prvalue olduğu. Adresi alınamaz `this` ya da bir lvalue başvurusuna bağlayabilirsiniz. Visual Studio'nun önceki sürümlerinde, derleyici, bu kısıtlama, bir yayın tarafından kullanımını aşmak çalıştırmasına olanak tanır. Visual Studio 2017 sürüm 15.3, derleyici hatası C2664 oluşturur.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemez bir temel sınıf dönüştürme

Visual Studio 2017 sürüm 15.3, erişilemeyen bir temel sınıf için bir tür dönüştürmeye çalıştığınızda bir hata oluşturur. Derleyici artık başlatır "hatası C2243: 'tür cast': dönüştürme vardı *' için ' B *' var, ancak erişilebilir değil". Aşağıdaki kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Bu kodu karşılaştığında derleyici artık C2243 üretir:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>Varsayılan bağımsız değişkenler üzerinde üye işlevleri satır tanımlarını dışında izin verilmez

Varsayılan bağımsız değişkenleri, şablon sınıflarındaki üye işlevlerin satır dışı tanımları üzerinde izin verilmez. Derleyici bir uyarı verecek **/ permissive**ve bir donanım hatası altında **/ permissive-** .

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

### <a name="use-of-offsetof-with-compound-member-designator"></a>Kullanım `offsetof` bileşik üye göstergesi ile

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

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Kullanarak `offsetof` statik veri üyesine veya üye işlevi

Visual Studio kullanarak 2017 sürüm 15.3, `offsetof(T, m)` burada *m* statik veri üyesine veya üye işlevi bir hata sonuçlarında ifade eder. Aşağıdaki kod üretir "hatası C4597: tanımsız davranış: offsetof 'örneğinde' üye işlevine uygulanan" ve "hatası C4597: tanımsız davranış: 'örnek' statik veri üyesine offsetof uygulandı":

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

Bu kod, hatalı biçimlendirilmiş ve potansiyel olarak çalışma zamanında Çökmeye neden. Hatayı düzeltmek için artık tanımlanmamış davranışı çağırmak için kodu değiştirin. Tarafından izin verilmeyen taşınabilir olmayan kodu C++ standart.

### <a name="declspec"></a> Üzerinde yeni uyarı `__declspec` öznitelikleri

Visual Studio 2017 sürüm 15.3, derleyici artık öznitelikleri yok sayar `__declspec(...)` önce uygulanan `extern "C"` bağlama belirtimi. Daha önce derleyici çalışma zamanı etkileri olabilir özniteliği yok. Zaman **/Wall** ve **wx** seçenekleri ayarlanır, aşağıdaki kodu üretir "C4768 Uyarı: bağlantı belirtiminden önceki __declspec öznitelikleri yoksayılır":

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarıyı çözmek için put `extern "C"` ilk:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Bu uyarı kapalı 15.3, varsayılan olarak, ancak şirket varsayılan 15.5 sürümünde ve yalnızca etkileyen kod ile derlenmiş olan **/Wall** **wx**.

### <a name="decltype-and-calls-to-deleted-destructors"></a>`decltype` ve Silinen yıkıcı çağrıları

Silinen bir yok edici bir çağrı ile ilişkili ifadenin bağlamında gerçekleştiğinde Visual Studio'nun önceki sürümlerinde, derleyici algılamadık `decltype`. Visual Studio 2017 sürüm 15.3, aşağıdaki kod üretir "hatası C2280: \<T >:: ~ A(void)': silinmiş bir işleve başvurmaya çalışıyor ":

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

Visual Studio 2017 RTW sürüm olan bir gerileme, C++ derleyici tanılama Eğer sorun mıydı bir `const` değildi değişkeni başlatılır. Visual Studio 2017 sürüm 15.3 Bu gerileme düzeltildi. Aşağıdaki kod artık üretir "C4132 Uyarı: 'Value': const nesnenin başlatılması gerekir ":

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

Uyarıları kaldırmak için açıklama veya boş bildirimleri. Burada adlandırılmamış nesne (RAII gibi) bir yan etkisi amaçlanmıştır durumlarda, bir ad verilmelidir.

Uyarı altında hariç tutulan **/Wv:18** ve uyarı düzeyi W2 altında varsayılan olarak açıktır.

### <a name="stdisconvertible-for-array-types"></a>`std::is_convertible` dizi türleri için

Önceki derleyici sürümleri için hatalı sonuçlar verdi [std::is_convertible](../standard-library/is-convertible-class.md) dizi türleri için. Bu, özel durum Microsoft kitaplığı yazıcılarının gerekli C++ kullanırken derleyici `std::is_convertible<...>` türü niteliğine. Aşağıdaki örnekte, Visual Studio'nun önceki sürümlerini geçişte statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

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

### <a name="private-destructors-and-stdisconstructible"></a>Özel yok ediciler ve `std::is_constructible`

Bir yok edici sonucunu verirken özel olup olmadığını göz ardı derleyicinin önceki sürümlerini [std::is_constructible](../standard-library/is-constructible-class.md). Artık bunları değerlendirir. Aşağıdaki örnekte, Visual Studio'nun önceki sürümlerini geçişte statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

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

Bazen derleyicinin önceki sürümlerini başarısız her ikisi de aracılığıyla birden fazla adayı bulduğunuzda belirsizlik algılamak bildirimler ve bağımsız değişkene bağlı arama kullanılarak. Bu hata yanlış aşırı yükleme seçildiği ve beklenmeyen çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 C2668 'f' doğru başlatır: aşırı yüklenmiş işleve belirsiz çağrı:

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

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişkene bağlı arama

Yerel işlev bildirimleri, işlev bildirimi kapsayan kapsamda gizleyebilir ve bağımsız değişkene bağlı arama devre dışı bırakın. Ancak, derleyici önceki sürümlerini bağımsız değişkene bağlı arama bu durumda, büyük olasılıkla yanlış aşırı seçildiği ve beklenmeyen çalışma zamanı davranışı için önde gelen gerçekleştirdi. Genellikle, yanlış bir yerel işlev bildiriminin imzasının nedeniyle hatasıdır. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 C2660 'f' doğru başlatır: işlevi iki bağımsız değişken almaz:

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

Sınıf üyeleri, bildirildikleri, sırayla değil Başlatıcı Listeleri göründükleri sırayla başlatılır. Önceki derleyici sürümleri, başlatıcı listesi sırası sırasının bildirim farklıydı uyar kaydetmedi. Başka bir üye zaten başlatılmış listesinde bir üye başlatma bağımlı değilse bu sorun tanımlanmamış çalışma zamanı davranışına neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 (ile **/Wall**) başlatır "uyarısı C5038: veri üyesi 'A::x' 'A::y' başlatılacaktır veri üyesi":

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Sorunu gidermek için bildirimleri aynı sırada olmasını başlatıcı listesi düzenleyin. Bir veya iki başlatıcılar temel sınıf üyelerine başvuru benzer bir uyarı tetiklenir.

Kapalı-varsayılan olarak bu bir uyarıdır ve yalnızca etkiler kod ile derlenmiş olan **/Wall**.

## <a name="update_155"></a> Hata düzeltmeleri ve diğer Visual Studio 2017 sürüm 15.5 davranış değişiklikleri

### <a name="partial-ordering-change"></a>Kısmi değişiklik sıralama

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

### <a name="tr1"></a> `std::tr1` ad alanı kullanım dışıdır

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
warning C4996: 'std::tr1': warning STL4002: The non-standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
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

### <a name="annex_d"></a> Standart kitaplık özellikleri Annex d kullanım dışı olarak işaretlendi

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
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
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

### <a name="single-line-comments"></a>Tek satırlı açıklama

Visual Studio 2017 sürüm 15.5, C4001 ve C4179 uyarılar artık C derleyicisi tarafından gönderilir. Daha önce bunlar yalnızca altında yayılan **/Za** derleyici anahtarı.  Tek satırlı yorumlar, C99 beri C standardının bir parçası olmuştur çünkü uyarıları artık gereklidir.

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

### <a name="declspec-attributes-with-extern-c-linkage"></a>`__declspec` ile öznitelikleri `extern "C"` bağlantı

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

Bu yeni uyarı C4768 ile Visual Studio 2017 15.3 sevk edilen bazı Windows SDK'sı başlıklarında verilen ya da eski (örneğin: sürüm 10.0.15063.0, RS2 SDK olarak da bilinir). Ancak, böylece bunlar uyarı üretmediği sonraki sürümlerinde Windows SDK'sı üst bilgileri (özellikle ShlObj.h ve ShlObj_core.h) düzeltildi. Windows SDK'sı üst bilgileri yakında bu uyarıyı gördüğünüzde, bu eylemleri gerçekleştirebilirsiniz:

1. Visual Studio 2017 sürüm 15.5 sürüm ile birlikte gelen en son Windows SDK geçin.

1. Uyarı geçici olarak devre dışı bırakma # Windows SDK'sı üstbilgi deyiminin include:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>Extern constexpr bağlantı

Visual Studio'nun önceki sürümlerinde, derleyici her zaman verdiğiniz bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15.5, yeni bir derleyici anahtarı ( **/ZC: externconstexpr**) doğru standartlara uyan davranışını etkinleştirir. Sonuçta bu davranışı, varsayılan olur.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Bir üstbilgi dosyası bildirilen bir değişken içeriyorsa `extern constexpr`, işaretlenmesi gerekir `__declspec(selectany)` doğru birleştirilmiş, yinelenen bildirimler için:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>`typeid` Eksik sınıf türü üzerinde kullanılamaz

Visual Studio'nun önceki sürümlerinde, derleyici yanlış potansiyel olarak yanlış tür bilgileri aşağıdaki koddaki izin verilir. Visual Studio 2017 sürüm 15.5, derleyici doğru bir hata oluşturur:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdisconvertible-target-type"></a>`std::is_convertible` Hedef türü

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

### <a name="noexcept_removal"></a> Dinamik özel durum belirtimi kaldırma ve `noexcept`

C ++ 17 ' de `throw()` için bir diğer addır `noexcept`, `throw(<type list>)` ve `throw(...)` kaldırılır, ve belirli türlerini içerebilir `noexcept`. Bu değişiklik, C ++ 14 veya önceki uyan koduyla kaynak uyumluluk sorunlarına neden olabilir. **/Zc:noexceptTypes-** anahtarı, C ++ 14 sürümüne geri almak için kullanılabilir `noexcept` genel C ++ 17 modunda kullanırken. Tüm yeniden yazmak zorunda kalmadan C ++ 17'ye uyması için kaynak kodunuzu güncelleştirmenizi sağlar, `throw()` aynı zamanda kod.

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

Constexpr statik veri üyeleri, bir sınıf içerisinde bildirim artık kendi tanım olduğu anlamına gelir satır içi örtük olarak sunulmuştur. Constexpr statik veri üyesi için satır dışı tanımı kullanarak yedekli ve artık kullanım dışı. Visual Studio 2017 sürüm 15.5, zaman **/Std: c ++ 17** anahtar uygulanan aşağıdaki kodu artık uyarı C5041 üretir *'boyutu': constexpr statik veri üyesi için satır dışı tanımı gerekli değildir ve kullanım dışıdır C ++ 17'de*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)` C4768 şimdi üzerinde varsayılan olarak uyarı

Uyarı, Visual Studio 2017 sürüm 15.3 eklendi, ancak varsayılan olarak kapalı olan. Visual Studio 2017 sürüm 15.5, uyarı varsayılan olarak açıktır. Daha fazla bilgi için [üzerinde yeni uyarı \_ \_declspec öznitelikleri](#declspec).

### <a name="defaulted-functions-and-declspecnothrow"></a>Varsayılan olarak, İşlevler ve `__declspec(nothrow)`

Derleyici, daha önce ile bildirilmesi varsayılan olarak ayarlanan işlevler izin `__declspec(nothrow)` karşılık gelen taban/üye işlevleri özel durumların ne zaman izin verilir. Bu davranış contrary şeklindedir C++ standart ve çalışma zamanında tanımsız davranışa neden olabilir. Standart özel durum belirtimi bir uyuşmazlık varsa silindi olarak tanımlanmış olması için bu tür işlevleri gerektirir.  Altında **/Std: c ++ 17**, aşağıdaki kodu C2280 başlatır *silinmiş bir işleve başvurmaya çalışıyor. Açık özel durum belirtimi, örtük bildirim ile uyumsuz olduğundan işlev örtük olarak silindi.*

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

### <a name="noexcept-and-partial-specializations"></a>`noexcept` ve kısmi uzmanlıklar

İle `noexcept` tür sisteminde eşleşen "çağrılabilir" belirli türler için kısmi uzmanlıkları nedeniyle işaretçiler için noexcept işlevleri için eksik kısmi özelleştirme birincil şablonun seçin ya da derleme başarısız olabilir.

Böyle durumlarda işlemek için ek kısmi uzmanlıklar eklemeniz gerekebilir `noexcept` işlev işaretçileri ve `noexcept` üye işlevlerinin işaretçileri. Bu aşırı yüklemeler yalnızca yasal **/Std: c ++ 17** modu. Geriye doğru uyumluluk C ++ 14 ile saklanabilir ve diğerleri kullanma ve ardından bu yeni aşırı yüklemeler içinde koruyucu kod yazıyorsanız `#ifdef` yönergeleri. Kendi içinde bir modül, ardından kullanmak yerine çalışıyorsanız `#ifdef` yalnızca derleyebileceğiniz ile cf **/Zc:noexceptTypes-** geçin.

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

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++17: Varsayılan bağımsız bir birincil Sınıf şablonunda

Bu davranış değişikliği için önkoşul olduğundan [şablon bağımsız değişkeni kesintisi sınıf şablonları - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html).

Daha önce derleyici varsayılan bağımsız bir birincil Sınıf şablonunda yok sayıldı:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

İçinde **/Std: c ++ 17** değilse Visual Studio 2017 sürüm 15.7, varsayılan bağımsız değişken modunda yoksayıldı:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Bağımlı ad çözümlemesi

Bu davranış değişikliği için önkoşul olduğundan [şablon bağımsız değişkeni kesintisi sınıf şablonları - P0091R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0091r3.html).

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

Visual Studio 2017 sürüm 15.7, içinde **/Std: c ++ 17** modunu gerektirir `typename` anahtar sözcüğünü `using` D. deyiminde Olmadan `typename`, C4346 uyarı derleyici başlatır: *' B < T\*>:: türü ': bağımlı öğe adı bir tür değil* hatası C2061: *söz dizimi hatası: tanımlayıcı 'type'* :

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

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C ++ 17: `[[nodiscard]]` öznitelik - uyarı düzeyini artırın

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

### <a name="constexpr-aggregate-initialization"></a>`constexpr` Toplama başlatma

Önceki sürümlerini C++ yanlış işlenmesine derleyici `constexpr` toplama başlatma; burada toplama başlatma listesi çok fazla öğe vardı ve hatalı codegen için üretilen kabul BT geçersiz kod. Aşağıdaki kod, bu tür bir kod örneğidir:

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

### <a name="typename-on-unqualified-identifiers"></a>`typename` Nitelenmemiş tanımlayıcılarını

İçinde [/ permissive-](../build/reference/permissive-standards-conformance.md) modu, sahte `typename` diğer şablon tanımlarında nitelenmemiş tanımlayıcılar anahtar sözcükleri artık derleyici tarafından kabul edilir. Aşağıdaki kod artık C7511 üretir *'T': 'typename' anahtar sözcüğü, bir tam ad gelmelidir*:

```cpp
template <typename T>
using  X = typename T;
```

Hatayı düzeltmek için ikinci satırın değiştirme `using  X = T;`.

### <a name="declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()` sağ tarafta diğer şablon tanımları

[__declspec](../cpp/declspec.md) sağ tarafında bir diğer ad şablon tanımının artık izin verilir. Bu kod, daha önce kabul edildi, ancak derleyici tarafından yok sayılır ve diğer kullanıldığında hiçbir zaman kullanımdan kaldırılma uyarısı neden olur.

Standart C++ özniteliği [ \[ \[kullanım dışı\] \] ](../cpp/attributes.md) yerine kullanılabilir ve Visual Studio 2017 sürüm 15.6 uyulduğundan. Aşağıdaki kod artık C2760 üretir *söz dizimi hatası: beklenmeyen belirteç '__declspec' beklenen 'türü tanımlayıcısı'* :

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

İki aşamalı ad aramayı bağımlı olmayan adları şablon gövdeleri kullanılan tanımı zaman şablona görünür olmasını gerektirir. Daha önce Microsoft C++ derleyici bir unfound ada örnek oluşturma saat gönderinizi looked bırakın. Şimdi, bağımlı olmayan adları şablon gövdesinde ilişkili gerektirir.

Bu bildirim bir arama bağımlı temel sınıflar ile yoludur. Daha önce bunlar tüm türlerin çözümlenmiş olduğunda oluşturmada süre boyunca aranabilir çünkü derleyici bağımlı temel sınıflarında tanımlanan adları kullanılmasına izin. Artık bu kodu hata kabul edilir. Bu gibi durumlarda, örnek oluşturma zamanında taban sınıf türünde uygun veya aksi halde, örneğin, ekleyerek bağımlı Bakılacak değişkeni zorlayabilirsiniz bir `this->` işaretçi.

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

**Not:** Boost python Kitaplığı'nda olmuştur uzun bir süre için bir şablon iletme bildiriminde bir MSVC özgü geçici çözüm [unwind_type.hpp](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp). Altında [/ permissive-](../build/reference/permissive-standards-conformance.md) Visual Studio 2017 sürüm 15,8 başlangıç modu (_MSC_VER 1915 =), bu geçici çözüm guard yapma ve diğer derleyiciler ile tutarlıdır ve bağımsız değişkene bağlı ad araması (ADL) desteklemez doğru MSVC derleyicisi gereksiz. Hatayı önlemek için *C3861: 'unwind_type': tanımlayıcı bulunamadı*, bkz: [çekme isteği 229](https://github.com/boostorg/python/pull/229) Boost depodaki üstbilgi dosyasını güncelleştirmek için. Biz zaten yama [vcpkg](../build/vcpkg.md) Boost paket, bu nedenle daha sonra almak ya da Boost kaynaklarınızı vcpkg ' yükseltme ayrı olarak düzeltme eki uygulama gerekmez.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>bildirimler ve tanımlar ad alanında ilet `std`

C++ standart iletme bildirimlerine veya tanımlarına ad alanında eklemek bir kullanıcı izin vermeyen `std`. Ad alanına bildirimlerine veya tanımlarına ekleme `std` veya ad alanı içinde bir ad alanına `std` artık tanımsız davranışlara neden olur.

Bazı zaman gelecekteki Microsoft bazı standart kitaplık türleri tanımlandığı konumuna taşınır. Bu değişiklik bildirimleri ad alanına ekler mevcut kodu kesintiye uğratacağını `std`. Yeni bir uyarı C4643, bu tür kaynak sorunlarını belirlemenize yardımcı olur. Uyarı etkin **/varsayılan** modunu ve varsayılan olarak kapalıdır. İle derlenmiş programlar etkiler **/Wall** veya **wx**.

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

C++ Standart önerir temsilci oluşturucusu kendisini yetkilendirir, derleyici bir tanılama yayması. Microsoft C++ derleyicisindeki [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) ve [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md) modları artık C7535 başlatır: *'X::X': temsilci Oluşturucu, çağıran kendisini*.

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

### <a name="offsetof-with-constant-expressions"></a>`offsetof` sabit ifadeler

[offsetof](../c-runtime-library/reference/offsetof-macro.md) gerektiren bir makro kullanarak geleneksel olarak uygulanmıştır bir [reinterpret_cast](../cpp/reinterpret-cast-operator.md). Ancak Microsoft, sabit bir ifade gerektiren bağlamlarda bu kullanım geçersiz C++ derleyici geleneksel izin verdiği bu. `offsetof` Standart kitaplığına doğru bir iç derleyici kullandıkça gönderildiğini makrosu ( **__builtin_offsetof**), ancak çoğu kişi makrosu ux'in kendi tanımlamak için kullanılan `offsetof`.

Visual Studio 2017 sürüm 15,8, derleyici alanları kısıtlar, bunlar `reinterpret_cast` işleçleri standardına uygun kod yardımcı olmak için varsayılan modda görünebilir C++ davranışı. Altında [/ permissive-](../build/reference/permissive-standards-conformance.md), kısıtlamaları taşıyabilmek. Sonucu kullanarak bir `offsetof` uyarı C4644 sorunları sabit ifadeler, kodda sonuçlanabilir gerektiren yerde *sabit ifadeler offsetof makrosu tabanlı desende kullanımını standart; kullanım offsetof tanımlanan C++ Standart Kitaplığı yerine* veya C2975 *geçersiz şablon bağımsız değişkeni, beklenen derleme zamanı sabit ifadesi*.

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

Hatayı düzeltmek için kullanmak `offsetof` aracılığıyla tanımlanan \<cstddef >:

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

Microsoft'ın önceki sürümlerini C++ derleyici yaramadı algılamak da paket genişletmesi tabi olduysa bir temel sınıf cv niteleyicileri vardı.

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

### <a name="template-keyword-and-nested-name-specifiers"></a>`template` anahtar sözcüğü ve iç içe-ad-tanımlayıcıları

İçinde **/ permissive-** modu, derleyici artık gerektirir `template` anahtar sözcüğü, bir şablon adı öncesinde, bir bağımlı iç içe-adı-belirticisinden sonra geldiğinde.

Aşağıdaki kod içinde **/ permissive-** modu şimdi C7510 başlatır: *'örneğinde': bağımlı şablon adı 'şablon' ile önekini almalıdır. Not: sınıf şablonu örneklemesi için bkz ' X<T>' olan derlenmiş*:

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

Hatayı düzeltmek için ekleme `template` anahtar `Base<T>::example<int>();` aşağıdaki örnekte gösterildiği gibi deyimi:

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

- Tüketim tarafında (Main.cpp öğesi) seçeneğini **/ehsc** belirtilmemiş.

- C++ Sürümü **/Std: c ++ 17** oluşturma tarafında ve **/Std: c ++ 14** tüketim tarafında.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Her iki durumda C5050 derleyici başlatır: *C5050 Uyarı: Modülün içeri aktarılması sırasında olası uyumlu ortamı 'M ': C++ sürümleri eşleşmiyor.  Geçerli "201402" Modül sürümü "201703"* .

Derleyici, ayrıca .ifc dosyası ile oynanmış her C7536 başlatır. Modül arabirimi üstbilgisi bir SHA2 karma aşağıdaki içeriği içerir. İçeri aktarma işlemi sırasında .ifc dosya aynı şekilde karma ve üst bilgide sağlanan karma karşılaştırılarak. Bunlar eşleşmiyorsa, hata C7536 ortaya çıkar: *IFC bütünlük denetimi başarısız oldu.  SHA2 bekleniyor: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'* .

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Kısmi sıralama içeren diğer adlar ve atanan bağlamları

Atanan bağlamlarda diğer adları içeren kısmi sıralama kuralları uygulamaları ayırmak. Aşağıdaki örnek, GCC ve Microsoft C++ derleyicisi (içinde **/ permissive-** modu) kodu Clang kabul ederken bir hata oluştur.

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

' Teki bir gerileme nedeniyle uygulama Geçitler olan C++ standart ifadesi. Bu aşırı yüklemeler sıralanmasına izin bazı metin 2235 temel sorun çözümü kaldırıldı. Geçerli C++ standart sunmaz kısmen sırası için bir mekanizma bu işlevler, belirsiz kabul edilmeleri için.

Geçici bir çözüm olarak, kısmi bu sorunu çözmek için sıralamasını kullandığını değil önerilir. Bunun yerine, SFINAE belirli yüklemelerini kaldırmak için kullanın. Aşağıdaki örnekte yardımcı bir sınıf kullandığımız `IsA` kaldırmak için ilk aşırı zaman `Alloc` özelleştirmesi olan `A`:

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

Geçersiz ifadeleri ve sabit olmayan değer türleri artık doğru şekilde açıkça özelleştirilmiş şablonlu işlevleri tanımlarında tanı koydu. Daha önce bu tür hatalar için işlev tanımı yayılan olmayan. Ancak geçersiz ifade veya sabit olmayan değer türü yine de sabit bir ifade bir parçası olarak değerlendirildiğinde tanı koydu.

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

Visual Studio 2017 sürüm 15.9, bu hata kodu oluşturur:

```Output
error C3615: constexpr function 'S<int>::f' cannot result in a constant expression.
note: failure was caused by call of undefined function or one not declared 'constexpr'
note: see usage of 'g'.
```

Hatayı önlemek için kaldırma `constexpr` işlevi açıkça örneğinin gelen niteleyicisi `f()`.

::: moniker-end

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>C++Visual Studio 2015'te uyumluluk geliştirmeleri

Visual Studio 2015 güncelleştirme 3 ile uyumluluk geliştirmeleri tam listesi için bkz. [Visual C++ neler yeni 2003 ile 2015 arasındaki](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ dil uyumluluğu](../visual-cpp-language-conformance.md)
