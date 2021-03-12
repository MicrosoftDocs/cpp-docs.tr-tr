---
title: Visual Studio 2019 ' de C++ uyumluluk geliştirmeleri
description: Visual Studio 'da Microsoft C++, C++ 20 dil standardı ile tam uygunluğu doğru ilerliyor.
ms.date: 03/10/2021
ms.technology: cpp-language
ms.openlocfilehash: 3b78551ee4d8590403cdfaf77c267eef0ab6d811
ms.sourcegitcommit: f8ba5db09d05683b24c58505f0e57c21f85545dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103087265"
---
# <a name="c-conformance-improvements-behavior-changes-and-bug-fixes-in-visual-studio-2019"></a>Visual Studio 2019 ' de C++ uygunluk geliştirmeleri, davranış değişiklikleri ve hata düzeltmeleri

Visual Studio 'da Microsoft C/C++ (MSVC) her sürümde uyumluluk geliştirmeleri ve hata düzeltmeleri yapar. Bu makalede, ana sürüme ve ardından sürüme göre iyileştirmeler listelenmektedir. Belirli bir sürümdeki değişikliklere doğrudan geçmek için **Bu makalede** aşağıdaki listeyi kullanın.

Bu belgede, Visual Studio 2019 'deki değişiklikler listelenir. Visual Studio 2017 ' deki değişikliklere yönelik bir kılavuz için bkz. [Visual studio 2017 ' de C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md). Önceki uyumluluk geliştirmelerinden oluşan kapsamlı bir liste için bkz. yenilikler [2003 ile 2015 arasında Visual C++](../porting/visual-cpp-what-s-new-2003-through-2015.md).

## <a name="conformance-improvements-in-visual-studio-2019-rtw-version-160"></a><a name="improvements_160"></a> Visual Studio 2019 RTW (sürüm 16,0) ile uyumluluk geliştirmeleri

Visual Studio 2019 RTW, Microsoft C++ derleyicisinde aşağıdaki uygunluk geliştirmelerini, hata düzeltmelerini ve davranış değişikliklerini içerir.

> [!NOTE]
> C++ 20 özelliği, **`/std:c++latest`** hem derleyici hem de IntelliSense için, c++ 20 uygulama tamamlanana kadar modunda kullanılabilir. Bu sırada, **`/std:c++20`** derleyici modunu tanıtacağız.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modüller desteği

Modüller artık C++ 20 standardında resmi olarak bulunur. Visual Studio 2017 sürüm 15,9 ' ye geliştirilmiş destek eklenmiştir. Daha fazla bilgi için bkz. [MSVC 2017 sürüm 15,9 Ile C++ modüllerinde daha iyi şablon desteği ve hata algılama](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Toplu türün değiştirilmiş belirtimi

C++ 20 ' de bir toplama türünün belirtimi değişmiştir (bkz. [Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla](https://wg21.link/p1008r1)). Visual Studio 2019 ' de, altında, **`/std:c++latest`** Kullanıcı tarafından tanımlanmış bir oluşturucuya sahip bir sınıf (örneğin, bir Oluşturucu `= default` veya) bir `= delete` toplama değildir. Daha önce, yalnızca Kullanıcı tarafından sunulan oluşturucular bir sınıfın bir toplama olmasını eledi. Bu değişiklik, bu tür türlerin nasıl başlatıladığıyla ilgili daha fazla kısıtlama koyar.

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

Daha önce, MSVC, en üst düzeyin altında eşleşmeyen CV niteleyicilerine sahip bir türden başvurunun doğrudan bağlamasını izin verilir. Bu bağlama, başvuruya göre başvuruda bulunulan düzgün const verileri değişikliğine izin verebilir. Derleyici artık standart tarafından gerekli olduğu gibi geçici bir durum oluşturur. Visual Studio 2017 ' de, aşağıdaki kod uyarılar olmadan derlenir. Visual Studio 2019 ' de, derleyici uyarı C4172 başlatır:

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
    auto p = x.PData(); // C4172 <func:#1 "?PData@X@@QBEABQBXXZ"> returning address of local variable or temporary
}
```

### <a name="reinterpret_cast-from-an-overloaded-function"></a>`reinterpret_cast` aşırı yüklenmiş bir işlevden

İçin bağımsız değişken, **`reinterpret_cast`** aşırı yüklenmiş bir işlevin adresine izin verilen bağlamların değil. Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019, C2440 hatasını oluşturuyor:

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f); // C2440: cannot convert from 'overloaded-function' to 'fp'
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

C++ 14 ' te lambda kapatma türleri değişmez değer değildir. Bu kuralın birincil sonucu bir lambda değişkenine atanmayabilir **`constexpr`** . Aşağıdaki kod, Visual Studio 2017 ' de hata olmadan derlenir, ancak Visual Studio 2019, C2127 hatasını oluşturuyor:

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 'l': illegal initialization of 'constexpr' entity with a non-constant expression
}
```

Hatayı önlemek için, **`constexpr`** niteleyiciyi kaldırın ya da uyumluluk modunu olarak değiştirin **`/std:c++17`** .

### <a name="stdcreate_directory-failure-codes"></a>`std::create_directory` hata kodları

C++ 20 ' den koşullu [P1164](https://wg21.link/p1164r1) uygulandı. Bu `std::create_directory` , hedefin hata durumunda zaten bir dizin olup olmadığını denetlemek için değişir. Daha önce, tüm ERROR_ALREADY_EXISTS türü hataları başarılı oldu-ancak Dizin oluşturulmamış kodlara açıldı.

### `operator<<(std::ostream, nullptr_t)`

Her [LWG 2221](https://cplusplus.github.io/LWG/issue2221), `operator<<(std::ostream, nullptr_t)` akışlara yazma için eklenmiştir **`nullptr`** .

### <a name="more-parallel-algorithms"></a>Daha fazla paralel algoritma

,,,,, Ve ' nin yeni paralel sürümleri `is_sorted` `is_sorted_until` `is_partitioned` `set_difference` `set_intersection` `is_heap` `is_heap_until` .

### <a name="atomic-initialization"></a>Atomik başlatma

[P0883 "atomik başlatma düzeltme"](https://wg21.link/p0883r1) `std::atomic` değeri, varsayılan olarak başlatma yerine içerilen değeri başlatın `T` . Microsoft standart kitaplığı ile Clang/LLVM kullanılırken bu çözüm etkinleştirilir. İşlem sırasında oluşan bir hata için geçici çözüm olarak, Microsoft C++ derleyicisi için şu anda devre dışı bırakılmıştır **`constexpr`** .

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` ve `remove_cvref_t`

`remove_cvref` `remove_cvref_t` [P0550](https://wg21.link/p0550r2)öğesinden ve tür nitelikleri uygulandı. Bunlar, bir türden başvuru ve CV nitelemesini kaldırma işlevleri ve diziler (ve ' nin aksine) olmadan bir türden kaldırır `std::decay` `std::decay_t` .

### <a name="feature-test-macros"></a>Özellik testi makroları

[P0941R2-Feature-test makroları](https://wg21.link/p0941r2) , desteğiyle birlikte tamamlanmıştır `__has_cpp_attribute` . Özellik testi makroları tüm standart modlarda desteklenir.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Kullanıcı tarafından belirtilen oluşturucularla toplamaları yasakla

C++ 20 [P1008R1-Kullanıcı tarafından belirtilen oluşturucularla proyaları toplamalar](https://wg21.link/p1008r1) tamamlanmıştır.

### <a name="reinterpret_cast-in-a-constexpr-function"></a>`reinterpret_cast` bir `constexpr` işlevde

Bir **`reinterpret_cast`** **`constexpr`** işlevde geçersizdir. Microsoft C++ derleyicisi, daha önce **`reinterpret_cast`** yalnızca bir bağlamda kullanıldıysa reddedebilirler **`constexpr`** . Visual Studio 2019 ' de, tüm dil standartları modlarında, derleyici bir işlevin tanımında bir öğesini doğru bir şekilde tanılar **`reinterpret_cast`** **`constexpr`** . Aşağıdaki kod artık C3615 üretir:

```cpp
long long i = 0;
constexpr void f() {
    int* a = reinterpret_cast<int*>(i); // C3615: constexpr function 'f' cannot result in a constant expression
}
```

Hatayı önlemek için, **`constexpr`** işlev bildiriminden değiştiricisini kaldırın.

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>Basic_string Range Oluşturucusu için tanılama doğru

Visual Studio 2019 ' de `basic_string` Aralık Oluşturucusu artık ile derleyici tanılamayı göstermez **`static_cast`** . Aşağıdaki kod, Visual Studio 2017 ' de uyarılar olmadan derlenir ve bu, başlatma sırasında veri kaybına neden olabilir **`wchar_t`** **`char`** `out` :

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end()); // VS2019 C4244: 'argument': conversion from 'wchar_t' to 'const _Elem', possible loss of data.
```

Visual Studio 2019, uyarı C4244 'ı doğru şekilde yükseltir. Uyarıyı önlemek için, `std::string` Aşağıdaki örnekte gösterildiği gibi öğesini başlatabilirsiniz:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>`+=`Veya altına yanlış çağrılar `-=` ve `/clr` `/ZW` artık doğru şekilde algılandı

Visual Studio 2017 ' de, derleyicinin hataları sessizce yoksaymasına ve veya altında geçersiz çağrılar için kod üretmesinin nedeni olan bir hata sunulmuştur **`+=`** **`-=`** **`/clr`** **`/ZW`** . Aşağıdaki kod Visual Studio 2017 ' de hata olmadan derlenir ancak Visual Studio 2019, C2845 hatasını doğru şekilde oluşturuyor:

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // in VS2019 C2845: 'System::String ^': pointer arithmetic not allowed on this type.
}
```

Bu örnekteki hatayı önlemek için, **`+=`** işleci yöntemi ile kullanın `ToString()` : `s += E::e.ToString();` .

### <a name="initializers-for-inline-static-data-members"></a>Satır içi statik veri üyeleri için başlatıcılar

Ve başlatıcıların içindeki geçersiz üye erişimleri **`inline`** **`static constexpr`** artık doğru şekilde algılandı. Aşağıdaki örnek Visual Studio 2017 ' de hatasız derlenir, ancak Visual Studio 2019 ' de **`/std:c++17`** modda hata C2248:

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // VS2019 C2248: cannot access private member declared in class 'X'.
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

Visual Studio 2017 ' de, uyarı C4822 yalnızca derleyici seçeneği **`/w14822`** açıkça ayarlandığında tetiklenir. İle gösterilmez **`/Wall`** . Visual Studio 2019 ' de C4822, bu, açık bir uyarıdır. Bu, **`/Wall`** açıkça ayarlanması gerekmeden altında bulunabilir hale gelir **`/w14822`** .

```cpp
void example()
{
    struct A
        {
            int boo(); // warning C4822: Local class member function doesn't have a body
        };
}
```

### <a name="function-template-bodies-containing-if-constexpr-statements"></a>Deyim içeren işlev şablonu gövdeleri `if constexpr`

Deyimleri içeren şablon işlevi **`if constexpr`** gövdelerinin [`/permissive-`](../build/reference/permissive-standards-conformance.md) ayrıştırılmasındaki bazı denetimler var. Örneğin, Visual Studio 2017 ' de, yalnızca seçenek ayarlanmamışsa, aşağıdaki kod C7510 oluşturur **`/permissive-`** . Visual Studio 2019 ' de, seçenek ayarlandığında de aynı kod hata oluşturuyor **`/permissive-`** :

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510: 'Type': use of dependent type name must be prefixed with 'typename'

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

Aşağıdaki kod hem Visual Studio 2017 15,9 hem de Visual Studio 2019 içinde C7552 üretir:

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {  // C7552: inline assembler is not supported in a lambda

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

**`static_cast`** `std::string` Standart tarafından çağrılmadığı ve yanlışlıkla C4244 daraltma uyarılarını gizlenen bir şekilde kaldırıldı. Artık, bir ' a `std::string::string(const wchar_t*, const wchar_t*)` daraltma hakkında C4244 ' i daha uygun bir şekilde çağırma girişimleri `wchar_t` `char` .

### <a name="various-fixes-for-filesystem-correctness"></a>Doğruluk açısından çeşitli düzeltmeler \<filesystem>

- `std::filesystem::last_write_time`Dizinin son yazma zamanı değiştirilmeye çalışılırken hata düzeltildi.
- `std::filesystem::directory_entry`Oluşturucu artık varolmayan bir hedef yolu sağlandığı zaman bir özel durum oluşturmak yerine başarısız bir sonucu depolar.
- `std::filesystem::create_directory`2 parametreli sürüm, 1 parametreli sürümü çağırmak üzere değiştirilmiştir ve temel alınan `CreateDirectoryExW` işlev `copy_symlink` `existing_p` bir symlink olduğunda kullanılır.
- `std::filesystem::directory_iterator` bozuk bir oluşturmaksızın bulunduğunda artık başarısız olmaz.
- `std::filesystem::space` Artık göreli yolları kabul eder.
- `std::filesystem::path::lexically_relative` , [LWG 3096](https://cplusplus.github.io/LWG/issue3096)olarak bildirilen eğik çizgiler tarafından artık karıştırılmamalıdır.
- İçindeki eğik `CreateSymbolicLinkW` çizgi ile yolları reddetme `std::filesystem::create_symlink`
- `delete`Windows 10 LTSB 1609 ' de var olan, ancak gerçekten dosyaları silmeyen POSIX silme modu işlevine geçici olarak çalıştık.
- `std::boyer_moore_searcher`Ve `std::boyer_moore_horspool_searcher` kopya oluşturucuları ve kopya atama işleçleri artık öğeleri kopyalayamıyorum.

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

- Geliştirilmiş bir IntelliSense deneyimi için birçok standart kitaplık iç kapsayıcı işlevleri yapılmıştır `private` . MSVC 'in sonraki sürümlerinde üyeleri beklenen şekilde işaretlemek için daha fazla düzeltme `private` .

- , Ve gibi düğüm tabanlı kapsayıcılara neden olan özel durum güvenliği doğruluk sorunlarını düzelttik `list` `map` `unordered_map` . `propagate_on_container_copy_assignment`Veya `propagate_on_container_move_assignment` yeniden atama işlemi sırasında, kapsayıcının Sentinel düğümünü eski ayırıcıyla boşalttık, eski ayırıcı üzerinde POCCA/POCMA atamasını yapar ve ardından yeni ayırıcıdan Sentinel düğümünü edinmeye çalışırsınız. Bu ayırma başarısız olduysa, kapsayıcı bozulmuştur. Bir Sentinel düğümü sabit bir veri yapısı sabiti olduğu için bile yok edilmez. Bu kod, mevcut Sentinel düğümünü yok etmeden önce kaynak kapsayıcısının ayırıcıyı kullanarak yeni Sentinel düğümünü oluşturmak için düzeltildi.

- Kapsayıcılar, `propagate_on_container_copy_assignment` `propagate_on_container_move_assignment` `propagate_on_container_swap` belirtilen ayrıcılar için bile, ve ' a göre ayırıcıları her zaman kopyalamak/taşımak/değiştirmek için düzeltildi `is_always_equal` .

- Kapsayıcı birleştirme için aşırı yüklemeler eklendi ve rvalue kapsayıcılarını kabul eden üye işlevleri ayıklayın. Daha fazla bilgi için bkz. [P0083 "splicing Maps and Sets"](https://wg21.link/p0083r3)

### <a name="stdbasic_istreamread-processing-of-rn-n"></a>`std::basic_istream::read``\r\n`` =>`\n ' işleniyor

`std::basic_istream::read` , işlenmek üzere bir parçası olarak sağlanan arabelleğin bölümlerine geçici olarak yazılmadığından düzeltildi `\r\n` `\n` . Bu değişiklik, Visual Studio 2017 15,8 ' de en fazla 4K boyutunda daha büyük okumalar için kazanılan performans avantajlarından bazılarını sağlar. Bununla birlikte, karakter başına üç sanal çağrının önünden kaçınmanın verimlilik geliştirmeleri hala mevcuttur.

### <a name="stdbitset-constructor"></a>`std::bitset` constructor

`std::bitset`Oluşturucu artık büyük bit kümelerine ait olanları ve sıfırları ters sırayla okumamaktadır.

### <a name="stdpairoperator-regression"></a>`std::pair::operator=` regresyon

`std::pair`Atama işlecinde, [lwg 2729 "eksık SFINAE on `std::pair::operator=` "; üzerinde](https://cplusplus.github.io/LWG/issue2729)tanıtılan bir gerileme düzeltildi. Artık, ' a dönüştürülebilir türleri doğru şekilde kabul eder `std::pair` .

### <a name="non-deduced-contexts-for-add_const_t"></a>İçin çıkarılamayan bağlamlar `add_const_t`

Küçük tür nitelikleri hatası düzeltildi, burada `add_const_t` ve ilgili işlevlerin çıkarılamayan bir bağlam olması gerekir. Diğer bir deyişle, `add_const_t` için bir diğer ad olmalıdır `typename add_const<T>::type` `const T` .

## <a name="conformance-improvements-in-161"></a><a name="improvements_161"></a> 16,1 sürümündeki uyumluluk geliştirmeleri

### <a name="char8_t"></a>char8_t

[P0482r6](https://wg21.link/p0482r6). C++ 20, UTF-8 kod birimlerini temsil etmek için kullanılan yeni bir karakter türü ekler. `u8` C++ 20 ' deki dize sabit değerleri `const char8_t[N]` , yerine `const char[N]` , daha önce gelen bir durumdur. [N2231](https://wg14.link/n2231)içinde C standardı için benzer değişiklikler önerilir. **`char8_t`** Geriye dönük uyumluluk düzeltme için öneriler [P1423r3](https://wg21.link/p1423r3)içinde verilmiştir. Microsoft C++ derleyicisi, **`char8_t`** derleyici seçeneğini belirttiğinizde Visual Studio 2019 sürüm 16,1 ' de destek ekler **`/Zc:char8_t`** . Gelecekte, [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) aracılığıyla c++ 17 davranışına geri döndürülebilmesi ile desteklenecektir **`/Zc:char8_t-`** . IntelliSense 'i destekleyen EDG derleyicisi henüz desteklememektedir. Yalnızca gerçek derlemeyi etkilemeyen hataların yalnızca IntelliSense 'e sahip olduğunu görebilirsiniz.

#### <a name="example"></a>Örnek

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>`std::type_identity` programlayıcılarına ve `std::identity` Function nesnesi

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

Visual Studio 2017 ' de, bu kod uyarılar olmadan derlenir, ancak Visual Studio 2019 ' de hata C2760 hatası veriyor:

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t; // C2760 syntax error: unexpected token 'identifier', expected ';'
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

**`constexpr`** işlevler, **`noexcept`** sabit bir ifadede kullanıldığında artık varsayılan olarak değerlendirilmez. Bu davranış değişikliği, çekirdek çalışma grubu 'nun (CWG) [1351](https://wg21.link/cwg1351) çözümlenerek ' de etkinleştirilir [`/permissive-`](../build/reference/permissive-standards-conformance.md) . Aşağıdaki örnek Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' te C2338 üretir:

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

Uyarıyı önlemek için, [`static_cast`](../cpp/static-cast-operator.md) ikinci işleneni dönüştürmek üzere kullanın:

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

Uyarıyı önlemek için, [`static_cast`](../cpp/static-cast-operator.md) ikinci işleneni dönüştürmek üzere kullanın:

```cpp
enum E1 { a };
int main() {
   double i = static_cast<int>(a) * 1.1;
}
```

### <a name="equality-and-relational-comparisons-of-arrays"></a>Dizilerin eşitlik ve ilişkisel karşılaştırmaları

Dizi türünün iki işleneni arasındaki eşitlik ve ilişkisel karşılaştırmalar, C++ 20 ' de ([P1120R0](https://wg21.link/p1120r0)) kullanım dışıdır. Diğer bir deyişle, iki dizi arasındaki karşılaştırma işlemi (derece ve kapsam benzerlikleri) artık bir uyarıdır. Visual Studio 2019 sürüm 16,2 ' den başlayarak, derleyici seçeneği etkinleştirildiğinde aşağıdaki kod C5056 üretir [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) :

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (a == b) { return 1; } // warning C5056: operator '==': deprecated for array types
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

İki dizinin içeriğinin eşit olup olmadığını anlamak için [`std::equal`](../standard-library/algorithm-functions.md#equal) işlevini kullanın:

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
  return lhs == rhs; // error C2676
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs; // error C2676
}
```

Hatayı önlemek için, `operator==` Varsayılan olarak tanımlayın veya bildirin:

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
- [P0020R6](https://wg21.link/p0020r6): `atomic<float>` , `atomic<double>` , `atomic<long double>`
- [P0463R1](https://wg21.link/p0463r1): endian
- [P0482R6](https://wg21.link/p0482r6): Için kitaplık desteği `char8_t`
- [P0600R1](https://wg21.link/p0600r1): `[[nodiscard]]` STL, 1. bölüm için
- [P0653R2](https://wg21.link/p0653r2): `to_address()`
- [P0754R2](https://wg21.link/p0754r2): \<version>
- [P0771R1](https://wg21.link/p0771r1): `noexcept` for the `std::function` Move Oluşturucusu

### <a name="const-comparators-for-associative-containers"></a>İlişkilendirilebilir kapsayıcılar için const Karşılaştırıcılar

,, Ve içinde arama ve ekleme için kod [`set`](../standard-library/set-class.md) , [`map`](../standard-library/map-class.md) [`multiset`](../standard-library/multiset-class.md) [`multimap`](../standard-library/multimap-class.md) daha az kod boyutu için birleştirildi. Ekleme işlemleri artık **`const`** , arama işlemlerinin daha önce yapıldığı şekilde, bir karşılaştırma funından daha az karşılaştırmayı çağırır. Aşağıdaki kod, Visual Studio 2019 sürüm 16,1 ve önceki sürümlerde derlenir, ancak Visual Studio 2019 sürüm 16,2 ' C3848 yükseltir:

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

## <a name="conformance-improvements-in-visual-studio-2019-version-163"></a><a name="improvements_163"></a> Visual Studio 2019 sürüm 16,3 ' de uyumluluk geliştirmeleri

### <a name="stream-extraction-operators-for-char-removed"></a>Kaldırılan için akış ayıklama işleçleri `char*`

Karakterlere işaretçi için akış ayıklama işleçleri kaldırıldı ve karakter dizisi ( [P0487R1](https://wg21.link/p0487r1)başına) için ayıklama işleçleri tarafından değiştirildi. WG21 kaldırılan aşırı yüklemeleri güvensiz kabul eder. [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md)Modda aşağıdaki örnek artık C2679 üretir:

```cpp
// stream_extraction.cpp
// compile by using: cl /std:c++latest stream_extraction.cpp

#include <iostream>
#include <iomanip>

int main() {
    char x[42];
    char* p = x;
    std::cin >> std::setw(42);
    std::cin >> p;  // C2679: binary '>>': no operator found which takes a right-hand operand of type 'char *' (or there is no acceptable conversion)
}
```

Hatayı önlemek için, ayıklama işlecini bir değişkenle birlikte kullanın `char[]` :

```cpp
#include <iostream>
#include <iomanip>

int main() {
    char x[42];
    std::cin >> std::setw(42);
    std::cin >> x;  // OK
}
```

### <a name="new-keywords-requires-and-concept"></a>Yeni anahtar sözcükler `requires` ve `concept`

Yeni anahtar sözcükler **`requires`** ve **`concept`** Microsoft C++ derleyicisine eklenmiştir. Modda bir tanımlayıcı olarak birini kullanmayı denerseniz [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) , derleyici C2059: "sözdizimi hatası" olarak yükseltir.

### <a name="constructors-as-type-names-disallowed"></a>Tür adları olarak oluşturucular izin verilmiyor

Derleyici artık Oluşturucu adlarını bu durumda eklenen sınıf adları olarak kabul eder: bir sınıf şablonu özelleştirmesine bir diğer addan sonra tam ad halinde görüntülendiklerinde. Daha önce, oluşturucular diğer varlıkları bildirmek için bir tür adı olarak kullanılabilir. Aşağıdaki örnek artık C3646 üretir:

```cpp
#include <chrono>

class Foo {
   std::chrono::milliseconds::duration TotalDuration{}; // C3646: 'TotalDuration': unknown override specifier
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

Bir **`extern "C"`** işlev farklı ad alanlarında bildirilirse, Microsoft C++ derleyicisinin önceki sürümleri bildirimlerin uyumlu olup olmadığını denetmedi. Visual Studio 2019 sürüm 16,3 ' den başlayarak, derleyici uyumluluğu denetler. [`/permissive-`](../build/reference/permissive-standards-conformance.md)Modunda, aşağıdaki kod C2371 ve C2733 hatalarını üretir:

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
    // C2116: 'N::f': function parameter lists do not match between declarations
    // C2733: 'f': you cannot overload a function with 'extern "C"' linkage
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

Derleyici artık olmayan bir dönüş türü içeriyorsa kullanarak ifadeleri yeniden yazar `operator==` **`bool`** . Aşağıdaki kod artık C2088 hatasını veriyor:

```cpp
struct U {
    operator bool() const;
};

struct S {
    U operator==(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;  // C2088: '!=': illegal for struct
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

Derleyici artık birleşim benzeri bir sınıfın üyesiyse, varsayılan olarak bir karşılaştırma işleci tanımlamıyor. Aşağıdaki örnek şimdi hata C2120 oluşturuyor:

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

Sınıf bir başvuru üyesi içeriyorsa, derleyici artık varsayılan olarak bir karşılaştırma işleci tanımlamaz. Aşağıdaki kod artık C2120 hatasını veriyor:

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
error LNK2019: unresolved external symbol "public: static int S<char>::a" (?a@?$S@D@@2HA) referenced in function _main at link time.
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

### <a name="import-and-module-keywords-are-context-dependent"></a>`import` ve `module` anahtar sözcükler bağlama bağımlıdır

[P1857R1](https://wg21.link/P1857R1)başına `import` ve `module` Önişlemci yönergelerinin sözdizimi hakkında yeni kısıtlamalar vardır. Bu örnek artık derlenmezse:

```cpp
import // Invalid
m;     // error C2146: syntax error: missing ';' before identifier 'm'
```

Sorunu çözmek için içeri aktarma işlemi aynı satırda kalsın:

```cpp
import m; // OK
```

### <a name="removal-of-stdweak_equality-and-stdstrong_equality"></a>`std::weak_equality`Ve ' nin kaldırılması`std::strong_equality`

[P1959R0](https://wg21.link/P1959R0) birleştirmesi, derleyicisinin ve türlerine yönelik davranışı ve başvuruları kaldırmasını gerektirir `std::weak_equality` `std::strong_equality` .

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

Bu değişiklik derleyici hatalarına neden olabilir. Örneğin, daha önce `pow(complex<float>, int)` bir ile çarpmanız gerekir **`float`** . `complex<T> operator*`Aynı türde bağımsız değişkenleri beklediği için aşağıdaki örnek artık derleyici hatası C2676 yayar:

```cpp
// pow_error.cpp
// compile by using: cl /EHsc /nologo /W4 pow_error.cpp
#include <complex>

int main() {
    std::complex<float> cf(2.0f, 0.0f);
    (void) (std::pow(cf, -1) * 3.0f);
}
```

```Output
pow_error.cpp(7): error C2676: binary '*': 'std::complex<double>' does not define this operator or a conversion to a type acceptable to the predefined operator
```

Birçok olası düzeltme vardır:

- **`float`** Çoğulun türünü ve ile değiştirin **`double`** . Bu bağımsız değişken `complex<double>` , tarafından döndürülen türle eşleşecek şekilde doğrudan öğesine dönüştürülebilir `pow` .

- Sonucunu `pow` söyleyerek olarak daraltın `complex<float>` `complex<float>{pow(ARG, ARG)}` . Daha sonra bir değerle çarparak devam edebilirsiniz **`float`** .

- **`float`** Yerine olarak geçirin **`int`** `pow` . Bu işlem daha yavaş olabilir.

- Bazı durumlarda tamamen kaçınabilirsiniz `pow` . Örneğin, `pow(cf, -1)` bölüm ile değiştirilebilir.

### <a name="switch-related-warnings-for-c"></a>C için anahtarla ilgili uyarılar

Visual Studio 2019 sürüm 16,6 ' den başlayarak, derleyici C olarak derlenen kod için önceden varolan C++ uyarılarını uygular. Şu uyarılar artık farklı düzeylerde etkinleştirilmiştir: C4060, C4061, C4062, C4063, C4064, C4065, C4808 ve C4809. Uyarılar C4065 ve C4060, C 'de varsayılan olarak devre dışıdır.

Eksik **`case`** deyimler, tanımsız **`enum`** ve hatalı **`bool`** anahtarlar (yani çok fazla durum içeren) üzerinde uyarılar tetiklenir. Örnek:

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

### <a name="is-trivially-copyable-definition"></a>daha *düşük bir kopyalanabilir* tanımı

C++ 20 ' nin tanımı, *üç aylık kopyalanabilir olarak* değiştirildi. Bir sınıfta tam tür olan statik olmayan bir veri üyesi olduğunda **`volatile`** , bu, derleyicinin ürettiği kopyalama veya taşıma oluşturucusunun ya da kopyalama ya da taşıma işlecinin önemsiz olmayan bir kopyasına sahip olduğu anlamına gelir. C++ standart Komitesi bu değişikliği bir hata raporu olarak daha etkin bir şekilde uyguladı. MSVC ' de, derleyici davranışı veya gibi farklı dil modlarında değişmez **`/std:c++14`** **`/std:c++latest`** .

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

```Output
warning C5220: `'S::m': a non-static data member with a volatile qualified type no longer implies that compiler generated copy/move constructors and copy/move assignment operators are non trivial`
```

### <a name="pointer-to-member-and-string-literal-conversions-to-bool-are-narrowing"></a>İşaretçiden üyeye ve dize değişmez değer dönüştürmeleri `bool` daraltımı

C++ standart Komitesi, son zamanlarda [](https://wg21.link/p1957r2) `T*` **`bool`** bir daraltma dönüştürmesi olarak Niteyen hata raporu P1957R2. MSVC, bir hatayı daha önce daraltma olarak tanılayan, `T*` **`bool`** ancak bir dize sabit değerinin **`bool`** veya bir üyeye işaretçiden üyeye dönüştürülmesini tanılamamıştı **`bool`** .

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

C++ 11 ' de, **`nullptr`** yalnızca **`bool`** *doğrudan dönüştürme* olarak dönüştürülebilir; Örneğin, bir **`bool`** örgü Başlatıcı listesi kullanarak bir başlattığınızda. Bu kısıtlama hiçbir şekilde MSVC tarafından zorlanmaz. MSVC artık kuralı uygular [`/permissive-`](../build/reference/permissive-standards-conformance.md) . Örtük dönüştürmeler artık hatalı biçimlendirilmiş olarak tanılanıyor. Öğesine bağlama dönüştürmeye **`bool`** hala izin verilir, çünkü doğrudan başlatma `bool b(nullptr)` geçerli olur.

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

Bu program daha önce hatalı bir şekilde derlenmiş ve bağlanmış, ancak şimdi hata C7631 yayacaktır.

```Output
error C7631: '`anonymous-namespace'::x': variable with internal linkage declared but not defined
```

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

## <a name="conformance-improvements-in-visual-studio-2019-version-168"></a><a name="improvements_168"></a> Visual Studio 2019 sürüm 16,8 ' de uyumluluk geliştirmeleri

### <a name="class-rvalue-used-as-lvalue-extension"></a>' Sınıf rvalue değeri lvalue olarak kullanıldı ' uzantısı

MSVC, bir lvalue olarak bir rvalue sınıfı kullanılmasına izin veren bir uzantıya sahiptir. Uzantı, rvalue sınıfının ömrünü genişletmez ve çalışma zamanında tanımsız davranışa yol açabilir. Şimdi standart kuralı uyguladık ve bu uzantıya izin vermeiyoruz **`/permissive-`** .
**`/permissive-`** Henüz kullanmıyorsanız, **`/we4238`** uzantıya açıkça izin vermek için kullanabilirsiniz. Aşağıda bir örnek verilmiştir:

```cpp
// Compiling with /permissive- now gives:
// error C2102: '&' requires l-value
struct S {};

S f();

void g()
{
    auto p1 = &(f()); // The temporary returned by 'f' is destructed after this statement. So 'p1' points to an invalid object.

    const auto &r = f(); // This extends the lifetime of the temporary returned by 'f'
    auto p2 = &r; // 'p2' points to a valid object
}
```

### <a name="explicit-specialization-in-non-namespace-scope-extension"></a>' Ad alanı olmayan kapsamda açık özelleştirme ' uzantısı

MSVC, ad alanı olmayan kapsamda açık özelleşmeye izin veren bir uzantıya sahipti. CWG 727 çözümlendikten sonra artık standart bir parçasıdır. Ancak, davranış farklılıkları vardır. Standart ile hizalamak için derleyicimizin davranışını ayarladık.

```cpp
// Compiling with 'cl a.cpp b.cpp /permissive-' now gives:
//   error LNK2005: "public: void __thiscall S::f<int>(int)" (??$f@H@S@@QAEXH@Z) already defined in a.obj
// To fix the linker error,
// 1. Mark the explicit specialization with 'inline' explicitly. Or,
// 2. Move its definition to a source file.

// common.h
struct S {
    template<typename T> void f(T);
    template<> void f(int);
};

// This explicit specialization is implicitly inline in the default mode.
template<> void S::f(int) {}

// a.cpp
#include "common.h"

int main() {}

// b.cpp
#include "common.h"
```

### <a name="checking-for-abstract-class-types"></a>Soyut sınıf türleri denetleniyor

C++ 20 standardı, bir soyut sınıf türünün işlev parametresi olarak kullanımını algılamak için işlem derleyicilerinin kullanımını değiştirdi. Özellikle, artık bir SFıNAE hatası değildir. Daha önce, derleyici bir işlev şablonunun bir özelleştirmesi bir işlev parametresi olarak soyut sınıf türü örneğine sahip olacağını algıladıysa, bu özelleştirme hatalı biçimlendirilmiş olarak değerlendirilir. Bu, uygulanabilir aday işlevler kümesine eklenmez. C++ 20 ' de, bir soyut sınıf türü parametresi için denetim, işlev çağrılana kadar gerçekleşmez. Bu efekt, derleme için kullanılan kod bir hataya neden olmaz. Aşağıda bir örnek verilmiştir:

```cpp
class Node {
public:
    int index() const;
};

class String : public Node {
public:
    virtual int size() const = 0;
};

class Identifier : public Node {
public:
    const String& string() const;
};

template<typename T>
int compare(T x, T y)
{
    return x < y ? -1 : (x > y ? 1 : 0);
}

int compare(const Node& x, const Node& y)
{
    return compare(x.index(), y.index());
}

int f(const Identifier& x, const String& y)
{
    return compare(x.string(), y);
}
```

Daha önce, için çağrısı, `compare` `compare` `String` için bir şablon bağımsız değişkeni kullanarak işlev şablonunu özelleştirecek şekilde denenir `T` . Soyut bir sınıf olduğundan, geçerli bir özelleştirme oluşturması başarısız olur `String` . Yalnızca uygulanabilir aday olacaktır `compare(const Node&, const Node&)` . Ancak, C++ 20 ' nin altında, işlev çağrılana kadar soyut sınıf türü denetimi gerçekleşmez. Bu nedenle, `compare(String, String)` özelleşme, önemli adaylar kümesine eklenir ve ' den ' e dönüştürme, ' dan ' `const String&` a dönüştürme `String` işleminden daha iyi bir dönüştürme sırası olduğundan en iyi aday olarak seçilir `const String&` `const Node&` .

C++ 20 ' nin altında Bu örnek için olası bir çözüm kavramlardır; diğer bir deyişle, öğesinin tanımını `compare` olarak değiştirin:

```cpp
template<typename T>
int compare(T x, T y) requires !std::is_abstract_v<T>
{
    return x < y ? -1 : (x > y ? 1 : 0);
}
```

Ya da, C++ kavramları kullanılamıyorsa, SFINAE ' ye geri dönebiliyor:

```cpp
template<typename T, std::enable_if_t<!std::is_abstract_v<T>, int> = 0>
int compare(T x, T y)
{
    return x < y ? -1 : (x > y ? 1 : 0);
}
```

### <a name="support-for-p0960r3---allow-initializing-aggregates-from-a-parenthesized-list-of-values"></a>P0960R3 için destek-parantez içine alınmış değerler listesinden toplamalar başlatmaya izin ver

C++ 20 [P0960R3](https://wg21.link/P0960R3) , parantez içine alınmış Başlatıcı listesi kullanarak bir toplama başlatma desteği ekler. Örneğin, aşağıdaki kod C++ 20 ' de geçerlidir:

```cpp
struct S {
    int i;
    int j;
};

S s(1, 2);
```

Bu özelliğin çoğu eklenebilir, diğer bir deyişle, daha önce derlenmeyen kod artık derlenir. Ancak, davranışını değiştirir `std::is_constructible` . C++ 17 modunda bu **`static_assert`** başarısız olur, ancak c++ 20 modunda başarılı olur:

```cpp
static_assert(std::is_constructible_v<S, int, int>, "Assertion failed!");
```

Bu Type-nitelik, aşırı yükleme çözümlemesi denetimi için kullanırsanız, C++ 17 ile C++ 20 arasındaki davranış değişikliğine yol açabilir.

### <a name="overload-resolution-involving-function-templates"></a>İşlev şablonları içeren aşırı yükleme çözümlemesi

Daha önce derleyici, derlenmemelidir bölümünde bazı kodların derlenmesine izin verilir **`/permissive-`** . Bu efekt, derleyici, çalışma zamanı davranışındaki bir değişikliğe yanlış işlev lideri olarak çağırdı:

```cpp
int f(int);

namespace N
{
    using ::f;
    template<typename T>
    T f(T);
}

template<typename T>
void g(T&& t)
{
}

void h()
{
    using namespace N;
    g(f);
}
```

Çağrısı `g` iki işlev içeren bir aşırı yükleme kümesi kullanır `::f` ve `N::f` . `N::f`Bir işlev şablonu olduğundan, derleyici işlev bağımsız değişkenini *çıkarılamayan bir bağlam* olarak kabul etmelidir. Bu durumda, `g` derleyici şablon parametresi için bir tür belirleyemediği için çağrısının başarısız olması gerektiğini gösterir `T` . Ne yazık ki derleyici, `::f` işlev çağrısı için iyi bir eşleşme olduğuna karar verdi. Bir hata yaymanın yerine, derleyici `g` bağımsız değişken olarak kullanarak çağırmak için kod üretir `::f` .

`::f`İşlevin bağımsız değişkeni olarak kullanıldığı birçok durumda, kullanıcının beklediği şeydir, yalnızca kod ile derlendiyse bir hata sunuyoruz **`/permissive-`** .

### <a name="migrating-from-await-to-c20-coroutines"></a>`/await`C++ 20 eş 'e geçiş

Standart C++ 20 eş değerleri artık altında varsayılan olarak üzerinde yapılır **`/std:c++latest`** . Bunlar, anahtar altındaki destekten ve bu uygulamalardan farklıdır **`/await`** . ' Den **`/await`** Standart eş ve arasında geçiş yapmak bazı kaynak değişiklikleri gerektirebilir.

#### <a name="non-standard-keywords"></a>Standart olmayan anahtar sözcükler

Eski **`await`** ve **`yield`** anahtar sözcükler c++ 20 modunda desteklenmez. Kod **`co_await`** , yerine kullanılmalıdır **`co_yield`** . Standart mod aynı zamanda bir eş yordamın kullanılmasına izin vermez `return` . **`return`** Bir eş yordamın her birinde kullanması gerekir **`co_return`** .

```cpp
// /await
task f_legacy() {
    ...
    await g();
    return n;
}
// /std:c++latest
task f() {
    ...
    co_await g();
    co_return n;
}
```

#### <a name="types-of-initial_suspendfinal_suspend"></a>İnitial_suspend/final_suspend türleri

' In altında **`/await`** , Promise INITIAL ve askıya alma işlevleri döndürülen olarak bildirilemez **`bool`** . Bu davranış standart değildir. C++ 20 ' de, bu işlevlerin genellikle önemsiz bir tür bir sınıf türü döndürmesi gerekir: `std::suspend_always` işlev daha önce döndürülürse **`true`** veya `std::suspend_never` döndürülürse **`false`** .

```cpp
// /await
struct promise_type_legacy {
    bool initial_suspend() noexcept { return false; }
    bool final_suspend() noexcept { return true; }
    ...
};

// /std:c++latest
struct promise_type {
    auto initial_susepend() noexcept { return std::suspend_never{}; }
    auto final_suspend() noexcept { return std::suspend_always{}; }
    ...
};
```

#### <a name="type-of-yield_value"></a>Türü `yield_value`

C++ 20 ' de promise `yield_value` işlevinin bir awasever döndürmesi gerekir. **`/await`** Modunda, `yield_value` işlevin döndürmesine izin verildi **`void`** ve her zaman askıya alır. Bu tür işlevler, döndüren bir işlevle değiştirilebilir `std::suspend_always` .

```cpp
// /await
struct promise_type_legacy {
    ...
    void yield_value(int x) { next = x; };
};

// /std:c++latest
struct promise_type {
    ...
    auto yield_value(int x) { next = x; return std::suspend_always{}; }
};
```

#### <a name="exception-handling-function"></a>Özel durum işleme işlevi

**`/await`** özel durum işleme işlevi olmayan bir Promise türünü ya da ' i alan adlı bir özel durum işleme işlevini destekler `set_exception` `std::exception_ptr` . C++ 20 ' de Promise türü, bağımsız değişken alan adlı bir işleve sahip olmalıdır `unhandled_exception` . Özel durum nesnesi, gerektiğinde adresinden elde edilebilir `std::current_exception` .

```cpp
// /await
struct promise_type_legacy {
    void set_exception(std::exception_ptr e) { saved_exception = e; }
    ...
};
// /std:c++latest
struct promise_type {
    void unhandled_exception() { saved_exception = std::current_exception(); }
    ...
};
```

#### <a name="deduced-return-types-of-coroutines-not-supported"></a>Çıkarılan dönüş türleri desteklenmiyor

C++ 20, gibi bir yer tutucu türü içeren bir dönüş türü ile eş yordamları desteklemez **`auto`** . Eş yordamın dönüş türleri açıkça bildirilmelidir. Altında **`/await`** , bu çıkarılan türler her zaman deneysel bir tür içerir ve gerekli türü tanımlayan bir üst bilginin eklenmesini gerektirir: `std::experimental::task<T>` ,, `std::experimental::generator<T>` veya `std::experimental::async_stream<T>` .

```cpp
// /await
auto my_generator() {
    ...
    co_yield next;
};

// /std:c++latest
#include <experimental/generator>
std::experimental::generator<int> my_generator() {
    ...
    co_yield next;
};
```

#### <a name="return-type-of-return_value"></a>Dönüş türü `return_value`

Promise işlevinin dönüş türü olmalıdır `return_value` **`void`** . **`/await`** Modunda, dönüş türü herhangi bir şey olabilir ve yok sayılır. Bu tanılama, yazarın dönüş değerini `return_value` bir çağırana geri döndürüldüğünde ne zaman yanlış varsaydığı gibi hafif hataları tespit etmenize yardımcı olabilir.

```cpp
// /await
struct promise_type_legacy {
    ...
    int return_value(int x) { return x; } // incorrect, the return value of this function is unused and the value is lost.
};

// /std:c++latest
struct promise_type {
    ...
    void return_value(int x) { value = x; }; // save return value
};
```

#### <a name="return-object-conversion-behavior"></a>Nesne dönüştürme davranışını döndür

Bir eş yordamın belirtilen dönüş türü Promise işlevinin dönüş türüyle eşleşmiyorsa `get_return_object` , öğesinden döndürülen nesne `get_return_object` eş yordamın dönüş türüne dönüştürülür. Bu dönüştürme, altında, **`/await`** eş yordam olamaz gövdesinin yürütme şansı olmadan önce erken yapılır. **`/std:c++latest`**' De, bu dönüştürme değeri çağırana döndürüldüğünde yapılır. Eş metin gövdesinin içinden döndürülen nesneyi kullanmasını sağlamak için ilk askıya alma noktasında askıya olmayan eş değerleri sağlar `get_return_object` .

#### <a name="coroutine-promise-parameters"></a>Coroutine Promise parametreleri

C++ 20 ' de, derleyici eş yordam olamaz parametrelerini (varsa) Promise türünün oluşturucusuna geçirmeye çalışır. Başarısız olursa, varsayılan bir Oluşturucu ile yeniden dener. **`/await`** Modunda, yalnızca varsayılan Oluşturucu kullanıldı. Taahhütde birden çok Oluşturucu varsa, bu değişiklik davranış farklılığı oluşmasına neden olabilir. Ya da bir eş yordam olamaz parametresinden Promise türüne dönüştürme varsa.

```cpp
struct coro {
    struct promise_type {
        promise_type() { ... }
        promise_type(int x) { ... }
        ...
    };
};

coro f1(int x);

// Under /await the promise gets constructed using the default constructor.
// Under /std:c++latest the promise gets constructed using the 1-argument constructor.
f1(0);

struct Object {
template <typename T> operator T() { ... } // Converts to anything!
};

coro f2(Object o);

// Under /await the promise gets constructed using the default constructor
// Under /std:c++latest the promise gets copy- or move-constructed from the result of
// Object::operator coro::promise_type().
f2(Object{});
```

### <a name="permissive--and-c20-modules-are-on-by-default-under-stdclatest"></a>`/permissive-` ve C++ 20 modülleri, varsayılan olarak `/std:c++latest`

C++ 20 modülleri desteği varsayılan olarak ' ın altında bulunur **`/std:c++latest`** . Bu değişiklik hakkında daha fazla bilgi ve **`module`** ve **`import`** koşullu anahtar sözcük olarak kabul edilen senaryolar hakkında daha fazla bilgi için bkz. [Visual Studio 2019 sürüm 16,8 ' de MSVC ile Standart c++ 20 modülleri desteği](https://devblogs.microsoft.com/cppblog/standard-c20-modules-support-with-msvc-in-visual-studio-2019-version-16-8/).

Modül desteği için bir önkoşul olarak, **`permissive-`** belirtildiğinde artık etkindir **`/std:c++latest`** . Daha fazla bilgi için bkz. [`/permissive-`](../build/reference/permissive-standards-conformance.md).

Daha önce altında derlenen **`/std:c++latest`** ve uyumsuz derleyici davranışları gerektiren kodda, **`permissive`** derleyicide katı uyumluluk modunu kapatmak için belirtilebilir. Derleyici seçeneği, **`/std:c++latest`** komut satırı bağımsız değişken listesinden sonra gelmelidir. Ancak, **`permissive`** Modül kullanımı algılanırsa hata oluşur:

> hata C1214: modüller '*Option*' aracılığıyla istenen standart olmayan davranışla çakışıyor

*Seçeneğinin* en yaygın değerleri şunlardır:

| Seçenek | Açıklama |
|--|--|
| **`/Zc:twoPhase-`** | İki aşamalı ad arama C++ 20 modülleri için gereklidir ve tarafından kapsanıyor **`permissive-`** . |
| **`/Zc:hiddenFriend-`** | Standart gizli arkadaş adı arama kuralları C++ 20 modülleri için gereklidir ve tarafından kapsanıyor **`permissive-`** . |
| **`/Zc:preprocessor-`** | Yalnızca C++ 20 başlık birimi kullanımı ve oluşturma için uyumlu ön işlemci gereklidir. Adlandırılmış modüller bu seçeneği gerektirmez. |

[`/experimental:module`](../build/reference/experimental-module.md) *`std.*`* Henüz standartlaştırılmış olmadığından, Visual Studio ile birlikte gelen modülleri kullanmak için bu seçenek hala gereklidir.

**`/experimental:module`** Seçeneği de ve anlamına **`/Zc:twoPhase`** gelir **`/Zc:hiddenFriend`** . Daha önce modüllerle derlenen kod bazen **`/Zc:twoPhase-`** Yalnızca modül tüketilmişse ile derlenebilir. Bu davranış artık desteklenmiyor.

## <a name="conformance-improvements-in-visual-studio-2019-version-169"></a><a name="improvements_169"></a> Visual Studio 2019 sürüm 16,9 ' de uyumluluk geliştirmeleri

### <a name="copy-initialization-of-temporary-in-reference-direct-initialization"></a>Başvuru doğrudan başlatmasında geçici ' ın kopyasını başlatma

Ana çalışma grubu [2267](https://wg21.link/cwg2267) sorunu, parantez içine alınmış Başlatıcı listesi ve bir örgü Başlatıcı listesi arasında bir tutarsızlıkla daðýtýlýr. Çözüm iki formu uyumleştirir.

Visual Studio 2019 sürüm 16,9, değiştirilen davranışı tüm **`/std`** derleyici modlarında uygular. Ancak, büyük olasılıkla kaynak kıran bir değişiklik olduğundan, yalnızca kod kullanılarak derlenmişse desteklenir **`/permissive-`** .

Bu örnek, davranış değişikliğini gösterir:

```cpp
struct A { };

struct B {
    explicit B(const A&);
};

void f()
{
    A a;
    const B& b1(a);     // Always an error
    const B& b2{ a };   // Allowed before resolution to CWG 2267 was adopted: now an error
}
```

### <a name="destructor-characteristics-and-potentially-constructed-subobjects"></a>Yıkıcı özellikleri ve olası oluşturulmuş alt nesnelerin

Çekirdek çalışma grubu sorunu [CWG 2336](https://wg21.link/cwg2336) , sanal temel sınıfları olan sınıflarda yok edicilerin örtük özel durum belirtimleri hakkında bir atlama içerir. Türetilmiş bir sınıftaki yok edicinin bir taban sınıftan daha zayıf bir özel durum belirtimi olabilir ve bu taban bir temeltir `virtual` .

Visual Studio 2019 sürüm 16,9, değiştirilen davranışı tüm **`/std`** derleyici modlarında uygular.

Bu örnek, yorumın nasıl değiştiğini gösterir:

```cpp
class V {
public:
    virtual ~V() noexcept(false);
};

class B : virtual V {
    virtual void foo () = 0;
    // BEFORE: implicitly defined virtual ~B() noexcept(true);
    // AFTER: implicitly defined virtual ~B() noexcept(false);
};

class D : B {
    virtual void foo ();
    // implicitly defined virtual ~D () noexcept(false);
};
```

Bu değişiklikten önce, `B` `noexcept` yalnızca büyük olasılıkla oluşturulmuş alt nesnelerin kabul edildiği için örtük olarak tanımlanmış yıkıcısı idi. Temel sınıf, `V` temel bir değer olduğu ve soyut olduğu için, büyük olasılıkla oluşturulmuş bir alt nesne değildir `virtual` `B` . Ancak, temel sınıf, `V` sınıfının büyük olasılıkla oluşturulmuş bir alt nesnesi olur `D` ve bu nedenle `D::~D` `noexcept(false)` , temel olarak daha zayıf bir özel durum belirtimine sahip türetilmiş bir sınıfa öncü olarak belirlenir. Bu yorum güvenli değil. B 'den türetilmiş bir sınıfın yıkıcısında bir özel durum oluşursa yanlış çalışma zamanı davranışına neden olabilir.

Bu değişiklik ile, bir yıkıcı sanal bir yıkıcıya sahipse ve herhangi bir sanal taban sınıfı potansiyel olarak bir atma yok edicisi içeriyorsa, büyük olasılıkla bir yıkıcıya de

### <a name="similar-types-and-reference-binding"></a>Benzer türler ve başvuru bağlama

Temel çalışma grubu sorunu [CWG 2352](https://wg21.link/cwg2352) , başvuru bağlama kuralları ve benzerlik türüne yapılan değişiklikler arasında bir tutarsızlık ile ilgilidir. Tutarsızlık, önceki hata raporlarında ( [CWG 330](https://wg21.link/cwg330)gibi) tanıtılmıştı. Bu değişiklik ile, bir başvuruyu daha önce geçici olarak bağlayan kod artık yalnızca CV niteleyicilerine göre farklılık gösteren doğrudan bağlanabilir.

Visual Studio 2019 sürüm 16,9, değiştirilen davranışı tüm **`/std`** derleyici modlarında uygular. Büyük olasılıkla kaynak kıbir değişiklik olabilir.

Bu örnek değiştirilen davranışı gösterir:

```cpp
int *ptr;
const int *const &f() {
    return ptr; // Now returns a reference to 'ptr' directly.
    // Previously returned a reference to a temporary and emitted C4172
}
```

Güncelleştirme, sunulan bir geçici üzerinde bir program davranışını değiştirebilir:

```cpp
int func() {
    int i1 = 13;
    int i2 = 23;
    
    int* iptr = &i1;
    int const * const&  iptrcref = iptr;

    // iptrcref is a reference to a pointer to i1 with value 13.
    if (*iptrcref != 13)
    {
        return 1;
    }
    
    // Now change what iptr points to.

    // Prior to CWG 2352 iptrcref should be bound to a temporary and still points to the value 13.
    // After CWG 2352 it is bound directly to iptr and now points to the value 23.
    iptr = &i2;
    if (*iptrcref != 23)
    {
        return 1;
    }

    return 0;
}
```

### <a name="zctwophase-and-zctwophase--switch-behavior-change"></a>`/Zc:twoPhase` ve `/Zc:twoPhase-` geçiş davranışı değişikliği

Normal olarak, MSVC derleyici anahtarları son bir WINS olan prensibi üzerinde çalışır. Ne yazık ki, ve anahtarlarıyla bu durum **`/Zc:twoPhase`** değildir **`/Zc:twoPhase-`** . Bu anahtarlar "Sticky" olarak değiştirildi, bu nedenle sonraki anahtarlar bunları geçersiz kılmadı. Örnek:

`cl /Zc:twoPhase /permissive a.cpp`

Bu durumda, ilk **`/Zc:twoPhase`** anahtar katı iki aşamalı ad aramasını mümkün bir şekilde sunar. İkinci anahtar, katı uyumluluk modunu devre dışı bırakmak (öğesinin tersidir **`/permissive-`** ), ancak devre dışı olmadıysa **`/Zc:twoPhase`** .

Visual Studio 2019 sürüm 16,9, bu davranışı tüm **`/std`** derleyici modlarında değiştirir. **`/Zc:twoPhase`****`/Zc:twoPhase-`** artık "yapışkan" değildir ve daha sonra anahtarlar bunları geçersiz kılabilir.

### <a name="explicit-noexcept-specifiers-on-destructor-templates"></a>Yıkıcı şablonlarındaki açık noexcept tanımlayıcıları

Derleyici daha önce bir atma olmayan özel durum belirtimi ile belirtilen ancak açık bir noexcept belirleyicisi olmadan tanımlanmış bir yıkıcı şablonunu kabul etti. Bir yıkıcının örtük özel durum belirtimi, bir şablonun tanımı noktasında tanınamayan Sınıf özelliklerinin özelliklerine bağlıdır. C++ standardı da bu davranışı gerektirir: bir yıkıcı bir noexcept belirleyicisi olmadan bildirilirse, örtük bir özel durum belirtimine sahiptir ve işlevin başka bir bildiriminde noexcept belirleyicisi olamaz.

Visual Studio 2019 sürüm 16,9 tüm derleyici modlarında uyumlu davranış değişiklikleri **`/std`** .

Bu örnek, derleyici davranışında değişiklik gösterir:

```cpp
template <typename T>
class B {
    virtual ~B() noexcept; // or throw()
};

template <typename T>
B<T>::~B() { /* ... */ } // Before: no diagnostic.
// Now diagnoses a definition mismatch. To fix, define the implementation by 
// using the same noexcept-specifier. For example,
// B<T>::~B() noexcept { /* ... */ }
```

### <a name="rewritten-expressions-in-c20"></a>C++ 20 ' de yeniden yazan ifadeleri

Visual Studio 2019 sürüm 16,2 ' nin altında, **`/std:c++latest`** derleyici aşağıdaki örnekteki kodu kabul etmiş demektir:

```cpp
#include <compare>

struct S {
    auto operator<=>(const S&) const = default;
    operator bool() const;
};

bool f(S a, S b) {
    return a < b;
}
```

Ancak, derleyici yazarın beklediği karşılaştırma işlevini çağırmaz. Yukarıdaki kod olarak yeniden yazılması gerekir `a < b` `(a <=> b) < 0` . Bunun yerine, derleyici `operator bool()` Kullanıcı tanımlı dönüştürme işlevini kullandı ve karşılaştırılır `bool(a) < bool(b)` . Derleyici, Visual Studio 2019 sürüm 16,9 ' den başlayarak, ifadeyi beklenen Spaceship işleç ifadesini kullanarak yeniden yazar.

#### <a name="source-breaking-change"></a>Kaynak bölünmesi değişikliği

Yeniden yazma ifadelerine dönüştürmeleri doğru şekilde uygulamak başka bir etkiye sahiptir: derleyici Ayrıca, ifadeyi yeniden yazma girişimlerini doğru bir şekilde belirsizlikleri. Bu örneği ele alalım:

```cpp
struct Base {
    bool operator==(const Base&) const;
};

struct Derived : Base {
    Derived();
    Derived(const Base&);
    bool operator==(const Derived& rhs) const;
};

bool b = Base{} == Derived{};
```

C++ 17 ' de, ifadenin sağ tarafındaki türetilmiş-taban dönüştürmesi nedeniyle bu kod kabul edilir `Derived` . C++ 20 ' de, birleştirilmiş ifade adayı da eklenmiştir: `Derived{} == Base{}` . Standart olan, Dönüştürmelere göre WINS işlevi ile ilgili kurallar nedeniyle, ve arasında seçim yapmak ve seçimi ortadan `Base::operator==` `Derived::operator==` kaldırılmaz. Bunun nedeni, iki deyimdeki dönüştürme dizilerinin birbirlerine göre daha iyi veya daha kötü olmaması nedeniyle örnek kodun belirsizliğe neden olur.

Belirsizliği çözmek için, iki dönüştürme sırası içine tabi olmayacak yeni bir aday ekleyin:

```cpp
bool operator==(const Derived&, const Base&);
```

#### <a name="runtime-breaking-change"></a>Çalışma zamanının bölünmesi değişikliği

C++ 20 ' deki işleç yeniden yazma kuralları nedeniyle, daha düşük bir dil modunda bulamadığı yeni bir aday bulmak için aşırı yükleme çözümlemesi mümkündür. Yeni aday, eski adaydan daha iyi bir eşleşme olabilir. Bu örneği ele alalım:

```cpp
struct iterator;
struct const_iterator {
  const_iterator(const iterator&);
  bool operator==(const const_iterator &ci) const;
};

struct iterator {
  bool operator==(const const_iterator &ci) const { return ci == *this; }
};
```

C++ 17 ' de, için tek aday ' `ci == *this` dır `const_iterator::operator==` . Bu bir eşleşmedir çünkü, ' a `*this` yönelik türetilmiş-temel dönüşümden geçer `const_iterator` . C++ 20 ' de, başka bir yeniden yazan aday eklenmiştir: `*this == ci` , öğesini çağırır `iterator::operator==` . Bu aday için dönüştürme gerekmez, bu nedenle daha iyi bir eşleşmedir `const_iterator::operator==` . Yeni adaydaki sorun şu anda tanımlanmakta olduğu için işlevin yeni semantiğinin sonsuz bir özyinelemeli tanımı olmasına neden olur `iterator::operator==` .

Örnek gibi kodda yardım almak için, derleyici yeni bir uyarı uygular:

```cmd
$ cl /std:c++latest /c t.cpp
t.cpp
t.cpp(8): warning C5232: in C++20 this comparison calls 'bool iterator::operator ==(const const_iterator &) const' recursively
```

Kodu onarmak için hangi dönüştürmenin kullanılacağı hakkında açık olun:

```cpp
struct iterator {
  bool operator==(const const_iterator &ci) const { return ci == static_cast<const const_iterator&>(*this); }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft C++ dil uygunluğu tablosu](visual-cpp-language-conformance.md)
