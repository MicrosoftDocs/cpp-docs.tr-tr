---
description: 'Daha fazla bilgi edinin: C ve C++ tamsayı sınırları'
title: C ve C++ tamsayı sınırları
ms.date: 10/21/2019
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
ms.openlocfilehash: c9d15e5366acb482f688e1c5020c43ee83e4e802
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292981"
---
# <a name="c-and-c-integer-limits"></a>C ve C++ tamsayı sınırları

**Microsoft'a Özgü**

C ve C++ içindeki tamsayı türleri için sınırlar aşağıdaki tabloda listelenmiştir. Bu sınırlar, C standart üstbilgi dosyasında tanımlanmıştır `<limits.h>` . C++ standart kitaplığı üst bilgisi `<limits>` içerir `<climits>` `<limits.h>` .

Microsoft C Ayrıca, 8-, 16-, 32 veya 64-bit tam sayı türleri olan boyutlu tamsayı değişkenlerinin bildirimine izin verir. C 'de boyutlandırılmış tamsayılar hakkında daha fazla bilgi için bkz. [boyutlandırılmış tamsayı türleri](../c-language/c-sized-integer-types.md).

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri için sınırlar

|**Sabit**|Anlamı|Değer|
|------------------|-------------|-----------|
|**CHAR_BIT**|En küçük değişkende bit alanı olmayan bit sayısı.|8|
|**SCHAR_MIN**|Türünde bir değişken için minimum değer **`signed char`** .|-128|
|**SCHAR_MAX**|Türünde bir değişken için maksimum değer **`signed char`** .|127|
|**UCHAR_MAX**|Türünde bir değişken için maksimum değer **`unsigned char`** .|255 (0xFF)|
|**CHAR_MIN**|Türünde bir değişken için minimum değer **`char`** .|-128; /J seçeneği kullanılırsa 0|
|**CHAR_MAX**|Türünde bir değişken için maksimum değer **`char`** .|127; 255 Eğer/J seçeneği kullanılırsa|
|**MB_LEN_MAX**|Çok karakterli bir sabitteki en fazla bayt sayısı.|5|
|**SHRT_MIN**|Türünde bir değişken için minimum değer **`short`** .|-32768|
|**SHRT_MAX**|Türünde bir değişken için maksimum değer **`short`** .|32767|
|**USHRT_MAX**|Türünde bir değişken için maksimum değer **`unsigned short`** .|65535 (0xFFFF)|
|**INT_MIN**|Türünde bir değişken için minimum değer **`int`** .|-2147483647-1|
|**INT_MAX**|Türünde bir değişken için maksimum değer **`int`** .|2147483647|
|**UINT_MAX**|Türünde bir değişken için maksimum değer **`unsigned int`** .|4294967295 (0xffffffff)|
|**LONG_MIN**|Türünde bir değişken için minimum değer **`long`** .|-2147483647-1|
|**LONG_MAX**|Türünde bir değişken için maksimum değer **`long`** .|2147483647|
|**ULONG_MAX**|Türünde bir değişken için maksimum değer **`unsigned long`** .|4294967295 (0xffffffff)|
|**LLONG_MIN**|Türünde bir değişken için minimum değer **`long long`** .|-9.223.372.036.854.775.807-1|
|**LLONG_MAX**|Türünde bir değişken için maksimum değer **`long long`** .|9.223.372.036.854.775.807|
|**ULLONG_MAX**|Türünde bir değişken için maksimum değer **`unsigned long long`** .|18446744073709551615 (0xffffffffffffffff)|

Bir değer en büyük tamsayı gösterimini aşarsa, Microsoft derleyicisi bir hata oluşturur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C tamsayı sabitleri](../c-language/c-integer-constants.md)
