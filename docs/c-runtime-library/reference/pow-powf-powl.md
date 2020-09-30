---
title: pow, powf, powl
description: Pow, powf ve ptıl için API başvurusu; bir güce göre hesaplamayı hesaplayabilirsiniz.
ms.date: 08/31/2020
api_name:
- powl
- pow
- powf
- _o_pow
- _o_powf
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
- powl
- pow
- _powl
- powf
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
ms.openlocfilehash: 8fb6679e2b509274b4ea60c410a81b54df866416
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505573"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

*X* ' i *y*'nin kuvvetine göre hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
define pow(X, Y) // Requires C11 or higher

double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>Parametreler

*sayı*\
Temel.

*Iz*\
S.

## <a name="return-value"></a>Dönüş Değeri

*X*<sup>*y*</sup>değerini döndürür. Taşma veya yetersiz kalması üzerine bir hata iletisi yazdırılmaz.

|X ve y değerleri|POW dönüş değeri|
|-----------------------|-------------------------|
|*x* ! = 0,0 ve *y* = = 0,0|1|
|*x* = = 0,0 ve *y* = = 0,0|1|
|*x* = = 0,0 ve *y* < 0|INF|

## <a name="remarks"></a>Açıklamalar

**POW** , 2<sup>64</sup> 'den büyük tamsayı kayan nokta değerlerini tanımıyor (örneğin, 1.0 E100).

**POW** , Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahiptir. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_set_SSE2_enable](set-sse2-enable.md).

C++ aşırı yüklemeye izin verdiğinden, **POW**'ın çeşitli aşırı yüklerini çağırabilirsiniz. C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız takdirde **POW** her zaman iki **`double`** değer alır ve bir **`double`** değer döndürür.

\<tgmath.h> `pow()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

`pow(int, int)`Aşırı yükleme artık kullanılamıyor. Bu aşırı yüklemeyi kullanırsanız, derleyici [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)yayabilir. Bu sorundan kaçınmak için, ilk parametreyi **`double`** , veya olarak atayın **`float`** **`long double`** .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-|-|-|
|**POW**, **powf**, **ptıl**|\<math.h>|\<math.h> veya \<cmath>|
|**POW** makrosu | \<tgmath.h> ||

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_pow.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.0, y = 3.0, z;

   z = pow( x, y );
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );
}
```

```Output
2.0 to the power of 3.0 is 8.0
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md) <br/>
[sqrt, sqrtf, sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
