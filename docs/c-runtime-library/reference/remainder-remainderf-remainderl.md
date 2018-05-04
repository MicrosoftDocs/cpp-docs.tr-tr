---
title: kalan, remainderf, remainderl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f277292f413e09b9c41a87cd82e438e0e1e883a8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

Sayının yakın tamsayı değerine yuvarlanan iki kayan nokta değerlerinin kalanı hesaplar.

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

*Y*<br/>
Payda değeri.

## <a name="return-value"></a>Dönüş Değeri

Kayan nokta geri kalanı *x* / *y*. Varsa değerini *y* 0.0, olan **kalan** sessiz NaN döndürür. Sessiz NaN tarafından gösterimini hakkında bilgi için **printf** ailesi, bkz: [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Kalan** işlevler hesapla kayan nokta kalan *r* , *x* / *y* şekilde *x*   =  *n* * *y* + *r*, burada *n*olduğu tamsayı değeri'yakın *x* / *y* ve *n*olsa bile her &#124; *n*  -  *x* / *y* &#124; = 1/2. Zaman *r* = 0, *r* aynı işarete sahip *x*.

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **kalan** alın ve dönüş **float** veya **uzun** **çift** değerleri. Bir C programı **kalan** her zaman iki alan **çift** bağımsız değişkenleri ve döndürür bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|--------------|---------------------|-|
|**kalan**, **remainderf**, **remainderl**|\<Math.h >|\<cmath > veya \<math.h >|

Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
