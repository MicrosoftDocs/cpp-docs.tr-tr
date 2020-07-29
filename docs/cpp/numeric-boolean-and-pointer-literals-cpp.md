---
title: Sayısal, Boole ve işaretçi değişmez değerleri (C++)
description: Integer, kayan nokta, Boole ve işaretçi değişmez değerleri için C++ standart dil biçimleri.
ms.date: 11/04/2016
helpviewer_keywords:
- literals, C++
- constants, literals
- literals [C++]
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
ms.openlocfilehash: def223682b58f3d0c8bd3dd88f6d54fc5aa8b8a4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186457"
---
# <a name="numeric-boolean-and-pointer-literals"></a>Sayısal, boole ve işaretçi değişmez değerleri

Değişmez değer, doğrudan bir değeri temsil eden bir program öğesidir. Bu makale Integer, kayan nokta, Boolean ve işaretçi türündeki sabit değerleri içerir. Dize ve karakter değişmez değerleri hakkında daha fazla bilgi için bkz. [dize ve karakter değişmez değerleri (C++)](../cpp/string-and-character-literals-cpp.md). Ayrıca, bu kategorilerden herhangi birine göre kendi sabit değerlerini de tanımlayabilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı tanımlı değişmez değerler (C++)](../cpp/user-defined-literals-cpp.md)

. Birden çok bağlamdaki sabit değerleri kullanabilirsiniz, ancak çoğunlukla adlandırılmış değişkenleri başlatabilir ve bağımsız değişkenleri işlevlere geçirebilirsiniz:

```cpp
const int answer = 42;      // integer literal
double d = sin(108.87);     // floating point literal passed to sin function
bool b = true;              // boolean literal
MyClass* mc = nullptr;      // pointer literal
```

Bazen derleyiciye bir hazır değeri nasıl yorumlayacağını ya da kendisine verilecek belirli türü söylemeniz önemlidir. Bu işlem, sabit değere ön ekler veya sonekler eklenerek yapılır. Örneğin, önek `0x` derleyiciye onu bir onaltılık değer olarak takip eden sayıyı yorumlamasını söyler `0x35` . `ULL`Sonek, derleyicinin değeri ' **`unsigned long long`** de olduğu gibi bir tür olarak değerlendirmesine söyler `5894345ULL` . Her sabit değer türü için ön eklerin ve son eklerin listesi için aşağıdaki bölümlere bakın.

## <a name="integer-literals"></a>Tamsayı sabit değerleri

Tamsayı sabit değerleri bir basamakla başlar ve kesirli parçaları ya da üsleri içermez. Tamsayı sabit değerlerini ondalık, sekizli veya onaltılı biçimde belirtebilirsiniz. İmzalanmış veya imzasız türleri ve uzun veya kısa türleri belirtebilirsiniz.

Ön ek veya sonek olmadığında, derleyici bir tamsayı değişmez değer türü **`int`** (32 bit) verir, aksi takdirde, bu değer buna uyum sağlar **`long long`** (64 bit).

Ondalık integral sabit değerini belirtmek için, belirtimi sıfır dışında bir basamakla başlatın. Örnek:

```cpp
int i = 157;        // Decimal literal
int j = 0198;       // Not a decimal number; erroneous octal literal
int k = 0365;       // Leading zero specifies octal literal, not decimal
int m = 36'000'000  // digit separators make large values more readable
```

Sekizlik bir integral sabit değer belirtmek için, belirtimi 0 ile, ardından 0 ile 7 aralığındaki bir dizi basamakla başlatın. 8 ve 9 rakamları, sekizlik bir sabit değer belirtirken hatalar. Örnek:

```cpp
int i = 0377;   // Octal literal
int j = 0397;   // Error: 9 is not an octal digit
```

Onaltılı bir integral sabit değeri belirtmek için veya ile ( `0x` `0X` "x" önemli değildir), ve (veya) arasında aralıktaki bir basamak dizisi `0` ve ( `9` `a` `A` `f` veya `F` ) ile belirtimi başlatın. `a` (veya `A`) ile `f` (veya `F`) arasındaki onaltılık basamaklar, 10 ile 15 aralığındaki değerleri temsil eder. Örnek:

```cpp
int i = 0x3fff;   // Hexadecimal literal
int j = 0X3FFF;   // Equal to i
```

İşaretsiz bir tür belirtmek için ya da sonekini kullanın `u` `U` . Uzun bir tür belirtmek için ya da sonekini kullanın `l` `L` . 64 bitlik bir integral türü belirtmek için LL veya ll sonekini kullanın. İ64 soneki hala destekleniyor, ancak bunu önermiyoruz. Microsoft 'a özeldir ve taşınabilir değildir. Örnek:

```cpp
unsigned val_1 = 328u;                  // Unsigned value
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

Kayan nokta değişmez değerleri, kesirli bir bölümü olması gereken değerleri belirtir. Bu değerler, ondalık noktaları ( **`.`** ) içerir ve üsleri içerebilir.

Kayan nokta değişmez değerleri, sayının değerini belirten bir *mantisinin* (bazen *Mantis*olarak adlandırılır) olur. Bu, sayının büyüklüğünü belirten bir *üssün*oluşur. Ayrıca, değişmez değer türünü belirten isteğe bağlı bir sonekine sahiptirler. Mantisinin bir rakam ve ardından bir nokta ve sonra sayının kesirli kısmını temsil eden isteğe bağlı bir basamak sırası olarak belirtilir. Örnek:

```cpp
18.46
38.
```

Varsa üs değeri, aşağıdaki örnekte gösterildiği gibi, sayının 10 ' un bir kuvvetinin büyüklüğünü belirtir:

```cpp
18.46e0      // 18.46
18.46e1      // 184.6
```

Üs, ya da ile `e` `E` aynı anlamı olan, sonra isteğe bağlı bir işaret (+ veya-) ve bir basamak dizisi ile belirtilebilir.  Bir üs varsa, sondaki ondalık basamak, gibi tüm sayılarda gereksizdir `18E0` .

Kayan nokta değişmez değerleri varsayılan olarak türündedir **`double`** . Ya da veya ya da ya da ya da ya da ya da `f` `l` `F` `L` (son ek büyük/küçük harf duyarlı değildir) kullanarak, değişmez değer **`float`** veya **`long double`**

**`long double`** **`double`** Aynı gösterimine sahip olsa da, aynı türde değildir. Örneğin, gibi aşırı yüklenmiş işlevlere sahip olabilirsiniz

```cpp
void func( double );
```

ve

```cpp
void func( long double );
```

## <a name="boolean-literals"></a>Boole sabit değerleri

Boolean sabit değerleri **`true`** ve ' dir **`false`** .

## <a name="pointer-literal-c11"></a>İşaretçi sabit değeri (C++ 11)

C++, [`nullptr`](../cpp/nullptr.md) sıfır ile başlatılmış bir işaretçi belirtmek için değişmez değeri tanıtır. Taşınabilir kodda, **`nullptr`** tam sayı türü sıfır veya gibi makrolar yerine kullanılmalıdır `NULL` .

## <a name="binary-literals-c14"></a>İkili sabit değerler (C++ 14)

Bir ikili değişmez değer, `0B` veya `0b` öneki tarafından, ardından 1 ve 0 ' ın bir sırası ile belirtilebilir:

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

Önceki örnekte, "MAXIMUM_ERROR_THRESHOLD" gibi açık bir anlamı veren adlandırılmış bir sabiti kullanmak daha iyi bir uygulamadır. "Başarı" dönüş değeri son kullanıcılar tarafından görüeyse, adlandırılmış bir dize sabiti kullanmak daha iyi olabilir. Dize sabitlerini, diğer dillere yerelleştirilebilecek bir dosyada tek bir konumda tutabilirsiniz. Adlandırılmış sabitlerin kullanılması, hem kendi hem de diğerlerinin kodun amacını anlamasına yardımcı olur.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük kuralları](../cpp/lexical-conventions.md)<br/>
[C++ dize değişmez değerleri](../cpp/string-and-character-literals-cpp.md)<br/>
[C++ Kullanıcı tanımlı sabit değerleri](../cpp/user-defined-literals-cpp.md)
