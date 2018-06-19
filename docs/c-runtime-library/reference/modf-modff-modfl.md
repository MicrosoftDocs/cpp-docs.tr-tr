---
title: modf, modff, modfl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87cddb8b565cdc369e6b1e9679583db64039bb49
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404837"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

Bir kayan nokta değeri kesirli ve tamsayı bölümleri böler.

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
Saklı tamsayı bölümü işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlev imzalı kesirli kısmını döndürür *x*. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

**Modf** işlevleri bölün kayan nokta değeri *x* kesirli içine ve her birinin olan aynı işarete tamsayı bölümleri *x*. İmzalı kesirli kısmı *x* döndürülür. Tamsayı bölümü bir kayan nokta değeri olarak depolanan *IntPtr*.

**modf** Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulamaya sahip. Bkz: [_set_SSE2_enable](set-sse2-enable.md) ilgili bilgileri ve SSE2 uygulama kullanılmasındaki kısıtlamalar.

C++ verir aşırı yüklemesi, aşırı çağırması **modf** alın ve dönüş **float** veya **uzun** **çift** parametreleri. Bir C programı **modf** her zaman iki çift değerlerini alır ve bir double değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<math.h ><br /><br /> C++:, \<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
