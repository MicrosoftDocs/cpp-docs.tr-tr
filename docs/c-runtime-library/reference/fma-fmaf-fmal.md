---
title: fma, fmaf, fmal
ms.date: 4/2/2020
api_name:
- fma
- fmaf
- fmal
- _o_fma
- _o_fmaf
- _o_fmal
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: be3578aa9c66f329e191749b4506091bff69b1eb
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914949"
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

*sayı*<br/>
Çarpılacak ilk değer.

*Iz*<br/>
Çarpılacak ikinci değer.

*kadar*<br/>
Eklenecek değer.

## <a name="return-value"></a>Dönüş Değeri

`(x * y) + z` döndürür. Dönüş değeri bundan sonra geçerli yuvarlama biçimi kullanılarak yuvarlanır.

Aksi takdirde, aşağıdaki değerlerden birini döndürebilir:

|Sorun|Döndürülmesini|
|-----------|------------|
|*x* = Infinity, *y* = 0 veya<br /><br /> *x* = 0, *y* = sonsuzluk|NaN|
|*x* veya *y* = tam ± Infinity, *z* = Infinity ters işaretle|NaN|
|*x* veya *y* = Nan|NaN|
|Not (*x* = 0, *y*= sonsuz) ve *z* = Nan<br /><br /> Not (*x*= sonsuz, *y*= 0) ve *z* = Nan|NaN|
|Taşma aralığı hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|
|Yetersiz yer aralığı hatası|yuvarlama sonrasında değer doğru değeri.|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **FMA** aşırı yüklerini çağırabilirsiniz. C programında **FMA** her zaman bir **Double**alır ve döndürür.

Bu işlev değeri sonsuz duyarlığa alınmış gibi hesaplar ve sonra nihai sonucu yuvarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**FMA**, **fmaf**, **Fmal**|\<Math. h>|\<cmath>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
