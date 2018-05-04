---
title: Tamsayı sınırları | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 656873dc510f53fc05250a28c61cc452078c4aca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="integer-limits"></a>Tamsayı Sınırları

**Microsoft özel**

Tamsayı türleri için sınırları aşağıdaki tabloda listelenmiştir. Bu sınırlar da standart üstbilgi dosyası < lımıts.h > tanımlanır.

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri sınırlamaları

|Sabit|Açıklama|Değer|
|--------------|-------------|-----------|
|**CHAR_BIT**|Bit sayısı kadar küçük değişkeninde bir bit alan değil.|8|
|**SCHAR_MIN**|Türünde bir değişken için en düşük değer **char imzalı**.|-128|
|**SCHAR_MAX**|Türünde bir değişken için maksimum değeri **char imzalı**.|127|
|**UCHAR_MAX**|Türünde bir değişken için maksimum değeri **imzasız char**.|255 (0xff)|
|**CHAR_MIN**|Türünde bir değişken için en düşük değer **char**.|-128; /J seçeneği kullanılırsa 0|
|**CHAR_MAX**|Türünde bir değişken için maksimum değeri **char**.|127; /J seçeneği kullanılırsa 255|
|**MB_LEN_MAX**|En fazla multicharacter sabiti bayt sayısı.|5|
|**SHRT_MIN**|Türünde bir değişken için en düşük değer **kısa**.|-32768|
|**SHRT_MAX**|Türünde bir değişken için maksimum değeri **kısa**.|32767|
|**USHRT_MAX**|Türünde bir değişken için maksimum değeri **kısa imzasız**.|65535 (0xffff)|
|**INT_MIN**|Türünde bir değişken için en düşük değer **int**.|-2147483648|
|**INT_MAX**|Türünde bir değişken için maksimum değeri **int**.|2147483647|
|**UINT_MAX**|Türünde bir değişken için maksimum değeri **imzasız int**.|4294967295 (0xffffffff)|
|**LONG_MIN**|Türünde bir değişken için en düşük değer **uzun**.|-2147483648|
|**LONG_MAX**|Türünde bir değişken için maksimum değeri **uzun**.|2147483647|
|**ULONG_MAX**|Türünde bir değişken için maksimum değeri **uzun imzasız**.|4294967295 (0xffffffff)|
|**LLONG_MIN**|Türünde bir değişken için en düşük değer **uzun uzun**|-9223372036854775808|
|**LLONG_MAX**|Türünde bir değişken için maksimum değeri **uzun uzun**|9223372036854775807|
|**ULLONG_MAX**|Türünde bir değişken için maksimum değeri **uzun uzun imzalanmamış**|18446744073709551615 (0xffffffffffffffff)|

Bir değer en büyük tamsayı gösterimi aşarsa, Microsoft derleyici bir hata oluşturur.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca Bkz.

[Kayan Sınırlar](../cpp/floating-limits.md)  
