---
title: tan, tanf, tanl
description: Tan, tanf ve tanl için API başvurusu; bir kayan nokta değerinin tanjantını hesaplayan.
ms.date: 1/15/2021
api_name:
- tan
- tanf
- tanl
- _o_tan
- _o_tanf
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
- tan
- tanf
- _tanl
- tanl
helpviewer_keywords:
- tanl function
- _tanl function
- tan function
- calculating tangents
- tangent
- tanf function
- trigonometric functions
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
ms.openlocfilehash: 056afdf0bbac422c498bd54c2a154472bfd97c34
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564062"
---
# <a name="tan-tanf-tanl"></a>`tan`, `tanf`, `tanl`

Tanjantı hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double tan( double x );
float tanf( float x );
long double tanl( long double x );
#define tan(x) // Requires C11 or higher
```

```cpp
float tan( float x );  // C++ only
long double tan( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*`x`*\
Radyan cinsinden açı.

## <a name="return-value"></a>Döndürülen değer

**`tan`** İşlevleri, tanjantını döndürür *`x`* . *`x`* 263 ' den büyük veya buna eşitse ya da-263 ' den küçük ya da eşitse, sonuçta anlam kaybı meydana gelir.

|Giriş|SEH özel durumu|**`Matherr`** duruma|
|-----------|-------------------|-------------------------|
|`± QNAN`,`IND`|yok|`_DOMAIN`|
|`± INF`|**Geçersiz**|`_DOMAIN`|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **`tan`** alan veya değer alma ve döndürme yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız takdirde, **`tan`** her zaman alır ve döndürür **`double`** .

`<tgmath.h>` `tan()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------|-|
|**`tan`**, **`tanf`**, **`tanl`**|`<math.h>`|`<cmath>` veya `<math.h>`|
|**`tan()`** makroya | `<tgmath.h>` ||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`acos, acosf, acosl`](acos-acosf-acosl.md)\
[`asin, asinf, asinl`](asin-asinf-asinl.md)\
[`atan, atanf, atanl, atan2, atan2f, atan2l`](atan-atanf-atanl-atan2-atan2f-atan2l.md)\
[`cos, cosf, cosl`](cos-cosf-cosl.md)\
[`sin, sinf, sinl`](sin-sinf-sinl.md)\
[`_CItan`](../../c-runtime-library/citan.md)