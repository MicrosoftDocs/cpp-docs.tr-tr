---
description: 'Daha fazla bilgi edinin: isascıı, __isascii, ıwascıı'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0d0a7964ba5b9a3133f100ea94fd4bac95407627
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332734"
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

*,*<br/>
Sınanacak tamsayı.

## <a name="return-value"></a>Dönüş Değeri

**C** , ASCII karakterinin belirli bir gösterimiyse, bu yordamların her biri sıfır dışında bir değer döndürür. **c** bir ASCII karakteriyse (0x00-0x7F aralığında) **__isascii** sıfır dışında bir değer döndürür. **c** , ASCII karakterinin geniş karakterli bir gösterimiyse **ıswascıı** sıfır dışında bir değer döndürür. Bu yordamların her biri, **c** , test koşulunu karşılamadığı takdirde 0 döndürür.

## <a name="remarks"></a>Açıklamalar

Önişlemci makrosu _CTYPE_DISABLE_MACROS tanımlanmadığı sürece hem **__isascii** hem de **ıswascıı** makrolar olarak uygulanır.

Geriye dönük uyumluluk için, **ısascıı** yalnızca [&#95;&#95;stdc&#95;&#95;](../../preprocessor/predefined-macros.md) tanımlanmamışsa veya 0 olarak tanımlanmışsa bir makro olarak uygulanır; Aksi takdirde, tanımsız olur.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascıı**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isascıı**, **__isascii**|, \<ctype.h><br /><br /> C++: \<cctype> veya \<ctype.h>|
|**iswascıı**|C: \<wctype.h> , \<ctype.h> veya \<wchar.h><br /><br /> C++: \<cwctype> , \<cctype> , \<wctype.h> , \<ctype.h> , veya \<wchar.h>|

**Isascıı**, **__isascii** ve **ıwascıı** işlevleri, Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
