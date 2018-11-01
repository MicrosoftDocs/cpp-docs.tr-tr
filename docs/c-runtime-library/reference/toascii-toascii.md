---
title: ToAscii, __toascii
ms.date: 11/04/2016
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
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
ms.openlocfilehash: 22f76bdbdb21eb5b3cc9a226c111e321ee2fd0ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578977"
---
# <a name="toascii-toascii"></a>ToAscii, __toascii

Karakterleri 7 bit ASCII için kesilmesi nedeniyle dönüştürür.

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

**__toascii** değerini dönüştürür *c* için 7 bit ASCII aralığı ve sonucu döndürür. Dönüş değeri bir hatayı göstermek için ayrılmış.

## <a name="remarks"></a>Açıklamalar

**__Toascii** yordamı belirli karakterine dönüştürür bir ASCII karakter için düşük düzey 7 bit tarafından kesiliyor. Diğer bir dönüştürme uygulanır.

**__Toascii** önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece yordamı makro olarak tanımlanır. Geriye dönük uyumluluk için **toascii** makro olarak tanımlanan yalnızca [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) tanımlı değil veya; 0 olarak tanımlandığında aksi tanımsızdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ToAscii**, **__toascii**|C: \<ctype.h ><br /><br /> C++: \<cctype > veya \<ctype.h >|

**Toascii** makrodur bir POSIX uzantısı ve **__toascii** POSIX uzantıyı Microsoft'a özgü uygulamasıdır. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[to İşlevleri](../../c-runtime-library/to-functions.md)<br/>
