---
title: ACOS, acosf, acosl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- acosf
- acos
- acosl
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
- acos
- acosl
- acosf
- math/acosf
- math/acosl
dev_langs:
- C++
helpviewer_keywords:
- acos function
- acosl function
- acosf function
- trigonometric functions
- arccosine function
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2acce9216d113616cfb053e6e9cd6fe74705e806
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="acos-acosf-acosl"></a>acos, acosf, acosl

Arkkosinüsünü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double acos( double x );
float acosf( float x );
long double acosl( long double x );
```

```cpp
float acos( float x );   // C++ only
long double acos( long double x );   // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
-1 ve 1 (ters kosinüsünü) arkkosinüsünü hesaplanacağı arasında değeri.

## <a name="return-value"></a>Dönüş Değeri

**Acos** işlevi sayının arkkosinüsünü döndürür *x* π radyan aralıktaki 0.

Varsayılan olarak, varsa *x* -1 veya 1 ' den büyük küçük **acos** bir belirsiz döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± ∞|**GEÇERSİZ**|**_DOMAIN**|
|± QNAN, UL|yok|**_DOMAIN**|
|&#124;x&#124;>1|**GEÇERSİZ**|**_DOMAIN**|

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **acos** alın ve dönüş **float** ve **uzun** **çift** türleri. Bir C programı **acos** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|----------------------|
|**ACOS**, **acosf**, **acosl**|\<Math.h >|\<errno.h >|

## <a name="example"></a>Örnek

Bu program aralık 1 -1 değeri ister. Bu aralığın dışında kalan giriş değerleri üretmek **_domaın** hata iletileri. Geçerli bir değer girilmezse, program arksinüsünü ve bu değeri arkkosinüsünü yazdırır.

```C
// crt_asincos.c
// arguments: 0

#include <math.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int ac, char* av[] )
{
    double  x,
            y;
    errno_t err;

    // argument checking
    if (ac != 2)
    {
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",
                   av[0]);
        return 1;
    }

    // Convert argument into a double value
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)
    {
        fprintf_s( stderr, "Error converting argument into ",
                   "double value.\n");
        return 1;
    }

    // Arcsine of X
    y = asin( x );
    printf_s( "Arcsine of %f = %f\n", x, y );

    // Arccosine of X
    y = acos( x );
    printf_s( "Arccosine of %f = %f\n", x, y );
}
```

```Output
Arcsine of 0.000000 = 0.000000
Arccosine of 0.000000 = 1.570796
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[Sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[Bronz, tanf, tanl](tan-tanf-tanl.md)<br/>