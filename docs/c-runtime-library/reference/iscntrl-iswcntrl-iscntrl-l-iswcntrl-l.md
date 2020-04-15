---
title: iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l
ms.date: 4/2/2020
api_name:
- iscntrl
- _iswcntrl_l
- _iscntrl_l
- iswcntrl
- _o_iscntrl
- _o_iswcntrl
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
- _istcntrl_l
- _iswcntrl_l
- iswcntrl
- _iscntrl_l
- iscntrl
- _istcntrl
helpviewer_keywords:
- iscntrl function
- _iscntrl_l function
- _iswcntrl_l function
- _istcntrl function
- istcntrl function
- iswcntrl function
- _istcntrl_l function
ms.assetid: 616eebf9-aed4-49ba-ba2c-8677c8fe6fb5
ms.openlocfilehash: d3760102ca07c883ac711c66994ff470cb46cf84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343880"
---
# <a name="iscntrl-iswcntrl-_iscntrl_l-_iswcntrl_l"></a>iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l

Bir tamsedenin bir denetim karakterini temsil edip etmediğini belirler.

## <a name="syntax"></a>Sözdizimi

```C
int iscntrl(
   int c
);
int iswcntrl(
   wint_t c
);
int _iscntrl_l(
   int c,
   _locale_t locale
);
int _iswcntrl_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Test etmek için sonda

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

*C* bir denetim karakterinin belirli bir temsili ise, bu yordamların her biri sıfırsız döndürür. *c* bir kontrol karakteri ise **iscntrl** sıfır olmayan bir değer döndürür (0x00 - 0x1F veya 0x7F). **c** bir denetim geniş karakter ise *c* sıfır olmayan bir değer döndürür. *C* test koşulunu karşılamazsa bu yordamların her biri 0 döndürür.

**_l** sonek olan bu işlevlerin sürümleri, geçerli yerel yerine geçen yerel parametreyi kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*c* EOF değilse veya 0 ile 0xFF aralığında, dahil ise **iscntrl** ve **_iscntrl_l** davranışı tanımsızdır. Hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir iddiayı yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istcntrl**|**iscntrl**|**iscntrl**|**iswcntrl**|
|**_istcntrl_l**|**_iscntrl_l**|**_iscntrl_l**|**_iswcntrl_l**|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**iscntrl**|\<ctype.h>|
|**iswcntrl**|\<ctype.h> \<veya wchar.h>|
|**_iscntrl_l**|\<ctype.h>|
|**_iswcntrl_l**|\<ctype.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
