---
title: "Kullanıcı tanımlı değişmez değerler (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6643df5e0d5b49155a07763cca68ffc66cb2d38d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="user-defined-literals--c"></a>Kullanıcı tanımlı değişmez değerler (C++)
Değişmez değerler beş ana kategoriye ayrılır: tamsayı, karakteri, kayan nokta, dize, boolean ve işaretçi.  C++ 11 başlangıç ortak deyimleri için söz dizim kısayollar sağlar ve tür güvenliği artırmak için bu kategorilere göre kendi değişmez değerleri tanımlayabilirsiniz. Örneğin, bir uzaklık sınıf sahip varsayalım. Bir hazır değer kilometre için ve mil için başka bir tanımlayın ve yalnızca yazarak ölçü hakkında açık kullanıcının olmasını öneririz: otomatik d 42.0_km veya otomatik d = 42.0_mi =. Performans avantajı veya kullanıcı tanımlı değişmez değerler dezavantajı yoktur; derleme zamanı tür kesintisi veya kolaylık olması için öncelikle oldukları. Kullanıcı tanımlı değişmez değerler std:string, std::complex ve birimleri standart kitaplığı zamanını ve süresini işlemlerinde sahip \<chrono > Üstbilgi:  
  
```  
Distance d = 36.0_mi + 42.0_km;         // Custom UDL (see below)  
    std::string str = "hello"s + "World"s;  // Standard Library <string> UDL  
    complex<double> num =   
        (2.0 + 3.01i) * (5.0 + 4.3i);       // Standard Library <complex> UDL  
    auto duration = 15ms + 42h;             // Standard Library <chrono> UDLs  
```  
  
## <a name="user-defined-literal-operator-signatures"></a>Kullanıcı tanımlı değişmez değer işleci imzaları  
 Kullanıcı tanımlı değişmez değer tanımlayarak uygulamak bir `operator""` aşağıdaki biçimlerden biri ile ad alanı kapsamda:  
  
```  
ReturnType operator "" _a(unsigned long long int);   // Literal operator for user-defined INTEGRAL literal  
ReturnType operator "" _b(long double);              // Literal operator for user-defined FLOATING literal  
ReturnType operator "" _c(char);                     // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _d(wchar_t);                  // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _e(char16_t);                 // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _f(char32_t);                 // Literal operator for user-defined CHARACTER literal  
ReturnType operator "" _g(const     char*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _h(const  wchar_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _i(const char16_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _g(const char32_t*, size_t);  // Literal operator for user-defined STRING literal  
ReturnType operator "" _r(const char*);              // Raw literal operator  
template<char...> ReturnType operator "" _t();       // Literal operator template  
```  
  
 Önceki örnekte işleci sağladığınız ad yer tutucular adlarıdır; Ancak, baştaki alt çizgi gereklidir. (Yalnızca standart kitaplığı alt çizgi olmadan değişmez değerleri tanımlayın izin verilmez.) Dönüş türü, dönüştürme ya da sabit gerçekleştirir başka bir işlem özelleştirme burada ' dir. Ayrıca, bu işleçlere hiçbirini olarak tanımlanabilir `constexpr`.  
  
## <a name="cooked-literals"></a>Hazırlanan değişmez değerleri  
 Kullanıcı tanımlı ya da alfasayısal karakterler, aslında bir dizi gibi değil tüm değişmez değeri kaynağında kod `101`, veya `54.7`, veya `"hello"` veya `true`. Derleme sırası bir tamsayı, kayan nokta, const char olarak yorumlar\* dize ve benzeri. Değişmez değer atanmış derleyici türü ne olursa olsun girdi olarak kabul eden bir kullanıcı tanımlı bir hazır değer basit olarak bilinen bir *hazırlanan değişmez değeri*. Yukarıdaki tüm işleçleri hariç `_r` ve `_t` değişmez değerleri hazırlanan. Örneğin, bir hazır değer `42.0_km` _b ve sabit benzer bir imzaya sahip _km adında bir operatör bağlamak `42_km` _Sütun için benzer bir imza ile bir işleç bağlayın.  
  
 Aşağıdaki örnekte nasıl kullanıcı tanımlı değişmez değerler gösterilmektedir arayanlar hakkında kendi giriş açık olmasını öneririz. Oluşturmak için bir `Distance`, kullanıcı açıkça kilometre ya da mil uygun kullanıcı tanımlı değişmez değeri kullanarak belirtmeniz gerekir. Elbette ayrıca diğer yollarla aynı sonucu elde edebilirsiniz, ancak kullanıcı tanımlı değişmez değerler alternatifleri daha az ayrıntılıdır.  
  
```  
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
  
 Değişmez değer sayı ondalık kullanmanız gerekir, aksi takdirde sayısı bir tamsayı olarak yorumlanacağını ve türü işleç ile uyumlu olmayacaktır unutmayın. Ayrıca, giriş noktası değişken için tür olmalıdır unutmayın `long double`ve olmalıdır tam sayı türleri için `long long`.  
  
## <a name="raw-literals"></a>Ham değişmez değerleri  
 Bir ham kullanıcı tanımlı değişmez değeri, tanımladığınız işleci sabit bir karakter değerleri dizisi kabul eder ve bir sayı veya dize veya diğer tür o sırada yorumlamak için en fazla olur. Bu sayfanın önceki bölümlerinde gösterilen işleçleri listesinde `_r` ve `_t` ham değişmez değerleri tanımlamak için kullanılabilir:  
  
```  
ReturnType operator "" _r(const char*);              // Raw literal operator  
template<char...> ReturnType operator "" _t();       // Literal operator template  
```  
  
 Ham değişmez değerleri derleyici gerçekleştirmek daha farklı bir giriş sırası özel bir yorumu sağlamak için kullanabilirsiniz. Örneğin, sırası dönüştüren bir hazır değer tanımlayabilirsiniz `4.75987` içine bir IEEE kayan noktası türü 754 yerine özel bir Decimal türü. Ham değişmez değerleri, ister değişmez değerleri hazırlanan, aynı zamanda giriş sıralarının derleme zamanı doğrulama gerçekleştirmek için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  
### <a name="limitations-of-raw-literals"></a>Ham değişmez değerleri sınırlamaları  
 Yalnızca ham değişmez değer işleci ve değişmez değer işleci şablon Entegral ve kayan nokta kullanıcı tanımlı değişmez değerler için aşağıdaki örnekte gösterildiği gibi çalışır:  
  
```  
#include <cstddef>  
#include <cstdio>  
  
void operator "" _dump(unsigned long long int lit)  { printf("operator \"\" _dump(unsigned long long int) : ===>%llu<===\n", lit); };  // Literal operator for user-defined INTEGRAL literal  
void operator "" _dump(long double lit)             { printf("operator \"\" _dump(long double)            : ===>%Lf<===\n",  lit); };  // Literal operator for user-defined FLOATING literal  
void operator "" _dump(char lit)                    { printf("operator \"\" _dump(char)                   : ===>%c<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(wchar_t lit)                 { printf("operator \"\" _dump(wchar_t)                : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(char16_t lit)                { printf("operator \"\" _dump(char16_t)               : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(char32_t lit)                { printf("operator \"\" _dump(char32_t)               : ===>%d<===\n",   lit); };  // Literal operator for user-defined CHARACTER literal  
void operator "" _dump(const     char* lit, size_t) { printf("operator \"\" _dump(const     char*, size_t): ===>%s<===\n",   lit); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const  wchar_t* lit, size_t) { printf("operator \"\" _dump(const  wchar_t*, size_t): ===>%ls<===\n",  lit); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const char16_t* lit, size_t) { printf("operator \"\" _dump(const char16_t*, size_t):\n"                  ); };  // Literal operator for user-defined STRING literal  
void operator "" _dump(const char32_t* lit, size_t) { printf("operator \"\" _dump(const char32_t*, size_t):\n"                  ); };  // Literal operator for user-defined STRING literal  
void operator "" _dump_raw(const char* lit)         { printf("operator \"\" _dump_raw(const char*)        : ===>%s<===\n",   lit); };  // Raw literal operator  
  
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
    // 'A'_dump_raw;               // There is no raw literal operator or literal operator template support on this type  
    //L'B'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //u'C'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //U'D'_dump_raw;              // There is no raw literal operator or literal operator template support on this type  
    //  "Hello World"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    // L"Wide String"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    //u8"UTF-8 String"_dump_raw;   // There is no raw literal operator or literal operator template support on this type  
    // u"UTF-16 String"_dump_raw;  // There is no raw literal operator or literal operator template support on this type  
    // U"UTF-32 String"_dump_raw;  // There is no raw literal operator or literal operator template support on this type  
}  
/*****  
Output:  
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
*****/  
  
```