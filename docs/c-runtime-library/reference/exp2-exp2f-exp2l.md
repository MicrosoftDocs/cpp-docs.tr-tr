---
title: exp2, exp2f, exp2l
description: Exp2 (), exp2f () ve exp2l () için API ref, belirtilen değere oluşturulan 2.
ms.date: 9/1/2020
api_name:
- exp2
- exp2f
- exp2l
- _o_exp2
- _o_exp2f
- _o_exp2l
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
ms.openlocfilehash: 518525a38ef575583fde3b7732561f2fa553dd18
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556625"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

2 ' nin belirtilen değere göre oluşturulan hesaplar.

## <a name="syntax"></a>Söz dizimi

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
#define exp2(X) // Requires C11 or higher
```

### <a name="parameters"></a>Parametreler

*sayı*\
Üs değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, *x*'nin taban 2 üssün, yani 2<sup>x</sup>döndürür. Aksi takdirde, aşağıdaki değerlerden birini döndürür:

|Sorun|Döndürülmesini|
|-----------|------------|
|*x* = ± 0|1|
|*x* =-sonsuzluk|+0|
|*x* = + sonsuzluk|+ SONSUZLUK|
|*x* = Nan|NaN|
|Taşma aralığı hatası|+ HUGE_VAL, + HUGE_VALF veya + HUGE_VALL|
|Yetersiz yer aralığı hatası|Yuvarlama sonrasında doğru sonuç|

Hatalar [_matherr](matherr.md)belirtilen şekilde bildirilir.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, ve türlerini alıp döndüren **exp2** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız **müddetçe,** **`double`** makroyu <tgmath. h> kullanmadığınız durumlar dışında her zaman alır ve döndürür.

\<tgmath.h> `exp2()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgisi|
|-------------|--------------|------------------|
|**exp2**, **expf2**, **expl2**|\<math.h>|\<cmath>|
|**exp2** makrosu | \<tgmath.h> ||

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
