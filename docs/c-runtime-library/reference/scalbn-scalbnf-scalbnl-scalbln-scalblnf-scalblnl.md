---
title: scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
ms.date: 04/05/2018
api_name:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
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
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
ms.openlocfilehash: 794d0bdceb13aafb83de85fb29e47a4fa3125cd6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948909"
---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl

Kayan noktalı sayıyı FLT_RADIX 'in tam sayı gücüyle çarpar.

## <a name="syntax"></a>Sözdizimi

```C
double scalbn(
   double x,
   int exp
);
float scalbn(
   float x,
   int exp
);  // C++ only
long double scalbn(
   long double x,
   int exp
);  // C++ only
float scalbnf(
   float x,
   int exp
);
long double scalbnl(
   long double x,
   int exp
);
double scalbln(
   double x,
   long exp
);
float scalbln(
   float x,
   long exp
);  // C++ only
long double scalbln(
   long double x,
   long exp
);  // C++ only
float scalblnf(
   float x,
   long exp
);
long double scalblnl(
   long double x,
   long exp
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta değeri.

*exp*<br/>
Tamsayı üs.

## <a name="return-value"></a>Dönüş Değeri

**Scalbümn** işlevleri başarılı olduğunda *x* \* **FLT_RADIX**<sup>Exp</sup> değerini döndürür. Taşma durumunda ( *x*işaretine bağlı olarak), **scalbümn** +/- **HUGE_VAL**; döndürür **errno** değeri **ERANGE**olarak ayarlanır.

**Errno** ve olası hata dönüş değerleri hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**FLT_RADIX** , \<float. h >, ikili sistemlerde yerel kayan nokta Radix; olarak tanımlanır; 2 değeri vardır ve **scalbümn** , [ldexp](ldexp.md)ile eşdeğerdir.

Aşırı C++ yüklemeye izin verdiğinden, **float** veya **Long** **Double** türlerini alıp döndüren **scalbümn** ve **scalbln** aşırı yüklerini çağırabilirsiniz. C programında, **scalbümn** her zaman bir **Double** ve **int** alır ve bir **Double**döndürür ve **scalbln** her zaman **çift** ve **uzun** sürer ve bir **Double**döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**scalbümn**, **scalbümnf**, **scalbümnl**, **scalbln**, **scalblnf**, **scalblnl**|\<Math. h >|\<cmath >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_scalbn.c
// Compile using: cl /W4 crt_scalbn.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 6.4, y;
   int p = 3;

   y = scalbn( x, p );
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );
}
```

### <a name="output"></a>Çıkış

```Output
6.4 times FLT_RADIX to the power of 3 is 51.2
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
