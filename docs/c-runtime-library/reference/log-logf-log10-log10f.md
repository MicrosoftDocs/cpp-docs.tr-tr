---
title: Günlük, logf, logl, log10, log10f, log10l
ms.date: 04/05/2018
apiname:
- log10f
- logf
- log10
- log
- log10l
- logl
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
- logf
- logl
- _log10l
- log
- _logl
- log10f
- log10l
- log10
helpviewer_keywords:
- calculating logarithms
- log10f function
- log10 function
- log function
- log10l function
- logl function
- logf function
- logarithms
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
ms.openlocfilehash: c8e3f73e61fefa7a39a6d53d63739b094d78c499
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543305"
---
# <a name="log-logf-logl-log10-log10f-log10l"></a>Günlük, logf, logl, log10, log10f, log10l

Logaritmaları hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double log( double x );
float logf( float x );
long double logl( double x );
double log10( double x );
float log10f ( float x );
long double log10l( double x );
```

```cpp
float log( float x );  // C++ only
long double log( long double x );  // C++ only
float log10( float x );  // C++ only
long double log10( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Bulunacak logaritmasını olan değer.

## <a name="return-value"></a>Dönüş Değeri

**Günlük** işlevler doğal logaritmasını döndürür (temel *e*), *x* başarılı olursa. **Log10** işlevler 10 tabanında logaritmasını döndürür. Varsa *x* olan negatif, bu işlevler bir belirsiz (Ara), varsayılan olarak döndürür. Varsa *x* 0 ise, bunlar sonsuz (INF) döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± QNAN, ONRAKİNİ BUL|yok|_DOMAIN|
|± 0|ZERODIVIDE|_SING|
|*x* < 0|GEÇERSİZ|_DOMAIN|

**Günlük** ve **log10** , Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamasına sahipseniz. Bkz: [_set_SSE2_enable](set-sse2-enable.md) bilgi ve SSE2 uygulama kullanılmasındaki kısıtlamalar.

## <a name="remarks"></a>Açıklamalar

C++ sağlar aşırı yüklemesi, aşırı yüklemesini çağırabilirsiniz **günlük** ve **log10** alan ve getiren **float** veya **uzun çift** değerleri. C programında **günlük** ve **log10** her zaman alan ve getiren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**Günlük**, **logf**, **logl**, **log10**, **log10f**, **log10l**|\<Math.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_log.c
/* This program uses log and log10
* to calculate the natural logarithm and
* the base-10 logarithm of 9,000.
*/

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 9000.0;
   double y;

   y = log( x );
   printf( "log( %.2f ) = %f\n", x, y );
   y = log10( x );
   printf( "log10( %.2f ) = %f\n", x, y );
}
```

```Output
log( 9000.00 ) = 9.104980
log10( 9000.00 ) = 3.954243
```

Matematik ilişki için diğer tabanlara logaritmaları oluşturmak için kullanın: temel b oturum bir doğal logaritmayı (a) == / doğal (b) oturum açın.

```cpp
// logbase.cpp
#include <math.h>
#include <stdio.h>

double logbase(double a, double base)
{
   return log(a) / log(base);
}

int main()
{
   double x = 65536;
   double result;

   result = logbase(x, 2);
   printf("Log base 2 of %lf is %lf\n", x, result);
}
```

```Output
Log base 2 of 65536.000000 is 16.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[_matherr](matherr.md) <br/>
[pow, powf, powl](pow-powf-powl.md) <br/>
[_CIlog](../../c-runtime-library/cilog.md) <br/>
[_CIlog10](../../c-runtime-library/cilog10.md)<br/>
