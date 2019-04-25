---
title: exp, expf, expl
ms.date: 04/05/2018
apiname:
- expf
- expl
- exp
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
ms.openlocfilehash: b9fb38adcc442e60864ec632cd92793f16e47502
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288194"
---
# <a name="exp-expf-expl"></a>exp, expf, expl

Üssünü hesaplar.

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
Kayan nokta exponentiate için doğal logaritma tabanı değer *e* tarafından.

## <a name="return-value"></a>Dönüş Değeri

**Exp** işlevler kayan nokta parametresi üstel değerini döndürür *x*, başarılı olursa. Diğer bir deyişle, sonucudur *e*<sup>*x*</sup>burada *e* ve Doğal logaritmanın tabanıdır. Taşmada, INF (sonsuz) işlevi döndürür ve taşma, **exp** 0 döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± Sessiz NaN, belirsiz|Yok.|_DOMAIN|
|± Sonsuz|GEÇERSİZ|_DOMAIN|
|x ≥ 7.097827e + 002|FİLTRESİNİN + TAŞMASI|TAŞMA|
|X ≤-7.083964e + 002|INEXACT+UNDERFLOW|YETERSİZ KALMASI|

**Exp** işlevi, Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulaması vardır. Bkz: [_set_SSE2_enable](set-sse2-enable.md) bilgi ve SSE2 uygulama kullanılmasındaki kısıtlamalar.

## <a name="remarks"></a>Açıklamalar

C++ sağlar aşırı yüklemesi, aşırı yüklemesini çağırabilirsiniz **exp** süren bir **float** veya **uzun çift** bağımsız değişken. C programında **exp** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üst bilgisi|
|--------------|---------------------|---|
|**exp**, **expf**, **expl**|\<Math.h >|\<cmath > veya \<math.h >|

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
