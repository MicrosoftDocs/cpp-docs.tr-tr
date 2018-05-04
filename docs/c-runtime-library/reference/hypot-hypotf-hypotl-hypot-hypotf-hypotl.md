---
title: hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _hypotf
- hypot
- hypotf
- _hypot
- _hypotl
- hypotl
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
- hypotf
- hypotl
- _hypotl
- hypot
- _hypot
- _hypotf
dev_langs:
- C++
helpviewer_keywords:
- hypotenuse calculation
- hypot function
- hypotf function
- triangles, calculating hypotenuse
- hypotl function
- calculating hypotenuses
- _hypot function
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a8488b160c10eb29f0448127c44d3514f8debf3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="hypot-hypotf-hypotl-hypot-hypotf-hypotl"></a>hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl

Hipotenüsü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double hypot(
   double x,
   double y
);
float hypotf(
   float x,
   float y
);
long double hypotl(
   long double x,
   long double y
);
double _hypot(
   double x,
   double y
);
float _hypotf(
   float x,
   float y
);
long double _hypotl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parametreler

*x*, *y*<br/>
Kayan nokta değerleri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **hypot** hipotenüsü; taşmaya uzunluğunu döndürür **hypot** INF (sonsuz) döndürür ve **errno** değişken ayarlandığında **ERANGE** . Kullanabileceğiniz **_matherr** hata işleme değiştirmek için.

Dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Hypot** işlevler hesapla iki kenara uzunluğu belirtilen bir sağ üçgen hipotenüsü uzunluğu *x* ve *y* (diğer bir deyişle, kare kökünü *x*<sup>2</sup> + *y*<sup>2</sup>).

Önde gelen alt çizgi olan işlevler sürümleri önceki standartları ile uyumluluk için sağlanır. Davranışlarını başında alt çizgi sahip olmayan sürümleri için aynıdır. Önde gelen alt çizgi olmadan sürümleri için yeni kod kullanmanızı öneririz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**hypot**, **hypotf**, **hypotl**, **_hypot**, **_hypotf**, **_hypotl**|\<Math.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_hypot.c
// This program prints the hypotenuse of a right triangle.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 3.0, y = 4.0;

   printf( "If a right triangle has sides %2.1f and %2.1f, "
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );
}
```

```Output
If a right triangle has sides 3.0 and 4.0, its hypotenuse is 5.0
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_cabs](cabs.md)<br/>
[_matherr](matherr.md)<br/>