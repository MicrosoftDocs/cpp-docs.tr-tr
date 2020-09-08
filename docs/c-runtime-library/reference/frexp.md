---
title: frexp, frexpf, frexpl
description: Frexp, frexpf ve frexpl için API başvurusu; bir kayan noktalı sayının Mantis ve üstürünü alır.
ms.date: 9/1/2020
api_name:
- frexp
- _o_frexp
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: a23de4160abcfab2518125bfa0fd35a389901674
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555754"
---
# <a name="frexp-frexpf-frexpl"></a>frexp, frexpf, frexpl

Kayan noktalı sayının Mantis ve üstürünü alır.

## <a name="syntax"></a>Söz dizimi

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
#define frexpl(X, INT_PTR) // Requires C11 or higher
```

```cpp
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

*sayı*\
Kayan nokta değeri.

*expptr*\
Depolanan tamsayı üs işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

**frexp** , Mantis döndürür. *X* 0 ise, işlev hem Mantis hem de üs için 0 döndürür. *Expptr* **null**ise, geçersiz parametre işleyicisi [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Frexp** işlevi kayan nokta değerini (*x*) bir Mantis (*e*) ve üs (*n*) olarak ayırır; Örneğin, sıfırdan büyük değer *0,5, 1,0* ' den küçük ve *x*  =  *e* * 2<sup>*n*</sup>. Tamsayı üssü *n* , *expptr*tarafından işaret edilen konumda depolanır.

C++ aşırı yüklemeye izin verdiğinden, **frexp**aşırı yüklerini çağırabilirsiniz. C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **frexp** her zaman bir **`double`** ve bir işaretçi alır **`int`** ve döndürür **`double`** .

\<tgmath.h> `frexp()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**frexp**, **frexpf**, **frexpl**|\<math.h>|
|**frexp** makrosu | \<tgmath.h> |

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

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
