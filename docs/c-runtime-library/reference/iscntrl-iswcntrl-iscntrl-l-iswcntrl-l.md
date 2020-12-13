---
description: 'Daha fazla bilgi edinin: SCC, ıswcnu, _iscntrl_l _iswcntrl_l'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b4dcba09b139d1ad1c80e495477a6b7b2283e3f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332705"
---
# <a name="iscntrl-iswcntrl-_iscntrl_l-_iswcntrl_l"></a>iscntrl, iswcntrl, _iscntrl_l, _iswcntrl_l

Bir tamsayının bir denetim karakterini temsil edip etmediğini belirler.

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

*,*<br/>
Sınanacak tamsayı

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Eğer *c* bir denetim karakterinin belirli bir gösterimiyse, bu yordamların her biri sıfır dışında bir değer döndürür. Eğer *c* bir denetim karakteriyse (0x00-0x1F veya 0x7F), **SCC** sıfır olmayan bir değer döndürür. *c* bir denetim genelindeki karakter ise, **ıswcnm** sıfır dışında bir değer döndürür. Bu yordamların her biri, *c* , test koşulunu karşılamadığı takdirde 0 döndürür.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli yerel ayar yerine geçirilen yerel ayar parametresini kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*C* 'nin EOF veya 0 ile 0xFF (dahil) aralığında olması halinde, **SCC** ve **_iscntrl_l** davranışı tanımsızdır. Bir hata ayıklama CRT kitaplığı kullanıldığında ve *c* bu değerlerden biri değilse, işlevler bir onaylama işlemi yükseltir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istcntrl**|**iscntrl**|**iscntrl**|**iswcnw**|
|**_istcntrl_l**|**_iscntrl_l**|**_iscntrl_l**|**_iswcntrl_l**|

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**iscntrl**|\<ctype.h>|
|**iswcnw**|\<ctype.h> veya \<wchar.h>|
|**_iscntrl_l**|\<ctype.h>|
|**_iswcntrl_l**|\<ctype.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[, isw yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
