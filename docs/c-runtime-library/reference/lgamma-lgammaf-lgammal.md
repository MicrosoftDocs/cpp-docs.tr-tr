---
title: lgamma, lgammaf, lgammal
ms.date: 04/05/2018
api_name:
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 9baf8f0fefb50cea6a5301aac9ffd48ff3cd5bde
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953369"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Belirtilen değerin gama işlevinin mutlak logaritmasına ilişkin doğal logaritmayı belirler.

## <a name="syntax"></a>Sözdizimi

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Hesaplama değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x*'in gama işlevinin mutlak logaritmasını döndürün.

|Sorun|döndürülmesini|
|-----------|------------|
|*x* = Nan|NaN|
|*x* = ±0|\+ SONSUZLUK|
|*x*= negatif tamsayı|\+ SONSUZLUK|
|± INFINITY|\+ SONSUZLUK|
|direk hatası|\+ HUGE_VAL, + HUGE_VALF veya + HUGE_VALL|
|Taşma aralığı hatası|± HUGE_VAL, ± HUGE_VALF veya ± HUGE_VALL|

Hatalar [_matherr](matherr.md)içinde belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** türlerini alıp döndüren **lgama** aşırı yüklerini çağırabilirsiniz. C programında, **lgama** her zaman bir **Double**alır ve döndürür.

X bir Rational Number ise, bu işlev (x-1) faktöriyelini logaritmasını döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**lgamma**, **lgamaf**, **lgammal**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
