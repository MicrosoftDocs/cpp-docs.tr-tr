---
title: Dize ve karakter değişmez değerleri (C++)
description: C++ ' da dize ve karakter değişmez değerlerini bildirme ve tanımlama.
ms.date: 02/18/2020
f1_keywords:
- R
- L
- u
- u8
- LR
- uR
- u8R
helpviewer_keywords:
- literal strings [C++]
- string literals [C++]
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
ms.openlocfilehash: 60389ecf01cf16b1cf2a86fc68da94bd558b6d83
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231136"
---
# <a name="string-and-character-literals-c"></a>Dize ve karakter değişmez değerleri (C++)

C++ çeşitli dize ve karakter türlerini destekler ve bu türlerin her birinin sabit değerlerini ifade etmek için yollar sağlar. Kaynak kodunuzda karakter kümesi kullanarak karakter ve dize sabit değerlerinin içeriğini ifade edersiniz. Evrensel karakter adları ve kaçış karakterleri yalnızca temel kaynak karakter kümesini kullanarak herhangi bir dize ifade etmeniz için izin verir. Ham dize değişmez değeri kaçış karakterleri kullanmaktan kaçınmanızı sağlar ve tüm dize sabit değerlerini ifade etmek için kullanılabilir. `std::string`Ek oluşturma veya dönüştürme adımları gerçekleştirmek zorunda kalmadan de sabit değerler oluşturabilirsiniz.

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

    // Multicharacter literals
    auto m0 = 'abcd'; // int, value 0x61626364

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

Dize değişmez değerleri, `u8` `L` `u` `U` sırasıyla dar karakteri (tek baytlık veya çok baytlı), UTF-8, geniş karakter (UCS-2 veya UTF-16), UTF-16 ve UTF-32 kodlamaları belirtmek için ön ek veya,, ve öneklere sahip olamaz. Ham dize değişmez değeri,, `R` , `u8R` `LR` `uR` ve `UR` Bu kodlamaları için ham sürüm eşdeğerlerine yönelik öneklere sahip olabilir.  Geçici veya statik değerler oluşturmak için `std::string` , bir sonek ile dize değişmezlerini veya ham dize değişmez değerlerini kullanabilirsiniz `s` . Daha fazla bilgi için aşağıdaki [dize sabit değerleri](#string-literals) bölümüne bakın. Temel kaynak karakter kümesi ve evrensel karakter adları hakkında daha fazla bilgi edinmek ve kaynak kodunuzda genişletilmiş codepages 'ten karakterler kullanmak için bkz. [karakter kümeleri](../cpp/character-sets.md).

## <a name="character-literals"></a>Karakter sabit değerleri

Bir *karakter sabit değeri* sabit bir karakterden oluşur. Tek tırnak işaretleriyle çevrelenen karakterle temsil edilir. Beş tür karakter değişmezi vardır:

- Türünün sıradan karakter sabit değerleri **`char`** , örneğin`'a'`

- Örneğin, UTF-8 karakter değişmez değerleri **`char`** ( **`char8_t`** c++ 20 ' de), örneğin`u8'a'`

- Türünde geniş karakter sabit değerleri **`wchar_t`** , örneğin`L'a'`

- UTF-16 karakter değişmez değerleri **`char16_t`** , örneğin`u'a'`

- UTF-32 karakter değişmez değerleri **`char32_t`** , örneğin`U'a'`

Bir karakter sabiti için kullanılan karakter, ayrılmış karakterler ters eğik çizgi ( **`\`** ), tek tırnak işareti ( **`'`** ) veya yeni satır dışında herhangi bir karakter olabilir. Ayrılmış karakterler, bir kaçış sırası kullanılarak belirtilebilir. Tür karakteri tutacak kadar büyük olduğu sürece, evrensel karakter adları kullanılarak karakterler belirtilebilir.

### <a name="encoding"></a>Encoding

Karakter değişmez değerleri, ön ekine göre farklı şekilde kodlanır.

- Öneki olmayan bir karakter sabit değeri, normal bir karakter sabit değeri değildir. Yürütme karakter kümesinde gösterilebilen tek bir karakter, kaçış sırası veya evrensel karakter adı içeren sıradan bir karakter sabit değerinin değeri, yürütme karakter kümesindeki kodlamasının sayısal değerine eşit bir değere sahiptir. Birden fazla karakter, kaçış dizisi veya evrensel karakter adı içeren sıradan bir karakter sabit değeri *çok karakterli bir sabit*değerdir. Yürütme karakter kümesinde temsil edilemeden çok karakterli bir sabit değer veya normal bir karakter sabit **`int`** değeri tür ve uygulama tanımlı. MSVC için aşağıdaki **Microsoft 'a özgü** bölümüne bakın.

- Önekiyle başlayan bir karakter sabit değeri, `L` geniş karakterli bir sabit değerdir. Tek bir karakter, kaçış dizisi veya evrensel karakter adı içeren geniş karakterli bir sabit değerin değeri, yürütme geniş karakter kümesinde, karakter değişmez değeri, yürütme genelindeki karakter kümesinde bir gösterimi olmadığından, bu değerin uygulama tanımlı olması durumunda, kendi kodlamasının sayısal değerine eşit bir değere sahiptir. Birden çok karakter, kaçış sırası veya evrensel karakter adı içeren bir geniş karakterli sabit değerin değeri uygulama tanımlı. MSVC için aşağıdaki **Microsoft 'a özgü** bölümüne bakın.

- Önekiyle başlayan bir karakter sabit değeri `u8` UTF-8 karakter sabiti olur. Tek bir karakter, kaçış dizisi veya evrensel karakter adı içeren bir UTF-8 karakter sabit değerinin değeri, tek bir UTF-8 kod birimi ile temsil ediliyorsa (C0 denetimlerine ve temel Latin Unicode bloğuna karşılık gelen) ISO 10646 kod noktası değerine eşit bir değere sahiptir. Değer tek bir UTF-8 kod birimi ile temsil ediülmediği takdirde, program hatalı biçimlendirilmiş olur. Birden fazla karakter, kaçış sırası veya evrensel karakter adı içeren UTF-8 karakter sabit değeri hatalı biçimlendirilmiş.

- Önekiyle başlayan bir karakter sabit değeri `u` UTF-16 karakter sabiti olur. Tek bir karakter, kaçış dizisi veya evrensel karakter adı içeren bir UTF-16 karakter sabit değerinin değeri, tek bir UTF-16 kod birimi (temel çok dilli düzlemine karşılık gelen) ile temsil edilebiliyorsanız ISO 10646 kod noktası değerine eşit bir değere sahiptir. Değer tek bir UTF-16 kod birimi ile temsil ediülmediği takdirde, program hatalı biçimlendirilmiş olur. Birden fazla karakter, kaçış sırası veya evrensel karakter adı içeren UTF-16 karakter sabit değeri hatalı biçimlendirilmiş.

- Önekiyle başlayan bir karakter sabit değeri `U` UTF-32 karakter sabit değeri olur. Tek bir karakter, kaçış dizisi veya evrensel karakter adı içeren bir UTF-32 karakter sabit değerinin değeri ISO 10646 kod noktası değerine eşit bir değere sahiptir. Birden fazla karakter, kaçış sırası veya evrensel karakter adı içeren bir UTF-32 karakter sabit değeri hatalı biçimlendirilmiş.

### <a name="escape-sequences"></a><a name="bkmk_Escape"></a>Kaçış dizileri

Üç tür kaçış dizisi vardır: basit, sekizlik ve onaltılı. Kaçış dizileri aşağıdaki değerlerden herhangi biri olabilir:

|Değer|Kaçış sırası|
|-----------|---------------------|
| yeni satır | \\No |
| ters eğik çizgi | \\\\ |
| yatay sekme | \\şı |
| soru işareti | ? or \\ ? |
| dikey sekme | \\Yönetim |
| tek tırnak | \\' |
| geri al | \\kenarı |
| Çift tırnak | \\" |
| satır başı | \\sağ |
| null karakter | \\0 |
| Form akışı | \\vadeli |
| sekizlik | \\Ooo |
| uyarı (zil) | \\a |
| onaltılık | \\xhhh |

Sekizlik kaçış sırası, bir ters eğik çizgidir ve bir ile üç sekizlik basamak dizisini izler. Sekizlik kaçış sırası, üçüncü sayıdan daha önce karşılaşılırsa, sekizlik basamak olmayan ilk karakterden sona erer. Mümkün olan en yüksek sekizlik değer `\377` .

Onaltılı kaçış sırası, ardından karakter ve ardından `x` bir veya daha fazla onaltılı basamak dizisi gelen bir ters eğik çizgidir. Öndeki sıfırlar yok sayılır. Sıradan veya U8 önekli bir karakter sabit değerinde, en yüksek onaltılı değer 0xFF ' dir. L önekli veya u önekli geniş karakter sabit değerinde en yüksek onaltılı değer 0xFFFF ' dir. U ön eki olan geniş karakter sabit değerinde, en yüksek onaltılı değer 0xFFFFFFFF ' dir.

Bu örnek kod, normal karakter değişmez değerleri kullanılarak atlanan karakterlerin bazı örneklerini gösterir. Aynı kaçış dizisi sözdizimi, diğer karakter sabit türleri için geçerlidir.

```cpp
#include <iostream>
using namespace std;

int main() {
    char newline = '\n';
    char tab = '\t';
    char backspace = '\b';
    char backslash = '\\';
    char nullChar = '\0';

    cout << "Newline character: " << newline << "ending" << endl;
    cout << "Tab character: " << tab << "ending" << endl;
    cout << "Backspace character: " << backspace << "ending" << endl;
    cout << "Backslash character: " << backslash << "ending" << endl;
    cout << "Null character: " << nullChar << "ending" << endl;
}
/* Output:
Newline character:
ending
Tab character:  ending
Backspace character:ending
Backslash character: \ending
Null character:  ending
*/
```

Ters eğik çizgi karakteri ( **`\`** ) satırın sonuna yerleştirildiğinde bir satır devamlılık karakteridir. Ters eğik çizgi karakterinin bir karakter sabit değeri olarak görünmesini istiyorsanız, bir satıra () iki ters eğik çizgi yazmanız gerekir **`\\`** . Satır devamlılık karakteri hakkında daha fazla bilgi için bkz. [Çeviri aşamaları](../preprocessor/phases-of-translation.md).

#### <a name="microsoft-specific"></a>Microsoft'a özgü

Dar çok karakterli bir değişmez değerden değer oluşturmak için, derleyici karakter veya karakter dizisini 32 bitlik bir tamsayı içindeki tek tırnak arasına 8 bitlik değerlere dönüştürür. Sabit değerindeki birden fazla karakter, gereken baytları yüksek sıralı ve düşük sıraya göre doldurur. Daha sonra derleyici, her zamanki kuralları takip eden hedef türüne göre tamsayıyı dönüştürür. Örneğin, bir değer oluşturmak için **`char`** , derleyici düşük sıra baytı alır. Bir **`wchar_t`** veya değeri oluşturmak için **`char16_t`** , derleyici düşük sıralı kelimeyi alır. Derleyici, atanan Byte veya Word üzerinde herhangi bir bit ayarlandıysa sonucun kesileceğini uyarır.

```cpp
char c0    = 'abcd';    // C4305, C4309, truncates to 'd'
wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'
int i0     = 'abcd';    // 0x61626364
```

Üçten fazla basamak içeren bir Sekizli kaçış dizisi, 3 basamaklı sekizlik bir sıra olarak değerlendirilir ve ardından, daha sonra gelen basamaklar çok karakterli bir değişmez değer olarak daha sonra, ortaya çıkan sonuçlara izin verebilir. Örnek:

```cpp
char c1 = '\100';   // '@'
char c2 = '\1000';  // C4305, C4309, truncates to '0'
```

Sekizlik olmayan karakterler içeren kaçış dizileri, son sekizlik karaktere kadar sekizlik bir sıra olarak değerlendirilir ve ardından kalan karakterler çok karakterli bir değişmez değerde sonraki karakterler olarak değerlendirilir. İlk sekizlik olmayan karakter ondalık bir sayı ise, uyarı C4125 oluşturulur. Örnek:

```cpp
char c3 = '\009';   // '9'
char c4 = '\089';   // C4305, C4309, truncates to '9'
char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'
```

Daha yüksek bir değere sahip sekizlik kaçış sırası, `\377` hataya neden C2022: ' Decimal-of *-Decimal*': karakter için çok büyük.

Onaltılık ve onaltılık olmayan karakterler içeren bir kaçış dizisi, son onaltılı karaktere kadar bir onaltılık kaçış sırası içeren çok karakterli değişmez değer olarak değerlendirilir ve ardından onaltılık olmayan karakterler gelir. Onaltılı basamaklar içermeyen bir onaltılı kaçış dizisi, derleyici hatası C2153: "onaltılı değişmez değerler en az bir onaltılı basamak içermelidir".

```cpp
char c6 = '\x0050'; // 'P'
char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'
```

Önekli geniş bir karakter sabit değeri `L` çok karakterli bir dizi içeriyorsa, değer ilk karakterden alınır ve derleyici uyarı C4066 başlatır. Sonraki karakterler, eşdeğer sıradan çoklu karakter sabit değerinin davranışının aksine yok sayılır.

```cpp
wchar_t w1 = L'\100';   // L'@'
wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored
wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored
wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored
wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored
wchar_t w6 = L'\x0050'; // L'P'
wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored
```

**Microsoft 'a özgü** bölüm burada sona erer.

### <a name="universal-character-names"></a><a name="bkmk_UCN"></a>Evrensel karakter adları

Karakter değişmezleri ve yerel (ham olmayan) dize sabit değerleri içinde, herhangi bir karakter bir evrensel karakter adı ile temsil edilebilir.  Evrensel karakter adları `\U` , daha sonra sekiz basamaklı bir Unicode kod noktası veya ön ek ve `\u` dört basamaklı bir Unicode kod noktası tarafından oluşturulan bir ön ek tarafından oluşturulur. Doğru biçimlendirilmiş bir evrensel karakter adı oluşturmak için sırasıyla tüm sekiz veya dört basamak mevcut olmalıdır.

```cpp
char u1 = 'A';          // 'A'
char u2 = '\101';       // octal, 'A'
char u3 = '\x41';       // hexadecimal, 'A'
char u4 = '\u0041';     // \u UCN 'A'
char u5 = '\U00000041'; // \U UCN 'A'
```

#### <a name="surrogate-pairs"></a>Vekil çiftleri

Evrensel karakter adları, D800-DFFF yedek kod noktası aralığındaki değerleri kodlayamıyor. Unicode vekil çiftleri için, kullanarak evrensel karakter adını belirtin `\UNNNNNNNN` , burada NNNNNNNN karakter için sekiz basamaklı bir kod noktasıdır. Derleyici, gerekirse bir vekil çift oluşturur.

C++ 03 ' de, dil yalnızca evrensel karakter adlarıyla temsil edilecek bir karakter alt kümesine izin verilir ve gerçekte geçerli bir Unicode karakteri temsil etmeyen bazı evrensel karakter adlarına izin verilir. Bu hata C++ 11 standardında düzeltildi. C++ 11 ' de, hem karakter hem de dize sabit değerleri ve tanımlayıcılar evrensel karakter adlarını kullanabilir.  Evrensel karakter adları hakkında daha fazla bilgi için bkz. [karakter kümeleri](../cpp/character-sets.md). Unicode hakkında daha fazla bilgi için bkz. [Unicode](/windows/win32/intl/unicode). Vekil çiftleri hakkında daha fazla bilgi için bkz. [vekil çiftleri ve tamamlayıcı karakterler](/windows/win32/Intl/surrogates-and-supplementary-characters).

## <a name="string-literals"></a><a name="string-literals"></a>Dize sabit değerleri

Dize sabit değeri, birlikte null ile sonlandırılmış bir dize oluşturan bir karakter dizisini temsil eder. Karakterler çift tırnak işaretleri arasında olmalıdır. Aşağıdaki tür dize sabit değerleri vardır:

### <a name="narrow-string-literals"></a>Dar dize sabit değerleri

Dar dize sabit değeri, ön eki olmayan, çift tırnak işareti ayrılmış, null sonlandırılmış bir dizidir `const char[n]` , burada n dizinin bayt cinsinden uzunluğudur. Dar dize sabit değeri, çift tırnak işareti ( `"` ), ters eğik çizgi ( `\` ) veya yeni satır karakteri dışında herhangi bir grafik karakteri içerebilir. Dar dize sabit değeri, yukarıda listelenen kaçış sıralarını ve bir bayta sığan evrensel karakter adlarını da içerebilir.

```cpp
const char *narrow = "abcd";

// represents the string: yes\no
const char *escaped = "yes\\no";
```

#### <a name="utf-8-encoded-strings"></a>UTF-8 kodlu dizeler

UTF-8 ile kodlanmış dize, U8-önekli, çift tırnak sınırlı, null sonlandırılmış bir dizidir `const char[n]` , burada *n* , kodlanan dizenin bayt cinsinden uzunluğudur. U8-önekli bir dize sabit değeri, çift tırnak işareti ( `"` ), ters eğik çizgi ( `\` ) veya yeni satır karakteri dışında herhangi bir grafik karakteri içerebilir. U8-önekli bir dize değişmez değeri, yukarıda listelenen kaçış sıralarını ve tüm evrensel karakter adlarını da içerebilir.

```cpp
const char* str1 = u8"Hello World";
const char* str2 = u8"\U0001F607 is O:-)";
```

### <a name="wide-string-literals"></a>Geniş dize sabit değerleri

Geniş dize sabit değeri, **`wchar_t`** ' ' öğesinin ön eki olan `L` ve çift tırnak işareti ( **`"`** ), ters eğik çizgi ( **`\`** ) veya yeni satır karakteri hariç tüm grafik karakterlerini içeren null ile sonlandırılmış bir dizidir. Geniş dize sabit değeri yukarıda listelenen çıkış dizilerini ve herhangi bir evrensel karakter adını içerebilir.

```cpp
const wchar_t* wide = L"zyxw";
const wchar_t* newline = L"hello\ngoodbye";
```

#### <a name="char16_t-and-char32_t-c11"></a>char16_t ve char32_t (C++ 11)

C++ 11 taşınabilir **`char16_t`** (16 bit Unicode) ve **`char32_t`** (32 bit Unicode) karakter türlerini tanıtır:

```cpp
auto s3 = u"hello"; // const char16_t*
auto s4 = U"hello"; // const char32_t*
```

### <a name="raw-string-literals-c11"></a>Ham dize değişmez değerleri (C++ 11)

Bir ham dize değişmez değeri, çift tırnak işareti ( **`"`** ), ters eğik çizgi ( **`\`** ) veya yeni satır karakteri de dahil olmak üzere herhangi bir grafik karakteri içeren herhangi bir karakter türündeki null sonlandırılmış dizidir. Ham dize değişmez değerleri genellikle karakter sınıfları kullanan normal ifadelerde ve HTML dizeleri ve XML dizeleri ile kullanılır. Örnekler için aşağıdaki makaleye bakın: [Bjarne Stroustrup 'ın c++ 11 hakkında SSS](http://www.stroustrup.com/C++11FAQ.html).

```cpp
// represents the string: An unescaped \ character
const char* raw_narrow = R"(An unescaped \ character)";
const wchar_t* raw_wide = LR"(An unescaped \ character)";
const char*       raw_utf8  = u8R"(An unescaped \ character)";
const char16_t* raw_utf16 = uR"(An unescaped \ character)";
const char32_t* raw_utf32 = UR"(An unescaped \ character)";
```

Sınırlayıcı, bir ham dize değişmez değerinin açma parantezinden hemen önce gelen ve en fazla 16 karakterden oluşan Kullanıcı tanımlı bir dizidir ve hemen ardından sağ parantez izler.  Örneğin, `R"abc(Hello"\()abc"` sınırlayıcı dizisinde `abc` ve dize içeriği `Hello"\(` . Çift tırnak işareti ve parantezler içeren ham dizeleri ayırt etmek için sınırlayıcı kullanabilirsiniz. Bu dize değişmez değeri bir derleyici hatasına neden olur:

```cpp
// meant to represent the string: )"
const char* bad_parens = R"()")";  // error C2059
```

Ancak bir sınırlayıcı bunu çözer:

```cpp
const char* good_parens = R"xyz()")xyz";
```

Kaynakta bir yeni satır (kaçan karakteri değil) içeren bir ham dize sabit değeri oluşturabilirsiniz:

```cpp
// represents the string: hello
//goodbye
const wchar_t* newline = LR"(hello
goodbye)";
```

### <a name="stdstring-literals-c14"></a>std:: String değişmez değerleri (C++ 14)

`std::string`değişmez değerler, Kullanıcı tanımlı değişmez değerler (aşağıya bakın) `"xyz"s` (bir sonek ile) olarak temsil edilen standart kitaplık uygulamalarıdır `s` . Bu tür bir dize değişmez değeri,,, `std::string` `std::wstring` `std::u32string` veya `std::u16string` belirtilen öneke bağlı olarak,, veya türünde geçici bir nesne oluşturur. Bir önek kullanılmazsa, yukarıdaki gibi, bir `std::string` oluşturulur. `L"xyz"s`bir oluşturur `std::wstring` . `u"xyz"s`[std:: u16string](../standard-library/string-typedefs.md#u16string)üretir ve `U"xyz"s` [std:: u32string](../standard-library/string-typedefs.md#u32string)üretir.

```cpp
//#include <string>
//using namespace std::string_literals;
string str{ "hello"s };
string str2{ u8"Hello World" };
wstring str3{ L"hello"s };
u16string str4{ u"hello"s };
u32string str5{ U"hello"s };
```

`s`Sonek, ham dize değişmez değerlerinde de kullanılabilir:

```cpp
u32string str6{ UR"(She said "hello.")"s };
```

`std::string`değişmez değerler, `std::literals::string_literals` üstbilgi dosyasındaki ad alanında tanımlanır \<string> . `std::literals::string_literals`Ve `std::literals` her ikisi de [satır içi ad alanları](../cpp/namespaces-cpp.md)olarak bildirildiği için, `std::literals::string_literals` doğrudan ad alanına ait gibi otomatik olarak kabul edilir `std` .

### <a name="size-of-string-literals"></a>Dize sabit değerlerinin boyutu

ANSI `char*` dizeleri ve diğer tek baytlı kodlamalar (UTF-8 değil) için, bir dize sabit değerinin boyutu (bayt olarak), Sonlandırıcı null karakteri için karakter sayısı artı 1 ' dir. Diğer tüm dize türleri için boyut, tam olarak karakter sayısıyla ilgili değildir. UTF-8 **`char`** , bazı *kod birimlerini*kodlamak için en fazla dört öğe KULLANıR ve **`char16_t`** veya **`wchar_t`** UTF-16 olarak kodlanarak tek bir *kod birimini*kodlamak için iki öğe (Toplam dört bayt için) kullanılabilir. Bu örnekte, bir geniş dize sabit değerinin bayt cinsinden boyutu gösterilmektedir:

```cpp
const wchar_t* str = L"Hello!";
const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);
```

Bu, `strlen()` `wcslen()` boyutu dize türünün öğe boyutuna eşit olan Sonlandırıcı null karakterinin boyutunu eklemeyin: bir `char*` veya dizedeki bir bayt `char8_t*` , iki bayt `wchar_t*` veya `char16_t*` dizeler ve dizeler üzerinde dört bayt `char32_t*` .

Dize sabit değerinin uzunluk üst sınırı 65.535 bayttır. Bu sınır hem dar dize değişmez değerleri hem de geniş dize sabit değerleri için geçerlidir.

### <a name="modifying-string-literals"></a>Dize sabit değerlerini değiştirme

Dize sabit değerleri ( `std::string` değişmez değerler dahil değil) sabitler olduğundan, bunlar değiştirilmeye çalışılıyor — Örneğin, `str[2] = 'A'` bir derleyici hatasına neden olur.

#### <a name="microsoft-specific"></a>Microsoft'a özgü

Microsoft C++ ' da, const olmayan veya bir işaretçi başlatmak için bir dize sabiti kullanabilirsiniz **`char`** **`wchar_t`** . Bu const olmayan başlatmaya C99 kodunda izin verilir, ancak C++ 98 ' de kullanım dışıdır ve C++ 11 ' de kaldırılır. Bu örnekte olduğu gibi, dizeyi değiştirme girişimi bir erişim ihlaline neden olur:

```cpp
wchar_t* str = L"hello";
str[2] = L'a'; // run-time error: access violation
```

Bir dize sabit değeri, [ `/Zc:strictStrings` (dize sabit değer dönüştürme dönüşümü devre dışı bırak)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) derleyici seçeneğini belirlediğinizde const olmayan bir karakter işaretçisine dönüştürüldüğünde derleyicinin hata vermesine neden olabilir. Standart uyumlu taşınabilir kod için önerilir. **`auto`** Doğru (const) tür olarak çözümlendiğinden, dize değişmez değer başlatılmış işaretçiler bildirmek için anahtar sözcüğünü kullanmak da iyi bir uygulamadır. Örneğin, bu kod örneği derleme zamanında bir dize hazır bilgisine yazma girişimini yakalar:

```cpp
auto str = L"hello";
str[2] = L'a'; // C3892: you cannot assign to a variable that is const.
```

Bazı durumlarda, yürütülebilir dosyada yer kazanmak için özdeş dize sabit değerleri havuza alınabilir. Dize-sabit değer havuzundaki derleyici, belirli bir dize değişmez değerine tüm başvuruların, her başvuru için dize sabit değerinin ayrı bir örneğine sahip olması yerine, bellekteki aynı konuma işaret etmesine neden olur. Dize havuzunu etkinleştirmek için [`/GF`](../build/reference/gf-eliminate-duplicate-strings.md) derleyici seçeneğini kullanın.

**Microsoft 'a özgü** bölüm burada sona erer.

### <a name="concatenating-adjacent-string-literals"></a>Bitişik dize değişmez değerlerini bitiştirme

Bitişik geniş veya dar dize sabit değerleri bitiştirilir. Bu bildirim:

```cpp
char str[] = "12" "34";
```

Bu bildirimle aynıdır:

```cpp
char atr[] = "1234";
```

bu bildirime:

```cpp
char atr[] =  "12\
34";
```

Dize değişmezlerini belirtmek için gömülü onaltılı kaçış kodları kullanmak beklenmeyen sonuçlara neden olabilir. Aşağıdaki örnek, ASCII 5 karakteri ve ardından f, i, v ve e karakterlerinden oluşan bir dize sabit değeri oluşturmayı arar:

```cpp
"\x05five"
```

Gerçek sonuç, alt çizgi için ASCII kodu, ardından i, v ve e karakterlerinden oluşan bir onaltılı 5F 'dir. Doğru sonucu elde etmek için şu kaçış dizilerinden birini kullanabilirsiniz:

```cpp
"\005five"     // Use octal literal.
"\x05" "five"  // Use string splicing.
```

`std::string`türler oldukları için değişmez değerler, `std::string` **`+`** türler için tanımlanan işleçle birleştirilebilir [`basic_string`](../standard-library/basic-string-class.md) . Ayrıca bitişik dize değişmez değerleri ile aynı şekilde birleştirilebilir. Her iki durumda da, dize kodlaması ve sonekin eşleşmesi gerekir:

```cpp
auto x1 = "hello" " " " world"; // OK
auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix
auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes
auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes
```

### <a name="string-literals-with-universal-character-names"></a>Evrensel karakter adlarıyla dize sabit değerleri

Yerel (ham olmayan) dize sabit değerleri, evrensel karakter adı, dize türünde bir veya daha fazla karakter olarak kodlanabilen herhangi bir karakteri temsil etmek için evrensel karakter adları kullanabilir.  Örneğin, genişletilmiş bir karakteri temsil eden bir evrensel karakter adı, ANSI kod sayfası kullanılarak dar bir dizede kodlanamaz, ancak bazı çok baytlı kod sayfalarındaki veya UTF-8 dizelerindeki veya geniş bir dizedeki dar dizeler halinde kodlanabilen. C++ 11 ' de Unicode desteği `char16_t*` ve `char32_t*` dize türleriyle genişletilir:

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

[Karakter kümeleri](../cpp/character-sets.md)\
[Sayısal, Boole ve işaretçi değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md)\
[Kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md)
