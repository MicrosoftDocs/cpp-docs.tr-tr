---
title: _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
ms.date: 11/04/2016
api_name:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
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
ms.openlocfilehash: 6a64a0d9be83733fa5482eee84ce6576dd32c221
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953792"
---
# <a name="_ismbclower-_ismbclower_l-_ismbcupper-_ismbcupper_l"></a>_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l

Çok baytlı bir karakterin küçük harf veya büyük harf olup olmadığını denetler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*c*<br/>
Sınanacak karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, karakter test koşulunu karşılıyorsa veya 0 değilse sıfır dışında bir değer döndürür. *C*< = 255 ise ve karşılık gelen bir **_ismbb** yordamı varsa (örneğin, **_ismbcalnum** , **_ismbbalnum**öğesine karşılık gelir), sonuç karşılık gelen **_ismbb** yordamının dönüş değeridir.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için verilen bir çok baytlı karakteri sınar.

**_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbclower**|Küçük harfli alfabetik|Yalnızca *c* , ASCII küçük harfli İngilizce harfinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x61 < =*c*< = 0x7A.|
|**_ismbclower_l**|Küçük harfli alfabetik|Yalnızca *c* , ASCII küçük harfli İngilizce harfinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x61 < =*c*< = 0x7A.|
|**_ismbcupper**|Büyük harfli alfabetik|Yalnızca *c* , ASCII büyük harfli İngilizce harfinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x41 < =*c*< = 0x5A.|
|**_ismbcüste_l**|Büyük harfli alfabetik|Yalnızca *c* , ASCII büyük harfli İngilizce harfinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x41 < =*c*< = 0x5A.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbclower**|\<mbstring. h >|
|**_ismbclower_l**|\<mbstring. h >|
|**_ismbcupper**|\<mbstring. h >|
|**_ismbcüste_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
