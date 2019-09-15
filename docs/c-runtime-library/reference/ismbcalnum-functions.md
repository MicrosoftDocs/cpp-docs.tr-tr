---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
ms.date: 11/04/2016
api_name:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
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
ms.openlocfilehash: f13d1faab2923827707d8749a8783a10cf989b88
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953962"
---
# <a name="_ismbcalnum-_ismbcalnum_l-_ismbcalpha-_ismbcalpha_l-_ismbcdigit-_ismbcdigit_l"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l

Çok baytlı bir karakterin alfasayısal, Alfa veya sayı karakteri olup olmadığını denetler.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*c*<br/>
Sınanacak karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu yordamların her biri, karakter test koşulunu karşılıyorsa veya 0 değilse sıfır dışında bir değer döndürür. *C*< = 255 ise ve karşılık gelen bir **_ismbb** yordamı varsa (örneğin, **_ismbcalnum** , **_ismbbalnum**öğesine karşılık gelir), sonuç karşılık gelen **_ismbb** yordamının dönüş değeridir.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri belirli bir koşul için belirli bir çok baytlı karakteri sınar.

**_L** sonekine sahip bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayar yerine geçirilen yerel ayarı kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|Sayısal|Yalnızca *c* , ASCII İngilizce harfinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: **_İsmbcdigit** ve **_ismbcalpha**örneklerine bakın.|
|**_ismbcalpha**, **_ismbcalpha_l**|Alfabetik|Yalnızca *c* , ASCII İngilizce harfinin tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x41 < =*c*< = 0x5A veya 0x61 < =*c*< = 0x7A; ya da Katakana harfi: 0xA6 < =*c*< = 0xDF.|
|**_ismbcdigit**, **_ismbcdigit**|Gurmukhi|Yalnızca *c* bir ASCII basamağının tek baytlık bir gösterimiyse sıfır olmayan bir değer döndürür: 0x30 < =*c*< = 0x39.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|\<mbstring. h >|
|**_ismbcalpha**, **_ismbcalpha_l**|\<mbstring. h >|
|**_ismbcdigit**, **_ismbcdigit_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
