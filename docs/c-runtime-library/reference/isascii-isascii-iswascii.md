---
title: isascii, __isascii, iswascii
ms.date: 4/2/2020
api_name:
- iswascii
- __isascii
- _o_iswascii
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: aeb9c27fee4d179cc16caa50c6f0aae521402beb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343920"
---
# <a name="isascii-__isascii-iswascii"></a>isascii, __isascii, iswascii

Belirli bir karakterin ASCII karakteri olup olmadığını belirler.

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

*C*<br/>
Test etmek için sonda.

## <a name="return-value"></a>Dönüş Değeri

**C** bir ASCII karakterinin belirli bir temsili yse, bu yordamların her biri sıfırsız döndürür. **__isascii,** **ASCII** karakteri ise (0x00 - 0x7F aralığında) sıfır olmayan bir değer verir. **c** bir ASCII karakterinin geniş karakterli bir temsili ise **iswascii** sıfır olmayan bir değer döndürür. **C** test koşulunu karşılamazsa bu yordamların her biri 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Önişlemci makro_CTYPE_DISABLE_MACROS tanımlanmadığı sürece **hem __isascii** hem de **iswascii** makro olarak uygulanır.

Geriye dönük uyumluluk için **isascii,** yalnızca [&#95;&#95;STDC&#95;&#95;](../../preprocessor/predefined-macros.md) tanımlanmamışsa veya 0 olarak tanımlanmışsa makro olarak uygulanır; aksi takdirde tanımsız.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype \<> veya ctype.h>|
|**iswascii**|C: \<wctype.h \<>, ctype.h \<> veya wchar.h><br /><br /> C++: \<cwctype \<>, cctype>, \<wctype.h>, \< \<ctype.h> veya wchar.h>|

**isascii**, **__isascii** ve **iswascii** işlevleri Microsoft'a özgüdür. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
