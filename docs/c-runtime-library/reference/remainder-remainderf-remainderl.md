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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 4b70d3175a125d72ff67710c83899c44dbf72015
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332874"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

En yakın integral değerine yuvarlanmış iki kayan nokta değerinin kalan kısmını hesaplar.

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

*X*<br/>
Sayı.

*Y*<br/>
Payda.

## <a name="return-value"></a>Dönüş Değeri

*X* / *y'nin*kayan noktası geri kalanı. *y* değeri 0.0 ise, **kalan** sessiz bir NaN döndürür. **Printf** ailesi tarafından sessiz bir NaN temsili hakkında bilgi için [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Kalan** işlevler *x* / *y'nin* kayan noktası kalan *r'sini* *hesaplar,* = x*n* \* *y* + *r*, *n'nin* *x* / *y* ve *n*değerine en yakın tamsayı olduğu yerde *n* - *x* / *y* &#124; = 1/2 &#124; bile. *r* = 0 olduğunda, *r* *x*ile aynı işarete sahiptir.

C++ aşırı yüklemeye izin verdiğinden, **float** veya uzun **long** **çift** değerleri alan ve **döndüren fazla** kalan yükleri arayabilirsiniz. C programında, **kalan** her zaman iki **çift** bağımsız değişken alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üstbilgi (C)|Gerekli üstbilgi (C++)|
|--------------|---------------------|-|
|**kalan**, **remainderf**, **remainderl**|\<math.h>|\<cmath> \<veya math.h>|

Uyumluluk bilgileri için [bkz.](../../c-runtime-library/compatibility.md)

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
