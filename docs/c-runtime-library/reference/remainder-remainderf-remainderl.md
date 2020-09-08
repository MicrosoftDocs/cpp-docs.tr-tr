---
title: remainder, remainderf, remainderl
description: Geri kalan, remainderf ve remainderl için API başvurusu; iki kayan nokta değerinin bölümünün geri kalanını hesaplama, en yakın tamsayı değerine yuvarlanır.
ms.date: 9/1/2020
api_name:
- remainderl
- remainder
- remainderf
- _o_remainder
- _o_remainderf
- _o_remainderl
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
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: ef2b326bef2288b52dba8988749e030ff0b46077
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556015"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

İki kayan noktalı değer bölümünün geri kalanını hesaplar ve en yakın tamsayı değerine yuvarlanır.

## <a name="syntax"></a>Söz dizimi

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
#define remainder(X, Y) // Requires C11 or higher

float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>Parametreler

*sayı*\
Pay.

*Iz*\
Payda.

## <a name="return-value"></a>Dönüş Değeri

X y 'nin kayan nokta kalanı *x*  /  *y*. *Y* değeri 0,0 ise, **kalanı** sessiz bir NaN döndürür. **Printf** ailesi tarafından sessiz bir NaN 'ın temsili hakkında daha fazla bilgi için bkz. [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Kalan** işlevler x n y r 'nin kayan nokta *geri kalanını* hesaplar *x*  /  *y* *x*  =  *n* \* *y*  +  *r*. burada *n*, x y değeri için en yakın tamsayıdır ve n *x*  /  *y* her &#124; *n* *n*  -  *x*  /  *y* &#124; = 1/2 olur. *R* = 0 olduğunda, *r* *x*işaretine eşittir.

C++ aşırı yüklemeye izin verdiğinden, geri kalan ve değer döndüren **geri** yüklerin aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız takdirde, **kalan** her zaman iki **`double`** bağımsız değişken alır ve döndürür **`double`** .

\<tgmath.h> `remainder()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|--------------|---------------------|-|
|**kalan**, **remainderf**, **remainderl**|\<math.h>|\<cmath> veya \<math.h>|
|**kalan** makro | \<tgmath.h> ||

Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_remainder.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = remainder(w, x);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[ldiv, lldıv](ldiv-lldiv.md)\
[imaxdiv](imaxdiv.md)\
[FMOD, fmodf](fmod-fmodf.md)\
[remquo, remquof, remquol](remquo-remquof-remquol.md)
