---
title: tgamma, tgammaf, tgammal
ms.date: 04/05/2018
api_name:
- tgamma
- tgammaf
- tgammal
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 02926fa49bbabeb9cf532f53cfa6e30a77805e70
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946207"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Belirtilen değerin gama işlevini belirler.

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
Gamasını bulmak için değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *x*'in gamasını döndürür.

*X* büyüklüğü çok büyükse veya veri türü için çok küçük olduğunda Aralık hatası oluşabilir. *X* < = 0 olduğunda bir etki alanı hatası veya Aralık hatası oluşabilir.

|Sorun|döndürülmesini|
|-----------|------------|
|x = ±0|± INFINITY|
|x = negatif tamsayı|NaN|
|x =-sonsuzluk|NaN|
|x = + sonsuzluk|\+ SONSUZLUK|
|x = NaN|NaN|
|etki alanı hatası|NaN|
|direk hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|
|Taşma aralığı hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|
|Yetersiz yer aralığı hatası|yuvarlama sonrasında doğru değer.|

Hatalar [_matherr](matherr.md)içinde belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **tgama** aşırı yüklerini çağırabilirsiniz. C programında **tgama** her zaman bir **Double**alır ve döndürür.

X doğal bir sayı ise, bu işlev (x-1) faktöriyelini döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**tgama**, **tgamaf**, **tgammal**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
