---
title: isascii, __isascii, iswascii | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- iswascii
- __isascii
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
dev_langs:
- C++
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bffc46bae24689558999d188f96e5b9f8d21c54e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402279"
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

Belirli bir karakterin bir ASCII karakter olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Test etmek için bir tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamları döndürür sıfır olmayan IF her **c** bir ASCII karakter belirli bir gösterimidir. **__isascii** sıfır olmayan bir değer döndürür **c** ASCII karakter (aralığında 0x00 - 0x7F). **iswascii** sıfır olmayan bir değer döndürür **c** bir ASCII karakter joker karakter gösterimidir. Bu yordamlar her 0 döndürür **c** test durumu uygun değil.

## <a name="remarks"></a>Açıklamalar

Her ikisi de **__isascii** ve **iswascii** önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece makroları olarak uygulanır.

Geriye dönük uyumluluk için **isascii** makrosu yalnızca IF uygulanan [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) tanımlı değil ya da 0; tanımlanan aksi tanımlı değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h ><br /><br /> C++: \<cctype > veya \<ctype.h >|
|**iswascii**|C: \<wctype.h >, \<ctype.h >, veya \<wchar.h ><br /><br /> C++: \<cwctype >, \<cctype >, \<wctype.h >, \<ctype.h >, veya \<wchar.h >|

**İsascii**, **__isascii** ve **iswascii** Microsoft belirli işlevlerdir. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
