---
description: 'Hakkında daha fazla bilgi edinin: toascıı, __toascii'
title: toascii, __toascii
ms.date: 11/04/2016
api_name:
- __toascii
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
ms.openlocfilehash: 9f1718da5e7d701bb6cc6ea68c1e21b6fe4283f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318357"
---
# <a name="toascii-__toascii"></a>toascii, __toascii

Karakterleri, kesilerek 7 bit ASCII 'ye dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>Parametreler

*,*<br/>
Dönüştürülecek karakter.

## <a name="return-value"></a>Dönüş Değeri

**__toascii** , *c* değerini 7 bit ASCII aralığına dönüştürür ve sonucu döndürür. Bir hatayı göstermek için ayrılmış dönüş değeri yok.

## <a name="remarks"></a>Açıklamalar

**__Toascii** yordamı, alt sıra 7 bitleriyle kesilerek VERILEN karakteri ASCII karaktere dönüştürür. Başka dönüşüm uygulanmaz.

Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece **__toascii** yordamı makro olarak tanımlanır. Geriye dönük uyumluluk için **toascıı** , yalnızca [&#95;&#95;stdc&#95;&#95;](../../preprocessor/predefined-macros.md) tanımlanmadığında veya 0 olarak tanımlandığında bir makro olarak tanımlanır; Aksi takdirde, tanımsız olur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**toascıı**, **__toascii**|, \<ctype.h><br /><br /> C++: \<cctype> veya \<ctype.h>|

**Toascıı** MAKROSU bir POSIX uzantısıdır ve **__toascii** , POSIX uzantısının Microsoft 'a özgü uygulamasıdır. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to Işlevleri](../../c-runtime-library/to-functions.md)<br/>
