---
title: "C++ tamsayı sınırları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- limits, integer
- limits, integer constants
- integer limits
ms.assetid: 0c23cbd6-29fb-4d9c-b689-5984e19748de
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 861310be7e13c0ca5e656edc4214e59f5dacd659
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-integer-limits"></a>C++ Tamsayı Sınırları
**Microsoft özel**  
  
 Tamsayı türleri için sınırları aşağıdaki tabloda listelenmiştir. Bu sınırlar da standart üstbilgi tanımlanan dosya SINIRLARI. H. Microsoft C ayrıca boyutu 8-tam sayı türleri olan boyutlu tamsayı değişken bildirimi verir 16 veya 32-bit. Boyutlu tamsayı hakkında daha fazla bilgi için bkz: [boyutlu tamsayı türleri](../c-language/c-sized-integer-types.md).  
  
### <a name="limits-on-integer-constants"></a>Tamsayı sabitleri sınırlamaları  
  
|**Sabit**|Açıklama|Değer|  
|------------------|-------------|-----------|  
|**CHAR_BIT**|Bit sayısı kadar küçük değişkeninde bir bit alan değil.|8|  
|**SCHAR_MIN**|Türünde bir değişken için en düşük değer **char imzalı**.|-128|  
|**SCHAR_MAX**|Türünde bir değişken için maksimum değeri **char imzalı**.|127|  
|**UCHAR_MAX**|Türünde bir değişken için maksimum değeri `unsigned char`.|255 (0xff)|  
|**CHAR_MIN**|Türünde bir değişken için en düşük değer `char`.|-128; /J seçeneği kullanılırsa 0|  
|**CHAR_MAX**|Türünde bir değişken için maksimum değeri `char`.|127; /J seçeneği kullanılırsa 255|  
|**MB_LEN_MAX**|En fazla multicharacter sabiti bayt sayısı.|5|  
|**SHRT_MIN**|Türünde bir değişken için en düşük değer **kısa**.|-32768|  
|**SHRT_MAX**|Türünde bir değişken için maksimum değeri **kısa**.|32767|  
|**USHRT_MAX**|Türünde bir değişken için maksimum değeri **kısa imzasız**.|65535 (0xffff)|  
|**INT_MIN**|Türünde bir değişken için en düşük değer `int`.|-2147483647 - 1|  
|**INT_MAX**|Türünde bir değişken için maksimum değeri `int`.|2147483647|  
|**UINT_MAX**|Türünde bir değişken için maksimum değeri `unsigned int`.|4294967295 (0xffffffff)|  
|**LONG_MIN**|Türünde bir değişken için en düşük değer **uzun**.|-2147483647 - 1|  
|**LONG_MAX**|Türünde bir değişken için maksimum değeri **uzun**.|2147483647|  
|**ULONG_MAX**|Türünde bir değişken için maksimum değeri `unsigned long`.|4294967295 (0xffffffff)|  
  
 Bir değer en büyük tamsayı gösterimi aşarsa, Microsoft derleyici bir hata oluşturur.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Tamsayı Sabitleri](../c-language/c-integer-constants.md)