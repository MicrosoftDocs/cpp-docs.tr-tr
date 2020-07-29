---
title: Kullanıcı tanımlı değişmez değerler (C++)
description: Standart C++ ' da Kullanıcı tanımlı sabit değerlerin amacını ve kullanımını açıklar.
ms.date: 02/10/2020
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
ms.openlocfilehash: 21ed3db84f057131b0404d5f950a4419cb753070
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227055"
---
# <a name="user-defined-literals"></a>Kullanıcı tanımlı sabit değerler

C++: Integer, character, kayan nokta, dize, Boolean ve işaretçi olmak üzere, C++ ' da altı ana sabit kategori vardır. C++ 11 ' den başlayarak, genel deyimler için sözdizimsel kısayollar sağlamak ve tür güvenliğini artırmak için bu kategorilere göre kendi sabit değerlerini tanımlayabilirsiniz. Örneğin, bir sınıfınız olduğunu varsayalım `Distance` . Kilometre için bir sabit değer ve mil için bir tane tanımlayabilir ve kullanıcının ölçü birimleriyle ilgili olarak şu yazarak açık olmasını önerin: `auto d = 42.0_km` veya `auto d = 42.0_mi` . Kullanıcı tanımlı değişmez değerler için performans avantajı veya olumsuz bir avantaj yoktur; Bunlar öncelikli olarak veya derleme zamanı tür kesintiden daha kolay bir şekilde yapılır. Standart kitaplıkta, ve için Kullanıcı tanımlı sabit değerler ve `std::string` `std::complex` başlıktaki süre ve süre işlemleri için \<chrono> :

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

Önceki örnekteki işleç adları, sağladığınız ad için yer tutuculardır; Ancak, önde gelen alt çizgi gereklidir. (Yalnızca standart kitaplığın alt çizgi olmadan sabit değer tanımlamasına izin verilir.) Dönüş türü, dönüştürme işlemini veya değişmez değer tarafından gerçekleştirilen diğer işlemleri özelleştirdiğiniz yerdir. Ayrıca, bu işleçlerden herhangi biri olarak tanımlanabilir **`constexpr`** .

## <a name="cooked-literals"></a>Tanıtım sabit değerleri

Kaynak kodunda, Kullanıcı tanımlı veya değil, temelde, veya ya da gibi alfasayısal karakterlerden oluşan bir dizi `101` `54.7` `"hello"` **`true`** . Derleyici, diziyi bir Integer, float, const char dizesi vb. olarak yorumlar \* . Kullanıcı tanımlı bir sabit değer olarak kabul eden bir dize, değişmez değer değerine atanmış olan derleyicinin, birlikte bulunan *değişmez*değer olarak bilinen bir tür olsun. Ve dışındaki tüm işleçler, `_r` diğer `_t` sabit değer olarak kullanılır. Örneğin, bir sabit değeri, `42.0_km` _b benzer bir imzaya sahip _km adlı bir işlece bağlanır ve değişmez değer `42_km` _a benzer bir imzaya sahip bir işlece bağlanır.

Aşağıdaki örnek, Kullanıcı tanımlı değişmez değerlerin çağıranların girişi hakkında açık olmasını nasıl teşvik edebilir gösterir. Bir oluşturmak için `Distance` Kullanıcı, Kullanıcı tanımlı uygun sabit değeri kullanarak kilometre içe veya mil belirtmelidir. Aynı sonucu başka yollarla elde edebilirsiniz, ancak kullanıcı tanımlı değişmez değerler alternatiflere göre daha az ayrıntılıdır.

```cpp
// UDL_Distance.cpp

#include <iostream>
#include <string>

struct Distance
{
private:
    explicit Distance(long double val) : kilometers(val)
    {}

    friend Distance operator"" _km(long double val);
    friend Distance operator"" _mi(long double val);

    long double kilometers{ 0 };
public:
    const static long double km_per_mile;
    long double get_kilometers() { return kilometers; }

    Distance operator+(Distance other)
    {
        return Distance(get_kilometers() + other.get_kilometers());
    }
};

const long double Distance::km_per_mile = 1.609344L;

Distance operator"" _km(long double val)
{
    return Distance(val);
}

Distance operator"" _mi(long double val)
{
    return Distance(val * Distance::km_per_mile);
}

int main()
{
    // Must have a decimal point to bind to the operator we defined!
    Distance d{ 402.0_km }; // construct using kilometers
    std::cout << "Kilometers in d: " << d.get_kilometers() << std::endl; // 402

    Distance d2{ 402.0_mi }; // construct using miles
    std::cout << "Kilometers in d2: " << d2.get_kilometers() << std::endl;  //646.956

    // add distances constructed with different units
    Distance d3 = 36.0_mi + 42.0_km;
    std::cout << "d3 value = " << d3.get_kilometers() << std::endl; // 99.9364

    // Distance d4(90.0); // error constructor not accessible

    std::string s;
    std::getline(std::cin, s);
    return 0;
}
```

Sabit değer numarası bir Decimal kullanmalıdır. Aksi takdirde, sayı bir tamsayı olarak yorumlanır ve tür işleçle uyumlu olmaz. Kayan nokta girişi için tür ve olması gereken **`long double`** integral türleri için olmalıdır **`long long`** .

## <a name="raw-literals"></a>Ham değişmez değerler

Kullanıcı tanımlı ham sabit değerinde, tanımladığınız işleç sabit değeri char değerlerinin bir dizisi olarak kabul eder. Bu sırayı sayı veya dize veya diğer tür olarak yorumlamak sizin için bir sayıdır. Bu sayfada daha önce gösterilen işleçler listesinde `_r` ve `_t` ham değişmez değerleri tanımlamak için kullanılabilir:

```cpp
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

Derleyicinin normal davranışından farklı bir giriş dizisinin özel bir yorumunu sağlamak için ham değişmez değerler kullanabilirsiniz. Örneğin, bir `4.75987` ıeee 754 kayan nokta türü yerine, diziyi özel bir ondalık türüne dönüştüren bir değişmez değer tanımlayabilirsiniz. Tanıtım sabit değerleri gibi ham değişmez değerler de giriş sıralarının derleme zamanı doğrulaması için kullanılabilir.

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
