---
title: tgamma, tgammaf, tgammal | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- tgamma
- tgammaf
- tgammal
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs:
- C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7861b297646f4a704134e0d874fad8c924a7ebc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Belirtilen değer Gama işlevinin belirler.

## <a name="syntax"></a>Sözdizimi

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);

```

### <a name="parameters"></a>Parametreler

*x*<br/>
Gama, bulunacak değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, gama döndürür *x*.

Bir aralık hata oluşabilir büyüklüğünü *x* çok büyük ya da veri türü için çok küçük. Bir etki alanı hatası ya da aralık hatası ortaya çıkabilir *x* < = 0.

|Sorun|Döndür|
|-----------|------------|
|x = ±0|±INFINITY|
|x = negatif tamsayı|NaN|
|x = - SONSUZ|NaN|
|x = + SONSUZ|+ SONSUZ|
|x NaN =|NaN|
|etki alanı hatası|NaN|
|kutbu'na hata|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|taşma aralık hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|Underflow aralık hatası|doğru değeri, yuvarlama sonra.|

Hataları raporlanır belirtilmiş [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **tgamma** alın ve dönüş **float** ve **uzun** **çift** türleri. Bir C programı **tgamma** her zaman alan ve döndüren bir **çift**.

X doğal sayı ise, bu işlevi (x-1) çarpımını döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**, **tgammal**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
