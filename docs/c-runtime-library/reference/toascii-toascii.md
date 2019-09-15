---
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
ms.openlocfilehash: 09df829511b38b87cb41e32a59bee9f38a9b8f32
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957468"
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

*c*<br/>
Dönüştürülecek karakter.

## <a name="return-value"></a>Dönüş Değeri

**__toascıı** , *c* değerini 7 bit ASCII aralığına dönüştürür ve sonucu döndürür. Bir hatayı göstermek için ayrılmış dönüş değeri yok.

## <a name="remarks"></a>Açıklamalar

**__Toascıı** yordamı, alt sıra 7 bitine kırarak VERILEN karakteri ASCII karakterine dönüştürür. Başka dönüşüm uygulanmaz.

Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece **__toascıı** yordamı bir makro olarak tanımlanır. Geriye dönük uyumluluk için **toascıı** , yalnızca [ &#95; &#95;stdc&#95; ](../../preprocessor/predefined-macros.md) tanımlanmadığında veya 0 olarak tanımlandığında bir makro olarak tanımlanır; Aksi takdirde, tanımsız olur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**toascıı**, **__toascıı**|C: \<CType. h ><br /><br /> C++: \<cctype > veya \<CType. h >|

**Toascıı** MAKROSU bir POSIX uzantısıdır ve **__TOASCıı** , POSIX uzantısının Microsoft 'a özgü uygulamasıdır. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
