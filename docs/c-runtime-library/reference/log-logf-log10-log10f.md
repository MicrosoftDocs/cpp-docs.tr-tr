---
title: log, logf, logl, log10, log10f, log10l
ms.date: 4/2/2020
api_name:
- log10f
- logf
- log10
- log
- log10l
- logl
- _o_log
- _o_log10
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
ms.openlocfilehash: ab6f2654e9e647f140d5c579087b76001b317887
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341869"
---
# <a name="log-logf-logl-log10-log10f-log10l"></a>log, logf, logl, log10, log10f, log10l

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

*X*<br/>
Logaritma bulunan değer.

## <a name="return-value"></a>Dönüş Değeri

**Günlük** işlevleri başarılı olursa *x'in* doğal logaritmasını (baz *e)* döndürer. **Log10** işlevleri base-10 logaritma döndürün. *x* negatifse, bu işlevler varsayılan olarak belirsiz (IND) döndürer. *x* 0 ise, sonsuz (INF) döndürün.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± QNAN, IND|yok|_DOMAIN|
|± 0|SIFIR BÖL|_SING|
|*x* < 0|Geçersiz|_DOMAIN|

**log** ve **log10'** un Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulaması vardır. SSE2 uygulamasını kullanma yla ilgili bilgi ve kısıtlamalar için [_set_SSE2_enable](set-sse2-enable.md) bakın.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verir, böylece **float** veya **uzun çift** değerleri alan ve döndüren **günlük** ve **log10** yüklerini arayabilirsiniz. Bir C programında, **günlük** ve **log10** her zaman almak ve bir **çift**dönmek .

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**log**, **logf**, **logl**, **log10**, **log10f**, **log10l**|\<math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

Diğer bazlar için logaritma oluşturmak için matematiksel ilişkiyi kullanın: a == doğal günlük (a) / doğal günlük (b) günlük tabanı b.

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
