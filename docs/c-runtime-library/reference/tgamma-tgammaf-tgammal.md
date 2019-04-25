---
title: tgamma, tgammaf, tgammal
ms.date: 04/05/2018
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
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
ms.openlocfilehash: c9ff92658163fc20ce21496aba34b22b3661748b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155621"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Belirtilen değerin gama fonksiyonu belirler.

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

Bir aralık hatası oluşabilir büyüklüğünü *x* çok büyük ya da veri türü için çok küçük. Bir etki alanı hatası veya aralığı hata ortaya çıkabilir *x* < = 0.

|Sorun|döndürülecek|
|-----------|------------|
|x = ±0|±INFINITY|
|x = negatif tamsayı|NaN|
|x = - INFİNİTY|NaN|
|x = + INFİNİTY|+ INFİNİTY|
|x = NaN|NaN|
|etki alanı hatası|NaN|
|kutup hata|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|Taşma aralık hatası|±HUGE_VAL, ±HUGE_VALF veya ±HUGE_VALL|
|Yetersiz aralık hatası|doğru değeri, sonra yuvarlama.|

Hatalar rapor, belirtilen [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **tgamma** alan ve getiren **float** ve **uzun** **çift** türleri. C programında **tgamma** her zaman alan ve döndüren bir **çift**.

X doğal sayı ise, bu işlev (x-1) çarpımını döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**tgamma**, **tgammaf**,  **tgammal**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
