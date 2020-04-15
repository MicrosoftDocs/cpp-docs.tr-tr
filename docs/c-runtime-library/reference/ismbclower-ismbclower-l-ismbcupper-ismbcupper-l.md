---
title: _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
ms.date: 4/2/2020
api_name:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
- _o__ismbclower
- _o__ismbclower_l
- _o__ismbcupper
- _o__ismbcupper_l
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
- _ismbcupper
- _ismbclower
helpviewer_keywords:
- _ismbcupper function
- ismbclower function
- _ismbclower_l function
- ismbcupper_l function
- _ismbclower function
- ismbcupper function
- ismbclower_l function
- _ismbcupper_l function
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
ms.openlocfilehash: 9a0991d974c33cff22044364f7a4351f160215a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342925"
---
# <a name="_ismbclower-_ismbclower_l-_ismbcupper-_ismbcupper_l"></a>_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l

Çok baytlı bir karakterin küçük veya büyük harfli olup olmadığını denetler.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbclower(
   unsigned int c
);
int _ismbclower_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcupper(
   unsigned int c
);
int _ismbcupper_l(
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

Bu işlevlerin her biri belirli bir koşul için belirli bir çok bayt karakteri sınar.

**Bu işlevlerin _l** sonekli sürümleri, yerel liğe bağımlı davranışları için geçerli yerel alan yerine geçirilen yerel liği kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

|Yordam|Test koşulu|Kod sayfası 932 örnek|
|-------------|--------------------|---------------------------|
|**_ismbclower**|Küçük harf alfabetik|*Eğer c* bir ASCII küçük İngilizce harfin tek bayt gösterimi ise sıfırsız döndürür: 0x61<=*c*<=0x7A.|
|**_ismbclower_l**|Küçük harf alfabetik|*Eğer c* bir ASCII küçük İngilizce harfin tek bayt gösterimi ise sıfırsız döndürür: 0x61<=*c*<=0x7A.|
|**_ismbcupper**|Büyük harf alfabetik|*Eğer c* bir ASCII büyük Harf İngilizce harfinin tek bayt gösterimi ise sıfırsız döndürür: 0x41<=*c*<=0x5A.|
|**_ismbcupper_l**|Büyük harf alfabetik|*Eğer c* bir ASCII büyük Harf İngilizce harfinin tek bayt gösterimi ise sıfırsız döndürür: 0x41<=*c*<=0x5A.|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbclower**|\<mbstring.h>|
|**_ismbclower_l**|\<mbstring.h>|
|**_ismbcupper**|\<mbstring.h>|
|**_ismbcupper_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Rutinleri](../../c-runtime-library/ismbc-routines.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[olduğunu, isw Rutinleri](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
