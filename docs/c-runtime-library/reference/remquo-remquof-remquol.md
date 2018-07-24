---
title: remquo, remquof, remquol | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- remquof
- remquo
- remquol
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
- remquof
- remquol
- remquo
dev_langs:
- C++
helpviewer_keywords:
- remquol function
- remquof function
- remquo function
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 480bf65d61581866fe447c9563a267d08d17c838
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207659"
---
# <a name="remquo-remquof-remquol"></a>remquo, remquof, remquol

İki tamsayı değerinin kalanını hesaplar ve işaretli ve yaklaşık büyüklük tamsayı değerini bir parametre içinde belirtilen bir konumda saklar.

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

*numarası*<br/>
Pay.

*denom*<br/>
Payda.

*quo*<br/>
İşaretli ve yaklaşık büyüklük olan bir değeri depolamak için bir tamsayıya yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**remquo** kayan nokta kalanını döndürür *x* / *y*. Varsa değerini *y* 0.0, olan **remquo** sessiz bir NaN döndürür. Tarafından sessiz bir NaN'ın sunumu hakkındaki bilgiler için **printf** ailesi, bkz: [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Remquo** işlevi kayan nokta kalanını hesaplar *f* , *x* / *y* şekilde *x*   =  *miyim* \* *y* + *f*burada *miyim* tamsayı , *f* aynı işarete sahip *x*ve mutlak değerini *f* mutlak değerini'dan küçük *y*.

C++ sağlar aşırı yüklemesi, aşırı yüklemesini çağırabilirsiniz **remquo** alan ve getiren **float** veya **uzun** **çift** değerleri. C programında **remquo** her zaman iki alan **çift** bağımsız değişkenleri ve döndürür bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------|-|
|**remquo**, **remquof**, **remquol**|\<Math.h >|\<cmath > veya \<math.h >|

Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
