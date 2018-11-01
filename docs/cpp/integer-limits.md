---
title: Tamsayı Sınırları
ms.date: 01/29/2018
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
ms.openlocfilehash: 0d14f6246dd2ec71c4e0b2286bb1f2b3325085b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522973"
---
# <a name="integer-limits"></a>Tamsayı Sınırları

**Microsoft'a özgü**

Tamsayı türleri için sınırlar aşağıdaki tabloda listelenmiştir. Bu sınırlar da standart üstbilgi dosyasında tanımlanan \<lımıts.h >.

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri sınırlamaları

|Sabit|Açıklama|Değer|
|--------------|-------------|-----------|
|CHAR_BIT|Bir bit alanı olmayan en küçük değişkeni bit sayısı.|8|
|SCHAR_MIN|Türünde bir değişken için minimum değeri **signed char**.|-128|
|SCHAR_MAX|Türünde bir değişken için maksimum değer **signed char**.|127|
|UCHAR_MAX|Türünde bir değişken için maksimum değer **imzasız char**.|255 (0xff)|
|CHAR_MIN|Türünde bir değişken için minimum değeri **char**.|-128; /J seçeneği kullandıysanız 0|
|CHAR_MAX|Türünde bir değişken için maksimum değer **char**.|127; /J seçeneği kullandıysanız 255|
|MB_LEN_MAX|Çoklu karakter sabitindeki bayt sayısı.|5|
|SHRT_MIN|Türünde bir değişken için minimum değeri **kısa**.|-32768|
|SHRT_MAX|Türünde bir değişken için maksimum değer **kısa**.|32767|
|USHRT_MAX|Türünde bir değişken için maksimum değer **işaretsiz**.|65535 (0xffff)|
|INT_MIN|Türünde bir değişken için minimum değeri **int**.|-2147483648|
|INT_MAX|Türünde bir değişken için maksimum değer **int**.|2147483647|
|UINT_MAX|Türünde bir değişken için maksimum değer **işaretsiz int**.|4294967295 (0xffffffff)|
|LONG_MIN|Türünde bir değişken için minimum değeri **uzun**.|-2147483648|
|LONG_MAX|Türünde bir değişken için maksimum değer **uzun**.|2147483647|
|ULONG_MAX|Türünde bir değişken için maksimum değer **işaretsiz uzun**.|4294967295 (0xffffffff)|
|LLONG_MIN|Türünde bir değişken için minimum değeri **uzun uzun**|-9223372036854775808|
|LLONG_MAX|Türünde bir değişken için maksimum değer **uzun uzun**|9223372036854775807|
|ULLONG_MAX|Türünde bir değişken için maksimum değer **işaretsiz long long**|18446744073709551615 (0xffffffffffffffff)|

Microsoft derleyicisi, bir değeri en büyük tamsayı gösterimi aşarsa, bir hata oluşturur.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Sınırlar](../cpp/floating-limits.md)