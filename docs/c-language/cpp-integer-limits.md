---
title: C++ Tamsayı Sınırları
ms.date: 01/29/2018
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
ms.openlocfilehash: 057da1ac8e4549a05d10a01cc3aead678045d9c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548297"
---
# <a name="c-integer-limits"></a>C++ Tamsayı Sınırları

**Microsoft'a özgü**

Tamsayı türleri için sınırlar aşağıdaki tabloda listelenmiştir. Bu sınırlar standart üstbilgisinde tanımlanan dosya SINIRLARI. H Microsoft C de verir boyutu 8-integral türleridir, boyutlandırılmış tamsayı değişkenlerinin bildirimi 16 veya 32-bit. Boyutlandırılmış tamsayıların hakkında daha fazla bilgi için bkz. [boyutlandırılmış tamsayı türleri](../c-language/c-sized-integer-types.md).

## <a name="limits-on-integer-constants"></a>Tamsayı sabitleri sınırlamaları

|**Sabit**|Açıklama|Değer|
|------------------|-------------|-----------|
|**CHAR_BIT**|Bir bit alanı olmayan en küçük değişkeni bit sayısı.|8|
|**SCHAR_MIN**|Türünde bir değişken için minimum değeri **signed char**.|-128|
|**SCHAR_MAX**|Türünde bir değişken için maksimum değer **signed char**.|127|
|**UCHAR_MAX**|Türünde bir değişken için maksimum değer **imzasız char**.|255 (0xff)|
|**CHAR_MIN**|Türünde bir değişken için minimum değeri **char**.|-128; /J seçeneği kullandıysanız 0|
|**CHAR_MAX**|Türünde bir değişken için maksimum değer **char**.|127; /J seçeneği kullandıysanız 255|
|**MB_LEN_MAX**|Çoklu karakter sabitindeki bayt sayısı.|5|
|**SHRT_MIN**|Türünde bir değişken için minimum değeri **kısa**.|-32768|
|**SHRT_MAX**|Türünde bir değişken için maksimum değer **kısa**.|32767|
|**USHRT_MAX**|Türünde bir değişken için maksimum değer **işaretsiz**.|65535 (0xffff)|
|**INT_MIN**|Türünde bir değişken için minimum değeri **int**.|-2147483647 - 1|
|**INT_MAX**|Türünde bir değişken için maksimum değer **int**.|2147483647|
|**UINT_MAX**|Türünde bir değişken için maksimum değer **işaretsiz int**.|4294967295 (0xffffffff)|
|**LONG_MIN**|Türünde bir değişken için minimum değeri **uzun**.|-2147483647 - 1|
|**LONG_MAX**|Türünde bir değişken için maksimum değer **uzun**.|2147483647|
|**ULONG_MAX**|Türünde bir değişken için maksimum değer **işaretsiz uzun**.|4294967295 (0xffffffff)|

Microsoft derleyicisi, bir değeri en büyük tamsayı gösterimi aşarsa, bir hata oluşturur.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Tamsayı Sabitleri](../c-language/c-integer-constants.md)
