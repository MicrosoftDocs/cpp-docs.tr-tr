---
title: fmod, fmodf, fmodl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fmod
- fmodf
- fmodl
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
- fmod
- _fmodl
- fmodf
dev_langs:
- C++
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmodl function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f6cc8cc10c026c5ecd621657c556da883c187f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fmod-fmodf-fmodl"></a>fmod, fmodf, fmodl

Kayan nokta kalanı hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double fmod(
   double x,
   double y
);
float fmod(
   float x,
   float y
);  // C++ only
long double fmod(
   long double x,
   long double y
);  // C++ only
float fmodf(
   float x,
   float y
);
long double fmodl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parametreler

*x*, *y*<br/>
Kayan nokta değerleri.

## <a name="return-value"></a>Dönüş Değeri

**fmod** kayan nokta geri kalanı döndürür *x* / *y*. Varsa değerini *y* 0.0, olan **fmod** sessiz NaN döndürür. Sessiz NaN tarafından gösterimini hakkında bilgi için **printf** ailesi, bkz: [printf](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Açıklamalar

**Fmod** işlevi kayan nokta kalanı hesaplar *f* , *x* / *y* şekilde *x*  =  *ı* * *y* + *f*, burada *ı* bir tamsayıdır *f* aynı işarete sahip *x*ve mutlak değerini *f* mutlak değerini'dan küçük *y*.

C++ verir aşırı yüklemesi, aşırı çağırması **fmod** alın ve dönüş **float** ve **uzun** **çift** değerleri. Bir C programı **fmod** her zaman iki alan **çift** bağımsız değişkenleri ve döndürür bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fmod**, **fmodf**, **fmodl**|\<Math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fmod.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = fmod( w, x );
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[fabs, fabsf, fabsl](fabs-fabsf-fabsl.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[_CIfmod](../../c-runtime-library/cifmod.md)<br/>
