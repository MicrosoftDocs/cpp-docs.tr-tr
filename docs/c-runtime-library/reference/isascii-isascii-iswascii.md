---
title: isascii, __isascii, iswascii
ms.date: 11/04/2016
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
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
ms.openlocfilehash: d150e7bb335dc77ed86f445128eebf97b8be5ac3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433665"
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

Belirli bir karakter, ASCII karakter olup olmadığını belirler.

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
Test edilecek tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Yordamların her biri bu döndürür sıfır olmayan **c** bir ASCII karakter belirli bir gösterimidir. **__isascii** sıfır olmayan bir değer döndürür **c** bir ASCII karakter (aralığında 0x00 - 0x7F). **iswascii** sıfır olmayan bir değer döndürür **c** bir ASCII karakterinin geniş karakter gösterimidir. Bu yordamların her biri 0 döndürür **c** test koşulu karşılamayan.

## <a name="remarks"></a>Açıklamalar

Her ikisi de **__isascii** ve **iswascii** önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece makroları olarak uygulanır.

Geriye dönük uyumluluk için **isascii** yalnızca bir makro durumlarda uygulanan [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) tanımlı değil veya; 0 olarak tanımlandığında aksi tanımsızdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h ><br /><br /> C++: \<cctype > veya \<ctype.h >|
|**iswascii**|C: \<wctype.h >, \<ctype.h >, veya \<wchar.h ><br /><br /> C++: \<cwctype >, \<cctype >, \<wctype.h >, \<ctype.h >, veya \<wchar.h >|

**İsascii**, **__isascii** ve **iswascii** Microsoft'a özgü işlevlerdir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
