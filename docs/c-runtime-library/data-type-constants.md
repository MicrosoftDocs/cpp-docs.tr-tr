---
title: Veri türü sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- FLT_MIN
- SHRT_MAX
- CHAR_MIN
- MB_LEN_MAX
- DBL_EPSILON
- SHRT_MIN
- _FLT_RADIX
- FLT_DIG
- FLT_MAX_10_EXP
- FLT_MANT_DIG
- DBL_MAX_EXP
- SCHAR_MIN
- SCHAR_MAX
- DBL_MIN
- FLT_MIN_10_EXP
- _DBL_ROUNDS
- USHRT_MAX
- FLT_MAX_EXP
- LONG_MAX
- DBL_MAX
- DBL_DIG
- FLT_MIN_EXP
- INT_MIN
- DBL_MIN_10_EXP
- CHAR_BIT
- INT_MAX
- ULONG_MAX
- DBL_MIN_EXP
- LONG_MIN
- _FLT_ROUNDS
- DBL_MANT_DIG
- _DBL_RADIX
- CHAR_MAX
- FLT_MAX
- DBL_MAX_10_EXP
- UCHAR_MAX
- FLT_EPSILON
- UINT_MAX
dev_langs:
- C++
helpviewer_keywords:
- DBL_MAX_EXP constant
- _DBL_RADIX constant
- FLT_MIN_EXP constant
- DBL_EPSILON constant
- INT_MIN constant
- FLT_EPSILON constant
- DBL_MANT_DIG constant
- _FLT_RADIX constant
- DBL_MIN constant
- USHRT_MAX constant
- FLT_MAX_10_EXP constant
- _FLT_ROUNDS constant
- data type constants [C++]
- _DBL_ROUNDS constant
- CHAR_MAX constant
- FLT_MAX_EXP constant
- FLT_MIN constant
- CHAR_MIN constant
- FLT_MIN_10_EXP constant
- DBL_MIN_EXP constant
- SCHAR_MAX constant
- FLT_RADIX constant
- CHAR_BIT constant
- UCHAR_MAX constant
- DBL_RADIX constant
- FLT_ROUNDS constant
- LONG_MIN constant
- SHRT_MAX constant
- LONG_MAX constant
- DBL_MAX_10_EXP constant
- DBL_MIN_10_EXP constant
- INT_MAX constant
- constants [C++], data type
- ULONG_MAX constant
- FLT_DIG constant
- MB_LEN_MAX constant
- DBL_DIG constant
- SHRT_MIN constant
- DBL_MAX constant
- DBL_ROUNDS constant
- FLT_MAX constant
- UINT_MAX constant
- FLT_MANT_DIG constant
- SCHAR_MIN constant
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf9a64b81ae90c517e9cd15e796dfb1333c7b08c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="data-type-constants"></a>Veri Türü Sabitleri
Veri türü sabitleri, tam sayı veri türleri için izin verilen değerlerin uygulama bağımlı aralıktır. Aşağıda listelenen sabitler aralıklara tam sayı veri türleri için vermek ve SINIRLARI tanımlanır. H.  
  
> [!NOTE]
>  /J derleyici seçeneği varsayılan değişiklikleri `char` için yazın `unsigned`.  
  
|Sabit|Değer|Açıklama|  
|--------------|-----------|-------------|  
|**SCHAR_MAX**|127|İmzalı maksimum `char` değeri|  
|**SCHAR_MIN**|-128|İmzalı minimum `char` değeri|  
|**UCHAR_MAX**|255 (0xff)|En fazla `unsigned char` değeri|  
|**CHAR_BIT**|8|Bit sayısı bir `char`|  
|**USHRT_MAX**|65535 (0xffff)|En fazla **kısa imzasız** değeri|  
|**SHRT_MAX**|32767|(İmzalanmış) maksimum **kısa** değeri|  
|**SHRT_MIN**|-32768|(İmzalanmış) minimum **kısa** değeri|  
|**UINT_MAX**|4294967295 (0xffffffff)|En fazla `unsigned int` değeri|  
|**ULONG_MAX**|4294967295 (0xffffffff)|En fazla `unsigned long` değeri|  
|**INT_MAX**|2147483647|(İmzalanmış) maksimum `int` değeri|  
|**INT_MIN**|-2147483647-1|(İmzalanmış) minimum `int` değeri|  
|**LONG_MAX**|2147483647|(İmzalanmış) maksimum **uzun** değeri|  
|**LONG_MIN**|-2147483647-1|(İmzalanmış) minimum **uzun** değeri|  
|**CHAR_MAX**|127 (/J seçeneği kullanılırsa 255)|En fazla `char` değeri|  
|**CHAR_MIN**|-128 (/J seçeneği kullanılırsa 0)|Minimum `char` değeri|  
|**MB_LEN_MAX**|2|Çok baytlı bayt sayısı `char`|  
|**_I64_MAX**|9223372036854775807|En fazla (imzalanmış) __**Int64** değeri|  
|**_I64_MIN**|-9223372036854775807-1|Minimum (imzalanmış) __**Int64** değeri|  
|**_UI64_MAX**|0xffffffffffffffff|En fazla (imzalanmamış) __**Int64** değeri|  
  
 Aşağıdaki sabitleri aralığı ve diğer özelliklerini verin **çift** ve **float** veri türleri ve bu FLOAT tanımlanmış. Y:  
  
|Sabit|Değer|Açıklama|  
|--------------|-----------|-----------------|  
|**DBL_DIG**|15|Duyarlık ondalık basamak sayısı|  
|**DBL_EPSILON**|2.2204460492503131e-016|En küçük şekilde 1.0 +**dbl_epsılon** ! = 1.0|  
|**DBL_MANT_DIG**|53|Mantis bit sayısı|  
|**DBL_MAX**|1.7976931348623158e + 308|En büyük değer|  
|**DBL_MAX_10_EXP**|308|En fazla ondalık üs|  
|**DBL_MAX_EXP**|1024|En fazla ikili üs|  
|**DBL_MIN**|2.2250738585072014e-308|En küçük pozitif bir değer|  
|**DBL_MIN_10_EXP**|(-307)|Minimum ondalık üs|  
|**DBL_MIN_EXP**|(-1021)|Minimum ikili üs|  
|**_DBL_RADIX**|2|Üs taban|  
|**_DBL_ROUNDS**|1.|Toplama yuvarlama: yakın|  
|**FLT_DIG**|6|Duyarlık ondalık basamak sayısı|  
|**FLT_EPSILON**|1.192092896e-07F|En küçük şekilde 1.0 +**flt_epsılon** ! = 1.0|  
|**FLT_MANT_DIG**|24|Mantis bit sayısı|  
|**FLT_MAX**|3.402823466e + 38F|En büyük değer|  
|**FLT_MAX_10_EXP**|38|En fazla ondalık üs|  
|**FLT_MAX_EXP**|128|En fazla ikili üs|  
|**FLT_MIN**|1.175494351e-38F|En küçük pozitif bir değer|  
|**FLT_MIN_10_EXP**|(-37)|Minimum ondalık üs|  
|**FLT_MIN_EXP**|(-125)|Minimum ikili üs|  
|**FLT_RADIX**|2|Üs taban|  
|**FLT_ROUNDS**|1.|Toplama yuvarlama: yakın|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Sabitler](../c-runtime-library/global-constants.md)