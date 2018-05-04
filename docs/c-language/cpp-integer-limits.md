---
title: C++ tamsayı sınırları | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c95e0affa9047aa41ee5ff04b011ac0fbd8d63d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-integer-limits"></a>C++ Tamsayı Sınırları

**Microsoft özel**

Tamsayı türleri için sınırları aşağıdaki tabloda listelenmiştir. Bu sınırlar da standart üstbilgi tanımlanan dosya SINIRLARI. H. Microsoft C ayrıca boyutu 8-tam sayı türleri olan boyutlu tamsayı değişken bildirimi verir 16 veya 32-bit. Boyutlu tamsayı hakkında daha fazla bilgi için bkz: [boyutlu tamsayı türleri](../c-language/c-sized-integer-types.md).

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri sınırlamaları

|**sabiti**|Açıklama|Değer|
|------------------|-------------|-----------|
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
|**INT_MIN**|Türünde bir değişken için en düşük değer **int**.|-2147483647 - 1|
|**INT_MAX**|Türünde bir değişken için maksimum değeri **int**.|2147483647|
|**UINT_MAX**|Türünde bir değişken için maksimum değeri **imzasız int**.|4294967295 (0xffffffff)|
|**LONG_MIN**|Türünde bir değişken için en düşük değer **uzun**.|-2147483647 - 1|
|**LONG_MAX**|Türünde bir değişken için maksimum değeri **uzun**.|2147483647|
|**ULONG_MAX**|Türünde bir değişken için maksimum değeri **uzun imzasız**.|4294967295 (0xffffffff)|

Bir değer en büyük tamsayı gösterimi aşarsa, Microsoft derleyici bir hata oluşturur.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[C Tamsayı Sabitleri](../c-language/c-integer-constants.md)  
