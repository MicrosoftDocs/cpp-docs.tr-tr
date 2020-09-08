---
title: modf, modff, modfl
description: Modf, modff ve modfl için API başvurusu; kayan nokta değerini kesirli ve tamsayı parçalara ayırır.
ms.date: 4/2/2020
api_name:
- modff
- modf
- modfl
- _o_modf
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
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
ms.openlocfilehash: 0d3522079acc8a9d2c8409b1cad78e7f50a7f788
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556768"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

Kayan nokta değerini kesirli ve tamsayı bölümlerine böler.

## <a name="syntax"></a>Söz dizimi

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

*x*<br/>
Kayan nokta değeri.

*serisi*<br/>
Depolanan tamsayı bölümü işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlev, *x*'in işaretli kesirli kısmını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**Modf** işlevleri kayan nokta değeri olan *x* ' i Kesir ve tamsayı bölümlerine ayırır, her birinin *x*ile aynı işareti vardır. *X* ' in işaretli kesir bölümü döndürülür. Tamsayı bölümü, *IntPtr*'de kayan nokta değeri olarak depolanır.

**modf** 'de Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_set_SSE2_enable](set-sse2-enable.md) .

C++ aşırı yüklemeye izin verdiğinden, işlem yapan ve döndüren **modf** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında **modf** her zaman iki çift değer alır ve bir Double değeri döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|, \<math.h><br /><br /> C++:, \<cmath> veya \<math.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
