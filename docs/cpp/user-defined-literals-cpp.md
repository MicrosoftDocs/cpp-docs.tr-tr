---
title: Kullanıcı tanımlı değişmez değerler (C++)
ms.date: 12/10/2019
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
ms.openlocfilehash: 31b8f1dfb261839c04a6829132975ada9c09d619
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301307"
---
# <a name="user-defined-literals"></a>Kullanıcı tanımlı sabit değerler

C++: Integer, character, kayan nokta, String, Boolean ve pointer için beş büyük sabit değer kategorisi vardır.  11 ' C++ den başlayarak, yaygın deyimler için sözdizimsel kısayollar sağlamak ve tür güvenliğini artırmak üzere bu kategorilere göre kendi sabit değerlerini tanımlayabilirsiniz. Örneğin, bir uzaklık sınıfınız olduğunu varsayalım. Kilometre için bir sabit değer ve mil için bir tane tanımlayabilir ve kullanıcıyı yalnızca yazarak ölçü birimleri hakkında açık olacak şekilde teşvik edebilirsiniz: Auto d = 42.0_km veya Auto d = 42.0_mi. Kullanıcı tanımlı değişmez değerler için performans avantajı veya dezavantajı yoktur; Bunlar öncelikli olarak veya derleme zamanı tür kesintiden daha kolay bir şekilde yapılır. Standart kitaplıkta std: dizesi için Kullanıcı tanımlı sabit değerler, std:: Complex için ve zaman ve süre işlemleri için \<hatası, > üst bilgisinde:

```cpp
Distance d = 36.0_mi + 42.0_km;         // Custom UDL (see below)
std::string str = "hello"s + "World"s;  // Standard Library <string> UDL
complex<double> num =
   (2.0 + 3.01i) * (5.0 + 4.3i);        // Standard Library <complex> UDL
auto duration = 15ms + 42h;             // Standard Library <chrono> UDLs
```

## <a name="user-defined-literal-operator-signatures"></a>Kullanıcı tanımlı sabit değer operatörü imzaları

Ad alanı kapsamında aşağıdaki biçimlerden birini kullanarak bir **"" işleci** tanımlayarak Kullanıcı tanımlı değişmez değer uyguladıysanız:

```cpp
ReturnType operator "" _a(unsigned long long int);   // Literal operator for user-defined INTEGRAL literal
ReturnType operator "" _b(long double);              // Literal operator for user-defined FLOATING literal
ReturnType operator "" _c(char);                     // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _d(wchar_t);                  // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _e(char16_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _f(char32_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _g(const char*, size_t);      // Literal operator for user-defined STRING literal
ReturnType operator "" _h(const wchar_t*, size_t);   // Literal operator for user-defined STRING literal
ReturnType operator "" _i(const char16_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _g(const char32_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

Önceki örnekteki işleç adları, sağladığınız ad için yer tutuculardır; Ancak, önde gelen alt çizgi gereklidir. (Yalnızca standart kitaplığın alt çizgi olmadan sabit değer tanımlamasına izin verilir.) Dönüş türü, dönüştürmeyi veya değişmez değerin gerçekleştirdiği diğer işlemi özelleştirdiğiniz yerdir. Ayrıca, bu işleçlerden herhangi biri `constexpr`olarak tanımlanabilir.

## <a name="cooked-literals"></a>Tanıtım sabit değerleri

Kaynak kodunda, Kullanıcı tanımlı veya değil, `101`, `54.7`veya `"hello"` ya da `true`gibi alfasayısal karakterlerden oluşan herhangi bir sabit değerdir. Derleyici, diziyi bir Integer, float, const char\* dize vb. olarak yorumlar. Kullanıcı tanımlı bir sabit değer olarak kabul eden bir dize, değişmez değer değerine atanmış olan derleyicinin, birlikte bulunan *değişmez*değer olarak bilinen bir tür olsun. `_r` ve `_t` dışında yukarıdaki tüm işleçler, açıklanmış değişmez değerler. Örneğin, bir sabit `42.0_km`, _b benzer bir imzaya sahip _km adlı bir işlece bağlanır `42_km` ve _a benzer bir imzaya sahip bir işleçle bağlanır.

Aşağıdaki örnek, Kullanıcı tanımlı değişmez değerlerin çağıranların girişi hakkında açık olmasını nasıl teşvik edebilir gösterir. `Distance`oluşturmak için Kullanıcı, Kullanıcı tanımlı uygun sabit değeri kullanarak kilometre içe veya mil olarak açıkça belirtilmelidir. Tabii ki aynı sonucu başka yollarla da elde edebilirsiniz, ancak kullanıcı tanımlı değişmez değerler alternatiflere göre daha az ayrıntılıdır.

```cpp
struct Distance
{
private:
    explicit Distance(long double val) : kilometers(val)
    {}

    friend Distance operator"" _km(long double  val);
    friend Distance operator"" _mi(long double val);
    long double kilometers{ 0 };
public:
    long double get_kilometers() { return kilometers; }
    Distance operator+(Distance& other)
    {
        return Distance(get_kilometers() + other.get_kilometers());
    }
};

Distance operator"" _km(long double  val)
{
    return Distance(val);
}

Distance operator"" _mi(long double val)
{
    return Distance(val * 1.6);
}
int main(int argc, char* argv[])
{
    // Must have a decimal point to bind to the operator we defined!
    Distance d{ 402.0_km }; // construct using kilometers
    cout << "Kilometers in d: " << d.get_kilometers() << endl; // 402

    Distance d2{ 402.0_mi }; // construct using miles
    cout << "Kilometers in d2: " << d2.get_kilometers() << endl;  //643.2

    // add distances constructed with different units
    Distance d3 = 36.0_mi + 42.0_km;
    cout << "d3 value = " << d3.get_kilometers() << endl; // 99.6

    // Distance d4(90.0); // error constructor not accessible

    string s;
    getline(cin, s);
    return 0;
}
```

Değişmez değerin bir Decimal kullanması gerektiğini unutmayın, aksi takdirde sayı tamsayı olarak yorumlanır ve tür işleçle uyumlu olmaz. Ayrıca, kayan nokta girişi için, türün **uzun çift**ve tamsayı türleri için **uzun**bir süre olması gerektiğini unutmayın.

## <a name="raw-literals"></a>Ham değişmez değerler

Kullanıcı tanımlı ham bir sabit değerde, tanımladığınız işleç sabit değeri bir char değeri dizisi olarak kabul eder ve bu diziyi sayı veya dize veya diğer tür olarak yorumlamak için kullanılır. Bu sayfada daha önce gösterilen işleçler listesinde `_r` ve `_t` ham değişmez değerleri tanımlamak için kullanılabilir:

```cpp
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

Derleyicinin gerçekleştireceği değerden farklı bir giriş dizisinin özel bir yorumunu sağlamak için ham değişmez değerler kullanabilirsiniz. Örneğin, dizi `4.75987` bir IEEE 754 kayan nokta türü yerine özel bir ondalık türüne dönüştüren bir değişmez değer tanımlayabilirsiniz. Birleşik değişmez değerler gibi ham değişmez değerler, giriş sıralarının derleme zamanı doğrulamasını gerçekleştirmek için de kullanılabilir.

### <a name="example-limitations-of-raw-literals"></a>Örnek: ham değişmez değerlerin sınırlamaları

Ham değişmez değer operatörü ve sabit değer operatörü şablonu, aşağıdaki örnekte gösterildiği gibi yalnızca integral ve kayan nokta Kullanıcı tanımlı değişmez değerler için geçerlidir:

```cpp
#include <cstddef>
#include <cstdio>

// Literal operator for user-defined INTEGRAL literal
void operator "" _dump(unsigned long long int lit)
{
    printf("operator \"\" _dump(unsigned long long int) : ===>%llu<===\n", lit);
};

// Literal operator for user-defined FLOATING literal
void operator "" _dump(long double lit)
{
    printf("operator \"\" _dump(long double)            : ===>%Lf<===\n",  lit);
};

// Literal operator for user-defined CHARACTER literal
void operator "" _dump(char lit)
{
    printf("operator \"\" _dump(char)                   : ===>%c<===\n",   lit);
};

void operator "" _dump(wchar_t lit)
{
    printf("operator \"\" _dump(wchar_t)                : ===>%d<===\n",   lit);
};

void operator "" _dump(char16_t lit)
{
    printf("operator \"\" _dump(char16_t)               : ===>%d<===\n",   lit);
};

void operator "" _dump(char32_t lit)
{
    printf("operator \"\" _dump(char32_t)               : ===>%d<===\n",   lit);
};

// Literal operator for user-defined STRING literal
void operator "" _dump(const     char* lit, size_t)
{
    printf("operator \"\" _dump(const     char*, size_t): ===>%s<===\n",   lit);
};

void operator "" _dump(const  wchar_t* lit, size_t)
{
    printf("operator \"\" _dump(const  wchar_t*, size_t): ===>%ls<===\n",  lit);
};

void operator "" _dump(const char16_t* lit, size_t)
{
    printf("operator \"\" _dump(const char16_t*, size_t):\n"                  );
};

void operator "" _dump(const char32_t* lit, size_t)
{
    printf("operator \"\" _dump(const char32_t*, size_t):\n"                  );
};

// Raw literal operator
void operator "" _dump_raw(const char* lit)
{
    printf("operator \"\" _dump_raw(const char*)        : ===>%s<===\n",   lit);
};

template<char...> void operator "" _dump_template();       // Literal operator template

int main(int argc, const char* argv[])
{
    42_dump;
    3.1415926_dump;
    3.14e+25_dump;
     'A'_dump;
    L'B'_dump;
    u'C'_dump;
    U'D'_dump;
      "Hello World"_dump;
     L"Wide String"_dump;
    u8"UTF-8 String"_dump;
     u"UTF-16 String"_dump;
     U"UTF-32 String"_dump;
    42_dump_raw;
    3.1415926_dump_raw;
    3.14e+25_dump_raw;

    // There is no raw literal operator or literal operator template support on these types:
    //  'A'_dump_raw;
    // L'B'_dump_raw;
    // u'C'_dump_raw;
    // U'D'_dump_raw;
    //   "Hello World"_dump_raw;
    //  L"Wide String"_dump_raw;
    // u8"UTF-8 String"_dump_raw;
    //  u"UTF-16 String"_dump_raw;
    //  U"UTF-32 String"_dump_raw;
}
```

```Output
operator "" _dump(unsigned long long int) : ===>42<===
operator "" _dump(long double)            : ===>3.141593<===
operator "" _dump(long double)            : ===>31399999999999998506827776.000000<===
operator "" _dump(char)                   : ===>A<===
operator "" _dump(wchar_t)                : ===>66<===
operator "" _dump(char16_t)               : ===>67<===
operator "" _dump(char32_t)               : ===>68<===
operator "" _dump(const     char*, size_t): ===>Hello World<===
operator "" _dump(const  wchar_t*, size_t): ===>Wide String<===
operator "" _dump(const     char*, size_t): ===>UTF-8 String<===
operator "" _dump(const char16_t*, size_t):
operator "" _dump(const char32_t*, size_t):
operator "" _dump_raw(const char*)        : ===>42<===
operator "" _dump_raw(const char*)        : ===>3.1415926<===
operator "" _dump_raw(const char*)        : ===>3.14e+25<===
```
