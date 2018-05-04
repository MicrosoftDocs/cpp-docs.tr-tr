---
title: ToAscii, __toascii | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __toascii
apilocation:
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
apitype: DLLExport
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
dev_langs:
- C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cead516a7e298e56d13d8f1a09a054057796ca64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="toascii-toascii"></a>ToAscii, __toascii

Karakter 7 bitlik ASCII tarafından kesme dönüştürür.

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

**__toascii** değerini dönüştürür *c* 7 bitlik ASCII aralığı ve sonucu döndürür. Hiçbir değer döndürmeyen bir hata belirtmek üzere ayrılmış.

## <a name="remarks"></a>Açıklamalar

**__Toascii** yordamı dönüştürür belirli bir karakter bir ASCII karakter için düşük düzey 7 bit kesilmesiyle tarafından. Diğer bir dönüştürme uygulanır.

**__Toascii** önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece, yordamı makro olarak tanımlanır. Geriye dönük uyumluluk için **toascii** makro olarak tanımlanan yalnızca [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) tanımlı değil ya da 0; tanımlanan aksi tanımlı değil.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ToAscii**, **__toascii**|C: \<ctype.h ><br /><br /> C++: \<cctype > veya \<ctype.h >|

**Toascii** makrosu POSIX uzantısı olan ve **__toascii** POSIX uzantısı Microsoft'a özgü uygulamasıdır. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
