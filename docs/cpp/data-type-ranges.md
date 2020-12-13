---
description: 'Hakkında daha fazla bilgi edinin: veri türü aralıkları'
title: Veri Türü Aralıkları
ms.date: 05/28/2020
helpviewer_keywords:
- float keyword [C++]
- char keyword [C++]
- unsigned long
- __wchar_t keyword [C++]
- unsigned short int [C++]
- enum keyword [C++]
- unsigned char keyword [C++]
- integer data type [C++], data type ranges
- int data type
- data types [C++], ranges
- unsigned int [C++]
- short data type
- short int data
- signed types [C++], data type ranges
- long long keyword [C++]
- long double keyword [C++]
- double data type [C++], data type ranges
- signed short int [C++]
- unsigned short
- sized integer types
- signed int [C++]
- signed long int [C++]
- signed char keyword [C++]
- wchar_t keyword [C++]
- long keyword [C++]
- ranges [C++]
- unsigned types [C++], data type ranges
- floating-point numbers [C++]
- data type ranges
- ranges [C++], data types
- long int keyword [C++]
- unsigned long int [C++]
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
ms.openlocfilehash: 8d4ae1b6aae3a4dbf12180248df6000085103efe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339533"
---
# <a name="data-type-ranges"></a>Veri Türü Aralıkları

Microsoft C++ 32-bit ve 64 bit derleyicileri, bu makalenin ilerleyen kısımlarında tablodaki türleri algılar.

- **`int`** (**`unsigned int`**)

- **`__int8`** (**`unsigned __int8`**)

- **`__int16`** (**`unsigned __int16`**)

- **`__int32`** (**`unsigned __int32`**)

- **`__int64`** (**`unsigned __int64`**)

- **`short`** (**`unsigned short`**)

- **`long`** (**`unsigned long`**)

- **`long long`** (**`unsigned long long`**)

Adı iki alt çizgi () ile başlıyorsa `__` , veri türü standart değildir.

Aşağıdaki tabloda belirtilen aralıklar dahil değildir.

|Tür adı|Bayt|Diğer adlar|Değer aralığı|
|---------------|-----------|-----------------|---------------------|
|**`int`**|4|**`signed`**|-2.147.483.648-2.147.483.647|
|**`unsigned int`**|4|**`unsigned`**|0-4.294.967.295|
|**`__int8`**|1|**`char`**|-128-127|
|**`unsigned __int8`**|1|**`unsigned char`**|0-255|
|**`__int16`**|2|**`short`**, **`short int`**, **`signed short int`**|-32.768-32.767|
|**`unsigned __int16`**|2|**`unsigned short`**, **`unsigned short int`**|0-65.535|
|**`__int32`**|4|**`signed`**, **`signed int`**, **`int`**|-2.147.483.648-2.147.483.647|
|**`unsigned __int32`**|4|**`unsigned`**, **`unsigned int`**|0-4.294.967.295|
|**`__int64`**|8|**`long long`**, **`signed long long`**|-9223372036854775808-9.223.372.036.854.775.807|
|**`unsigned __int64`**|8|**`unsigned long long`**|0-18446744073709551615|
|**`bool`**|1|yok|**`false`** veya **`true`**|
|**`char`**|1|yok|-128 varsayılan olarak 127<br /><br /> kullanılarak derlendiğinde 0-255 [`/J`](../build/reference/j-default-char-type-is-unsigned.md)|
|**`signed char`**|1|yok|-128-127|
|**`unsigned char`**|1|yok|0-255|
|**`short`**|2|**`short int`**, **`signed short int`**|-32.768-32.767|
|**`unsigned short`**|2|**`unsigned short int`**|0-65.535|
|**`long`**|4|**`long int`**, **`signed long int`**|-2.147.483.648-2.147.483.647|
|**`unsigned long`**|4|**`unsigned long int`**|0-4.294.967.295|
|**`long long`**|8|hiçbiri (ancak eşdeğeri **`__int64`** )|-9223372036854775808-9.223.372.036.854.775.807|
|**`unsigned long long`**|8|hiçbiri (ancak eşdeğeri **`unsigned __int64`** )|0-18446744073709551615|
|**`enum`**|olmadığına|yok| |
|**`float`**|4|yok|3.4 e +/-38 (7 basamak)|
|**`double`**|8|yok|1.7 e +/-308 (15 basamak)|
|**`long double`**|aynı **`double`**|yok|Aynı **`double`**|
|**`wchar_t`**|2|**`__wchar_t`**|0-65.535|

Nasıl kullanıldığına bağlı olarak, bir değişkeni **`__wchar_t`** geniş karakterli bir tür veya çok baytlı karakter türü belirler. `L`Geniş karakter türü sabiti belirlemek için bir karakter veya dize sabitinden önce öneki kullanın.

**`signed`** ve **`unsigned`** dışında herhangi bir integral türüyle kullanabileceğiniz değiştiriciler vardır **`bool`** . , **`char`** **`signed char`** Ve, **`unsigned char`** aşırı yükleme ve şablonlar gibi mekanizmaların amaçları için üç farklı tür olduğunu unutmayın.

**`int`** Ve **`unsigned int`** türleri dört baytlık bir boyuta sahiptir. Ancak, **`int`** dil standardı buna uygulamaya özgü olmasına izin verdiğinden taşınabilir kod boyutuna bağlı olmamalıdır.

Visual Studio 'da C/C++, boyutlandırılmış tamsayı türlerini de destekler. Daha fazla bilgi için bkz [`__int8, __int16, __int32, __int64`](../cpp/int8-int16-int32-int64.md) . ve [tamsayı sınırları](../cpp/integer-limits.md).

Her türün boyutlarının kısıtlamaları hakkında daha fazla bilgi için bkz. [Yerleşik türler](../cpp/fundamental-types-cpp.md).

Numaralandırılmış türlerin aralığı, dil bağlamına ve belirtilen derleyici bayraklarına göre değişir. Daha fazla bilgi için bkz. [C numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md) ve [numaralandırmalar](../cpp/enumerations-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)
