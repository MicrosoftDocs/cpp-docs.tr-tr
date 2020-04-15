---
title: remquo, remquof, remquol
ms.date: 4/2/2020
api_name:
- remquof
- remquo
- remquol
- _o_remquo
- _o_remquof
- _o_remquol
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
- remquof
- remquol
- remquo
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
ms.openlocfilehash: e6a6f211e83118379e0697464d21f5968ea68cee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332834"
---
# <a name="remquo-remquof-remquol"></a>remquo, remquof, remquol

İki tamsayı değerinin geri kalanını hesaplar ve bir tamsayı değerini bir parametrede belirtilen bir konumda işaret ve yaklaşık büyüklük ile birlikte depolar.

## <a name="syntax"></a>Sözdizimi

```C
double remquo( double numer, double denom, int* quo );
float remquof( float numer, float denom, int* quo );
long double remquol( long double numer, long double denom, int* quo );
```

```cpp
float remquo( float numer, float denom, int* quo ); /* C++ only */
long double remquo( long double numer, long double denom, int* quo ); /* C++ only */
```

### <a name="parameters"></a>Parametreler

*Numarası*<br/>
Sayı.

*payda*<br/>
Payda.

*Quo*<br/>
Bir tamsede işaretçisi işareti ve yaklaşık büyüklüğü olan bir değeri saklamak için.

## <a name="return-value"></a>Dönüş Değeri

**remquo** *x* / *y*kayan nokta geri kalanını döndürür. *y* değeri 0.0 ise, **remquo** sessiz bir NaN döndürür. **Printf** ailesi tarafından sessiz bir NaN temsili hakkında bilgi için [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Remquo** işlevi *x* / *y* kayan noktası kalan *f* hesaplar gibi *x* = *i* \* *y* + *f*, nerede *i* bir tamsayı, *f* *x*ile aynı işareti vardır , ve *f* mutlak değeri *y*mutlak değeri daha azdır .

C++ aşırı yüklemeye izin verir, böylece **float** veya **uzun** **çift** değerleri alan ve döndüren aşırı **remquo'u** arayabilirsiniz. C programında, **remquo** her zaman iki **çift** bağımsız değişken alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üstbilgi (C)|Gerekli üstbilgi (C++)|
|--------------|---------------------|-|
|**remquo**, **remquof**, **remquol**|\<math.h>|\<cmath> \<veya math.h>|

Uyumluluk bilgileri için [bkz.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_remquo.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;
   int quo = 0;

   z = remquo(w, x, &quo);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
   printf("Approximate signed quotient is %d\n", quo);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
Approximate signed quotient is -3
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
