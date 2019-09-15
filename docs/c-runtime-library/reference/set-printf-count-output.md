---
title: _set_printf_count_output
ms.date: 11/04/2016
api_name:
- _set_printf_count_output
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_printf_count_output
- _set_printf_count_output
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
ms.openlocfilehash: 0d53b4e4c56a69582a4eb517fa1a5c9e10cd7d2f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948416"
---
# <a name="_set_printf_count_output"></a>_set_printf_count_output

[Printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Family işlevlerinde **% n** biçiminin desteğini etkinleştirin veya devre dışı bırakın.

## <a name="syntax"></a>Sözdizimi

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>Parametreler

*etkinleştirebilir*<br/>
**% N desteğini etkinleştirmek için** sıfır olmayan bir değer, **% n** desteğini devre dışı bırakmak için 0.

## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bu işlev çağrılmadan önce **% n** desteğinin durumu: **% n** desteği etkinleştirildiyse sıfır olmayan, devre dışıysa 0.

## <a name="remarks"></a>Açıklamalar

Güvenlik nedeniyle, **% n** biçim belirticisi için destek, **printf** ve tüm türevleri için varsayılan olarak devre dışıdır. Bir **printf** biçim belirtiminde **% n** ile karşılaşılırsa, varsayılan davranış [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırmada olur. Sıfır olmayan bir bağımsız değişkenle **_set_printf_count_output** çağırmak, **printf**-Family işlevlerinin [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)bölümünde açıklandığı gibi **% n** öğesini yorumlamasını sağlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_printf_count_output**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_set_printf_count_output.c
#include <stdio.h>

int main()
{
   int e;
   int i;
   e = _set_printf_count_output( 1 );
   printf( "%%n support was %sabled.\n",
        e ? "en" : "dis" );
   printf( "%%n support is now %sabled.\n",
        _get_printf_count_output() ? "en" : "dis" );
   printf( "12345%n6789\n", &i ); // %n format should set i to 5
   printf( "i = %d\n", i );
}
```

```Output
%n support was disabled.
%n support is now enabled.
123456789
i = 5
```

## <a name="see-also"></a>Ayrıca bkz.

[_get_printf_count_output](get-printf-count-output.md)<br/>
