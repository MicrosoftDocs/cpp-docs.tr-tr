---
title: exp, expf, expl
description: Exp, expf ve expl için API başvurusu; üstel olarak hesaplama.
ms.date: 1/15/2021
api_name:
- expf
- expl
- exp
- _o_exp
- _o_expf
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
- _expl
- expf
- expl
- exp
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.openlocfilehash: ac51744fe332fbf378139df11e7d07afe44029ca
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564010"
---
# <a name="exp-expf-expl"></a>`exp`, `expf`, `expl`

Üstel 'yi hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double exp(
   double x
);
float exp(
   float x
);  // C++ only
long double exp(
   long double x
);  // C++ only
float expf(
   float x
);
long double expl(
   long double x
);
#define exp(z) // Requires C11 or higher
```

### <a name="parameters"></a>Parametreler

*`x`*\
Doğal logaritma tabanında *e tarafından üsl* olacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**`exp`** İşlevleri, başarılı olursa kayan nokta parametresinin üstel değerini döndürür *`x`* . Diğer bir deyişle, sonuç *e*'dir, <sup>*`x`*</sup> burada *e* doğal logaritmanın temelini alır. Taşma üzerinde, işlev `INF` (sonsuzluk) ve yetersiz kalması ' i döndürür, **`exp`** 0 döndürür.

|Giriş|SEH özel durumu|`Matherr` duruma|
|-----------|-------------------|-----------------------|
|± Quiet NaN, belirsiz|Yok|`_DOMAIN`|
|± Infinity|`INVALID`|`_DOMAIN`|
|x ≥ 7.097827 e + 002|`INEXACT+OVERFLOW`|`OVERFLOW`|
|X ≤-7.083964 e + 002|`INEXACT+UNDERFLOW`|`UNDERFLOW`|

**`exp`** İşlev, Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahiptir. [`_set_SSE2_enable`](set-sse2-enable.md)SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz..

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **`exp`** bir **`float`** veya bağımsız değişkeni alan aşırı yüklerini çağırabilirsiniz **`long double`** . C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **`exp`** her zaman bir alır ve döndürür **`double`** .

`<tgmath.h>` `exp()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|--------------|---------------------|---|
|**`exp`**, **`expf`**, **`expl`**|`<math.h>`|`<cmath>` veya `<math.h>`|
|**`exp`** makroya| `<tgmath.h>` ||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_exp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.302585093, y;

   y = exp( x );
   printf( "exp( %f ) = %f\n", x, y );
}
```

```Output
exp( 2.302585 ) = 10.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[girişindeki`og, logf, log10, log10f`](log-logf-log10-log10f.md)\
[`_CIexp`](../../c-runtime-library/ciexp.md)