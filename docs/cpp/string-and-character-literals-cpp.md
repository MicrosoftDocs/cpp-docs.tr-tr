---
title: Dize ve karakter değişmez değerleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- R
dev_langs:
- C++
helpviewer_keywords:
- L constant
- escape sequences
- Null strings, null-terminated strings
- literal strings, C++
- Null strings
- string literals, syntax
- string literals
- literal strings
- strings [C++], string literals
- NULL, character constant
- wide characters, strings
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de3dffbbacd69d19b2a3fc5ba1fac360712db19e
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895259"
---
# <a name="string-and-character-literals--c"></a>Dize ve karakter değişmez değerleri (C++)

C++, çeşitli dize ve karakter türleri destekler ve bu türlerinden her birinin değişmez değerler express için yöntemler sağlar. Kaynak kodunuzda bir karakter kümesini kullanarak, karakter ve dize değişmez değerleri içeriğini express. Evrensel karakter adları ve kaçış karakterleri yalnızca temel kaynak karakter kümesi kullanan herhangi bir dize express sağlar. Ham dize değişmez değeri kaçış karakterleri kullanmaktan kaçının sağlar ve her tür dize değişmez değerleri ifade etmek için kullanılabilir. Ek yapılma veya dönüştürme adımları yapmak zorunda kalmadan std::string değişmez değerleri daha da oluşturabilirsiniz.

```cpp
#include <string>
using namespace std::string_literals; // enables s-suffix for std::string literals

int main()  
{  
    // Character literals
    auto c0 =   'A'; // char
    auto c1 = u8'A'; // char
    auto c2 =  L'A'; // wchar_t
    auto c3 =  u'A'; // char16_t
    auto c4 =  U'A'; // char32_t

    // String literals
    auto s0 =   "hello"; // const char*  
    auto s1 = u8"hello"; // const char*, encoded as UTF-8
    auto s2 =  L"hello"; // const wchar_t*  
    auto s3 =  u"hello"; // const char16_t*, encoded as UTF-16
    auto s4 =  U"hello"; // const char32_t*, encoded as UTF-32

    // Raw string literals containing unescaped \ and "
    auto R0 =   R"("Hello \ world")"; // const char*  
    auto R1 = u8R"("Hello \ world")"; // const char*, encoded as UTF-8
    auto R2 =  LR"("Hello \ world")"; // const wchar_t*  
    auto R3 =  uR"("Hello \ world")"; // const char16_t*, encoded as UTF-16
    auto R4 =  UR"("Hello \ world")"; // const char32_t*, encoded as UTF-32

    // Combining string literals with standard s-suffix
    auto S0 =   "hello"s; // std::string
    auto S1 = u8"hello"s; // std::string
    auto S2 =  L"hello"s; // std::wstring
    auto S3 =  u"hello"s; // std::u16string
    auto S4 =  U"hello"s; // std::u32string

    // Combining raw string literals with standard s-suffix
    auto S5 =   R"("Hello \ world")"s; // std::string from a raw const char*  
    auto S6 = u8R"("Hello \ world")"s; // std::string from a raw const char*, encoded as UTF-8
    auto S7 =  LR"("Hello \ world")"s; // std::wstring from a raw const wchar_t*  
    auto S8 =  uR"("Hello \ world")"s; // std::u16string from a raw const char16_t*, encoded as UTF-16
    auto S9 =  UR"("Hello \ world")"s; // std::u32string from a raw const char32_t*, encoded as UTF-32
}  
```  

Dize değişmez değerleri, önek olabilir veya `u8`, `L`, `u`, ve `U` önekleri belirtmek için (tek baytlı veya çok baytlı) karakteri, UTF-8, geniş karakteri (UCS-2 veya UTF-16), UTF-16 ve UTF-32 kodlamalarına sırasıyla daraltın. Ham dize sabit değeri olabilir `R`, `u8R`, `LR`, `uR` ve `UR` ön ekleri için bu kodlamalarda ham sürümünün eşdeğeridir.  Geçici veya statik std::string değerleri oluşturmak için dize sabit değerleri veya ham dize sabit değerleri kullanabilirsiniz bir `s` soneki. Daha fazla bilgi için aşağıdaki dize değişmez değerleri bölümüne bakın. Temel kaynak karakter hakkında daha fazla bilgi için set, evrensel karakter adları ve genişletilmiş kod sayfaları karakterlerinden kaynak kodunuzu kullanma, bkz [karakter kümesi](../cpp/character-sets.md).

## <a name="character-literals"></a>Karakter değişmez değerleri

A *karakter sabit değeri* sabit karakterden oluşur. Tek tırnak işareti içine alınmış karakter olarak temsil edilir. Beş tür karakter değişmez değeri vardır:

-   Normal karakter değişmez değerleri türü **char**, örneğin `'a'`  

-   Türünde UTF-8 karakter değişmez değerleri **char**, örneğin `u8'a'`  

-   Türünde geniş karakter değişmez değerleri `wchar_t`, örneğin `L'a'`  

-   Türünde UTF-16 karakter değişmez değerleri `char16_t`, örneğin `u'a'`  

-   Türünde UTF-32 karakter değişmez değerleri `char32_t`, örneğin `U'a'`  

Ters eğik çizgi ayrılmış karakterler dışında herhangi bir karakter, bir karakter sabiti için kullanılan karakter olabilir ('\\'), tek tırnak işareti (') veya yeni satır. Ayrılmış karakterler bir çıkış sırası kullanılarak belirtilebilir. Tür karakter tutabilecek kadar büyük olduğu sürece karakter evrensel karakter adları kullanılarak belirtilebilir.

### <a name="encoding"></a>Kodlama

Karakter değişmez değerleri farklı kodlanır kendi ön ekine.

- Bir karakter sabiti öneki normal bir karakter sabiti ' dir. Normal bir karakter sabiti değeri içeren tek bir karakter kaçış dizisi veya yürütme karakter kümesindeki kodlama sayısal değerine eşit bir değer yürütme karakter kümesinde temsil edilebilir evrensel karakter adı vardır. Evrensel karakter adı birden fazla karakter veya kaçış dizisi içeren bir normal karakter sabit değeri bir *karakterli sabit değer*. Koşullu olarak tarafından desteklenen, bir çok karakterli sabit değer veya yürütme karakter kümesinde temsil edilemeyen bir normal karakter değişmez değer türü int sahiptir ve değeri uygulama tanımlanır.

- M ön Ekle başlayan bir karakter değişmez bir geniş karakter değişmez değerdir. Bir tek karakter, çıkış dizisi veya evrensel karakter adı içeren bir geniş karakter değişmez değeri, karakter sabit hiçbir gösterimi olmadıkça ayarlamak yürütme geniş karakter kodlama sayısal değerine eşit bir değer vardır uygulama tanımlı değeri bu durumda yürütme geniş karakterli ayarlayın. Birden çok karakterler, kaçış dizileri veya evrensel karakter adları içeren bir geniş karakter değişmez değer uygulama tarafından tanımlanır.

- U8 ön Ekle başlayan bir karakter değişmez bir UTF-8 karakter sabit değeri var. UTF-8 karakter sabiti değeri içeren tek bir karakter kaçış dizisi veya evrensel karakter adı (C0 denetimleri ve temel Latin karşılık gelen tek bir UTF-8 kod birimi tarafından temsil edilebilir ISO 10646 kod noktası değerine eşit bir değer sahipse Unicode bloğu). Değerin tek bir UTF-8 kod birimi tarafından temsil edilemiyorsa, program yapılı bir programdır. Birden fazla karakter, çıkış dizisi veya evrensel karakter adı içeren bir UTF-8 karakter hatalı biçimlendirilmiş.

- U ön Ekle başlayan bir karakter değişmez bir UTF-16 karakter sabiti ' dir. UTF-16 karakter sabiti değeri içeren tek bir karakter kaçış dizisi veya evrensel karakter adı (temel çok dilli düzlem için karşılık gelen tek bir UTF-16 kod birimi tarafından temsil edilebilir ISO 10646 kod noktası değerine eşit bir değer sahipse ). Değerin tek bir UTF-16 kod birimi tarafından temsil edilemiyorsa, program yapılı bir programdır. Birden fazla karakter, çıkış dizisi veya evrensel karakter adı içeren bir UTF-16 karakter hatalı biçimlendirilmiş.

- U ön Ekle başlayan bir karakter değişmez bir UTF-32 karakter sabiti ' dir. UTF-32 karakter sabiti değeri içeren tek bir karakter kaçış dizisi veya ISO 10646 kod noktası değerine eşit bir değer evrensel karakter adı vardır. Birden fazla karakter, çıkış dizisi veya evrensel karakter adı içeren bir UTF-8 karakter hatalı biçimlendirilmiş.

###  <a name="bkmk_Escape"></a> Kaçış dizileri

Üç tür kaçış dizisi vardır: basit, sekizlik ve onaltılık. Çıkış sıraları aşağıdakilerden biri olabilir:

|Değer|Kaçış sırası|Değer|Kaçış sırası|
|-----------|---------------------|-----------|---------------------|
|yeni satır|\n|Ters eğik çizgi|\\\|
|Yatay sekme|\t|soru işareti|? veya \\?|
|dikey sekme|\v|tek tırnak|\\'|
|Geri Al|\b|çift tırnak işareti|\\"|
|satır başı|\r|null karakteri|\0|
|form besleme|\f|sekizlik|\ooo|
|Uyarı (zil)|\a|onaltılık|\xhhh|

Aşağıdaki kod, kaçış karakterlerini normal karakter değişmez değerleri kullanarak bazı örnekler göstermektedir. Kaçış dizisi sözdiziminde, diğer karakter değişmez değer türleri için geçerlidir.

```cpp
#include <iostream>
using namespace std;

int main() {  
    char newline = '\n';
    char tab = '\t';
    char backspace = '\b';
    char backslash = '\\';
    char nullChar = '\0';

    cout << "Newline character: " << newline << "ending" << endl; // Newline character:
                                                                  //  ending
    cout << "Tab character: " << tab << "ending" << endl; // Tab character : ending
    cout << "Backspace character: " << backspace << "ending" << endl; // Backspace character : ending
    cout << "Backslash character: " << backslash << "ending" << endl; // Backslash character : \ending
    cout << "Null character: " << nullChar << "ending" << endl; //Null character:  ending
}  
```  

**Microsoft'a özgü**  

Bir değeri normal bir karakter sabiti (bir önek olmayanlar) oluşturmak için derleyicinin karakterin veya karakter dizisi halinde bir 32 bit tamsayı içindeki 8-bit değerleri tek tırnak işaretleri arasında dönüştürür. Birden çok karakter sabiti içinde karşılık gelen bayt düşük düzey yüksek sıralı gerektiği gibi doldurun. Oluşturmak için bir **char** değeri, derleyici, düşük düzey bayt alır. Oluşturmak için bir **wchar_t** veya `char16_t` değeri, derleyici, düşük düzey sözcüğü alır. Derleyici, herhangi bir BITS atanmış bayt veya word ayarlanırsa, sonuç kesilmiş sizi uyarır.

```cpp
char c0    = 'abcd';    // C4305, C4309, truncates to 'd'
wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'
```  

Sekizli çıkış dizisi, en fazla 3 sekizlik basamak dizisi tarafından izlenen bir ters eğik çizgidir. Görünen üçten fazla basamak içeren sekizli bir atlatma sırasının davranış, sonraki basamak karakteri olarak arkasından bir 3 basamaklı sekizli bir dizisi olarak kabul edilir; Bu, şaşırtıcı sonuçlar verebilirler. Örneğin:

```cpp
char c1 = '\100';   // '@'
char c2 = '\1000';  // C4305, C4309, truncates to '0'
```  

Sekizlik olmayan karakterler içeren görünmesini kaçış dizileri, kalan karakterleridir son sekizlik karaktere kadar sekizlik bir dizisi olarak değerlendirilir. Örneğin:

```cpp
char c3 = '\009';   // '9'
char c4 = '\089';   // C4305, C4309, truncates to '9'
char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'
```  

Onaltılık kaçış sırası karakterinin ardından gelen ters eğik çizgi olduğundan `x`çizgidir onaltılık basamak dizisi. Derleyici Hatası C2153 onaltılık basamak içermeyen kaçış dizisi neden olur: "onaltılık değişmez değerleri en az bir onaltılık basamak olmalıdır". Baştaki sıfırlar dikkate alınmaz. Onaltılık ve onaltılık olmayan karakterler sahip görünür bir kaçış dizisi, onaltılık olmayan karakterleridir son onaltılık karaktere kadar bir onaltılı çıkış dizisi olarak değerlendirilir.   Bir sıradan veya u8 önekli karakter sabit değeri, en yüksek onaltılık değer 0xFF değeridir. Bir L ön eki veya u önekli geniş karakter olarak sabit değeri, en yüksek onaltılık değer 0xFFFF ' dir. Bir U öneki geniş karakter sabit değeri, en yüksek onaltılık değer 0xFFFFFFFF olduğu.

```cpp
char c6 = '\x0050'; // 'P'
char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'
```  

Bir geniş karakter sabiti ön ekine sahip değilse `L` birden fazla karakter içeriyor. ilk karakter değeri alınır. Eşdeğer normal karakter sabiti davranışını, sonraki karakterler yoksayılır.

```cpp
wchar_t w1 = L'\100';   // L'@'
wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored
wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored
wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored
wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored
wchar_t w6 = L'\x0050'; // L'P'
wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored
```  

**END Microsoft özgü**  

Ters eğik çizgi karakteri (\\) bir satırın sonuna yerleştirildiğinde bir satır devam ettirme karakteridir. Ters kesme karakterinin bir karakter sabiti olarak görünmesini istiyorsanız, bir satırda iki ters eğik çizgi yazmanız gerekir (`\\`). Satır devamı karakteri hakkında daha fazla bilgi için bkz: [çeviri aşamaları](../preprocessor/phases-of-translation.md).

###  <a name="bkmk_UCN"></a> Evrensel karakter adları

Karakter değişmez değerleri ve yerel (ham olmayan) dize değişmez değerleri, herhangi bir karakterle evrensel karakter adı tarafından temsil edilebilir.  Evrensel karakter adları \U bir sekiz basamağı Unicode kod noktasını tarafından ya da dört basamak Unicode kod noktasını tarafından izlenen bir önek \u tarafından izlenen bir ön eke göre biçimlendirilir. Tüm sekiz ya da dört basamak sırasıyla, doğru biçimlendirilmiş evrensel karakter adı bulunmalıdır.

```cpp
char u1 = 'A';          // 'A'
char u2 = '\101';       // octal, 'A'
char u3 = '\x41';       // hexadecimal, 'A'
char u4 = '\u0041';     // \u UCN 'A'
char u5 = '\U00000041'; // \U UCN 'A'
```  

#### <a name="surrogate-pairs"></a>Yedek çiftler

Evrensel karakter adları yedek kod noktası aralığı D800 DFFF değerleri kodlanamıyor. Unicode vekil çifti kullanarak evrensel karakter adı belirtin. `\UNNNNNNNN`NNNNNNNN sekiz rakamlı bir kod noktası karakter olduğu. Gerekirse, derleyici bir yedek çifti oluşturur.

C ++ 03, dil yalnızca evrensel karakter adları tarafından temsil edilebilir karakter kümesini izin ve geçerli Unicode karakterler gerçekten sunmadı bazı evrensel karakter adları izin verilir. Bu, C ++ 11'de standart düzeltildi. C ++ 11'de hem karakter ve dize değişmez değerleri ve tanımlayıcıları evrensel karakter adları kullanabilirsiniz.  Evrensel karakter adları hakkında daha fazla bilgi için bkz. [karakter kümesi](../cpp/character-sets.md). Unicode hakkında daha fazla bilgi için bkz. [Unicode](https://msdn.microsoft.com/library/dd374081\(v=vs.85\).aspx). Yedek çiftler hakkında daha fazla bilgi için bkz. [yedek çiftler ve Tamamlayıcı karakterler](/windows/desktop/Intl/surrogates-and-supplementary-characters).

## <a name="string-literals"></a>Dize sabit değerleri

Bir dize sabit değeri, birlikte null ile sonlandırılmış bir dize oluşturan bir karakter dizisi temsil eder. Karakterler çift tırnak işaretleri arasına alınmalıdır. Aşağıdaki tür dize değişmez değerleri vardır:

### <a name="narrow-string-literals"></a>Dar dize değişmez değerleri

Bir dar dize değişmez değeri bir önek olmayan, çift tırnak ayrılmış, null ile sonlandırılmış türü dizisidir `const char[n]`, burada n bayt dizinin uzunluğu. Bir dar dize değişmez değeri çift tırnak işareti hariç tüm grafik karakterlerini içerebilir (`"`), ters eğik çizgi (`\`), veya yeni satır karakteri. Bir dar dize sabitinin bayt, uygun kaçış dizileri yukarıda listelenen ve evrensel karakter adları da içerebilir.

```cpp
const char *narrow = "abcd";

// represents the string: yes\no
const char *escaped = "yes\\no";
```  

#### <a name="utf-8-encoded-strings"></a>UTF-8 olarak kodlanmış dizeler

UTF-8 kodlamalı dize bir u8 öneki, çift tırnak ayrılmış, null ile sonlandırılmış türü dizisidir `const char[n]`, burada n bayt kodlanmış dizinin uzunluğu. U8 önekli dize değişmez değeri çift tırnak işareti hariç tüm grafik karakterlerini içerebilir (`"`), ters eğik çizgi (`\`), veya yeni satır karakteri. Kaçış dizileri, yukarıda listelenen ve herhangi bir evrensel karakter adı, u8 önekli dize değişmez değeri de içerebilir.

```cpp
const char* str1 = u8"Hello World";
const char* str2 = u8"\U0001F607 is O:-)";
```  

### <a name="wide-string-literals"></a>Geniş dize değişmez değerleri

Bir geniş dize değişmez değeri null ile sonlandırılmış bir dizi sabit olan **wchar_t** tarafından öneki '`L`' ve çift tırnak işareti ("), ters eğik çizgi hariç tüm grafik karakterlerini içeren (\\), veya yeni satır karakteri. Bir geniş dize sabit değeri, kaçış dizileri, yukarıda listelenen ve herhangi bir evrensel karakter adı içeriyor olabilir.

```cpp
const wchar_t* wide = L"zyxw";
const wchar_t* newline = L"hello\ngoodbye";
```  

#### <a name="char16t-and-char32t-c11"></a>char16_t ve char32_t (C ++ 11)  

C ++ 11 tanıtır taşınabilir `char16_t` (16-bit Unicode) ve `char32_t` (32-bit Unicode) karakter türleri:

```cpp
auto s3 = u"hello"; // const char16_t*  
auto s4 = U"hello"; // const char32_t*  
```  

### <a name="raw-string-literals-c11"></a>Ham dize değişmez değerleri (C ++ 11)

Ham dize sabit değeri bir null ile sonlandırılmış bir dizidir — herhangi bir karakter türü — çift tırnak işareti ("), ters eğik çizgi de dahil olmak üzere tüm grafik karakterlerini içeren (\\), veya yeni satır karakteri. Ham dize değişmez değerleri, karakter sınıfları kullanan normal ifadelerde ve HTML dizelerinde ve XML dizelerinde sık sık kullanılır. Örnekler için aşağıdaki makaleye bakın: [C ++ 11 Bjarne Stroustrup'un SSS'leri](http://www.stroustrup.com/C++11FAQ.html).

```cpp
// represents the string: An unescaped \ character
const char* raw_narrow = R"(An unescaped \ character)";
const wchar_t* raw_wide = LR"(An unescaped \ character)";
const char*       raw_utf8  = u8R"(An unescaped \ character)";
const char16_t* raw_utf16 = uR"(An unescaped \ character)";
const char32_t* raw_utf32 = UR"(An unescaped \ character)";
```

Sınırlayıcı, işlenmemiş bir dize sabitinin açma parantezinden hemen önce gelen ve kapatma dosyası hemen parantezinden bir kullanıcı tarafından tanımlanan en fazla 16 karakter dizisidir.  Örneğin, `R"abc(Hello"\()abc"` sınırlayıcı sırası `abc` ve dize içerik `Hello"\(`. Hem çift tırnak işaretleri hem parantezler içeren ham dizelerin belirsizliğini gidermek için sınırlayıcı kullanabilirsiniz. Bu, bir derleyici hatasına neden olur:

```cpp
// meant to represent the string: )"
const char* bad_parens = R"()")";  // error C2059
```  

Ancak bir sınırlayıcı bunu çözer:

```cpp
const char* good_parens = R"xyz()")xyz";
```  

İçinde yeni bir satır (atlatma karakteri değil) kaynak olarak bir ham dize değişmez değeri oluşturabilirsiniz:

```cpp
// represents the string: hello
//goodbye
const wchar_t* newline = LR"(hello
goodbye)";
```  

### <a name="stdstring-literals-c14"></a>Std::String değişmez değerleri (C ++ 14)

Std::String sabitleridir "xyx" s olarak temsil edilen kullanıcı tanımlı değişmez değerler (aşağıya bakın), standart kitaplık uygulamalarını (ile bir `s` soneki). Bu tür bir değişmez değer dize türü std::string, std::wstring, std::u32string veya std::u16string Belirtilen önek bağlı olarak geçici bir nesne oluşturur. Önek yok kullanıldığında olarak yukarıdaki bir std::string oluşturulur. L "xyz" s bir std::wstring üretir. u "xyz" s oluşturan bir [std::u16string](../standard-library/string-typedefs.md#u16string)ve U "xyz" s oluşturan bir [std::u32string](../standard-library/string-typedefs.md#u32string).

```cpp
//#include <string>
//using namespace std::string_literals;
string str{ "hello"s };
string str2{ u8"Hello World" };
wstring str3{ L"hello"s };
u16string str4{ u"hello"s };
u32string str5{ U"hello"s };
```  

S soneki ayrıca ham dize değişmez değerleri üzerinde kullanılabilir:

```cpp
u32string str6{ UR"(She said "hello.")"s };
```  

Std::String değişmez değerleri ad alanında tanımlanan `std::literals::string_literals` içinde \<dizesi > üst bilgi dosyası. Çünkü `std::literals::string_literals`, ve `std::literals` her ikisi de olarak bildirilen [satır içi ad alanları](../cpp/namespaces-cpp.md), `std::literals::string_literals` doğrudan ad alanında aitse gibi otomatik olarak kabul edilir `std`.

### <a name="size-of-string-literals"></a>Dize değişmez değerlerinin boyutu

ANSI karakter için\* dizeler ve diğer tek baytlık kodlamaları (UTF-8), bir dize sabitinin boyutu (bayt cinsinden) karakter sayısına 1 sondaki null karakter olduğu. Diğer tüm dize türleri için boyutu kesinlikle karakter sayısı için ilgili değildir. UTF-8 bazı kodlamak için en fazla dört karakter öğeleri kullanan *kod birimi*, char16_t veya UTF-16, tek bir kodlama için (toplam dört baytı için) iki öğe kullanabilir gibi kodlanmış wchar_t'ı ve *kod birimi*.   Bu örnek, bir geniş dize boyutunu bayt cinsinden sabit bir değer gösterir:

```cpp
const wchar_t* str = L"Hello!";
const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);
```  

Dikkat `strlen()` ve `wcslen()` boyutu dize türü öğesi boyutuna eşittir sondaki boş karakter boyutunu kapsamadığını: tek baytlık bir karakter üzerinde\* dize, wchar_t iki bayt\* veya char16_t\*dizeleri ve char32_t üzerindeki dört bayt\* dizeleri.

Bir dize sabitinin en fazla uzunluğu 65535 bayttır. Bu sınır hem dar dize değişmez değerleri hem de geniş dize değişmez değerleri için geçerlidir.

### <a name="modifying-string-literals"></a>Dize sabitlerini değiştirme

Dize değişmez değerleri (std:string değişmez değerler dahil değil) için bunları değiştirmeye çalışmak; Örneğin, `str[2] = 'A'`— bir derleyici hatasına neden olur.

**Microsoft'a özgü**

Visual c++'ta const olmayan bir işaretçi başlatmak için bir dize sabit değeri kullanabilirsiniz **char** veya **wchar_t**. Bu C99 kodunda izin verilir, ancak C ++ 98'de kullanım dışı ve C ++ 11'de kaldırılmıştır. Dize değiştirme girişimi şu örnekte olduğu gibi erişim ihlaline neden olur:

```cpp
wchar_t* str = L"hello";
str[2] = L'a'; // run-time error: access violation
```  

Bir dize sabit değeri ayarladığınızda non_const karakter işaretçisi dönüştürüldüğünde hata dönüştüğünde derleyicinin neden olabilir [/ZC: strictstrings (dize değişmez değer türü dönüşümünü devre dışı bırakma)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) derleyici seçeneği. Bunun için standartlara uygun taşınabilir kod öneririz. Bu ayrıca kullanmak iyi bir uygulamadır **otomatik** doğru (const) türe çözümlendiğinden, dize sabit işaretçileri, bildirmek için anahtar sözcüğü. Örneğin, bu kod örneği, bir dize değişmez deşerini derleme sırasında yazma denemsi yakalamıştır:

```cpp
auto str = L"hello";
str[2] = L'a'; // C3892: you cannot assign to a variable that is const.
```  

Bazı durumlarda, yürütülebilir dosyada yer kazanmak için aynı olan dize değişmezleri havuza. Düz dize havuzu içinde belirli her başvuru bellekte aynı konuma işaret edecek şekilde düz dize başvurularını derleyici nedenlerini dize sabit değerinin ayrı bir örneğine işaret edecek. Dize havuzunu etkinleştirmek için [/GF](../build/reference/gf-eliminate-duplicate-strings.md) derleyici seçeneği.

**End Microsoft özgü**

### <a name="concatenating-adjacent-string-literals"></a>Bitişik dize değişmez değerlerini birleştirme

Bitişik geniş veya dar dize değişmez değerleri sıralanır. Bu bildirim:

```cpp
char str[] = "12" "34";
```  

bildirimle aynıdır:

```cpp
char atr[] = "1234";
```  

Bu bildirim ve:

```cpp
char atr[] =  "12\
34";
```  

Dize değişmez değerleri belirtmek için katıştırılmış onaltılık atlatma kodları kullanma beklenmedik sonuçlara neden olabilir. Karakterleri, ardından da f ASCII 5 karakteri içeren bir dize değişmez değeri oluşturmak aşağıdaki istemektedir i, v ve e:

```cpp
"\x05five"
```  

Geldiği bir alt çizgi için ASCII kodu olan onaltılık 5F ve ardından, gerçek sonuç, i, v ve e. Doğru sonuçları elde etmek için bunlardan birini kullanabilirsiniz:

```cpp
"\005five"     // Use octal literal.
"\x05" "five"  // Use string splicing.
```  

Std::String değişmez değerleri, çünkü bunlar std::string türleri birleştirilmiş ile + için tanımlanan işleci [basic_string](../standard-library/basic-string-class.md) türleri. Bitişik dize değişmez değerleri aynı şekilde de birleştirilebilir. Her iki durumda da, kodlama dizesi ve soneki eşleşmesi gerekir:

```cpp
auto x1 = "hello" " " " world"; // OK
auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix
auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes
auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes
```  

### <a name="string-literals-with-universal-character-names"></a>Evrensel karakter adları dize sabit değerleri

Evrensel karakter adı dize türünde bir veya daha fazla karakter olarak kodlanmış sürece özgün (ham olmayan) dize değişmez değerleri, herhangi bir karakteri temsil etmesi için evrensel karakter adları kullanabilir.  Örneğin, genişletilmiş bir karakteri temsil eden bir evrensel karakter adı bir dar dize ANSI kod sayfası kullanılarak kodlanamaz, ancak bazı çok baytlı kod sayfaları veya UTF-8 dize veya bir geniş dize dar Dizelerdeki kodlanabilir. C ++ 11'de, char16_t tarafından Genişletilmiş Unicode desteği\* ve char32_t\* dize türleri:

```cpp
// ASCII smiling face
const char*     s1 = ":-)";

// UTF-16 (on Windows) encoded WINKING FACE (U+1F609)  
const wchar_t*  s2 = L"😉 = \U0001F609 is ;-)";

// UTF-8  encoded SMILING FACE WITH HALO (U+1F607)  
const char*     s3 = u8"😇 = \U0001F607 is O:-)";

// UTF-16 encoded SMILING FACE WITH OPEN MOUTH (U+1F603)  
const char16_t* s4 = u"😃 = \U0001F603 is :-D";

// UTF-32 encoded SMILING FACE WITH SUNGLASSES (U+1F60E)  
const char32_t* s5 = U"😎 = \U0001F60E is B-)";
```  

## <a name="see-also"></a>Ayrıca bkz.

[Karakter kümesi](../cpp/character-sets.md)   
[Sayısal, Boole ve işaretçi değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md)   
[Kullanıcı Tanımlı Sabit Değerler](../cpp/user-defined-literals-cpp.md)
