---
description: 'Hakkında daha fazla bilgi edinin: _get_output_format'
title: _get_output_format
ms.date: 11/04/2016
api_name:
- _get_output_format
api_location:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_output_format
- _get_output_format
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
ms.openlocfilehash: cdbe5038745273882685a79e148e143c3d65d7e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181741"
---
# <a name="_get_output_format"></a>_get_output_format

Çıkış biçimi bayrağının geçerli değerini alır.

> [!IMPORTANT]
> Bu işlev artık kullanılmıyor. Visual Studio 2015 ' den başlayarak CRT ' de kullanılamaz.

## <a name="syntax"></a>Syntax

```
unsigned int _get_output_format();
```

## <a name="return-value"></a>Dönüş Değeri

Çıkış biçimi bayrağının geçerli değeri.

## <a name="remarks"></a>Açıklamalar

Çıktı biçimi bayrağı, biçimlendirilen g/ç 'nin özelliklerini denetler. Şu anda bayrağın iki olası değeri vardır: 0 ve `_TWO_DIGIT_EXPONENT` . `_TWO_DIGIT_EXPONENT`Ayarlanırsa, üs boyutunun bir üçüncü basamak gerektirmediği takdirde, kayan nokta sayıları üs içinde yalnızca iki basamakla yazdırılır. Bayrak sıfırsa, kayan nokta çıkışı, değeri üç basamağa göstermek için gerekliyse, sıfırdan üç basamak görüntüler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_get_output_format`|\<stdio.h>|

Daha fazla uyumluluk bilgisi için bkz. karşılama 'da [Uyumluluk](../c-runtime-library/compatibility.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Biçim belirtimi sözdizimi: printf ve wprintf Işlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_set_output_format](../c-runtime-library/set-output-format.md)
