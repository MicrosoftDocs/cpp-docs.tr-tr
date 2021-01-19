---
title: atan, atanf, atanl, atan2, atan2f, atan2l
description: Atan, atanf, atanl, atan2, atan2f ve atan2l için API başvurusu; bir kayan nokta değerinin arktanjantını hesaplayan.
ms.date: 1/15/2021
api_name:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
- _o_atan
- _o_atan2
- _o_atan2f
- _o_atanf
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.openlocfilehash: bbfc08507bd48e1b9eb0b91350b2b39948d19a5f
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564075"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>`atan`, `atanf`, `atanl`, `atan2`, `atan2f`, `atan2l`

(,, **`x`** Ve) **`atan`** **`atanf`** **`atanl`** veya **`y`** / **`x`** ( **`atan2`** , **`atan2f`** , ve **`atan2l`** ) öğesinin arktanjantını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );
#define atan(X) // Requires C11 or higher

float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
#define atan2(Y, X) // Requires C11 or higher

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*`x`*, *`y`*\
Herhangi bir sayı.

## <a name="return-value"></a>Dönüş Değeri

**`atan`***`x`*-π/2 ile π/2 radyan aralığında olan arktanjantını döndürür. **`atan2`***`y`* / *`x`* -π-π radyana aralığında olan arktanjantını döndürür. *`x`* 0 ise **`atan`** 0 döndürür. Her iki parametre de **`atan2`** 0 ise, işlev 0 döndürür. Tüm sonuçlar radyan cinsinden olur.

**`atan2`** dönüş değerinin çeyreğine ilişkin her iki parametrenin işaretlerini kullanır.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± **`QNAN`**, **`IND`**|yok|**`_DOMAIN`**|

## <a name="remarks"></a>Açıklamalar

**`atan`** İşlevi arktanjantı (ters tanjant işlevi) hesaplar *`x`* . **`atan2`** öğesinin arktanjantını hesaplar *`y`* / *`x`* ( *`x`* 0 eşitse, **`atan2`** π/2 döndürür, Eğer *`y`* negatifse,-π/2 *`y`* veya 0 ise 0 *`y`* ).)

`<tgmath.h>` `atan()` Veya `atan2()` makrosunu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

**`atan`** Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahiptir. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz [`_set_SSE2_enable`](set-sse2-enable.md) ..

C++ aşırı yüklemeye izin verdiğinden, **`atan`** ve **`atan2`** tarafından yapılan **`float`** veya **`long double`** bağımsız değişken olan aşırı yüklerini çağırabilirsiniz. C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız **`atan`** ve **`atan2`** her zaman **`double`** bağımsız değişkenler alıp bir döndüren bir **`double`** .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------|-|
|**`atan`**, **`atan2`**, **`atanf`**, **`atan2f`**, **`atanl`**, **`atan2l`**|`<math.h>`|`<cmath>` veya `<math.h>`|
|**`atan()`**, **`atan2`** makrolar | `<tgmath.h>` ||

## <a name="example"></a>Örnek

```C
// crt_atan.c
// arguments: 5 0.5
#include <math.h>
#include <stdio.h>
#include <errno.h>

int main( int ac, char* av[] )
{
   double x, y, theta;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );
      return 1;
   }
   x = atof( av[1] );
   theta = atan( x );
   printf( "Arctangent of %f: %f\n", x, theta );
   y = atof( av[2] );
   theta = atan2( y, x );
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );
   return 0;
}
```

```Output
Arctangent of 5.000000: 1.373401
Arctangent of 0.500000 / 5.000000: 0.099669
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`acos`, `acosf`, `acosl`](acos-acosf-acosl.md)\
[`asin`, `asinf`, `asinl`](asin-asinf-asinl.md)\
[`cos`, `cosf`, `cosl`](cos-cosf-cosl.md)\
[`_matherr`](matherr.md)\
[`sin`, `sinf`, `sinl`](sin-sinf-sinl.md)\
[`tan`, `tanf`, `tanl`](tan-tanf-tanl.md)\
[`_CIatan`](../../c-runtime-library/ciatan.md)\
[`_CIatan2`](../../c-runtime-library/ciatan2.md)