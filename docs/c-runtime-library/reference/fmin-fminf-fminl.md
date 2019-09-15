---
title: fmin, fminf, fminl
ms.date: 04/05/2018
api_name:
- fmin
- fminf
- fminl
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
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
ms.openlocfilehash: df01f2205291920b8c0519db622c93048278beb1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957089"
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl

Belirtilen iki değerden daha küçük bir değer belirler.

## <a name="syntax"></a>Sözdizimi

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Karşılaştırılacak ilk değer.

*Iz*<br/>
Karşılaştırılacak ikinci değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *x* veya *y değerinden*küçük bir değer döndürür.

|Giriş|Sonuç|
|-----------|------------|
|*x* Nan|*Iz*|
|*y* Nan|*x*|
|*x* ve *y* Nan 'tir|NaN|

İşlev [_matherr](matherr.md) 'nin çağrılmasına neden olmaz, kayan nokta özel durumlarına neden olur veya **errno**değerini değiştirebilir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **fmin** aşırı yüklerini çağırabilirsiniz. C programında **fmin** her zaman bir **Double**değeri alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**fmin**, **fminf**, **fminl**|C: \<Math. h ><br />C++: \<Math. h > veya \<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
