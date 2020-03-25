---
title: Tamsayı Sınırları
ms.date: 01/29/2018
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
ms.openlocfilehash: 75cd05e73aba2d2e82e8077e0a289d8b0fae7ec4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178230"
---
# <a name="integer-limits"></a>Tamsayı Sınırları

**Microsoft 'a özgü**

Tamsayı türleri için sınırlar aşağıdaki tabloda listelenmiştir. Bu sınırlar Ayrıca, standart üstbilgi dosyasında \<limit. h > de tanımlanır.

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri için sınırlar

|Sabit|Anlamı|Değer|
|--------------|-------------|-----------|
|CHAR_BIT|En küçük değişkende bit alanı olmayan bit sayısı.|8|
|SCHAR_MIN|**İşaretli char**türünde bir değişken için minimum değer.|-128|
|SCHAR_MAX|**İşaretli char**türünde bir değişken için maksimum değer.|127|
|UCHAR_MAX|**İşaretsiz char**türünde bir değişken için maksimum değer.|255 (0xff)|
|CHAR_MIN|**Char**türünde bir değişken için minimum değer.|-128; /J seçeneği kullanılırsa 0|
|CHAR_MAX|**Char**türünde bir değişken için maksimum değer.|127; 255 Eğer/J seçeneği kullanılırsa|
|MB_LEN_MAX|Çok karakterli bir sabitteki en fazla bayt sayısı.|5|
|SHRT_MIN|**Short**türünde bir değişken için minimum değer.|-32768|
|SHRT_MAX|**Short**türünde bir değişken için maksimum değer.|32767|
|USHRT_MAX|**İşaretsiz Short**türünde bir değişken için maksimum değer.|65535 (0xFFFF)|
|INT_MIN|**İnt**türünde bir değişken için minimum değer.|-2147483648|
|INT_MAX|**İnt**türünde bir değişken için maksimum değer.|2147483647|
|UINT_MAX|**İşaretsiz int**türünde bir değişken için maksimum değer.|4294967295 (0xffffffff)|
|LONG_MIN|**Long**türünde bir değişken için minimum değer.|-2147483648|
|LONG_MAX|**Long**türünde bir değişken için maksimum değer.|2147483647|
|ULONG_MAX|**İşaretsiz Long**türünde bir değişken için maksimum değer.|4294967295 (0xffffffff)|
|LLONG_MIN|**Long Long** türünde bir değişken için en düşük değer|-9223372036854775808|
|LLONG_MAX|**Long Long** türünde bir değişken için maksimum değer|9223372036854775807|
|ULLONG_MAX|**İşaretsiz Long** Long türündeki bir değişken için maksimum değer|18446744073709551615 (0xffffffffffffffff)|

Bir değer en büyük tamsayı gösterimini aşarsa, Microsoft derleyicisi bir hata oluşturur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Sınırlar](../cpp/floating-limits.md)
