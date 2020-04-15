---
title: exp, expf, expl
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: cbf303b2b92afd83a1c3181dc98a1dbdcd639c1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347593"
---
# <a name="exp-expf-expl"></a>exp, expf, expl

Üstel olarak hesaplar.

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

*X*<br/>
Doğal logaritma tabanını üslemek için kayan nokta *değeri.*

## <a name="return-value"></a>Dönüş Değeri

**Exp** işlevleri kayan nokta parametrenin üstel değerini döndürür, *x*, başarılı olursa. Yani, sonuç *e*<sup>*x*</sup>, *e* doğal logaritma tabanıdır. Taşmada, işlev INF (sonsuz) ve akış **altında, exp** 0 döndürür.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± Sessiz NaN, belirsiz|None|_DOMAIN|
|± Sonsuzluk|Geçersiz|_DOMAIN|
|x ≥ 7.097827e+002|TAM OLMAYAN+TAŞMA|Taşma|
|X ≤ -7.083964e+002|TAM OLMAYAN+ALT Akış|ALT Akış|

**Exp** işlevi, Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahiptir. SSE2 uygulamasını kullanma yla ilgili bilgi ve kısıtlamalar için [_set_SSE2_enable](set-sse2-enable.md) bakın.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verir, böylece **float** veya **uzun çift** bağımsız değişken alan aşırı **exp** yüklerini arayabilirsiniz. Bir C programında, **exp** her zaman alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgi|Gerekli C++ üstbilgi|
|--------------|---------------------|---|
|**exp**, **expf**, **expl**|\<math.h>|\<cmath> \<veya math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
