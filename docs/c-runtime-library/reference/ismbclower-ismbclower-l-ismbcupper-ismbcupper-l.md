---
title: _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
ms.date: 11/04/2016
apiname:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
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
ms.openlocfilehash: 29a1e97f4583808931e5228a6905aed7c0a62702
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157296"
---
# <a name="ismbclower-ismbclowerl-ismbcupper-ismbcupperl"></a>_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l

Çok baytlı bir karakterin büyük harf veya küçük harf olup olmadığını denetler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Test edilecek karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test koşulunu veya 0 karşılıyorsa kullanmıyorsa bu yordamların her biri sıfır dışında bir değeri döndürür. Varsa *c*< = 255 ve karşılık gelen **_ismbb** yordamı (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Sonuç, karşılık gelen dönüş değeri olduğu **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için belirli bir çok baytlı karakteri test eder.

Sahip bu işlevlerin sürümleri **_l** sonekine yerel ayara bağlı davranışları için geçerli yerel ayarı yerine iletilen yerel ayarı kullanmaları dışında. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

|Yordam|Test koşulu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbclower**|Küçük harf alfabetik|Yalnız ve yalnızca döndürür *c* tek baytlık ASCII küçük harfli İngilizce harfin ise: 0x61 < =*c*< 0x7A =.|
|**_ismbclower_l**|Küçük harf alfabetik|Yalnız ve yalnızca döndürür *c* tek baytlık ASCII küçük harfli İngilizce harfin ise: 0x61 < =*c*< 0x7A =.|
|**_ismbcupper**|Büyük alfabetik|Yalnız ve yalnızca döndürür *c* tek baytlık ASCII büyük harfli İngilizce harfin ise: 0x41 < =*c*< 0x5A =.|
|**_ismbcupper_l**|Büyük alfabetik|Yalnız ve yalnızca döndürür *c* tek baytlık ASCII büyük harfli İngilizce harfin ise: 0x41 < =*c*< 0x5A =.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbclower**|\<Mbstring.h >|
|**_ismbclower_l**|\<Mbstring.h >|
|**_ismbcupper**|\<Mbstring.h >|
|**_ismbcupper_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
