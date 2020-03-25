---
title: Veri Türü Aralıkları
ms.date: 05/07/2019
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
ms.openlocfilehash: 8b4031eccccb432342790fef4da809542e77d669
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180270"
---
# <a name="data-type-ranges"></a>Veri Türü Aralıkları

Microsoft C++ 32-bit ve 64 bit derleyicileri, bu makalede daha sonra tablodaki türleri algılar.

- `int` (`unsigned int`)

- `__int8` (`unsigned __int8`)

- `__int16` (`unsigned __int16`)

- `__int32` (`unsigned __int32`)

- `__int64` (`unsigned __int64`)

- `short` (`unsigned short`)

- `long` (`unsigned long`)

- `long` `long` (`unsigned long long`)

Adı iki alt çizgi (`__`) ile başlıyorsa, veri türü standart değildir.

Aşağıdaki tabloda belirtilen aralıklar dahil değildir.

|Tür Adı|Bayt|Diğer adlar|Değer aralığı|
|---------------|-----------|-----------------|---------------------|
|**int**|4|**imza**|-2.147.483.648-2.147.483.647|
|**işaretsiz int**|4|**işaretlenmemiş**|0-4.294.967.295|
|**__int8**|1|**char**|-128-127|
|**imzasız __int8**|1|**işaretsiz karakter**|0-255|
|**__int16**|2|**kısa**, **kısa tamsayı**, **imzalanmış kısa tamsayı**|-32.768-32.767|
|**İmzasız __int16**|2|**işaretsiz kısa**, **işaretsiz kısa tamsayı**|0-65.535|
|**__int32**|4|**imzalanan**, **işaretli int**, **int**|-2.147.483.648-2.147.483.647|
|**imzasız __int32**|4|**işaretsiz**, **işaretsiz int**|0-4.294.967.295|
|**__int64**|8|**uzun**uzun, **imzalanan uzun uzun**|-9223372036854775808-9.223.372.036.854.775.807|
|**imzasız __int64**|8|**imzasız uzun uzun**|0-18446744073709551615|
|**bool**|1|yok|**yanlış** veya **doğru**|
|**char**|1|yok|-128 varsayılan olarak 127<br /><br /> [/j](../build/reference/j-default-char-type-is-unsigned.md) kullanılarak derlendiğinde 0-255|
|**işaretli karakter**|1|yok|-128-127|
|**işaretsiz karakter**|1|yok|0-255|
|**short**|2|**kısa tamsayı**, **imzalanmış kısa tamsayı**|-32.768-32.767|
|**işaretsiz kısa**|2|**işaretsiz kısa tamsayı**|0-65.535|
|**long**|4|**long int**, **signed long int**|-2.147.483.648-2.147.483.647|
|**imzasız Long**|4|**işaretsiz long int**|0-4.294.967.295|
|**uzun uzun**|8|hiçbiri (ancak **__int64**eşdeğerdir)|-9223372036854775808-9.223.372.036.854.775.807|
|**imzasız uzun uzun**|8|hiçbiri (ancak **işaretsiz __int64**eşdeğerdir)|0-18446744073709551615|
|**enum**|olmadığına|yok| |
|**float**|4|yok|3.4 e +/-38 (7 basamak)|
|**double**|8|yok|1.7 e +/-308 (15 basamak)|
|**uzun çift**|**Double** ile aynı|yok|**Double** ile aynı|
|**wchar_t**|2|**__wchar_t**|0-65.535|

Nasıl kullanıldığına bağlı olarak, **__wchar_t** değişkeni geniş karakterli bir tür veya çok baytlı karakter türü belirler. Geniş karakter türü sabiti belirlemek için bir karakter veya dize sabitinden önce `L` önekini kullanın.

**imzalı** ve **işaretsiz** , **bool**dışında herhangi bir integral türü ile kullanabileceğiniz değiştiricilerdir. **Karakter**, **işaretli karakter**ve **işaretsiz char** 'ın aşırı yükleme ve şablonlar gibi mekanizmaların amaçları için üç farklı tür olduğunu unutmayın.

**İnt** ve **işaretsiz int** türleri dört baytlık bir boyuta sahiptir. Ancak, dil standardı buna uygulamaya özgü olmasına izin verdiğinden taşınabilir kod, **int** boyutuna bağlı olmamalıdır.

Visual StudioC++ 'da C/, boyutlandırılmış tamsayı türlerini de destekler. Daha fazla bilgi için bkz. [__int8, \__int16, \__int32, \__int64](../cpp/int8-int16-int32-int64.md) ve [tamsayı sınırları](../cpp/integer-limits.md).

Her türün boyutlarının kısıtlamaları hakkında daha fazla bilgi için bkz. [Yerleşik türler](../cpp/fundamental-types-cpp.md).

Numaralandırılmış türlerin aralığı, dil bağlamına ve belirtilen derleyici bayraklarına göre değişir. Daha fazla bilgi için bkz. [C numaralandırma bildirimleri](../c-language/c-enumeration-declarations.md) ve [numaralandırmalar](../cpp/enumerations-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Yerleşik türler](../cpp/fundamental-types-cpp.md)
