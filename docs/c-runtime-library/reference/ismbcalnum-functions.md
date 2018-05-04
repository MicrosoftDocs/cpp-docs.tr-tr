---
title: _ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a90fe131ff216bd9f758f3312d366e0ec29d79ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ismbcalnum-ismbcalnuml-ismbcalpha-ismbcalphal-ismbcdigit-ismbcdigitl"></a>_ismbcalnum, _ismbcalnum_l, _ismbcalpha, _ismbcalpha_l, _ismbcdigit, _ismbcdigit_l

Birden çok baytlı karakter alfasayısal bir olup, alfa veya basamaklı karakter denetler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test durumu ya da 0 uymazsa mevcut değilse bu yordamlar her sıfır olmayan bir değer döndürür. Varsa *c*< = 255 ve karşılık gelen **_ismbb** yordamına (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Buna karşılık gelen dönüş değeri sonucudur **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu yordamlar her belirli bir birden çok baytlı karakter verilen bir koşul için sınar.

Bu işlevleri sürümlerini **_l** soneki, yerel ayara bağımlı davranışlarını geçerli yerel yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

|Yordam|Test durumu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|Alfasayısal|Sıfır olmayan ve yalnız döndürür *c* ASCII İngilizce harf tek baytlı gösterimidir: örnekler için bkz: **_ismbcdigit** ve **_ismbcalpha**.|
|**_ismbcalpha**, **_ismbcalpha_l**|Alfabetik|Sıfır olmayan ve yalnız döndürür *c* ASCII İngilizce harf tek baytlı gösterimidir: 0x41 < =*c*< 0x5A veya 0x61 = < =*c*< 0x7A; = veya katakana harf: 0xA6 < =*c*< 0xDF =.|
|**_ismbcdigit**, **_ismbcdigit**|Basamak|Sıfır olmayan ve yalnız döndürür *c* ASCII basamaklı tek baytlı gösterimidir: 0x30 < =*c*< 0x39 =.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbcalnum**, **_ismbcalnum_l**|\<Mbstring.h >|
|**_ismbcalpha**, **_ismbcalpha_l**|\<Mbstring.h >|
|**_ismbcdigit**, **_ismbcdigit_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
