---
title: frexp, frexpf, frexpl
ms.date: 04/05/2018
apiname:
- frexp
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
- frexp
- _frexpl
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
ms.openlocfilehash: c9e259f730d2d63d07032735be930f6f0fdb17e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332981"
---
# <a name="frexp-frexpf-frexpl"></a>frexp, frexpf, frexpl

Mantis ve kayan noktalı bir sayı alır.

## <a name="syntax"></a>Sözdizimi

```C
double frexp(
   double x,
   int *expptr
);
float frexpf(
   float x,
   int * expptr
);
long double frexpl(
   long double x,
   int * expptr
);
float frexp(
   float x,
   int * expptr
);  // C++ only
long double frexp(
   long double x,
   int * expptr
);  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta değeri.

*expptr*<br/>
Saklı tamsayı üs için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**frexp** Mantis döndürür. Varsa *x* 0 ise, işlev hem Mantis ve üs için 0 değerini döndürür. Varsa *expptr* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Frexp** işlevi kayan nokta değeri keser (*x*) içine bir Mantis (*m*) ve bir üs (*n*) gibi mutlak değerini *m* büyüktür veya eşittir 0,5 ve az 1.0 ve *x* = *m* * 2<sup>*n*</sup>. Tamsayı üs *n* tarafından işaret edilen konumda depolanır *expptr*.

C++ sağlar aşırı yüklemesi, aşırı yüklemesini çağırabilirsiniz **frexp**. C programında **frexp** her zaman alan bir **çift** ve **int** işaretçi ve döndürür bir **çift**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**frexp**, **frexpf**, **frexpl**|\<Math.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_frexp.c
// This program calculates frexp( 16.4, &n )
// then displays y and n.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y;
   int n;

   x = 16.4;
   y = frexp( x, &n );
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );
}
```

```Output
frexp( 16.400000, &n ) = 0.512500, n = 5
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
