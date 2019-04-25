---
title: _ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l
ms.date: 11/04/2016
apiname:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
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
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
ms.openlocfilehash: d2a5d0336e5ed4ad8bbb19f8a259128ab33d004e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286739"
---
# <a name="ismbchira-ismbchiral-ismbckata-ismbckatal"></a>_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l

**Kod sayfası 932 özel işlevler**

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _ismbchira(
   unsigned int c
);
int _ismbchira_l(
   unsigned int c,
   _locale_t locale
);
int _ismbckata(
   unsigned int c
);
int _ismbckata_l(
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

Karakter test koşulunu veya 0 karşılıyorsa kullanmıyorsa bu yordamların her biri sıfır dışında bir değeri döndürür. Varsa *c* < = 255 ve karşılık gelen **_ismbb** yordamı (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Sonuç, karşılık gelen dönüş değeri olduğu **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, belirli bir koşul için belirli bir çok baytlı karakteri test eder.

Sahip bu işlevlerin sürümleri **_l** sonekine yerel ayara bağlı davranışları için geçerli yerel ayarı yerine iletilen yerel ayarı kullanmaları dışında. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

|Yordam|Test koşulu (yalnızca kod sayfası 932)|
|-------------|-------------------------------------------|
|**_ismbchira**|Double-byte Hiragana: 0x829F < =*c*< 0x82F1 =.|
|**_ismbchira_l**|Double-byte Hiragana: 0x829F < =*c*< 0x82F1 =.|
|**_ismbckata**|Double-byte katakana: 0x8340 < =*c*< 0x8396 =.|
|**_ismbckata_l**|Double-byte katakana: 0x8340 < =*c*< 0x8396 =.|

**End kod sayfası 932 özel**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbchira**|\<Mbstring.h >|
|**_ismbchira_l**|\<Mbstring.h >|
|**_ismbckata**|\<Mbstring.h >|
|**_ismbckata_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
