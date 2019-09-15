---
title: isascii, __isascii, iswascii
ms.date: 11/04/2016
api_name:
- iswascii
- __isascii
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
ms.openlocfilehash: ee20711628d5c2135b4ee1c37b87cb77f3610695
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954568"
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

*c*<br/>
Sınanacak tamsayı.

## <a name="return-value"></a>Dönüş Değeri

**C** , ASCII karakterinin belirli bir gösterimiyse, bu yordamların her biri sıfır dışında bir değer döndürür. **c** bir ASCII karakteriyse (0x00-0x7F aralığında) **__isascıı** sıfır dışında bir değer döndürür. **c** , ASCII karakterinin geniş karakterli bir gösterimiyse **ıswascıı** sıfır dışında bir değer döndürür. Bu yordamların her biri, **c** , test koşulunu karşılamadığı takdirde 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece hem **__isascıı** hem de **ıwascıı** makrolar olarak uygulanır.

Geriye dönük uyumluluk için, **ısascıı** , yalnızca [ &#95; &#95;stdc&#95; ](../../preprocessor/predefined-macros.md) tanımlanmadığında veya 0 olarak tanımlanmışsa bir makro olarak uygulanır; Aksi takdirde, tanımsız olur.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascıı**|**__isascıı**|**__isascıı**|**iswascıı**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isascıı**, **__isascıı**|C: \<CType. h ><br /><br /> C++: \<cctype > veya \<CType. h >|
|**iswascıı**|C: \<wctype. h >, \<CType. h > veya \<wchar. h ><br /><br /> C++: \<cwctype >, \<cctype >, \<wctype. h >, \<CType. h > veya \<wchar. h >|

**Isascıı**, **__isascıı** ve **ıwascıı** işlevleri Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
