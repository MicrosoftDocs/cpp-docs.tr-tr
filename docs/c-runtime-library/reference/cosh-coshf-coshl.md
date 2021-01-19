---
title: cosh, coshf, coshl
description: Cosh, coshf ve coshl; için API başvurusu bir kayan nokta değerinin hiperbolik kosinüsünü hesaplar.
ms.date: 1/15/2021
api_name:
- cosh
- coshf
- coshl
- _o_cosh
- _o_coshf
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: c010dcdc30b16f94f55fca99d67b58e5c19370c7
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564101"
---
# <a name="cosh-coshf-coshl"></a>`cosh`, `coshf`, `coshl`

Hiperbolik kosinüsü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
#define cosh(X) // Requires C11 or higher

float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*`x`*\
Radyan cinsinden açı.

## <a name="return-value"></a>Dönüş Değeri

Öğesinin hiperbolik kosinüsü *`x`* .

Varsayılan olarak, bir, veya çağrısında sonuç çok büyükse, **`cosh`** **`coshf`** işlevi öğesini **`coshl`** döndürür ve öğesini **`HUGE_VAL`** **`errno`** olarak ayarlar **`ERANGE`** .

|Giriş|SEH özel durumu|`Matherr` duruma|
|-----------|-------------------|-----------------------|
|± **`QNAN`**, **`IND`**|yok|**`_DOMAIN`**|
|*`x`* ≥ 7.104760 e + 002|**`INEXACT`**+**`OVERFLOW`**|**`OVERFLOW`**|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **`cosh`** alan veya değer alma ve döndürme yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **`cosh`** her zaman bir alır ve döndürür **`double`** .

`<tgmath.h>` `cosh()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------|-|
|**`coshf`**, **`cosl`**, **`coshl`**|`<math.h>`|`<cmath>` veya `<math.h>`|
|**`coshf()`** makroya | `<tgmath.h>` ||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

, [ `sinh` `sinhf` ,, `sinhl` ](sinh-sinhf-sinhl.md)İçindeki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`acosh, acoshf, acoshl`](acosh-acoshf-acoshl.md)\
[`asinh, asinhf, asinhl`](asinh-asinhf-asinhl.md)\
[`atanh, atanhf, atanhl`](atanh-atanhf-atanhl.md)\
[`_matherr`](matherr.md)\
[`sinh, sinhf, sinhl`](sinh-sinhf-sinhl.md)\
[`tanh, tanhf, tanhl`](tanh-tanhf-tanhl.md)