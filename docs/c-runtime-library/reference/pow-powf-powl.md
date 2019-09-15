---
title: pow, powf, powl
ms.date: 04/05/2018
api_name:
- powl
- pow
- powf
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
ms.openlocfilehash: 863d2b76ec131670b10eefc086fa3485bd0a983d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950294"
---
# <a name="pow-powf-powl"></a>pow, powf, powl

*X* ' i *y*'nin kuvvetine göre hesaplar.

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

*x*<br/>
Temel.

*Iz*<br/>
S.

## <a name="return-value"></a>Dönüş Değeri

*X*<sup>*y*</sup>değerini döndürür. Taşma veya yetersiz kalması üzerine bir hata iletisi yazdırılmaz.

|X ve y değerleri|POW dönüş değeri|
|-----------------------|-------------------------|
|*x* ! = 0,0 ve *y* = = 0,0|1\.|
|*x* = = 0,0 ve *y* = = 0,0|1\.|
|*x* = = 0,0 ve *y* < 0|'SI|

## <a name="remarks"></a>Açıklamalar

**POW** , 2<sup>64</sup> 'den büyük tamsayı kayan nokta değerlerini tanımıyor (örneğin, 1.0 E100).

**POW** , Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahiptir. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_Set_sse2_enable](set-sse2-enable.md).

Aşırı C++ yüklemeye izin verdiğinden, **POW**'ın çeşitli aşırı yüklerini çağırabilirsiniz. C programında **POW** her zaman iki **çift** değer alır ve bir **Double** değeri döndürür.

`pow(int, int)` Aşırı yükleme artık kullanılamıyor. Bu aşırı yüklemeyi kullanırsanız, derleyici [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md)yayabilir. Bu sorundan kaçınmak için, ilk parametreyi **Double**, **float**veya **Long** **Double**olarak atayın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgiC++()|
|-|-|-|
|**POW**, **powf**, **ptıl**|\<Math. h >|\<Math. h > veya \<cmath >|

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md) <br/>
[sqrt, sqrtf, sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
