---
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
ms.openlocfilehash: 20afa988bc4fdf3bc3a6ff073a48a1cc00ff84c5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944363"
---
# <a name="_get_output_format"></a>_get_output_format

Çıkış biçimi bayrağının geçerli değerini alır.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015 ' den başlayarak CRT ' de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
unsigned int _get_output_format();
```

## <a name="return-value"></a>Dönüş Değeri

Çıkış biçimi bayrağının geçerli değeri.

## <a name="remarks"></a>Açıklamalar

Çıktı biçimi bayrağı, biçimlendirilen g/ç 'nin özelliklerini denetler. Yukarıdaki bayrakta iki olası değer vardır: 0 ve `_TWO_DIGIT_EXPONENT`. `_TWO_DIGIT_EXPONENT` Ayarlanırsa, üs boyutunun bir üçüncü basamak gerektirmediği takdirde, kayan nokta sayıları üs içinde yalnızca iki basamakla yazdırılır. Bayrak sıfırsa, kayan nokta çıkışı, değeri üç basamağa göstermek için gerekliyse, sıfırdan üç basamak görüntüler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_get_output_format`|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. karşılama 'da [Uyumluluk](../c-runtime-library/compatibility.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_set_output_format](../c-runtime-library/set-output-format.md)
