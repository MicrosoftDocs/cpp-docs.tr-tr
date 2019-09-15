---
title: modf, modff, modfl
ms.date: 04/05/2018
api_name:
- modff
- modf
- modfl
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
ms.openlocfilehash: 32caadb787031dca0b0726c546a11c5cd6722b82
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951535"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

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

*x*<br/>
Kayan nokta değeri.

*serisi*<br/>
Depolanan tamsayı bölümü işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlev, *x*'in işaretli kesirli kısmını döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**Modf** işlevleri kayan nokta değeri olan *x* ' i Kesir ve tamsayı bölümlerine ayırır, her birinin *x*ile aynı işareti vardır. *X* ' in işaretli kesir bölümü döndürülür. Tamsayı bölümü, *IntPtr*'de kayan nokta değeri olarak depolanır.

**modf** 'de Streaming SIMD Extensions 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma hakkında bilgi ve sınırlamalar için bkz. [_Set_sse2_enable](set-sse2-enable.md) .

C++aşırı yüklemeye izin verir, böylece **float** veya **Long** **Double** parametreleri alıp döndüren **modf** 'nin aşırı yüklerini çağırabilirsiniz. C programında **modf** her zaman iki çift değer alır ve bir Double değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<Math. h ><br /><br /> C++:, \<cmath > veya \<Math. h >|

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
