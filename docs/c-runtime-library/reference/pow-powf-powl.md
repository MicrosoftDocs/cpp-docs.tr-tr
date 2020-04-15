---
title: pow, powf, powl
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b181959ac05814a673ab11f33e4cfc5a39e3869e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333113"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

*Y'nin*gücüne yükseltilen *x'i* hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
```

```cpp
double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Temel.

*Y*<br/>
Üs.

## <a name="return-value"></a>Dönüş Değeri

*x*<sup>*y*</sup>değerini verir. Taşma veya akış altında hiçbir hata iletisi yazdırılır.

|x ve y değerleri|Pow'un iade değeri|
|-----------------------|-------------------------|
|*x* != 0.0 ve *y* == 0.0|1|
|*x* == 0.0 ve *y* == 0.0|1|
|*x* == 0.0 ve *y* < 0|ınf|

## <a name="remarks"></a>Açıklamalar

**pow,** 2<sup>64'ten</sup> büyük integral kayan nokta değerlerini tanımaz (örneğin, 1.0E100).

**pow'** un Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulaması vardır. SSE2 uygulamasını kullanma yla ilgili bilgi ve kısıtlamalar için [_set_SSE2_enable](set-sse2-enable.md)bkz.

C++ aşırı yüklemeye izin verdiğinden, çeşitli aşırı **pow**yüklerinden herhangi birini arayabilirsiniz. C **programında, pow** her zaman iki **çift** değer alır ve **bir çift** değer döndürür.

Aşırı `pow(int, int)` yükleme artık kullanılamıyor. Bu aşırı yükü kullanırsanız, derleyici [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)yatabilir. Bu sorunu önlemek için, ilk parametreyi **çift**, **float**veya **uzun** **çift**döküm .

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgi (C)|Gerekli üstbilgi (C++)|
|-|-|-|
|**pow**, **powf**, **yavru**|\<math.h>|\<math.h> \<veya cmath>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md) <br/>
[sqrt, sqrtf, sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
