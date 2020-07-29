---
title: Veri Türü Sabitleri
ms.date: 06/25/2018
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
ms.openlocfilehash: d9d053611fb733d55424d01be2bab030fc49e6e0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215172"
---
# <a name="data-type-constants"></a>Veri Türü Sabitleri

Veri türü sabitleri, tam sayı ve kayan nokta veri türleri için izin verilen değer aralıklarına bağımlıdır.

## <a name="integral-type-constants"></a>Integral türü sabitleri

Bu sabitler integral veri türleri için aralıklar verir. Bu sabitleri kullanmak için, kaynak dosyanıza limit. h üst bilgisini ekleyin:

```C
#include <limits.h>
```

> [!NOTE]
> [`/J`](../build/reference/j-default-char-type-is-unsigned.md)Derleyici seçeneği varsayılan **`char`** türü iken **`signed char`** olarak değiştirir **`unsigned char`** .

|Sabit|Değer|Açıklama|
|--------------|-----------|-------------|
|**CHAR_BIT**|8|A içindeki bit sayısı**`char`**|
|**SCHAR_MIN**|(-128)|En küçük **`signed char`** değer|
|**SCHAR_MAX**|127|En büyük **`signed char`** değer|
|**UCHAR_MAX**|255 (0xFF)|En büyük **`unsigned char`** değer|
|**CHAR_MIN**|(-128) ( **`/J`** seçenek kullanılırsa 0)|En küçük **`char`** değer|
|**CHAR_MAX**|127 (Bu **`/J`** seçenek kullanılırsa 255)|En büyük **`char`** değer|
|**MB_LEN_MAX**|5|Çok baytlı en fazla bayt sayısı**`char`**|
|**SHRT_MIN**|-32768|En küçük **`signed short`** değer|
|**SHRT_MAX**|32767|En büyük **`signed short`** değer|
|**USHRT_MAX**|65535 (0xFFFF)|En büyük **`unsigned short`** değer|
|**INT_MIN**|(-2147483647-1)|En küçük **`signed int`** değer|
|**INT_MAX**|2147483647|En büyük **`signed int`** değer|
|**UINT_MAX**|4294967295 (0xffffffff)|En büyük **`unsigned int`** değer|
|**LONG_MIN**|(-2147483647L-1)|En küçük **`signed long`** değer|
|**LONG_MAX**|2147483647L|En büyük **`signed long`** değer|
|**ULONG_MAX**|4294967295UL (0xfffffffful)|En büyük **`unsigned long`** değer|
|**LLONG_MIN**|(-9223372036854775807LL-1)|Minimum **`signed long long`** veya **`__int64`** değeri|
|**LLONG_MAX**|9223372036854775807LL|En büyük **`signed long long`** veya **`__int64`** değer|
|**ULLONG_MAX**|0xffffffffffffffffull|En büyük **`unsigned long long`** değer|
|**_I8_MIN**|(-127i8-1)|En az imzalanan 8 bit değer|
|**_I8_MAX**|127i8|En fazla imzalanan 8 bit değer|
|**_UI8_MAX**|0xffuı8|En fazla işaretsiz 8 bit değer|
|**_I16_MIN**|(-32767i16-1)|En düşük imzalı 16 bit değeri|
|**_I16_MAX**|32767i16|En fazla imzalanan 16 bit değer|
|**_UI16_MAX**|0xffffuı16|En fazla işaretsiz 16 bit değer|
|**_I32_MIN**|(-2147483647i32-1)|En düşük imzalı 32 bit değeri|
|**_I32_MAX**|2147483647i32|Maksimum imzalı 32 bit değeri|
|**_UI32_MAX**|0xffffffffuı32|Maksimum işaretsiz 32 bit değeri|
|**_I64_MIN**|(-9223372036854775807-1)|En düşük imzalı 64 bit değeri|
|**_I64_MAX**|9223372036854775807|Maksimum imzalı 64 bit değeri|
|**_UI64_MAX**|0xffffffffffffffffuı64|Maksimum işaretsiz 64 bit değeri|
|**_I128_MIN**|(-170141183460469231731687303715884105727i128-1)|En düşük imzalı 128 bit değeri|
|**_I128_MAX**|170141183460469231731687303715884105727i128|Maksimum imzalı 128 bit değeri|
|**_UI128_MAX**|0xffffffffffffffffffffffffffffffffuı128|Maksimum işaretsiz 128 bit değeri|
|**SIZE_MAX**|**_WIN64** tanımlanmışsa **_UI64_MAX** ile aynı veya **UINT_MAX**|En büyük yerel tamsayı boyutu|
|**RSIZE_MAX**|aynı (**SIZE_MAX** >> 1) ile aynı|En büyük güvenli kitaplık tamsayı boyutu|

## <a name="floating-point-type-constants"></a>Kayan nokta türü sabitleri

Aşağıdaki sabitler, **`long double`** **`double`** ve veri türlerinin aralığını ve diğer özelliklerini verir **`float`** . Bu sabitleri kullanmak için, kaynak dosyanıza float. h üst bilgisini ekleyin:

```C
#include <float.h>
```

|Sabit|Değer|Açıklama|
|--------------|-----------|-----------------|
|**DBL_DECIMAL_DIG**|17|yuvarlama duyarlığının ondalık basamak sayısı|
|**DBL_DIG**|15|duyarlık ondalık basamak sayısı|
|**DBL_EPSILON**|2.2204460492503131 e-bir|En küçük 1,0 + **DBL_EPSILON** ! = 1,0|
|**DBL_HAS_SUBNORM**|1|Tür alt normal (denormal) rakamları destekler|
|**DBL_MANT_DIG**|53|mantisinin içindeki bit sayısı (Mantis)|
|**DBL_MAX**|1.7976931348623158 e + 308|En büyük değer|
|**DBL_MAX_10_EXP**|308|Maksimum ondalık üs|
|**DBL_MAX_EXP**|1024|En yüksek ikili üs|
|**DBL_MIN**|2.2250738585072014 e-308|En düşük normalleştirilmiş pozitif değer|
|**DBL_MIN_10_EXP**|(-307)|En küçük ondalık üs|
|**DBL_MIN_EXP**|(-1021)|En küçük ikili üs|
|**_DBL_RADIX**|2|Üs taban x|
|**DBL_TRUE_MIN**|4.9406564584124654 e-324|Minimum pozitif alt normal değer|
|**FLT_DECIMAL_DIG**|9|Yuvarlama duyarlığının ondalık basamak sayısı|
|**FLT_DIG**|6|Duyarlık ondalık basamak sayısı|
|**FLT_EPSILON**|1.192092896 e-07F|En küçük 1,0 + **FLT_EPSILON** ! = 1,0|
|**FLT_HAS_SUBNORM**|1|Tür alt normal (denormal) rakamları destekler|
|**FLT_MANT_DIG**|24|Mantisinin 'deki bit sayısı (Mantis)|
|**FLT_MAX**|3.402823466 e + 38F|En büyük değer|
|**FLT_MAX_10_EXP**|38|Maksimum ondalık üs|
|**FLT_MAX_EXP**|128|En yüksek ikili üs|
|**FLT_MIN**|1.175494351 e-38F|En düşük normalleştirilmiş pozitif değer|
|**FLT_MIN_10_EXP**|(-37)|En küçük ondalık üs|
|**FLT_MIN_EXP**|(-125)|En küçük ikili üs|
|**FLT_RADIX**|2|Üs taban x|
|**FLT_TRUE_MIN**|1.401298464 e-45F|Minimum pozitif alt normal değer|
|**LDBL_DIG**|15|duyarlık ondalık basamak sayısı|
|**LDBL_EPSILON**|2.2204460492503131 e-bir|En küçük 1,0 + **LDBL_EPSILON** ! = 1,0|
|**LDBL_HAS_SUBNORM**|1|Tür alt normal (denormal) rakamları destekler|
|**LDBL_MANT_DIG**|53|mantisinin içindeki bit sayısı (Mantis)|
|**LDBL_MAX**|1.7976931348623158 e + 308|En büyük değer|
|**LDBL_MAX_10_EXP**|308|Maksimum ondalık üs|
|**LDBL_MAX_EXP**|1024|En yüksek ikili üs|
|**LDBL_MIN**|2.2250738585072014 e-308|En düşük normalleştirilmiş pozitif değer|
|**LDBL_MIN_10_EXP**|(-307)|En küçük ondalık üs|
|**LDBL_MIN_EXP**|(-1021)|En küçük ikili üs|
|**_LDBL_RADIX**|2|Üs taban x|
|**LDBL_TRUE_MIN**|4.9406564584124654 e-324|Minimum pozitif alt normal değer|
|**DECIMAL_DIG**|**DBL_DECIMAL_DIG** ile aynı|Yuvarlama duyarlığının varsayılan (Double) ondalık basamakları|

## <a name="see-also"></a>Ayrıca bkz.

[Global sabitler](../c-runtime-library/global-constants.md)
