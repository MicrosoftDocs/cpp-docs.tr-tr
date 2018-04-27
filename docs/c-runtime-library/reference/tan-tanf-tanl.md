---
title: Tan, tanf, tanl | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- tan
- tanf
- tanl
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
- tan
- tanf
- _tanl
- tanl
dev_langs:
- C++
helpviewer_keywords:
- tanl function
- _tanl function
- tan function
- calculating tangents
- tangent
- tanf function
- trigonometric functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0dc25d2e197f31cce332b4cea67d8ba1c132bf42
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="tan-tanf-tanl"></a>Bronz, tanf, tanl

Tanjantını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double tan( double x );
float tanf( float x );
long double tanl( long double x );
```

```cpp
float tan( float x );  // C++ only
long double tan( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Radyan cinsinden açı.

## <a name="return-value"></a>Dönüş değeri

**Tan** işlevleri tanjantını Döndür *x*. Varsa *x* büyük veya 263 eşit veya daha az veya buna eşit -263, sonuç anlamlı kaybı oluşur.

|Giriş|SEH özel durumu|**Matherr** özel durumu|
|-----------|-------------------|-------------------------|
|± QNAN, UL|yok|_DOMAIN|
|± INF|**GEÇERSİZ**|_DOMAIN|

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **tan** alın ve dönüş **float** veya **uzun** **çift** değerleri. Bir C programı **tan** her zaman alan ve döndüren **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|-------------|---------------------|-|
|**tan**, **tanf**, **tanl**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_tan.c
// This program displays the tangent of pi / 4
// Compile by using: cl crt_tan.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x;

   x = tan( pi / 4 );
   printf( "tan( %f ) = %f\n", pi/4, x );
}
```

```Output
tan( 0.785398 ) = 1.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[Sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[_CItan](../../c-runtime-library/citan.md)<br/>