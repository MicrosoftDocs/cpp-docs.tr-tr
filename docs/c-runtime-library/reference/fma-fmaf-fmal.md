---
title: fma, fmaf, fmal
ms.date: 04/05/2018
api_name:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: 4ddc4061e5a24ee3b5176aedc569d134d85e0002
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957099"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

İki değeri birlikte çarpar, üçüncü bir değer ekler ve sonra, ara yuvarlama nedeniyle herhangi bir duyarlık kaybı olmadan sonucu yuvarlar.

## <a name="syntax"></a>Sözdizimi

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Çarpılacak ilk değer.

*Iz*<br/>
Çarpılacak ikinci değer.

*z*<br/>
Eklenecek değer.

## <a name="return-value"></a>Dönüş Değeri

Döndürür `(x * y) + z`. Dönüş değeri bundan sonra geçerli yuvarlama biçimi kullanılarak yuvarlanır.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|döndürülmesini|
|-----------|------------|
|*x* = Infinity, *y* = 0 veya<br /><br /> *x* = 0, *y* = sonsuzluk|NaN|
|*x* veya *y* = tam ± Infinity, *z* = Infinity ters işaretle|NaN|
|*x* veya *y* = Nan|NaN|
|Not (*x* = 0, *y*= sonsuz) ve *z* = Nan<br /><br /> Not (*x*= sonsuz, *y*= 0) ve *z* = Nan|NaN|
|Taşma aralığı hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|
|Yetersiz yer aralığı hatası|yuvarlama sonrasında değer doğru değeri.|

Hatalar [_matherr](matherr.md)içinde belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **FMA** aşırı yüklerini çağırabilirsiniz. C programında **FMA** her zaman bir **Double**alır ve döndürür.

Bu işlev değeri sonsuz duyarlığa alınmış gibi hesaplar ve sonra nihai sonucu yuvarlar.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**FMA**, **fmaf**, **Fmal**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
