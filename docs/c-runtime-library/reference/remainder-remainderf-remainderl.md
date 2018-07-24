---
title: geri kalan, remainderf remainderl | Microsoft Docs
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
ms.openlocfilehash: 96d87a213029ab33e4d3c0269c4e7ba41e1aed43
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39209423"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

En yakın tamsayı değerine yuvarlanır iki kayan nokta değerleri bölümünü geri kalanı hesaplar.

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
Payda.

## <a name="return-value"></a>Dönüş Değeri

Kayan nokta kalanını *x* / *y*. Varsa değerini *y* 0.0, olan **kalan** sessiz bir NaN döndürür. Tarafından sessiz bir NaN'ın sunumu hakkındaki bilgiler için **printf** ailesi, bkz: [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Kalan** işlevler hesapla kayan nokta kalanını *r* , *x* / *y* şekilde *x*   =  *n* \* *y* + *r*burada *n*olduğu tamsayı değeri için en yakın *x* / *y* ve *n*olsa bile her &#124; *n*  -  *x* / *y* &#124; = 1/2. Zaman *r* = 0, *r* aynı işarete sahip *x*.

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **kalan** alan ve getiren **float** veya **uzun** **çift** değerleri. C programında **kalan** her zaman iki alan **çift** bağımsız değişkenleri ve döndürür bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------|-|
|**kalan**, **remainderf**, **remainderl**|\<Math.h >|\<cmath > veya \<math.h >|

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
