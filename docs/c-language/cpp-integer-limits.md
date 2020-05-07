---
title: C ve C++ tamsayı sınırları
ms.date: 10/21/2019
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
ms.openlocfilehash: 6940f36e37ec58ca8fe23c9062928cbf90b125bd
ms.sourcegitcommit: ea9d78dbb93bf3f8841dde93dbc12bd66f6f32ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72778371"
---
# <a name="c-and-c-integer-limits"></a>C ve C++ tamsayı sınırları

**Microsoft'a Özgü**

C ve C++ içindeki tamsayı türleri için sınırlar aşağıdaki tabloda listelenmiştir. Bu sınırlar, C standart üstbilgi dosyasında `<limits.h>`tanımlanmıştır. C++ standart kitaplığı üst bilgisi `<limits>` `<climits>`içerir `<limits.h>`.

Microsoft C Ayrıca, 8-, 16-, 32 veya 64-bit tam sayı türleri olan boyutlu tamsayı değişkenlerinin bildirimine izin verir. C 'de boyutlandırılmış tamsayılar hakkında daha fazla bilgi için bkz. [boyutlandırılmış tamsayı türleri](../c-language/c-sized-integer-types.md).

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri için sınırlar

|**Sabit**|Anlamı|Değer|
|------------------|-------------|-----------|
|**CHAR_BIT**|En küçük değişkende bit alanı olmayan bit sayısı.|8|
|**SCHAR_MIN**|**İşaretli char**türünde bir değişken için minimum değer.|-128|
|**SCHAR_MAX**|**İşaretli char**türünde bir değişken için maksimum değer.|127|
|**UCHAR_MAX**|**İşaretsiz char**türünde bir değişken için maksimum değer.|255 (0xFF)|
|**CHAR_MIN**|**Char**türünde bir değişken için minimum değer.|-128; /J seçeneği kullanılırsa 0|
|**CHAR_MAX**|**Char**türünde bir değişken için maksimum değer.|127; 255 Eğer/J seçeneği kullanılırsa|
|**MB_LEN_MAX**|Çok karakterli bir sabitteki en fazla bayt sayısı.|5|
|**SHRT_MIN**|**Short**türünde bir değişken için minimum değer.|-32768|
|**SHRT_MAX**|**Short**türünde bir değişken için maksimum değer.|32767|
|**USHRT_MAX**|**İşaretsiz Short**türünde bir değişken için maksimum değer.|65535 (0xFFFF)|
|**INT_MIN**|**İnt**türünde bir değişken için minimum değer.|-2147483647-1|
|**INT_MAX**|**İnt**türünde bir değişken için maksimum değer.|2147483647|
|**UINT_MAX**|**İşaretsiz int**türünde bir değişken için maksimum değer.|4294967295 (0xffffffff)|
|**LONG_MIN**|**Long**türünde bir değişken için minimum değer.|-2147483647-1|
|**LONG_MAX**|**Long**türünde bir değişken için maksimum değer.|2147483647|
|**ULONG_MAX**|**İşaretsiz Long**türünde bir değişken için maksimum değer.|4294967295 (0xffffffff)|
|**LLONG_MIN**|**Long Long**türünde bir değişken için minimum değer.|-9.223.372.036.854.775.807-1|
|**LLONG_MAX**|**Long Long**türündeki bir değişken için maksimum değer.|9.223.372.036.854.775.807|
|**ULLONG_MAX**|**İşaretsiz Long**Long türündeki bir değişken için maksimum değer.|18446744073709551615 (0xffffffffffffffff)|

Bir değer en büyük tamsayı gösterimini aşarsa, Microsoft derleyicisi bir hata oluşturur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Tamsayı Sabitleri](../c-language/c-integer-constants.md)
