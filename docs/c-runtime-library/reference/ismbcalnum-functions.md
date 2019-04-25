---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l
ms.date: 11/04/2016
apiname:
- _ismbcalpha
- _ismbcalnum
- _ismbcdigit
- _ismbcalnum_l
- _ismbcdigit_l
- _ismbcalpha_l
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 1a2f928d826b70b788220130f69c53cc351b4910
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157317"
---
# <a name="ismbcalnum-ismbcalnuml-ismbcalpha-ismbcalphal-ismbcdigit-ismbcdigitl"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l

Çok baytlı karakteri bir alfasayısal olup, alfa veya basamak karakterli denetler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Test edilecek karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test koşulunu veya 0 karşılıyorsa kullanmıyorsa bu yordamların her biri sıfır dışında bir değeri döndürür. Varsa *c*< = 255 ve karşılık gelen **_ismbb** yordamı (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Sonuç, karşılık gelen dönüş değeri olduğu **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu yordamların her biri, belirli bir koşul için belirli bir çok baytlı karakteri test eder.

Sahip bu işlevlerin sürümleri **_l** sonekine yerel ayara bağlı davranışları için geçerli yerel ayarı yerine iletilen yerel ayarı kullanmaları dışında. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|Alfasayısal|Yalnız ve yalnızca döndürür *c* tek baytlık ASCII İngilizce harfin ise: Örnekler için bkz: **_ismbcdigit** ve **_ismbcalpha**.|
|**_ismbcalpha**, **_ismbcalpha_l**|Alfabetik|Yalnız ve yalnızca döndürür *c* tek baytlık ASCII İngilizce harfin ise: 0x41 < =*c*< 0x5A veya 0x61 = < =*c*< 0x7A; = veya katakana harf: 0xA6<=*c*<=0xDF.|
|**_ismbcdigit**, **_ismbcdigit**|basamak|Yalnız ve yalnızca döndürür *c* tek baytlık ASCII basamak ise: 0x30 < =*c*< 0x39 =.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|\<Mbstring.h >|
|**_ismbcalpha**, **_ismbcalpha_l**|\<Mbstring.h >|
|**_ismbcdigit**, **_ismbcdigit_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
