---
title: remainder, remainderf, remainderl
ms.date: 04/05/2018
api_name:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: 851f022325bb617cb2b0ae9a331b680b9d9fd303
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949421"
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

*x*<br/>
Pay.

*Iz*<br/>
Payda.

## <a name="return-value"></a>Dönüş Değeri

*X* / *y*'nin kayan nokta kalanı. *Y* değeri 0,0 ise, **kalanı** sessiz bir NaN döndürür. **Printf** ailesi tarafından sessiz bir NaN 'ın temsili hakkında daha fazla bilgi için bkz. [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Kalan** işlevler *x*  /  n\*y*r 'nin*kayan nokta geri kalanını hesaplar, burada n +  =  -  &#124; *x* *y değerine* en yakın *tamsayı ve n* *x*y / = 1/2 her seferinde &#124; eşit olur. /  *R* = 0 olduğunda, *r* *x*işaretine eşittir.

Aşırı C++ yüklemeye izin verdiğinden, **float** veya **Long** **Double** değerlerini alan ve döndüren **geri** yüklerin aşırı yüklerini çağırabilirsiniz. C programında, **kalan** her zaman iki **çift** bağımsız değişken alır ve bir **Double**döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgiC++()|
|--------------|---------------------|-|
|**kalan**, **remainderf**, **remainderl**|\<Math. h >|\<cmath > veya \<Math. h >|

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
