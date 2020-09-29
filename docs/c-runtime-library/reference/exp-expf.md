---
title: exp, expf, expl
description: Exp, expf ve expl için API başvurusu; üstel olarak hesaplama.
ms.date: 08/31/2020
api_name:
- expf
- expl
- exp
- _o_exp
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
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
ms.openlocfilehash: f6733f293f1c8f78e8143d9fdd395013147bbe83
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502104"
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
#define exp(z) // Requires C11 or higher
```

### <a name="parameters"></a>Parametreler

*sayı*\
Doğal logaritma tabanında *e tarafından üsl* olacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Exp** işlevleri, başarılı olursa *x*kayan nokta parametresinin üstel değerini döndürür. Diğer bir deyişle, sonuç *e*<sup>*x*</sup>olur. burada *e* , doğal logaritmanın temelini alır. Taşma durumunda işlev INF (Infinity) döndürür ve yetersiz kalması, **Exp** 0 döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± Quiet NaN, belirsiz|Hiçbiri|_DOMAIN|
|± Infinity|Geçersiz|_DOMAIN|
|x ≥ 7.097827 e + 002|INTAM + taşma|TAŞMA|
|X ≤-7.083964 e + 002|TAM aşağı + yetersız|ÖĞE|

**Exp** işlevinin, Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_set_SSE2_enable](set-sse2-enable.md) .

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, bir **exp** **`float`** veya bağımsız değişkeni alan exp aşırı yüklerini çağırabilirsiniz **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **Exp** her zaman alır ve döndürür **`double`** .

\<tgmath.h> `exp()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|--------------|---------------------|---|
|**Exp**, **expf**, **expl**|\<math.h>|\<cmath> veya \<math.h>|
|**Exp** makrosu| \<tgmath.h> ||

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[_CIexp](../../c-runtime-library/ciexp.md)<br/>
