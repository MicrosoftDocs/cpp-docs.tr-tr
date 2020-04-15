---
title: isspace, iswspace, _isspace_l, _iswspace_l
ms.date: 4/2/2020
api_name:
- iswspace
- _isspace_l
- _iswspace_l
- isspace
- _o_isspace
- _o_iswspace
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswspace
- _istspace
- isspace
helpviewer_keywords:
- iswspace function
- isspace function
- _iswspace_l function
- _isspace_l function
- iswspace_l function
- isspace_l function
- _istspace function
- istspace function
ms.assetid: b851e0c0-36bb-4dac-a1a3-533540939035
ms.openlocfilehash: 43d66a191427e886941fd3dcac5dc6b71146b68a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342758"
---
# <a name="isspace-iswspace-_isspace_l-_iswspace_l"></a>isspace, iswspace, _isspace_l, _iswspace_l

Bir tamsedinbir boşluk karakterini temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isspace(
   int c
);
int iswspace(
   wint_t c
);
int _isspace_l(
   int c,
   _locale_t locale
);
int _iswspace_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Test etmek için sonda.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her *biri, bir* boşluk karakterinin belirli bir temsili ise sıfırsız döndürür. **isspace,** *c* bir beyaz boşluk karakteriyse (0x09 - 0x0D veya 0x20) sıfır olmayan bir değer döndürür. **Isspace** işlevi için test koşulunun sonucu, LC_CTYPE **kategori** ayarlarına bağlıdır; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md) bakın. **_l** soneki olmayan bu işlevlerin sürümleri, yerel çözüme bağlı herhangi bir davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel alanı kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**iswspace,** *standart* bir beyaz boşluk karakterine karşılık gelen geniş bir karakterse sıfır olmayan bir değer döndürür.

*c* EOF değilse veya 0 ile 0xFF aralığında, dahil ise **isspace** ve **_isspace_l** davranışı tanımsızdır. Hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir iddiayı yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istspace**|**isspace**|[_ismbcspace](ismbcgraph-functions.md)|**iswspace**|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**isspace**|\<ctype.h>|
|**iswspace**|\<ctype.h> \<veya wchar.h>|
|**_isspace_l**|\<ctype.h>|
|**_iswspace_l**|\<ctype.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
