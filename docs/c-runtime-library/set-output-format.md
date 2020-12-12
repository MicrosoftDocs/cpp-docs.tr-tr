---
description: 'Hakkında daha fazla bilgi edinin: _set_output_format'
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
ms.openlocfilehash: d0e45f4f7ce2a6837bce1e583ec3afd5a70f108a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277186"
---
# <a name="_set_output_format"></a>_set_output_format

Biçimlendirilen g/ç işlevleri tarafından kullanılan çıkış biçimlerini özelleştirir.

> [!IMPORTANT]
> Bu işlev artık kullanılmıyor. Visual Studio 2015 ' den başlayarak CRT ' de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
unsigned int _set_output_format(
   unsigned int format
);
```

#### <a name="parameters"></a>Parametreler

*formatını*<br/>
'ndaki Kullanılacak biçimi temsil eden bir değer.

## <a name="return-value"></a>Döndürülen değer

Önceki çıkış biçimi.

## <a name="remarks"></a>Açıklamalar

`_set_output_format` , [printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)gibi biçimlendirilen g/ç işlevlerinin çıkışını yapılandırmak için kullanılır. Mevcut olduğunda, bu işlev tarafından değiştirilebilen tek biçimlendirme kuralı, kayan nokta numaralarının çıkışında üsler halinde görüntülenen basamak sayısıdır.

Varsayılan olarak, kayan nokta sayılarının `printf_s` ,, `wprintf_s` ve Visual C++ Standart C kitaplığındaki ilgili işlevler gibi işlevlere göre çıktısı, üs değerini temsil etmek için üç basamak gerekli olmasa bile üs için üç basamak yazdırır. Sıfır değeri üç basamağa kadar doldurma için kullanılır. `_set_output_format` üs boyutunun üçüncü bir basamak gerektirmediği takdirde üs içinde yalnızca iki basamak yazdırılması için bu davranışı değiştirmenize izin verir.

İki basamaklı üsleri etkinleştirmek için, örnekte gösterildiği gibi bu işlevi parametresiyle çağırın `_TWO_DIGIT_EXPONENT` . İki basamaklı üsleri devre dışı bırakmak için, bu işlevi 0 bağımsız değişkeniyle çağırın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_set_output_format`|\<stdio.h>|

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
