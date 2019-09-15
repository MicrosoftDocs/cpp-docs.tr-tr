---
title: exp2, exp2f, exp2l
ms.date: 04/05/2018
api_name:
- exp2
- exp2f
- exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
ms.openlocfilehash: 89e0448501cbd423278607bb22959c6cd1ed9464
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941566"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

2 ' nin belirtilen değere göre oluşturulan hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Üs değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x*'nin taban 2 üssün, yani 2<sup>x</sup>döndürür. Aksi takdirde, aşağıdaki değerlerden birini döndürür:

|Sorun|döndürülmesini|
|-----------|------------|
|*x* = ±0|1\.|
|*x* =-sonsuzluk|+0|
|*x* = + sonsuzluk|\+ SONSUZLUK|
|*x* = Nan|NaN|
|Taşma aralığı hatası|\+ HUGE_VAL, + HUGE_VALF veya + HUGE_VALL|
|Yetersiz yer aralığı hatası|Yuvarlama sonrasında doğru sonuç|

Hatalar [_matherr](matherr.md)içinde belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long Double** türlerini alıp döndüren **exp2** aşırı yüklerini çağırabilirsiniz. C programında, **exp2** her zaman bir **Double**alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++üst bilgi|
|-------------|--------------|------------------|
|**Exp**, **expf**, **expl**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
