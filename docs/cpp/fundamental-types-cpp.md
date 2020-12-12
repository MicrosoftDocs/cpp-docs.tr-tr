---
description: 'Hakkında daha fazla bilgi edinin: Yerleşik türler (C++)'
title: Yerleşik türler (C++)
ms.date: 07/22/2020
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- char8_t_cpp
- char16_t_cpp
- char32_t_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++]
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: 601bd0742002506272ec3da7af448a4bdba96065
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268749"
---
# <a name="built-in-types-c"></a>Yerleşik türler (C++)

Yerleşik türler ( *temel türler* de denir), C++ dil standardı tarafından belirtilir ve derleyicide yerleşik olarak bulunur. Yerleşik türler herhangi bir başlık dosyasında tanımlı değil. Yerleşik türler üç ana kategoriye ayrılmıştır: *integral*, *kayan nokta* ve *void*. Integral türleri tüm sayıları temsil eder. Kayan nokta türleri, kesirli parçaları olabilecek değerler belirtebilir. Çoğu yerleşik tür, derleyici tarafından ayrı türler olarak değerlendirilir. Ancak, bazı türler *eşanlamlı* veya derleyici tarafından eşdeğer tür olarak değerlendirilir.

## <a name="void-type"></a>Void türü

[`void`](void-cpp.md)Tür boş bir değer kümesi tanımlar. Türünde değişken **`void`** belirtilemez. **`void`** Tür, birincil olarak değer döndürmeyen işlevleri bildirmek veya türsüz ya da rastgele yazılmış verilere genel işaretçiler bildirmek için kullanılır. Herhangi bir ifade açıkça dönüştürülebilir veya türüne dönüştürülebilir **`void`** . Ancak, bu tür ifadeler aşağıdaki kullanımlar ile kısıtlıdır:

- Bir ifade deyimi. (Daha fazla bilgi için bkz. [ifadeler](expressions-cpp.md).)

- Virgül işlecinin sol işleneni. (Daha fazla bilgi için bkz. [virgül işleci](comma-operator.md).)

- Koşullu işlecin ikinci veya üçüncü işleneni ( `? :` ). (Daha fazla bilgi için bkz. [koşullu işlece sahip ifadeler](conditional-operator-q.md).)

## <a name="stdnullptr_t"></a>std:: nullptr_t

Anahtar sözcüğü, **`nullptr`** türünün `std::nullptr_t` herhangi bir ham işaretçi türüne dönüştürülebilir bir null işaretçi sabitinden oluşur. Daha fazla bilgi için bkz. [`nullptr`](nullptr.md).

## <a name="boolean-type"></a>Boole türü

[`bool`](bool-cpp.md)Türün değerleri [`true`](../cpp/true-cpp.md) ve olabilir [`false`](../cpp/false-cpp.md) . **`bool`** Türün boyutu uygulamaya özgüdür. Bkz. Microsoft 'a özgü uygulama ayrıntıları için [yerleşik türlerin boyutları](#sizes-of-built-in-types) .

## <a name="character-types"></a>Karakter türleri

**`char`** Türü, temel yürütme karakter kümesinin üyelerini verimli bir şekilde kodlayan bir karakter temsili türüdür. C++ derleyicisi,, ve türü değişkenleri **`char`** **`signed char`** **`unsigned char`** farklı türlere sahip olacak şekilde davranır.

**Microsoft 'a özgü**: tür değişkenleri, **`char`** **`int`** **`signed char`** [`/J`](../build/reference/j-default-char-type-is-unsigned.md) derleme seçeneği kullanılmadığı sürece varsayılan olarak türünden olarak yükseltilir. Bu durumda, bunlar tür olarak değerlendirilir **`unsigned char`** ve **`int`** oturum açma uzantısı olmadan ' a yükseltilir.

Türünde bir değişken **`wchar_t`** , geniş karakter veya çok baytlı bir karakter türüdür. **`L`** Geniş karakterli türü belirtmek için bir karakter veya dize değişmez değerinden önce öneki kullanın.

**Microsoft 'a özgü**: varsayılan olarak **`wchar_t`** yerel bir türdür, ancak [`/Zc:wchar_t-`](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) **`wchar_t`** için bir TypeDef oluşturmak için kullanabilirsiniz **`unsigned short`** . **`__wchar_t`** Tür yerel tür Için Microsoft 'a özgü bir eş anlamlıdır **`wchar_t`** .

**`char8_t`** Türü UTF-8 karakter gösterimi için kullanılır. Aynı gösterimine sahiptir **`unsigned char`** , ancak derleyici tarafından ayrı bir tür olarak kabul edilir. **`char8_t`** Tür c++ 20 ' de yenidir. **Microsoft 'a özgü**: öğesinin kullanımı **`char8_t`**  , [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği gerektirir.

**`char16_t`** Türü UTF-16 karakter gösterimi için kullanılır. Herhangi bir UTF-16 kod birimini temsil etmek için yeterince büyük olmalıdır. Derleyici tarafından ayrı bir tür olarak değerlendirilir.

**`char32_t`** Tür UTF-32 karakter gösterimi için kullanılır. Herhangi bir UTF-32 kod birimini temsil etmek için yeterince büyük olmalıdır. Derleyici tarafından ayrı bir tür olarak değerlendirilir.

## <a name="floating-point-types"></a>Kayan nokta türleri

Kayan nokta türleri, geniş bir magnitudes için kesirli değerlerin yaklaşık bir şekilde sağlanması için bir IEEE-754 temsili kullanır. Aşağıdaki tabloda, C++ ' daki kayan nokta türleri ve kayan nokta türü boyutlarında karşılaştırılma kısıtlamaları listelenmektedir. Bu kısıtlamalar C++ standardı tarafından uygulanan ve Microsoft uygulamasından bağımsızdır. Yerleşik kayan nokta türlerinin mutlak boyutu standart içinde belirtilmez.

| Tür | İçindekiler |
|--|--|
| **`float`** | Tür **`float`** C++ ' da en küçük kayan nokta türüdür. |
| **`double`** | Tür **`double`** , türünden büyük veya buna eşit olan **`float`** , ancak türünden küçük veya ona eşit olan bir kayan nokta türüdür **`long double`** . |
| **`long double`** | Tür **`long double`** , türünden büyük veya buna eşit olan bir kayan nokta türüdür **`double`** . |

**Microsoft 'a özgü**: temsili **`long double`** ve **`double`** aynıdır. Ancak, **`long double`** ve **`double`** derleyici tarafından ayrı türler olarak değerlendirilir. Microsoft C++ derleyicisi, 4 ve 8 baytlık IEEE-754 kayan nokta temsillerini kullanır. Daha fazla bilgi için bkz. [IEEE kayan nokta temsili](../build/ieee-floating-point-representation.md).

## <a name="integer-types"></a>Tam sayı türleri

**`int`** Tür, varsayılan temel tamsayı türüdür. Uygulamaya özgü bir Aralık üzerinde tüm sayıların tamamını temsil edebilir.

*İşaretli* bir tamsayı temsili hem pozitif hem de negatif değerleri tutabilecek bir sayıdır. Varsayılan olarak veya **`signed`** değiştirici anahtar sözcüğü mevcut olduğunda kullanılır. **`unsigned`** Değiştirici anahtar sözcüğü yalnızca negatif olmayan değerleri tutabilecek *işaretsiz* bir gösterimi belirtir.

Bir boyut değiştiricisi kullanılan tamsayı gösteriminin bit cinsinden genişliğini belirtir. Dil,, **`short`** **`long`** ve **`long long`** değiştiricilerini destekler. Bir **`short`** tür en az 16 bit genişliğinde olmalıdır. Bir **`long`** tür en az 32 bit genişliğinde olmalıdır. Bir **`long long`** tür en az 64 bit genişliğinde olmalıdır. Standart integral türleri arasındaki bir boyut ilişkisini belirtir:

`1 == sizeof(char) <= sizeof(short) <= sizeof(int) <= sizeof(long) <= sizeof(long long)`

Bir uygulama, her tür için hem minimum boyut gereksinimlerini hem de boyut ilişkisini korumalıdır. Ancak gerçek boyutlar uygulamalar arasında değişebilir ve farklılık gösterebilir. Bkz. Microsoft 'a özgü uygulama ayrıntıları için [yerleşik türlerin boyutları](#sizes-of-built-in-types) .

**`int`** **`signed`** , **`unsigned`** , Veya boyut değiştiricileri belirtildiğinde anahtar sözcük atlanabilir. Varsa değiştiriciler ve **`int`** tür herhangi bir sırada görünebilir. Örneğin, **`short unsigned`** ve **`unsigned int short`** aynı türe başvurun.

### <a name="integer-type-synonyms"></a>Tamsayı türü eş anlamlılar

Aşağıdaki tür grupları derleyici tarafından eş anlamlı olarak kabul edilir:

- **`short`**, **`short int`**, **`signed short`**, **`signed short int`**

- **`unsigned short`**, **`unsigned short int`**

- **`int`**, **`signed`**, **`signed int`**

- **`unsigned`**, **`unsigned int`**

- **`long`**, **`long int`**, **`signed long`**, **`signed long int`**

- **`unsigned long`**, **`unsigned long int`**

- **`long long`**, **`long long int`**, **`signed long long`**, **`signed long long int`**

- **`unsigned long long`**, **`unsigned long long int`**

**Microsoft 'a özgü** tamsayı türleri, belirli Genişlik **`__int8`** , **`__int16`** , **`__int32`** , ve türleri içerir **`__int64`** . Bu türler **`signed`** ve **`unsigned`** değiştiricilerini kullanabilir. **`__int8`** Veri türü türü ile eşanlamlıdır, türü ile eşanlamlıdır, türü ile eşanlamlıdır **`char`** **`__int16`** **`short`** **`__int32`** **`int`** ve **`__int64`** türüyle **`long long`** eşanlamlı olur.

## <a name="sizes-of-built-in-types"></a>Yerleşik türlerin boyutları

Çoğu yerleşik türde uygulama tanımlı boyutlar vardır. Aşağıdaki tabloda, Microsoft C++ ' ta yerleşik türler için gereken depolama alanı miktarı listelenmektedir. Özellikle, **`long`** 64 bit işletim sistemlerinde bile 4 bayttır.

| Tür | Boyut |
|--|--|
| **`bool`**, **`char`**, **`char8_t`**, **`unsigned char`**, **`signed char`**, **`__int8`** | 1 bayt |
| **`char16_t`**, **`__int16`**, **`short`**, **`unsigned short`**, **`wchar_t`**, **`__wchar_t`** | 2 bayt |
| **`char32_t`**, **`float`**, **`__int32`**, **`int`**, **`unsigned int`**, **`long`**, **`unsigned long`** | 4 bayt |
| **`double`**, **`__int64`**, **`long double`**, **`long long`**, **`unsigned long long`** | 8 bayt |

Her türün değer aralığının bir özeti için bkz. [veri türü aralıkları](data-type-ranges.md) .

Tür dönüştürmesi hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri türü aralıkları](data-type-ranges.md)
