---
title: Dize ve karakter değişmez değerleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
caps.latest.revision: 36
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8714ff649471b0f84e11a65ae4100c8facb06c52
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="string-and-character-literals--c"></a>Dize ve karakter değişmez değerleri (C++)
C++ çeşitli dize ve karakter türleri destekler ve bu türlerin her biri değişmez değerler express için yöntemler sağlar. Kaynak kodunuz bir karakter kümesini kullanarak, karakter ve dize değişmez değerleri içeriğini express. Evrensel karakter adları ve kaçış karakterleri yalnızca temel kaynak karakter kümesi kullanılarak herhangi bir dize express olanak sağlar. Ham dize sabit değeri kaçış karakterleri kullanmaktan kaçının olanak tanır ve dize değişmez değerleri tüm türleri ifade etmek için kullanılabilir. Ek yapım veya dönüştürme adımları gerçekleştirmek zorunda kalmadan std::string değişmez değerleri de oluşturabilirsiniz.  
  
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
  
 Dize değişmez değerler, önek olabilir veya `u8`, `L`, `u`, ve `U` önekleri belirtmek için bir karakter (tek baytlı veya çok bayt), UTF-8, geniş karakter (UCS-2 veya UTF-16), UTF-16 ve UTF-32 kodlamaları sırasıyla daraltın. Ham dize sabit değeri olabilir `R`, `u8R`, `LR`, `uR` ve `UR` bu Kodlamalar ham sürüm eşdeğerlerini öneklerini.  Geçici veya statik std::string değerleri oluşturmak için dize değişmez değerleri veya ham dize değişmez değerleri ile kullanabilirsiniz bir `s` soneki. Daha fazla bilgi için aşağıdaki dize değişmez değerleri bölümüne bakın. Temel kaynak karakteri hakkında daha fazla bilgi için ayarlamak, evrensel karakter adları ve kaynak kodunuzu genişletilmiş kod sayfaları karakterler kullanarak görmek [karakter kümesi](../cpp/character-sets.md).  
  
## <a name="character-literals"></a>Karakter değişmez değerleri  
 A *karakter sabit değeri* sabit bir karakteri oluşur. Tek tırnak işaretleri karakter ile temsil edilir. Karakter değişmez değerleri beş tür vardır:  
  
-   Sıradan karakter değişmez değerleri türü `char`, örneğin `'a'`  
  
-   UTF-8 karakter değişmez değerleri türü `char`, örneğin `u8'a'`  
  
-   Joker karakter değişmez değerleri türü `wchar_t`, örneğin `L'a'`  
  
-   UTF-16 karakter değişmez değerleri türü `char16_t`, örneğin `u'a'`  
  
-   UTF-32 karakter değişmez değerleri türü `char32_t`, örneğin `U'a'`  
  
 Karakter sabit değeri için kullanılan karakter ayrılmış karakterleri ters eğik çizgi dışında herhangi bir karakter olabilir ('\\'), tek tırnak işareti (') ya da yeni satır. Ayrılmış karakterleri kaçış dizisi kullanılarak belirtilebilir. Türü karakter tutmak için yeterince büyük olduğu sürece karakter evrensel karakter adları kullanılarak belirtilebilir.  
  
### <a name="encoding"></a>Kodlama  
 Karakter değişmez değerleri farklı kodlanır kendi önekini temel alan.  
  
-   Bir karakter öneki değişmez değer bir normal değişmez değer karakterdir. Değişmez değer bir normal karakter değeri tek bir karakter içeren çıkış sırasında veya kendi içinde yürütme karakter kümesi kodlaması sayısal değerine eşit bir değer yürütme karakter kümesinde temsil edilebilir evrensel karakter adı var. Birden fazla karakter, kaçış sırası veya evrensel karakter adını içeren bir sıradan karakter sabit değeri bir *multicharacter değişmez değer*. Koşullu-desteklenen, multicharacter bir hazır değer veya yürütme karakter kümesinde gösterilemez sıradan karakter sabit değeri int türü ve değeri uygulama tanımlı.  
  
-   L önek ile başlayan bir karakter sabit değeri bir joker karakter değişmez değeri değil. Karakter sabit değeri hiçbir gösterimi olmadıkça ayarlamak yürütme joker karakter olarak kendi kodlama sayısal değerine eşit bir değer tek bir karakter, kaçış sırası veya evrensel karakter adını içeren bir joker karakter değişmez değeri değerine sahip uygulama tanımlı değeri; bu durumda yürütme joker karakter ayarlayın. Birden çok karakter, çıkış sıraları veya evrensel karakter adları içeren bir joker karakter değişmez değeri uygulama tanımlı değeri.  
  
-   U8 önek ile başlayan bir karakter sabit değeri sabit bir UTF-8 karakterdir. Değerin değişmez değer UTF-8 karakterin tek bir karakter içeren çıkış sırasında veya (C0 denetimleri ve temel Latin için karşılık gelen tek bir UTF-8 kod birimi tarafından gösterilebilir, evrensel karakter adı ISO 10646 kod noktası değerine eşit bir değer var. Unicode bloğu). Değerin tek bir UTF-8 kod birimi tarafından gösterilemezse, hatalı oluşturulmuş programdır. Birden fazla karakter, kaçış sırası veya evrensel karakter adını içeren değişmez değer UTF-8 karakter hatalı oluşturulmuş.  
  
-   U önek ile başlayan bir karakter sabit değeri UTF-16 karakter sabit değeri var. UTF-16 karakter değişmez değeri tek bir karakter içeren kaçış dizisi veya (temel çok dilli düzlemi karşılık gelen tek bir UTF-16 kod birimi tarafından gösterilebilir, evrensel karakter adı ISO 10646 kod noktası değerine eşit bir değer var. ). Değerin tek bir UTF-16 kod birimi tarafından gösterilemezse, hatalı oluşturulmuş programdır. Birden fazla karakter, kaçış sırası veya evrensel karakter adını içeren değişmez değer UTF-16 karakter hatalı oluşturulmuş.  
  
-   U önek ile başlayan bir karakter sabit değeri sabit bir UTF-32 karakterdir. UTF-32 karakter değişmez değeri tek bir karakter içeren kaçış dizisi veya evrensel karakter adı ISO 10646 kod noktası değerine eşit bir değer içeriyor. Birden fazla karakter, kaçış sırası veya evrensel karakter adını içeren değişmez değer UTF-8 karakter hatalı oluşturulmuş.  
  
###  <a name="bkmk_Escape"></a> Kaçış dizileri  
 Kaçış dizileri üç tür vardır: basit, sekizlik ve onaltılık. Kaçış dizileri aşağıdakilerden biri olabilir:  
  
|Değer|Kaçış sırası|Değer|Kaçış sırası|  
|-----------|---------------------|-----------|---------------------|  
|yeni satır|\n|ters eğik çizgi|\\\|  
|Yatay sekme|\t|soru işareti|? veya \\?|  
|Dikey sekme|\v|tek tırnak işareti|\\'|  
|Geri Al|\b|çift tırnak işareti|\\"|  
|satır başı|\r|null karakteri|\0|  
|sonraki sayfaya geçme|\f|sekizlik|\ooo|  
|Uyarı (zil)|\a|onaltılık|\xhhh|  
  
 Aşağıdaki kod sıradan karakter değişmez değerleri kullanarak Atlanan karakterlerini bazı örnekleri gösterir. Kaçış sırası sözdiziminde başka karakter değişmez değer türleri için geçerli değil.  
  
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
  
 **Microsoft özel**  
  
 Arasında bir değer normal bir karakter sabiti (bir önek olmayanlar) oluşturmak için derleyici karakteri veya tek tırnak içine bir 32 bit tamsayı içindeki 8 bit değerleri arasındaki bir karakter dizisi dönüştürür. Birden çok karakter sabit değeri içinde karşılık gelen bayt düşük düzey yüksek düzey gerektiği gibi doldurun. Oluşturmak için bir `char` değeri, derleyici, düşük düzey bayt alır. Oluşturmak için bir `wchar_t` veya `char16_t` değeri, derleyici, düşük düzey word alır. Derleyici hiçbir BITS atanmış bayt veya word ayarlanırsa, sonuç kesilmiş konusunda sizi uyarır.  
  
```cpp  
char c0    = 'abcd';    // C4305, C4309, truncates to 'd'  
wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'  
```  
  
 Sekizli çıkış dizisi eğik çizgi ve en fazla 3 sekizli basamak dizisi tarafından ' dir. Birden fazla üç basamak içerecek şekilde görünen bir sekizli çıkış dizisi davranışını karakter sonraki basamakla arkasından bir 3 basamaklı sekizli sırası kabul edilir; Bu şaşırtıcı sonuçlar verebilir. Örneğin:  
  
```cpp  
char c1 = '\100';   // '@'  
char c2 = '\1000';  // C4305, C4309, truncates to '0'   
```  
  
 Sekizlik olmayan karakterler içeren görünmesini kaçış sıraları kadar kalan karakterle devam etmelidir son sekizli karakter sekizli dizisi olarak değerlendirilir. Örneğin:  
  
```cpp  
char c3 = '\009';   // '9'  
char c4 = '\089';   // C4305, C4309, truncates to '9'  
char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'  
```  
  
 Onaltılık çıkış dizisi karakterin ardından ters eğik çizgi olduğundan `x`bir onaltılık rakam dizisini ardından. Derleyici Hatası C2153 hiç onaltılık basamak içeren bir kaçış sırası neden: "onaltılık değişmez değerleri en az bir onaltılık rakam olmalıdır". 2f3b göz ardı edilir. Onaltılık ve onaltılık olmayan karakterler için görünen bir kaçış sırası onaltılık olmayan karakterle devam etmelidir son onaltılık karakter kadar onaltılık çıkış dizisi olarak değerlendirilir.   Bir sıradan veya u8 öneki karakter değişmez değer, en yüksek onaltılık 0xFF değerdir. Bir L öneki veya u önekli geniş karakter değişmez değer, en yüksek onaltılık 0xFFFF değerdir. Bir U önekli geniş karakter değişmez değer, en yüksek onaltılık değer olarak 0xFFFFFFFF kullanılır.  
  
```cpp  
char c6 = '\x0050'; // 'P'  
char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'  
```  
  
 Değişmez değer geniş karakter önekine sahip değilse `L` birden fazla karakter içeriyor değeri ilk karakter alınır. Sonraki karakterler, eşdeğer sıradan karakter değişmez değer davranışı farklı olarak dikkate alınmaz.  
  
```cpp  
wchar_t w1 = L'\100';   // L'@'  
wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored   
wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored  
wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored  
wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored  
wchar_t w6 = L'\x0050'; // L'P'  
wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored  
```  
  
 **SON Microsoft özel**  
  
 Ters eğik çizgi karakteri (\\) bir satırın sonuna yerleştirildiğinde bir satır devamlılığı karakterdir. Karakter sabit değeri olarak görünmesi bir ters bölü karakteri istiyorsanız, bir satırda iki ters eğik çizgi yazmanız gerekir (`\\`). Satır devamlılığı karakteri hakkında daha fazla bilgi için bkz: [çeviri aşamaları](../preprocessor/phases-of-translation.md).  
  
###  <a name="bkmk_UCN"></a> Evrensel karakter adları  
 Karakter değişmez değerleri ve özgün (ham olmayan) dize değişmez değerleri, herhangi bir karakter evrensel karakter adları tarafından temsil edilebilir.  Evrensel karakter adları \U bir sekiz basamaklı Unicode kod noktası tarafından ya da bir dört basamaklı Unicode kod noktası tarafından izlenen bir önek \u tarafından izlenen bir önek tarafından oluşturulur. Tüm sekiz veya dört basamak, sırasıyla, doğru biçimlendirilmiş evrensel karakter adları yapmak için mevcut olması gerekir.  
  
```cpp  
char u1 = 'A';          // 'A'  
char u2 = '\101';       // octal, 'A'   
char u3 = '\x41';       // hexadecimal, 'A'  
char u4 = '\u0041';     // \u UCN 'A'  
char u5 = '\U00000041'; // \U UCN 'A'  
```  
  
 **Temsilci çiftleri**  
  
 Evrensel karakter adları yedek kod noktası aralığındaki D800 DFFF değerleri kodlanamıyor. Unicode temsilci çiftleri için evrensel karakter adını kullanarak belirtin `\UNNNNNNNN`, burada NNNNNNNN sekiz basamaklı kodu karakter noktasıdır. Derleyici gerekiyorsa bir yedek çifti oluşturur.  
  
 C ++ 03, dil yalnızca bir alt evrensel karakter adları tarafından temsil edilebilir karakterlerin izin ve geçerli Unicode karakterlerin gerçekte sunmadı bazı evrensel karakter adları izin. Bu, C ++ 11'de standart giderilmiştir. C ++ 11'de, evrensel karakter adları karakter ve dize değişmez değerleri ve tanımlayıcıları kullanabilirsiniz.  Evrensel karakter adları hakkında daha fazla bilgi için bkz: [karakter kümesi](../cpp/character-sets.md). Unicode hakkında daha fazla bilgi için bkz: [Unicode](http://msdn.microsoft.com/library/dd374081\(v=vs.85\).aspx). Temsilci çiftleri hakkında daha fazla bilgi için bkz: [temsilci çiftleri ve yardımcı karakterlerini](http://msdn.microsoft.com/library/dd374069\(v=vs.85\).aspx).  
  
## <a name="string-literals"></a>Dize sabit değerleri  
 Bir dize sabit değeri null sonlandırılmış bir dize birlikte form bir karakter dizisi temsil eder. Karakterleri çift tırnak içine alınması gerekir. Dize değişmez değerleri şu tür vardır:  
  
### <a name="narrow-string-literals"></a>Dar dize değişmez değerleri  
 Dar dize sabit değeri bir önek olmayan, çift tırnak işareti ayrılmış, null ile sonlandırılmış türü dizisidir `const char[n]`, burada n dizi bayt cinsinden uzunluğu. Dar dize sabit değeri çift tırnak işareti dışında herhangi bir grafik karakter içerebilir (`"`), eğik çizgi (`\`), ya da yeni satır karakteri. Dar dize sabit değeri, bir bayt sığacak kaçış sıraları yukarıda listelenen ve evrensel karakter adları içerebilir.  
  
```cpp  
const char *narrow = "abcd";  
  
// represents the string: yes\no  
const char *escaped = "yes\\no";  
```  
  
#### <a name="utf-8-encoded-strings"></a>UTF-8 kodlanmış dizeleri  
  
 UTF-8 ile kodlanmış dize bir u8 öneki, çift tırnak işareti ayrılmış, null ile sonlandırılmış dizisi türü olan `const char[n]`, burada n kodlanmış dizinin bayt cinsinden uzunluğu. Bir u8 öneki dize sabit değeri çift tırnak işareti dışında herhangi bir grafik karakter içerebilir (`"`), eğik çizgi (`\`), ya da yeni satır karakteri. Bir u8 öneki dize sabit değeri, kaçış sıraları yukarıda listelenen ve herhangi bir evrensel karakter adı içerebilir.  
  
```cpp  
const char* str1 = u8"Hello World";  
const char* str2 = u8"\U0001F607 is O:-)";  
```  
  
### <a name="wide-string-literals"></a>Geniş dize değişmez değerleri  
 Geniş bir dize sabit değeri bir null ile sonlandırılmış sabiti dizisidir `wchar_t` tarafından öneki '`L`' ve çift tırnak işareti ("), eğik çizgi dışında herhangi bir grafik karakter içeriyor (\\), ya da yeni satır karakteri. Geniş bir dize sabit değeri kaçış sıraları yukarıda listelenen ve herhangi bir evrensel karakter adı içeriyor olabilir.  
  
```cpp  
const wchar_t* wide = L"zyxw";  
const wchar_t* newline = L"hello\ngoodbye";  
```  
  
#### <a name="char16t-and-char32t-c11"></a>char16_t ve char32_t (C ++ 11)  
  
 C ++ 11 tanıtır taşınabilir `char16_t` (16 bit Unicode) ve `char32_t` (32-bit Unicode) karakter türleri:  
  
```cpp  
auto s3 = u"hello"; // const char16_t*  
auto s4 = U"hello"; // const char32_t*  
```  
  
### <a name="raw-string-literals-c11"></a>Ham dize değişmez değerleri (C ++ 11)  
 Ham dize sabit değeri bir null ile sonlandırılmış bir dizidir — herhangi bir karakter türde — çift tırnak işareti ("), eğik çizgi dahil olmak üzere herhangi bir grafik karakter içeriyor (\\), ya da yeni satır karakteri. Ham dize değişmez değerleri genellikle normal ifadelerdeki karakter sınıfları kullanın ve HTML dizelerini ve XML dizeleri kullanılır. Örnekler için aşağıdaki makaleye bakın: [C ++ 11 çalışan Bjarne Stroustrup'ın sık sorulan sorular](http://go.microsoft.com/fwlink/p/?linkid=401172).  
  
```cpp  
// represents the string: An unescaped \ character  
const char* raw_narrow = R"(An unescaped \ character)";  
const wchar_t* raw_wide = LR"(An unescaped \ character)";  
const char*       raw_utf8  = u8R"(An unescaped \ character)";  
const char16_t* raw_utf16 = uR"(An unescaped \ character)";  
const char32_t* raw_utf32 = UR"(An unescaped \ character)";  
```  
  
 Bir sınırlayıcı ham dize sabit değeri, açma parantezi hemen önünde ve hemen kapanış parantezi izleyen bir kullanıcı tarafından tanımlanan en fazla 16 karakter dizisidir.  Örneğin, `R"abc(Hello"\()abc"` sınırlayıcı dizisini `abc` ve dize içeriği `Hello"\(`. Bir sınırlayıcı hem çift tırnak işareti ve parantez içeren ham dizeleri belirsizliğini ortadan kaldırmak için kullanabilirsiniz. Derleyici Hatası nedenleri:  
  
```cpp  
// meant to represent the string: )"  
const char* bad_parens = R"()")";  // error C2059  
```  
  
 Ancak bir sınırlayıcı çözer:  
  
```cpp  
const char* good_parens = R"xyz()")xyz";  
```  
  
 Olduğu bir satır başı karakteri (Atlanan karakteri değil) kaynakta bir ham değişmez dize oluşturabileceğiniz:  
  
```cpp  
// represents the string: hello  
//goodbye  
const wchar_t* newline = LR"(hello  
goodbye)";  
```  
  
### <a name="stdstring-literals-c14"></a>Std::String değişmez değerleri (C ++ 14)  
 Std::String değişmez değerleri olan "xyx" s olarak temsil kullanıcı tanımlı değişmez değerler (aşağıya bakın), standart kitaplığı uygulamalarını (ile bir `s` soneki). Bu tür bir dize değişmez değer türü std::string, std::wstring, std::u32string veya std::u16string Belirtilen önek bağlı olarak geçici bir nesne oluşturur. Önek kullanıldığında olarak yukarıda bir std::string oluşturulur. L "xyz" s bir std::wstring üretir. u "xyz" s oluşturan bir [std::u16string](../standard-library/string-typedefs.md#u16string), U "xyz" s üretir bir [std::u32string](../standard-library/string-typedefs.md#u32string).  
  
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
  
 Std::String değişmez değerleri ad alanında tanımlı `std::literals::string_literals` içinde \<dize > Üstbilgi dosyası. Çünkü `std::literals::string_literals`, ve `std::literals` olarak bildirilen her ikisi de [satır içi ad alanları](../cpp/namespaces-cpp.md), `std::literals::string_literals` doğrudan ad alanında aitse gibi otomatik olarak kabul edilir `std`.  
  
### <a name="size-of-string-literals"></a>Dize değişmez değerleri boyutu  
 ANSI karakter için\* dizeler ve diğer tek baytlı kodlamaları (değil UTF-8) boyutunu (bayt) bir değişmez dize değeri, karakterler artı 1 sonlandırma null karakter sayısı. Tüm diğer dize türleri için boyutu kesinlikle karakter sayısını ilişkili değil. UTF-8 bazı kodlamak için en fazla dört karakter öğeleri kullanan *kod birimleri*, char16_t veya UTF-16, tek bir kodlamak için (toplam dört bayt için) iki öğe kullanabilir olarak kodlanmış wchar_t ve *kod birimi*.   Bu örnek, geniş bir dizenin boyutunu bayt cinsinden değişmez değer gösterir:  
  
```cpp  
const wchar_t* str = L"Hello!";  
const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);  
```  
  
 Dikkat `strlen()` ve `wcslen()` büyüklüğü dize türü öğesi boyutuna eşittir sondaki boş karakter boyutu içermez: char * dizesini bir bayt, wchar_t iki bayt\* veya char16_t\* dizeleri ve char32_t dört bayt\* dizeleri.  
  
 Bir dize uzunluğu en fazla 65535 bayttır. Bu sınır dar dize değişmez değerleri ve geniş dize değişmez değerleri için geçerlidir.  
  
### <a name="modifying-string-literals"></a>Dize değişmez değerleri değiştirme  
 Dize değişmez değerleri (std:string değişmez değerleri dahil değil) sabitleri olduğundan, bunları değiştirilmeye çalışılırken — Örneğin, str [2] 'A' = — derleyici hatasına neden olur.  
  
 **Microsoft özel**  
  
 Visual c++'ta const olmayan bir işaretçi başlatmak için bir değişmez dize değeri kullanabilirsiniz `char` veya `wchar_t`. Bu C99 kodda izin verilir ancak C ++ 98'de kullanım dışı ve C ++ 11 kaldırıldı. Dize değiştirme girişimi bu örnekte olduğu gibi bir erişim ihlali neden olur:  
  
```cpp  
wchar_t* str = L"hello";  
str[2] = L'a'; // run-time error: access violation  
```  
  
 Bir hata ayarlarken bir değişmez dize değeri bir non_const karakter işaretçi dönüştürüldüğünde yaymak üzere derleyici neden [/ZC: strictstrings (dize değişmez değer türü dönüşümünü devre dışı bırakma)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) derleyici seçeneği. Bunun için standartlara uygun taşınabilir kod öneririz. Ayrıca kullanmak iyi bir uygulama olan `auto` doğru (#const) türe çözümler için dize değişmez değeri başlatılmış işaretçileri bildirmek için anahtar sözcüğü. Örneğin, bu kod örneği, bir derleme zamanında değişmez dize değeri için yazma girişimi yakalar:  
  
```cpp  
auto str = L"hello";  
str[2] = L'a'; // C3892: you cannot assign to a variable that is const.  
```  
  
 Bazı durumlarda, yürütülebilir dosyada alanı kaydetmek için aynı dize değişmez değerleri havuza. Değişmez dize değeri havuzu içindeki tüm başvurular bir belirli değişmez dize değeri her başvuru sahip olmak yerine bellekte aynı konuma işaret edecek şekilde derleyici nedenler dize sabit değeri ayrı bir örneğini gelin. Dize havuzu etkinleştirmek için [/GF](../build/reference/gf-eliminate-duplicate-strings.md) derleyici seçeneği.  
  
 **Son Microsoft özel**  
  
### <a name="concatenating-adjacent-string-literals"></a>Birleştirme bitişik dize değişmez değerleri  
 Bitişik geniş veya dar dize değişmez değerleri birleşir. Bu bildirim:  
  
```cpp  
char str[] = "12" "34";  
```  
  
 Bu bildirim için benzerdir:  
  
```cpp  
char atr[] = "1234";  
```  
  
 ve bu bildirim için:  
  
```cpp  
char atr[] =  "12\  
34";  
```  
  
 Dize değişmez değerleri belirtmek için katıştırılmış onaltılık çıkış kodları kullanılması beklenmeyen sonuçlara neden olabilir. Karakter f tarafından izlenen ASCII 5 karakter içeren bir dize sabit değeri oluşturmak aşağıdaki örnek arama i, v ve e:  
  
```cpp  
"\x05five"  
```  
  
 Bir çizgiyle karakterleriyle ASCII kodu bir onaltılık 5F gerçek sonucudur i, v ve e. Doğru sonucu elde etmek için bunlardan birini kullanabilirsiniz:  
  
```cpp  
"\005five"     // Use octal literal.  
"\x05" "five"  // Use string splicing.  
```  
  
 Std::String değişmez değerleri, çünkü bunlar std::string türleri birleştirilmiş ile + için tanımlanan işleci [basic_string](../standard-library/basic-string-class.md) türleri. Bunlar ayrıca bitişik dize değişmez değerleri aynı şekilde art arda eklenebilir. Her iki durumda da, kodlama dizesi ve sonek eşleşmesi gerekir:  
  
```cpp  
auto x1 = "hello" " " " world"; // OK  
auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix  
auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes  
auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes  
```  
  
### <a name="string-literals-with-universal-character-names"></a>Evrensel karakter adları ile dize değişmez değerleri  
 Evrensel karakter adını dize türü bir veya daha fazla karakter olarak kodlanmış sürece özgün (ham olmayan) dize değişmez değerleri herhangi bir karakteri temsil etmesi için evrensel karakter adları kullanabilir.  Örneğin, genişletilmiş bir karakter temsil eden evrensel karakter adları ANSI kod sayfası kullanılarak dar bir dizesinde kodlanamıyor, ancak bazı çok baytlı kod sayfaları veya UTF-8 dizeleri veya geniş bir dize dar dizelerde kodlanabilir. C ++ 11'de, Unicode desteği char16_t * ile char32_t genişletilir\* dize türleri:  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter kümeleri](../cpp/character-sets.md)   
 [Sayısal, Boole ve işaretçi değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md)   
 [Kullanıcı Tanımlı Sabit Değerler](../cpp/user-defined-literals-cpp.md)