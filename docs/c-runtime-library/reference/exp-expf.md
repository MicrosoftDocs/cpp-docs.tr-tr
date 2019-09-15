---
title: exp, expf, expl
ms.date: 04/05/2018
api_name:
- expf
- expl
- exp
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
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
ms.openlocfilehash: 380f3e861b3ae1ba2f57aa781c32829771612b9f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941632"
---
# <a name="exp-expf-expl"></a>exp, expf, expl

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
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Doğal logaritma tabanında *e tarafından üsl* olacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Exp** işlevleri, başarılı olursa *x*kayan nokta parametresinin üstel değerini döndürür. Diğer bir deyişle, sonuç *e*<sup>*x*</sup>olur. burada *e* , doğal logaritmanın temelini alır. Taşma durumunda işlev INF (Infinity) döndürür ve yetersiz kalması, **Exp** 0 döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± Quiet NaN, belirsiz|Yok.|_DOMAIN|
|± Infinity|GEÇERSİZ|_DOMAIN|
|x ≥ 7.097827 e + 002|INTAM + TAŞMA|TAŞMA|
|X ≤-7.083964 e + 002|INEXACT+UNDERFLOW|ÖĞE|

**Exp** işlevinin, Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_Set_sse2_enable](set-sse2-enable.md) .

## <a name="remarks"></a>Açıklamalar

C++aşırı yüklemeye izin verir, böylece bir **float** veya **Long Double** bağımsız değişkeni alan **Exp** aşırı yüklerini çağırabilirsiniz. C programında, **Exp** her zaman bir **Double**alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üst bilgi|
|--------------|---------------------|---|
|**Exp**, **expf**, **expl**|\<Math. h >|\<cmath > veya \<Math. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
