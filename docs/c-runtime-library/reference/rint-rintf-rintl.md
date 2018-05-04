---
title: Yazdır, rintf, rintl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- rintf
- rintl
- rint
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
- rintf
- rintl
- rint
dev_langs:
- C++
helpviewer_keywords:
- rintf function
- rint function
- rintl function
ms.assetid: 312ae3e6-278c-459a-9393-11b8f87d9184
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 784a540982c41ba7aa144559d3846746b59481f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="rint-rintf-rintl"></a>rint, rintf, rintl

Kayan nokta değeri kayan nokta biçiminde en yakın tamsayıya yuvarlar.

## <a name="syntax"></a>Sözdizimi

```C
double rint( double x );
float rintf( float x );
long double rintl( long double x );
```

```cpp
float rint( float x );  // C++ only
long double rint( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Yuvarlanacak kayan nokta değer.

## <a name="return-value"></a>Dönüş Değeri

**Azdır** işlevler en yakın tamsayıya temsil eden bir kayan nokta değer döndürmek *x*. Kayan nokta yuvarlama modu, aynı geçerli ayarına göre yarısı değerleri yuvarlanır **nearbyint** işlevleri. Farklı **nearbyint** İşlevler, **azdır** işlevleri Yükselt **FE_INEXACT** bağımsız değişken değeri sonucu farklıysa, kayan nokta özel durumu. Döndürülen hata yoktur.

|Giriş|SEH özel durumu|**_matherr** özel durumu|
|-----------|-------------------|--------------------------|
|± ∞, QNAN, UL|yok|yok|
|Denormals|EXCEPTION_FLT_UNDERFLOW|yok|

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **azdır** alın ve dönüş **float** ve **uzun** **çift** değerleri. Bir C programı **azdır** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**Yazdır**, **rintf**, **rintl**|\<Math.h >|\<cmath >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_rint.c
// Build with: cl /W3 /Tc crt_rint.c
// This example displays the rounded results of
// the floating-point values 2.499999, -2.499999,
// 2.8, -2.8, 2.5 and -2.5.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.499999;
   float y = 2.8f;
   long double z = 2.5;

   printf("rint(%f) is %.0f\n", x, rint (x));
   printf("rint(%f) is %.0f\n", -x, rint (-x));
   printf("rintf(%f) is %.0f\n", y, rintf(y));
   printf("rintf(%f) is %.0f\n", -y, rintf(-y));
   printf("rintl(%Lf) is %.0Lf\n", z, rintl(z));
   printf("rintl(%Lf) is %.0Lf\n", -z, rintl(-z));
}
```

```Output
rint(2.499999) is 2
rint(-2.499999) is -2
rintf(2.800000) is 3
rintf(-2.800000) is -3
rintl(2.500000) is 3
rintl(-2.500000) is -3
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
[lround, lroundf, lroundl, llround, llroundf, llroundl](lround-lroundf-lroundl-llround-llroundf-llroundl.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[Yazdır](rint-rintf-rintl.md)<br/>