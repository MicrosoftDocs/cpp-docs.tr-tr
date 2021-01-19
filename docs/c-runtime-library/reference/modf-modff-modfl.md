---
title: modf, modff, modfl
description: Modf, modff ve modfl için API başvurusu; kayan nokta değerini kesirli ve tamsayı parçalara ayırır.
ms.date: 1/15/2021
api_name:
- modff
- modf
- modfl
- _o_modf
- _o_modff
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.openlocfilehash: fbc68c3369e8b992350534e3baa5f19b0f2a5e39
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564024"
---
# <a name="modf-modff-modfl"></a>`modf`, `modff`, `modfl`

Kayan nokta değerini kesirli ve tamsayı bölümlerine böler.

## <a name="syntax"></a>Sözdizimi

```C
double modf( double x, double * intptr );
float modff( float x, float * intptr );
long double modfl( long double x, long double * intptr );
```

```cpp
float modf( float x, float * intptr );  // C++ only
long double modf( long double x, long double * intptr );  // C++ only
```

### <a name="parameters"></a>Parametreler

*`x`*\
Kayan nokta değeri.

*`intptr`*\
Depolanan tamsayı bölümü işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlev, öğesinin işaretli kesirli kısmını döndürür *`x`* . Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**Modf** işlevleri kayan nokta değerini *`x`* kesirli ve tamsayı bölümlerine ayırır, bunların her biri aynı işarete sahip olur *`x`* . Öğesinin işaretli kesirli kısmı *`x`* döndürülür. Tamsayı bölümü ' de kayan nokta değeri olarak depolanır *`intptr`* .

**modf** 'de Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. [`_set_SSE2_enable`](set-sse2-enable.md)SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz..

C++ aşırı yüklemeye izin verdiğinden, **`modf`** Bu, alan veya parametre alma ve döndürme yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında **`modf`** her zaman iki çift değer alır ve bir Double değeri döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`modf`**, **`modff`**, **`modfl`**|, `<math.h>`<br /><br /> C++:, `<cmath>` veya `<math.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_modf.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y, n;

   x = -14.87654321;      /* Divide x into its fractional */
   y = modf( x, &n );     /* and integer parts            */

   printf( "For %f, the fraction is %f and the integer is %.f\n",
           x, y, n );
}
```

```Output
For -14.876543, the fraction is -0.876543 and the integer is -14
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`frexp`](frexp.md)\
[`ldexp`](ldexp.md)