---
title: POW, powf, powl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs:
- C++
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59aecd68fd38ee1dadd9883374528554e67ce77e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="pow-powf-powl"></a>pow, powf, powl

Hesaplar *x* üssünü *y*.

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
Tabanı.

*Y*<br/>
Üs.

## <a name="return-value"></a>Dönüş Değeri

Değerini döndürür *x*<sup>*y*</sup>. Hata iletisi taşması veya underflow yazdırılır.

|X değerleri ve y|Pow dönüş değeri|
|-----------------------|-------------------------|
|*x* ! 0,0 = ve *y* == 0.0|1.|
|*x* == 0.0 ve *y* == 0.0|1.|
|*x* == 0.0 ve *y* < 0|INF|

## <a name="remarks"></a>Açıklamalar

**POW** 2'den büyük tam sayı kayan nokta değerlerine tanımıyor<sup>64</sup> (örneğin, 1.0E100).

**POW** Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahip. Bilgi ve kısıtlamaları SSE2 uygulama kullanımı hakkında bkz [_set_SSE2_enable](set-sse2-enable.md).

Aşırı yükleme C++ izin verdiğinden, çeşitli aşırı hiçbirini çağırabilirsiniz **pow**. C programı **pow** her zaman iki alan **çift** değerleri ve döndüren bir **çift** değeri.

`pow(int, int)` Aşırı kullanılabilir artık. Bu aşırı kullanırsanız, derleyici yayabilir [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md). Bu sorunu önlemek için ilk parametre olarak cast **çift**, **float**, veya **uzun** **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|-|-|-|
|**POW**, **powf**, **powl**|\<Math.h >|\<Math.h > veya \<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
