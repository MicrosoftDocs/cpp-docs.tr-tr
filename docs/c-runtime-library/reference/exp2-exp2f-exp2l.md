---
title: exp2, exp2f, exp2l
ms.date: 04/05/2018
apiname:
- exp2
- exp2f
- exp2l
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
ms.openlocfilehash: 70a3b7eb610556d4a26de7cf0aad55affcdbdc94
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562766"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

Belirtilen değere yükseltilmiş 2 hesaplar.

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

Başarılı olursa, 2 tabanında üssünü döndürür *x*, diğer bir deyişle, 2<sup>x</sup>. Aksi takdirde, aşağıdaki değerlerden birini döndürür:

|Sorun|döndürülecek|
|-----------|------------|
|*x* ±0 =|1.|
|*x* = - INFİNİTY|+0|
|*x* = + INFİNİTY|+ INFİNİTY|
|*x* NaN =|NaN|
|Taşma aralık hatası|+ HUGE_VAL + HUGE_VALF, veya + HUGE_VALL|
|Yetersiz aralık hatası|Sonra yuvarlama doğru sonucu|

Hatalar rapor, belirtilen [_matherr](matherr.md).

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **exp2** alan ve getiren **float** ve **uzun çift** türleri. C programında **exp2** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üst bilgisi|
|-------------|--------------|------------------|
|**exp**, **expf**, **expl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
