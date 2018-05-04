---
title: Sin, sinf, sinl | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- sinl
- sinf
- sin
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
- _sinl
- sinf
- sinl
- sin
dev_langs:
- C++
helpviewer_keywords:
- _sinl function
- sinl function
- calculating sines
- sin function
- trigonometric functions
- sinf function
ms.assetid: 737de73e-3590-45f9-8257-dc1c0c489dfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f99e7792e177c6203d38a368f3dd4125fe848a76
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="sin-sinf-sinl"></a>Sin, sinf, sinl

Kayan nokta değeri sinüsünü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double sin(double x);
float sinf(float x);
long double sinl(long double x);
```

```cpp
float sin(float x);  // C++ only
long double sin(long double x);  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Radyan cinsinden açı.

## <a name="return-value"></a>Dönüş değeri

**Sin** işlevleri sinüsünü Döndür *x*. Varsa *x* büyük veya 263 eşit veya daha az veya buna eşit -263, sonuç anlamlı kaybı oluşur.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± QNAN, UL|Yok.|_DOMAIN|
|± ∞ (sin, sinf, sinl)|GEÇERSİZ|_DOMAIN|

Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **sin** alın ve dönüş **float** veya **uzun** **çift** değerleri. Bir C programı **sin** her zaman alan ve döndüren **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|-|-|-|
|**sin**, **sinf**, **sinl**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_sincos.c
// This program displays the sine and cosine of pi / 2.
// Compile by using: cl /W4 crt_sincos.c

#include <math.h>
#include <stdio.h>

int main( void)
{
   double pi = 3.1415926535;
   double x, y;

   x = pi / 2;
   y = sin( x );
   printf( "sin( %f ) = %f\n", x, y );
   y = cos( x );
   printf( "cos( %f ) = %f\n", x, y );
}
```

```Output
sin( 1.570796 ) = 1.000000
cos( 1.570796 ) = 0.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIsin](../../c-runtime-library/cisin.md)<br/>
