---
title: modf, modff, modfl
ms.date: 04/05/2018
apiname:
- modff
- modf
- modfl
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
ms.openlocfilehash: 59d6e2b9b02ad182c5630d6dc9a989c035e8fa92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156336"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

Bir kayan nokta değeri kesirli ve tamsayı bölümlere böler.

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

*x*<br/>
Kayan nokta değeri.

*IntPtr*<br/>
Saklı tamsayı kısmı işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlev, işaretli kesirli kısmını döndürür. *x*. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

**Modf** işlevleri sonu kayan nokta değeri *x* kesirli ve tamsayı bölümlere, her biri aynı işarete sahip *x*. İşaretli kesirli kısmını *x* döndürülür. Tamsayı kısmı bir kayan nokta değeri olarak depolanan *IntPtr*.

**modf** , Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahiptir. Bkz: [_set_SSE2_enable](set-sse2-enable.md) bilgi ve SSE2 uygulama kullanılmasındaki kısıtlamalar.

C++ sağlar aşırı yüklemesi, aşırı yüklemesini çağırabilirsiniz **modf** alan ve getiren **float** veya **uzun** **çift** parametreleri. C programında **modf** her zaman iki çift değer alır ve bir çift değer döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<math.h ><br /><br /> C++:, \<cmath > veya \<math.h >|

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
