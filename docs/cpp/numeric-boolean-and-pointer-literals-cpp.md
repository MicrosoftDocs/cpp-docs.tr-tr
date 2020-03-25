---
title: Sayısal, Boole ve işaretçi değişmez değerleriC++()
ms.date: 11/04/2016
helpviewer_keywords:
- literals, C++
- constants, literals
- literals [C++]
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
ms.openlocfilehash: 21685af5fc4f2dcf042698e054430e50531163b7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177748"
---
# <a name="numeric-boolean-and-pointer-literals"></a>Sayısal, Boole ve işaretçi değişmez değerleri

Değişmez değer, doğrudan bir değeri temsil eden bir program öğesidir. Bu makale Integer, kayan nokta, Boolean ve işaretçi türündeki sabit değerleri içerir. Dize ve karakter değişmez değerleri hakkında daha fazla bilgi için bkz. [dize veC++karakter değişmez değerleri ()](../cpp/string-and-character-literals-cpp.md). Ayrıca, bu kategorilerden herhangi birine göre kendi sabit değerlerini de tanımlayabilirsiniz; daha fazla bilgi için bkz. [Kullanıcı tanımlı değişmezC++değerler ()](../cpp/user-defined-literals-cpp.md)

ziyaret edin. Birden çok bağlamdaki sabit değerleri kullanabilirsiniz, ancak çoğunlukla adlandırılmış değişkenleri başlatabilir ve bağımsız değişkenleri işlevlere geçirebilirsiniz:

```cpp
const int answer = 42; // integer literal
double d = sin(108.87);     //floating point literal passed to sin function
bool b = true;              // boolean literal
MyClass* mc = nullptr;      // pointer literal
```

Bazen derleyiciye bir hazır değeri nasıl yorumlayacağını ya da kendisine verilecek belirli türü söylemeniz önemlidir. Bunu, değişmez değere ön ekler veya sonekler ekleyerek yapabilirsiniz. Örneğin, 0x öneki derleyiciye bunu izleyen sayıyı onaltılık bir değer olarak yorumlamasını söyler, örneğin, 0x35. ULL soneki, derleyicinin değeri 5894345ULL gibi **işaretsiz uzun bir Long** türü olarak görmesini söyler. Her sabit değer türü için ön eklerin ve son eklerin listesi için aşağıdaki bölümlere bakın.

## <a name="integer-literals"></a>Tamsayı sabit değerleri

Tamsayı sabit değerleri bir basamakla başlar ve kesirli parçaları ya da üsleri içermez. Tamsayı sabit değerlerini ondalık, sekizli veya onaltılı biçimde belirtebilirsiniz. İşaretli veya işaretsiz türleri ve uzun veya kısa türleri belirtebilirler.

Ön ek veya son ek olmadığında, derleyici **tamsayı (32** bit) türünde bir tamsayı değeri verir, aksi takdirde bu değer, bu tür **uzun uzun** (64 bit) olur.

Ondalık integral sabit değerini belirtmek için, belirtimi sıfır dışında bir basamakla başlatın. Örneğin:

```cpp
int i = 157;   // Decimal literal
int j = 0198;       // Not a decimal number; erroneous octal literal
int k = 0365;       // Leading zero specifies octal literal, not decimal
int m = 36'000'000  // digit separators make large values more readable
int
```

Sekizlik bir integral sabit değer belirtmek için, belirtimi 0 ile, ardından 0 ile 7 aralığındaki bir dizi basamakla başlatın. 8 ve 9 rakamları, sekizlik bir sabit değer belirtirken hatalar. Örneğin:

```cpp
int i = 0377;   // Octal literal
int j = 0397;        // Error: 9 is not an octal digit
```

Onaltılı bir integral sabit değeri belirtmek için, `0x` veya `0X` ("x" büyük/küçük harf) ' i ile, `a` (veya `A`) `f` aracılığıyla `9` ve `F`(veya) arasında bir `0` basamak dizisi. `a` (veya `A`) ile `f` (veya `F`) arasındaki onaltılık basamaklar, 10 ile 15 aralığındaki değerleri temsil eder. Örneğin:

```cpp
int i = 0x3fff;   // Hexadecimal literal
int j = 0X3FFF;        // Equal to i
```

İşaretsiz bir tür belirtmek için `u` ya da `U` sonekini kullanın. Uzun bir tür belirtmek için `l` ya da `L` sonekini kullanın. 64 bitlik bir integral türü belirtmek için LL veya ll sonekini kullanın. İ64 soneki hala desteklenmektedir, ancak Microsoft 'a özgü olduğundan ve taşınabilir olmadığından kaçınılmalıdır. Örneğin:

```cpp
unsigned val_1 = 328u;             // Unsigned value
long val_2 = 0x7FFFFFL;                 // Long value specified
                                        //  as hex literal
unsigned long val_3 = 0776745ul;        // Unsigned long value
auto val_4 = 108LL;                           // signed long long
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long
```

**Basamak ayırıcıları**: tek tırnak karakterini (kesme işareti) kullanarak, insanların okunmasını kolaylaştırmak için değerleri daha büyük sayılara ayırabilirsiniz. Ayırıcıların derleme üzerinde hiçbir etkisi yoktur.

```cpp
long long i = 24'847'458'121
```

## <a name="floating-point-literals"></a>Kayan nokta sabit değerleri

Kayan nokta değişmez değerleri, kesirli bir bölümü olması gereken değerleri belirtir. Bu değerler, ondalık noktaları ( **.** ) içerir ve üsleri içerebilir.

Kayan nokta değişmez değerleri, sayının değerini belirten bir "Mantis", sayının boyutunu belirten bir "üs" ve değişmez değerin türünü belirten isteğe bağlı bir sonek. Mantis bir rakam ve ardından bir nokta ve sonra sayının kesirli kısmını temsil eden isteğe bağlı bir basamak sırası olarak belirtilir. Örneğin:

```cpp
18.46
38.
```

Varsa üs değeri, aşağıdaki örnekte gösterildiği gibi, sayının 10 ' un bir kuvvetinin büyüklüğünü belirtir:

```cpp
18.46e0      // 18.46
18.46e1           // 184.6
```

Üs değeri, aynı anlamı olan `e` veya `E`kullanılarak belirtilebilir, sonra isteğe bağlı bir işaret (+ veya-) ve bir basamak dizisi gelir.  Bir üs varsa, sondaki ondalık basamak, `18E0`gibi bütün sayılarda gereksizdir.

Kayan nokta değişmez değerleri **Double**türüne varsayılan değer. Son ek `f` veya `l` (veya `F` ya da `L` — sonek büyük/küçük harfe duyarlı değildir) kullanarak, sabit değer sırasıyla **float** veya **Long Double**olarak belirtilebilir.

**Long Double** ve **Double** aynı gösterimine sahip olsa da, aynı türde değildir. Örneğin, şu gibi aşırı yüklenmiş işlevlere sahip olabilirsiniz

```cpp
void func( double );
```

ile

```cpp
void func( long double );
```

## <a name="boolean-literals"></a>Boole sabit değerleri

Boolean sabit değerleri **true** ve **false**şeklindedir.

## <a name="pointer-literal-c11"></a>İşaretçi sabit değeri (C++ 11)

C++sıfır ile başlatılmış bir işaretçi belirtmek için [nullptr](../cpp/nullptr.md) değişmez değerini tanıtır. Taşınabilir kodda, tam sayı türü sıfır veya NULL gibi makrolar yerine **nullptr** kullanılmalıdır.

## <a name="binary-literals-c14"></a>İkili sabit değerler (C++ 14)

Bir ikili değişmez değer, `0B` veya `0b` öneki ile, ardından 1 ve 0 ' ın bir dizisi tarafından belirtilebilir:

```cpp
auto x = 0B001101 ; // int
auto y = 0b000001 ; // int
```

## <a name="avoid-using-literals-as-magic-constants"></a>Değişmez değerler "sihirli sabitler" olarak kullanmaktan kaçının

Her zaman iyi programlama uygulaması olmasa da, değişmez değerleri doğrudan ifadelerde ve deyimlerde kullanabilirsiniz:

```cpp
if (num < 100)
    return "Success";
```

Önceki örnekte, "MAXIMUM_ERROR_THRESHOLD" gibi açık bir anlamı veren adlandırılmış bir sabiti kullanmak daha iyi olabilir. "Başarı" dönüş değeri son kullanıcılar tarafından görüeyse, diğer dillere yerelleştirilebilecek bir dosyada tek bir konumda depolanabilecek adlandırılmış bir dize sabiti kullanmak daha iyi olabilir. Adlandırılmış sabitlerin kullanılması, kodun amacını anlamak için başkalarının yanı sıra kendinize de yardımcı olur.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)<br/>
[C++Dize sabit değerleri](../cpp/string-and-character-literals-cpp.md)<br/>
[C++Kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md)
