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
ms.openlocfilehash: 682ab9796942e52ed036193887158ea22b738189
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349335"
---
# <a name="_get_output_format"></a>_get_output_format

Çıktı biçimi bayrağının geçerli değerini alır.

> [!IMPORTANT]
> Bu işlev geçersizdir. Visual Studio 2015'ten itibaren CRT'de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
unsigned int _get_output_format();
```

## <a name="return-value"></a>Dönüş Değeri

Çıktı biçimi bayrağının geçerli değeri.

## <a name="remarks"></a>Açıklamalar

Çıkış biçimi bayrağı biçimlendirilmiş G/Ç özelliklerini denetler. Şu anda bayrak iki olası `_TWO_DIGIT_EXPONENT`değere sahiptir: 0 ve . `_TWO_DIGIT_EXPONENT` Ayarlanırsa, kayan nokta numaraları, üs boyutuna göre üçüncü bir basamak gerekmedikçe, üsiçinde yalnızca iki basamakla yazdırılır. Bayrak sıfırsa, kayan nokta çıkışı değeri üç basamak için gerekirse sıfırları kullanarak üç basamaklık üs görüntüler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_get_output_format`|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Giriş'te [Uyumluluk'a](../c-runtime-library/compatibility.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_set_output_format](../c-runtime-library/set-output-format.md)
