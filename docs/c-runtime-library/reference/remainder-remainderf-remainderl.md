---
title: remainder, remainderf, remainderl
ms.date: 4/2/2020
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
ms.openlocfilehash: 6b2a1a94fa39f9e9474f7bc3da3150bf4134d35f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917844"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

İki kayan noktalı değer bölümünün geri kalanını hesaplar ve en yakın tamsayı değerine yuvarlanır.

## <a name="syntax"></a>Sözdizimi

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>Parametreler

*sayı*<br/>
Pay.

*Iz*<br/>
Payda.

## <a name="return-value"></a>Dönüş Değeri

*X* / *y*'nin kayan nokta kalanı. *Y* değeri 0,0 ise, **kalanı** sessiz bir NaN döndürür. **Printf** ailesi tarafından sessiz bir NaN 'ın temsili hakkında daha fazla bilgi için bkz. [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Kalan** *y* işlevler *x* - *x* /  *x* /  + *r* / *y* *n* *y**y* *n* *n* *r*  = n \* y r 'nin kayan nokta geri kalanını hesaplar. burada n, x y *değeri için en*yakın *tamsayıdır ve n her &#124;* n x y &#124; = 1/2 olur. *R* = 0 olduğunda, *r* *x*işaretine eşittir.

C++ aşırı yüklemeye izin verdiğinden **float** veya **Long** **Double** değerlerini alan ve döndüren **geri** yüklerin aşırı yüklerini çağırabilirsiniz. C programında, **kalan** her zaman iki **çift** bağımsız değişken alır ve bir **Double**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|--------------|---------------------|-|
|**kalan**, **remainderf**, **remainderl**|\<Math. h>|\<cmath> veya \<Math. h>|

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
