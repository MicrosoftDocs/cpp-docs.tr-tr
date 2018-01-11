---
title: ToAscii, __toascii | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __toascii
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
dev_langs: C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25e11878772b4c8f7afb07f7297ca80a2a5a0130
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

*c*  
Dönüştürülecek karakter.

## <a name="return-value"></a>Dönüş Değeri

`__toascii`değerini dönüştürür *c* 7 bitlik ASCII aralığı ve sonucu döndürür. Hiçbir değer döndürmeyen bir hata belirtmek üzere ayrılmış.

## <a name="remarks"></a>Açıklamalar

`__toascii` Yordamı dönüştürür belirli bir karakter bir ASCII karakter için düşük düzey 7 bit kesilmesiyle tarafından. Diğer bir dönüştürme uygulanır.

`__toascii` Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece, yordamı makro olarak tanımlanır. Geriye dönük uyumluluk için `toascii` makro olarak tanımlanan yalnızca [&#95; &#95; STDC &#95; &#95; ](../../preprocessor/predefined-macros.md) tanımlı değil ya da 0; tanımlanan aksi tanımlı değil.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`toascii`, `__toascii`|C: \<ctype.h ><br /><br /> C++: \<cctype > veya \<ctype.h >|

`toascii` Makrosu POSIX uzantısı olan ve `__toascii` POSIX uzantısı Microsoft'a özgü uygulamasıdır. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.

## <a name="see-also"></a>Ayrıca Bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
[is, isw rutinleri](../../c-runtime-library/is-isw-routines.md)   
[to İşlevleri](../../c-runtime-library/to-functions.md)