---
title: exp, expf, expl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 580c756c53f1a177506230f669fabd2be39d71d6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="exp-expf-expl"></a>exp, expf, expl

Üstel hesaplar.

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
Kayan nokta exponentiate için Doğal logaritmanın tabanı değer *e* tarafından.

## <a name="return-value"></a>Dönüş Değeri

**Exp** işlevler döndürür üstel parametresinin değeri kayan nokta, *x*, başarılı olursa. Diğer bir deyişle, sonucu olan *e*<sup>*x*</sup>, burada *e* ve Doğal logaritmanın tabanıdır. Taşma, işlev dönüşleri INF (sonsuz) ve underflow, **exp** 0 döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± Sessiz NaN, belirsiz|Yok.|_DOMAIN|
|± Sonsuz|GEÇERSİZ|_DOMAIN|
|x ≥ 7.097827e + 002|KESİN OLMAYAN + TAŞMASI|TAŞMA|
|X ≤-7.083964e + 002|INEXACT+UNDERFLOW|UNDERFLOW|

**Exp** işlevi Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. Bkz: [_set_SSE2_enable](set-sse2-enable.md) ilgili bilgileri ve SSE2 uygulama kullanılmasındaki kısıtlamalar.

## <a name="remarks"></a>Açıklamalar

C++ verir aşırı yüklemesi, aşırı çağırması **exp** süren bir **float** veya **uzun çift** bağımsız değişkeni. Bir C programı **exp** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|--------------|---------------------|---|
|**exp**, **expf**, **expl**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
