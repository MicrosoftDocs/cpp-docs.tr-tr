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
ms.openlocfilehash: b67abb58f4d62c7c54b61d1b1699f09c1bd51b40
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957307"
---
# <a name="_set_output_format"></a>_set_output_format

Biçimlendirilen g/ç işlevleri tarafından kullanılan çıkış biçimlerini özelleştirir.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015 ' den başlayarak CRT ' de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
unsigned int _set_output_format(
   unsigned int format
);
```

#### <a name="parameters"></a>Parametreler

*format*<br/>
'ndaki Kullanılacak biçimi temsil eden bir değer.

## <a name="return-value"></a>Dönüş değeri

Önceki çıkış biçimi.

## <a name="remarks"></a>Açıklamalar

`_set_output_format`, [printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)gibi biçimlendirilen g/ç işlevlerinin çıkışını yapılandırmak için kullanılır. Mevcut olduğunda, bu işlev tarafından değiştirilebilen tek biçimlendirme kuralı, kayan nokta numaralarının çıkışında üsler halinde görüntülenen basamak sayısıdır.

Varsayılan olarak,,, ve görsel `printf_s` C++ standart C kitaplığındaki ilgili işlevler gibi işlevlere `wprintf_s`göre kayan nokta sayılarının çıktısı, değeri temsil etmek için üç basamak gerekli olmasa bile üs için üç basamak yazdırır . Sıfır değeri üç basamağa kadar doldurma için kullanılır. `_set_output_format`üs boyutunun üçüncü bir basamak gerektirmediği takdirde üs içinde yalnızca iki basamak yazdırılması için bu davranışı değiştirmenize izin verir.

İki basamaklı üsleri etkinleştirmek için, örnekte gösterildiği gibi bu işlevi parametresiyle `_TWO_DIGIT_EXPONENT`çağırın. İki basamaklı üsleri devre dışı bırakmak için, bu işlevi 0 bağımsız değişkeniyle çağırın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_set_output_format`|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. karşılama 'da [Uyumluluk](../c-runtime-library/compatibility.md) .

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
