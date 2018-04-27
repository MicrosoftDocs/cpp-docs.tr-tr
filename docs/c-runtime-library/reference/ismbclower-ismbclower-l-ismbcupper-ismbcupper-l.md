---
title: _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2350e8f3034d18dda32f3007d714d532828ee338
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="ismbclower-ismbclowerl-ismbcupper-ismbcupperl"></a>_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l

Birden çok baytlı karakter küçük harfler veya büyük olup olmadığını denetler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Karakter test durumu ya da 0 uymazsa mevcut değilse bu yordamlar her sıfır olmayan bir değer döndürür. Varsa *c*< = 255 ve karşılık gelen **_ismbb** yordamına (örneğin, **_ismbcalnum** karşılık gelen **_ismbbalnum**), Buna karşılık gelen dönüş değeri sonucudur **_ismbb** yordamı.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri belirli bir birden çok baytlı karakter verilen bir koşul için sınar.

Bu işlevleri sürümlerini **_l** soneki, yerel ayara bağımlı davranışlarını geçerli yerel yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

|Yordam|Test durumu|Kod sayfası 932 örneği|
|-------------|--------------------|---------------------------|
|**_ismbclower**|Küçük alfabetik|Sıfır olmayan ve yalnız döndürür *c* ASCII küçük harfli İngilizce harf tek baytlı gösterimidir: 0x61 < =*c*< 0x7A =.|
|**_ismbclower_l**|Küçük alfabetik|Sıfır olmayan ve yalnız döndürür *c* ASCII küçük harfli İngilizce harf tek baytlı gösterimidir: 0x61 < =*c*< 0x7A =.|
|**_ismbcupper**|Alfabetik büyük harf|Sıfır olmayan ve yalnız döndürür *c* ASCII büyük İngilizce harf tek baytlı gösterimidir: 0x41 < =*c*< 0x5A =.|
|**_ismbcupper_l**|Alfabetik büyük harf|Sıfır olmayan ve yalnız döndürür *c* ASCII büyük İngilizce harf tek baytlı gösterimidir: 0x41 < =*c*< 0x5A =.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ismbclower**|\<Mbstring.h >|
|**_ismbclower_l**|\<Mbstring.h >|
|**_ismbcupper**|\<Mbstring.h >|
|**_ismbcupper_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
