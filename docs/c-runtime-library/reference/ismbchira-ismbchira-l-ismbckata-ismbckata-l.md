---
title: _ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fe2b9c824fcc45eb2d0fda82cd350d3a9435b94
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ismbchira-ismbchiral-ismbckata-ismbckatal"></a>_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l

**Kod sayfası 932 özel işlevleri**

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Sınanacak karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test durumu ya da 0 uymazsa mevcut değilse bu yordamlar her sıfır olmayan bir değer döndürür. Varsa *c* < = 255 ve karşılık gelen **_ismbb** yordamına (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Buna karşılık gelen dönüş değeri sonucudur **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri belirli bir birden çok baytlı karakter verilen bir koşul için sınar.

Bu işlevleri sürümlerini **_l** soneki, yerel ayara bağımlı davranışlarını geçerli yerel yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

|Yordam|(Yalnızca kod sayfası 932) koşulu test|
|-------------|-------------------------------------------|
|**_ismbchira**|Çift baytlık Hiragana: 0x829F < =*c*< 0x82F1 =.|
|**_ismbchira_l**|Çift baytlık Hiragana: 0x829F < =*c*< 0x82F1 =.|
|**_ismbckata**|Çift baytlık katakana: 0x8340 < =*c*< 0x8396 =.|
|**_ismbckata_l**|Çift baytlık katakana: 0x8340 < =*c*< 0x8396 =.|

**Son kod sayfası 932 özel**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbchira**|\<Mbstring.h >|
|**_ismbchira_l**|\<Mbstring.h >|
|**_ismbckata**|\<Mbstring.h >|
|**_ismbckata_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
