---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
ms.date: 4/2/2020
api_name:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
- _o__ismbcalnum
- _o__ismbcalnum_l
- _o__ismbcalpha
- _o__ismbcalpha_l
- _o__ismbcdigit
- _o__ismbcdigit_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbcdigit
- ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha
- ismbcalnum
- ismbcdigit
- ismbcalpha
- _ismbcalnum_l
- _ismbcalnum
- ismbcdigit_l
helpviewer_keywords:
- ismbcalpha function
- _ismbcalnum function
- ismbcdigit_l function
- _ismbcalnum_l function
- _ismbcdigit function
- ismbcalnum function
- _ismbcalpha_l function
- ismbcdigit function
- _ismbcalpha function
- _ismbcdigit_l function
- ismbcalnum_l function
- ismbcalpha_l function
ms.assetid: 12d57925-aebe-46e0-80b0-82b84c4c31ec
ms.openlocfilehash: 828c8b68855197f0c17202739f98a45e0abb929c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343301"
---
# <a name="_ismbcalnum-_ismbcalnum_l-_ismbcalpha-_ismbcalpha_l-_ismbcdigit-_ismbcdigit_l"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l

Çok baytlı bir karakterin alfasayısal, alfa veya basamak karakteri olup olmadığını denetler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbcalnum
(
   unsigned int c
);
int _ismbcalnum_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcalpha
(
   unsigned int c
);
int _ismbcalpha_l
(
   unsigned int c,
   _locale_t locale
);
int _ismbcdigit
(
   unsigned int c
);
int _ismbcdigit_l
(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Karakter test edilecek.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Karakter test koşulunu karşılarsa, bu yordamların her biri sıfır olmayan bir değer döndürür. *C*<= 255 ve karşılık gelen **bir _ismbb** yordamı varsa (örneğin, **_ismbcalnum** **_ismbbalnum**karşılık geliyorsa), sonuç ilgili **_ismbb** yordamının geri dönüş değeridir.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri belirli bir durum için belirli bir çok bayt karakteri sınar.

**Bu işlevlerin _l** sonekli sürümleri, yerel liğe bağımlı davranışları için geçerli yerel alan yerine geçirilen yerel liği kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

|Yordam|Test koşulu|Kod sayfası 932 örnek|
|-------------|--------------------|---------------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|Alfasayısal|*Eğer c* bir ASCII İngilizce mektubunun tek bayt gösterimiyse sıfırsız döndürür: **_ismbcdigit** ve **_ismbcalpha**için örneklere bakın.|
|**_ismbcalpha**, **_ismbcalpha_l**|Alfabetik|*Eğer c* bir ASCII İngilizce harfinin tek bayt gösterimi ise sıfırsız döndürür: 0x41<=*c*<=0x61<=*c*<=0x7A; veya katakana harfi: 0xA6<=*c*<=0xDF.|
|**_ismbcdigit**, **_ismbcdigit**|Basamak|*Eğer c* bir ASCII basamağı tek bayt gösterimi ise sıfırsız döndürür: 0x30<=*c*<=0x39.|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|\<mbstring.h>|
|**_ismbcalpha**, **_ismbcalpha_l**|\<mbstring.h>|
|**_ismbcdigit**, **_ismbcdigit_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Rutinleri](../../c-runtime-library/ismbc-routines.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
