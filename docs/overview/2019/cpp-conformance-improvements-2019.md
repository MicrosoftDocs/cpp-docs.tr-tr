---
title: C++ uyumluluk geliştirmeleri
ms.date: 03/22/2019
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: e12504d4950c87042cbb030c6c683874f6ffc8b7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779478"
---
# <a name="c-conformance-improvements-in-visual-studio-2019"></a>Visual Studio 2019'deki C++ uyumluluk geliştirmeleri

Visual Studio 2019 RTW aşağıdaki uyumluluk geliştirmeleri, hata düzeltmeleri ve Microsoft C++ derleyicisi (MSVC) davranış değişiklikleri içerir.

**Not:** C ++ 20 özellikleri oluşturulacak bulunan `/std:c++latest` derleme ve IntelliSense için C ++ 20 uygulama tamamlanana kadar modu. O zaman `/std:c++20` derleyici modu kullanıma sunulan.

## <a name="conformance-improvements"></a>Uyumluluk geliştirmeleri

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Şablonlar ve hata algılama için geliştirilmiş modüller desteği

Modüller C ++ 20 standart resmi olarak sunulmuştur. Visual Studio 2017 sürüm 15.9 için geliştirilmiş destek eklendi. Daha fazla bilgi için [MSVC 2017 sürümü 15.9 ile C++ modüllerinde şablon desteği ve hata algılama daha iyi](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Değiştirilen toplama türü belirtimi

Bir toplama türü belirtimi, C ++ 20 değiştirildi (bkz [engelle kullanıcı bildirilen oluşturuculara sahip toplamalar](http://wg21.link/p1008r1)). Visual Studio 2019 içinde altında `/std:c++latest`, herhangi bir kullanıcı olarak bildirilen oluşturucusuna sahip bir sınıf (örneğin bir oluşturucu dahil olmak üzere bildirilen `= default` veya `= delete`) bir toplama ifadesi değil. Daha önce yalnızca kullanıcı tarafından sağlanan bir oluşturucu, bir sınıfın bir toplama engeller diskalifiye. Bu değişiklik bu türler nasıl başlatılabilir ek kısıtlamalar getirir.

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

C ++ 20 tanıtır `<=>` üç yönlü karşılaştırma işleci olarak da bilinen "savaş Gemisi operatörü". İçinde Visual Studio 2019 `/std:c++latest` modu artık izin verilmeyen söz dizimi hatalarını yükselterek işleci için kısmi destek tanıtır. Örneğin, aşağıdaki kod Visual Studio 2017'de hata olmadan derler ancak Visual Studio 2019 altında birden çok hataları başlatır `/std:c++latest`:

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

## <a name="bug-fixes-and-behavior-changes"></a>Hata düzeltmeleri ve davranış değişiklikleri

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

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>+= Ve/CLR veya /ZW altında-= yanlış çağrıları artık doğru şekilde algılanır.

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

MSVC C4800 çok gürültülü ve insuppressible bool değerine örtülü dönüştürme hakkında uyarı, bize VS 2017'de kaldırmak için önde gelen bir performans sağlamak için kullanılır. Ancak, VS 2017 yaşam döngüsü üzerinde çok sayıda geribildirim sorunu gidermeye yararlı durumlarını aldık. Biz Visual Studio 2019 dikkatli bir şekilde özel olarak uyarlanmış bir C4800 ikisi için de bir açık tür dönüştürme veya karşılaştırma uygun türde 0 ile kolayca gizlenebilir, eşlik eden C4165 birlikte geri getirin. Kapalı varsayılan düzey 4 uyarısı C4800 olduğu ve C4165 kapalı varsayılan düzey 3 bir uyarıdır. Her ikisini de kullanarak bulunabilirlik `/Wall` derleyici seçeneği.

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

### <a name="clr-now-incompatible-with-stdclatest"></a>/ CLR/Std: c ile uyumsuz artık ++ en son

MSVC C ++ 20 standart taslak altında özelliklerini uygulama başladığında `/std:c++latest` bayrak `/std:c++latest` artık uyumlu olmayan `/clr` (tüm özellikleri) `/ZW`, ve `/Gm`. Visual Studio 2019 ' kullanmak `/std:c++17` veya `/std:c++14` ile derleme yaparken modları `/clr`, `/ZW` veya `/Gm`.

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

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 2019 yenilikler](../what-s-new-for-visual-cpp-in-visual-studio.md)