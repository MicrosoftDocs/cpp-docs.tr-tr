---
title: _get_output_format
ms.date: 11/04/2016
apiname:
- _get_output_format
apilocation:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- get_output_format
- _get_output_format
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
ms.openlocfilehash: 60e209f6f8b723bfae1a4b434750b6237dc6479d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62343519"
---
# <a name="getoutputformat"></a>_get_output_format

Çıkış biçimi bayrağı geçerli değerini alır.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
unsigned int _get_output_format();
```

## <a name="return-value"></a>Dönüş Değeri

Çıkış biçimi bayrağı geçerli değeri.

## <a name="remarks"></a>Açıklamalar

Çıkış biçimi bayrağı biçimlendirilmiş g/ç özelliklerini denetler. Şu anda bayrağı iki olası değer vardır: 0 ve `_TWO_DIGIT_EXPONENT`. Varsa `_TWO_DIGIT_EXPONENT` ayarlandığında, kayan nokta numaralarını yazdırılıp yalnızca iki basamak ile üçüncü basamak üs boyutu tarafından gerekmedikçe. Kayan nokta bayrağı sıfırsa çıktısını görüntüler üç basamak sıfır üç basamak değerine doldurulacak gerekirse kullanarak üs.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_get_output_format`|\<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md) giriş.

## <a name="see-also"></a>Ayrıca bkz.

[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_set_output_format](../c-runtime-library/set-output-format.md)
