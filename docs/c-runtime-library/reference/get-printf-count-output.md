---
title: _get_printf_count_output
ms.date: 11/04/2016
api_name:
- _get_printf_count_output
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
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
ms.openlocfilehash: 15b37ac759821ad56cc5c03c9b98719d8f0cc19a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955717"
---
# <a name="_get_printf_count_output"></a>_get_printf_count_output

[Printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Family işlevlerinin **% n** biçimini destekleyip desteklemediğini gösterir.

## <a name="syntax"></a>Sözdizimi

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Dönüş Değeri

**% N** destekleniyorsa sıfır olmayan bir değer, **% n** desteklenmiyorsa 0.

## <a name="remarks"></a>Açıklamalar

**% N** desteklenmiyorsa (varsayılan), **printf** işlevlerinin herhangi birinin biçim dizesinde **% n** ile [karşılaşmak parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. **% N** desteği etkinse (bkz. [_set_printf_count_output](set-printf-count-output.md)), **% n** , [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)bölümünde açıklandığı gibi davranır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Set_printf_count_output](set-printf-count-output.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[_set_printf_count_output](set-printf-count-output.md)<br/>
