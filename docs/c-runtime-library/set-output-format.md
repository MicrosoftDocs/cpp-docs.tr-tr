---
title: _set_output_format
ms.date: 11/04/2016
api_name:
- _set_output_format
api_location:
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_output_format
- _set_output_format
helpviewer_keywords:
- _TWO_DIGIT_EXPONENT constant
- output formatting
- TWO_DIGIT_EXPONENT constant
- _set_output_format function
- set_output_format function
ms.assetid: 1cb48df8-44b4-4400-bd27-287831d6b3ff
ms.openlocfilehash: c855df4c29a53fd898b920f6446afe4e568ba5bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360914"
---
# <a name="_set_output_format"></a>_set_output_format

Biçimlendirilmiş G/Ç işlevleri tarafından kullanılan çıktı biçimlerini özelleştirer.

> [!IMPORTANT]
> Bu işlev geçersizdir. Visual Studio 2015'ten itibaren CRT'de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
unsigned int _set_output_format(
   unsigned int format
);
```

#### <a name="parameters"></a>Parametreler

*Biçim*<br/>
[içinde] Kullanılacak biçimi temsil eden bir değer.

## <a name="return-value"></a>Döndürülen değer

Önceki çıktı biçimi.

## <a name="remarks"></a>Açıklamalar

`_set_output_format`[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)gibi biçimlendirilmiş G/Ç işlevlerinin çıktısını yapılandırmak için kullanılır. Şu anda, bu işlev tarafından değiştirilebilen tek biçimlendirme kuralı, kayan nokta numaralarının çıktısında üsler halinde görüntülenen basamak sayısıdır.

Varsayılan olarak, Görsel C++ Standart C `printf_s`kitaplığındaki , ve `wprintf_s`ilgili işlevler gibi işlevler tarafından kayan nokta numaralarının çıktısı, üs değerini temsil etmek için üç basamak gerekli olmasa bile, üs için üç basamak yazdırır. Sıfırlar değeri üç basamaklı olarak deftere almak için kullanılır. `_set_output_format`üs boyutuna göre üçüncü bir basamak gerekmedikçe, yalnızca iki basamak üs içinde yazdırılır, böylece bu davranışı değiştirmenize olanak sağlar.

İki basamaklı üsleri etkinleştirmek için, örnekte gösterildiği gibi `_TWO_DIGIT_EXPONENT`bu işlevi parametreile çağırın. İki basamaklı üsleri devre dışı katmak için bu işlevi 0 bağımsız değişkeniyle çağırın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_set_output_format`|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Giriş'te [Uyumluluk'a](../c-runtime-library/compatibility.md) bakın.

## <a name="example"></a>Örnek

```C
// crt_set_output_format.c
#include <stdio.h>

void printvalues(double x, double y)
{
   printf_s("%11.4e %11.4e\n", x, y);
   printf_s("%11.4E %11.4E\n", x, y);
   printf_s("%11.4g %11.4g\n", x, y);
   printf_s("%11.4G %11.4G\n", x, y);
}

int main()
{
   double x = 1.211E-5;
   double y = 2.3056E-112;
   unsigned int old_exponent_format;

   // Use the default format
   printvalues(x, y);

   // Enable two-digit exponent format
   old_exponent_format = _set_output_format(_TWO_DIGIT_EXPONENT);

   printvalues(x, y);

   // Disable two-digit exponent format
   _set_output_format( old_exponent_format );

   printvalues(x, y);
}
```

```Output
1.2110e-005 2.3056e-112
1.2110E-005 2.3056E-112
1.211e-005  2.306e-112
1.211E-005  2.306E-112
1.2110e-05 2.3056e-112
1.2110E-05 2.3056E-112
  1.211e-05  2.306e-112
  1.211E-05  2.306E-112
1.2110e-005 2.3056e-112
1.2110E-005 2.3056E-112
1.211e-005  2.306e-112
1.211E-005  2.306E-112
```

## <a name="see-also"></a>Ayrıca bkz.

[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_get_output_format](../c-runtime-library/get-output-format.md)
