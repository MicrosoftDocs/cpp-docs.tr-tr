---
title: Veri türü sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
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
- LLONG_MIN
- LLONG_MAX
- ULLONG_MAX
- _I8_MIN
- _I8_MAX
- _UI8_MAX
- _I16_MIN
- _I16_MAX
- _UI16_MAX
- _I32_MIN
- _I32_MAX
- _UI32_MAX
- _I64_MIN
- _I64_MAX
- _UI64_MAX
- _I128_MIN
- _I128_MAX
- _UI128_MAX
- SIZE_MAX
- RSIZE_MAX
- LDBL_DIG
- LDBL_EPSILON
- LDBL_HAS_SUBNORM
- LDBL_MANT_DIG
- LDBL_MAX
- LDBL_MAX_10_EXP
- LDBL_MAX_EXP
- LDBL_MIN
- LDBL_MIN_10_EXP
- LDBL_MIN_EXP
- _LDBL_RADIX
- LDBL_TRUE_MIN
- DECIMAL_DIG
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
- LLONG_MIN constant
- LLONG_MAX constant
- ULLONG_MAX constant
- _I8_MIN constant
- _I8_MAX constant
- _UI8_MAX constant
- _I16_MIN constant
- _I16_MAX constant
- _UI16_MAX constant
- _I32_MIN constant
- _I32_MAX constant
- _UI32_MAX constant
- _I64_MIN constant
- _I64_MAX constant
- _UI64_MAX constant
- _I128_MIN constant
- _I128_MAX constant
- _UI128_MAX constant
- SIZE_MAX constant
- RSIZE_MAX constant
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef742989b4af7a3698f6047098110ee58e29bf4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035675"
---
# <a name="data-type-constants"></a>Veri Türü Sabitleri

Veri türü sabitleri, integral ve kayan nokta veri türleri için izin verilen değerlerin uygulama bağımlıdır aralıktır.

## <a name="integral-type-constants"></a>İntegral türü sabitleri

Bu sabitler tam sayı veri türleri için aralıklar verin. Bu sabitler kullanmak için kaynak dosyanızdaki lımıts.h üstbilgi şunlardır:

```C
#include <limits.h>
```

> [!NOTE]
> [/J](../build/reference/j-default-char-type-is-unsigned.md) derleyici seçeneği, varsayılan değişiklikleri **char** için yazın **işaretsiz**.

|Sabit|Değer|Açıklama|
|--------------|-----------|-------------|
|**CHAR_BIT**|8|Bit sayısı bir **char**|
|**SCHAR_MIN**|(-128)|İmzalı minimum **char** değeri|
|**SCHAR_MAX**|127|Maksimum oturum **char** değeri|
|**UCHAR_MAX**|255 (0xff)|En fazla **işaretsiz** **char** değeri|
|**CHAR_MIN**|(-128) (0 ise **/J** seçeneği kullanılır)|En az **char** değeri|
|**CHAR_MAX**|127 (255 ise **/J** seçeneği kullanılır)|En fazla **char** değeri|
|**MB_LEN_MAX**|5|Çok baytlı bayt sayısı **char**|
|**SHRT_MIN**|-32768|İmzalı minimum **kısa** değeri|
|**SHRT_MAX**|32767|Maksimum oturum **kısa** değeri|
|**USHRT_MAX**|65535 (0xffff)|En fazla **işaretsiz** **kısa** değeri|
|**INT_MIN**|(-2147483647 - 1)|İmzalı minimum **int** değeri|
|**INT_MAX**|2147483647|Maksimum oturum **int** değeri|
|**UINT_MAX**|4294967295 (0xffffffff)|En fazla **işaretsiz** **int** değeri|
|**LONG_MIN**|(-2147483647 M - 1)|İmzalı minimum **uzun** değeri|
|**LONG_MAX**|2147483647 M|Maksimum oturum **uzun** değeri|
|**ULONG_MAX**|4294967295UL (0xfffffffful)|En fazla **işaretsiz** **uzun** değeri|
|**LLONG_MIN**|(- 9223372036854775807LL - 1)|İmzalı minimum **uzun** **uzun** veya **__int64** değeri|
|**LLONG_MAX**|9223372036854775807LL|Maksimum oturum **uzun** **uzun** veya **__int64** değeri|
|**ULLONG_MAX**|0xffffffffffffffffull|En fazla **işaretsiz** **uzun** **uzun** değeri|
|**_I8_MIN**|(- 127i8 - 1)|En az 8-bit değeri işaretli|
|**_I8_MAX**|127i8|En fazla 8-bit değeri işaretli|
|**_UI8_MAX**|0xffui8|En fazla imzalanmamış 8 bit değeri|
|**_I16_MIN**|(- 32767i16 - 1)|En az 16-bit değeri işaretli|
|**_I16_MAX**|32767i16|En fazla 16-bit değeri işaretli|
|**_UI16_MAX**|0xffffui16|İmzasız en fazla 16-bit değeri|
|**_I32_MIN**|(- 2147483647i32 - 1)|En az 32-bit değeri işaretli|
|**_I32_MAX**|2147483647i32|En fazla 32-bit değeri işaretli|
|**_UI32_MAX**|0xffffffffui32|En fazla bir işaretsiz 32-bit değeri|
|**_I64_MIN**|(-9223372036854775807 - 1)|En az 64-bit değeri işaretli|
|**_I64_MAX**|9223372036854775807|En fazla 64-bit değeri işaretli|
|**_UI64_MAX**|0xffffffffffffffffui64|En fazla işaretsiz 64-bit değeri|
|**_I128_MIN**|(- 170141183460469231731687303715884105727i128 - 1)|En az 128-bit değeri işaretli|
|**_I128_MAX**|170141183460469231731687303715884105727i128|En fazla 128-bit değeri işaretli|
|**_UI128_MAX**|0xffffffffffffffffffffffffffffffffui128|İmzasız en fazla 128-bit değeri|
|**SIZE_MAX**|aynı **_UI64_MAX** varsa **_wın64** tanımlanır veya **uınt_max**|En fazla yerel tamsayı boyutu|
|**RSIZE_MAX**|aynı (**SIZE_MAX** >> 1)|En büyük güvenli kitaplığı tamsayı boyutu|

## <a name="floating-point-type-constants"></a>Kayan nokta türü sabitleri

Aşağıdaki sabitler aralığını ve diğer özellikleri de vermek **uzun** **çift**, **çift** ve **float** veri türleri. Bu sabitler kullanmak için kaynak dosyanızdaki float.h üstbilgi şunlardır:

```C
#include <float.h>
```

|Sabit|Değer|Açıklama|
|--------------|-----------|-----------------|
|**DBL_DECIMAL_DIG**|17|Duyarlık yuvarlama ondalık basamak sayısı|
|**DBL_DIG**|15|ondalık basamaklı duyarlık sayısı|
|**DBL_EPSILON**|2.2204460492503131e-016|En küçük olacak şekilde 1.0 + **dbl_epsılon** ! = 1,0|
|**DBL_HAS_SUBNORM**|1.|Subnormal türü destekler (denormal sayılar)|
|**DBL_MANT_DIG**|53|anlam (Mantis) bit sayısı|
|**DBL_MAX**|1.7976931348623158e + 308|En yüksek değer|
|**DBL_MAX_10_EXP**|308|En fazla ondalık üs|
|**DBL_MAX_EXP**|1024|En büyük ikili üs|
|**DBL_MIN**|2.2250738585072014e-308|En küçük pozitif değer normalleştirilmiş|
|**DBL_MIN_10_EXP**|(-307)|En düşük ondalık üs|
|**DBL_MIN_EXP**|(-1021)|En düşük ikili üs|
|**_DBL_RADIX**|2|Üs tabanı|
|**DBL_TRUE_MIN**|4.9406564584124654e-324|En küçük pozitif subnormal değer|
|**FLT_DECIMAL_DIG**|9|Duyarlık yuvarlama ondalık basamak sayısı|
|**FLT_DIG**|6|Ondalık basamaklı duyarlık sayısı|
|**FLT_EPSILON**|1.192092896e-07F|En küçük olacak şekilde 1.0 + **flt_epsılon** ! = 1,0|
|**FLT_HAS_SUBNORM**|1.|Subnormal türü destekler (denormal sayılar)|
|**FLT_MANT_DIG**|24|Anlam (Mantis) bit sayısı|
|**FLT_MAX**|3.402823466e + 38F|En yüksek değer|
|**FLT_MAX_10_EXP**|38|En fazla ondalık üs|
|**FLT_MAX_EXP**|128|En büyük ikili üs|
|**FLT_MIN**|1.175494351e-38F|En küçük pozitif değer normalleştirilmiş|
|**FLT_MIN_10_EXP**|(-37)|En düşük ondalık üs|
|**FLT_MIN_EXP**|(-125)|En düşük ikili üs|
|**FLT_RADIX**|2|Üs tabanı|
|**FLT_TRUE_MIN**|1.401298464e-45F|En küçük pozitif subnormal değer|
|**LDBL_DIG**|15|ondalık basamaklı duyarlık sayısı|
|**LDBL_EPSILON**|2.2204460492503131e-016|En küçük olacak şekilde 1.0 + **LDBL_EPSILON** ! = 1,0|
|**LDBL_HAS_SUBNORM**|1.|Subnormal türü destekler (denormal sayılar)|
|**LDBL_MANT_DIG**|53|anlam (Mantis) bit sayısı|
|**LDBL_MAX**|1.7976931348623158e + 308|En yüksek değer|
|**LDBL_MAX_10_EXP**|308|En fazla ondalık üs|
|**LDBL_MAX_EXP**|1024|En büyük ikili üs|
|**LDBL_MIN**|2.2250738585072014e-308|En küçük pozitif değer normalleştirilmiş|
|**LDBL_MIN_10_EXP**|(-307)|En düşük ondalık üs|
|**LDBL_MIN_EXP**|(-1021)|En düşük ikili üs|
|**_LDBL_RADIX**|2|Üs tabanı|
|**LDBL_TRUE_MIN**|4.9406564584124654e-324|En küçük pozitif subnormal değer|
|**DECIMAL_DIG**|aynı **DBL_DECIMAL_DIG**|Duyarlık yuvarlama varsayılan (çift) ondalık basamak sayısı|

## <a name="see-also"></a>Ayrıca bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)
