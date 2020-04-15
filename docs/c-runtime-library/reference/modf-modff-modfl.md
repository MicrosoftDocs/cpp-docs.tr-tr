---
title: modf, modff, modfl
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b509da5f18ea1f606b8a3b47ab66a78e4f595558
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338691"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

Kayan nokta değerini kesirli ve tamsayı parçalarına böler.

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

*X*<br/>
Kayan nokta değeri.

*ıntptr*<br/>
Tamsayı bölümünü depolamak için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlev *x'in*imzalı kesirli kısmını döndürür. Hata iadesi yok.

## <a name="remarks"></a>Açıklamalar

**Modf** fonksiyonları kayan nokta değeri *x'i* kesirli ve tamsayı parçalarına ayırır, her biri *x*ile aynı işarete sahiptir. *x'in* imzalı kesirli kısmı döndürülür. Tamsayı kısmı *intptr'da*kayan nokta değeri olarak depolanır.

**modf** Streaming SIMD Uzantıları 2 (SSE2) kullanan bir uygulama vardır. SSE2 uygulamasını kullanma yla ilgili bilgi ve kısıtlamalar için [_set_SSE2_enable](set-sse2-enable.md) bakın.

C++ aşırı yüklemeye izin verir, böylece **float** veya uzun **long** **çift** parametreleri alıp geri döndüren **aşırı modf** yüklerini arayabilirsiniz. C programında **modf** her zaman iki çift değer alır ve çift değer verir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<math.h><br /><br /> C++: \<, cmath \<> veya math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
