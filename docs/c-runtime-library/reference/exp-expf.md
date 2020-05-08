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
ms.openlocfilehash: b6d4906212073ab8cb04a0ab77d1234d444a4c95
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82909657"
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

*sayı*<br/>
Doğal logaritma tabanında *e tarafından üsl* olacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Exp** işlevleri, başarılı olursa *x*kayan nokta parametresinin üstel değerini döndürür. Diğer bir deyişle, sonuç *e*<sup>*x*</sup>olur. burada *e* , doğal logaritmanın temelini alır. Taşma durumunda işlev INF (Infinity) döndürür ve yetersiz kalması, **Exp** 0 döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± Quiet NaN, belirsiz|Yok|_DOMAIN|
|± Infinity|Geçersiz|_DOMAIN|
|x ≥ 7.097827 e + 002|INTAM + taşma|TAŞMA|
|X ≤-7.083964 e + 002|TAM aşağı + yetersız|ÖĞE|

**Exp** işlevinin, Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_set_SSE2_enable](set-sse2-enable.md) .

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** veya **Long Double** bağımsız değişkeni alan **Exp** aşırı yüklerini çağırabilirsiniz. C programında, **Exp** her zaman bir **Double**alır ve döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|--------------|---------------------|---|
|**Exp**, **expf**, **expl**|\<Math. h>|\<cmath> veya \<Math. h>|

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
