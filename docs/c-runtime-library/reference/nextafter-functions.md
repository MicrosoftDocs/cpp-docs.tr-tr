---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
description: Nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, NexTTo, nexttowardf ve nexttowardl; için API başvurusu bir sonraki gösterilemeyen kayan nokta değeri döndürür.
ms.date: 9/1/2020
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
- _o__nextafter
- _o_nextafter
- _o_nextafterf
- _o_nextafterl
- _o_nexttoward
- _o_nexttowardf
- _o_nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
ms.openlocfilehash: cdcfb1a1d0bf1523a0252d779dba603ce1814b14
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555832"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

Sonraki gösterilemeyen kayan noktalı değeri döndürür.

## <a name="syntax"></a>Söz dizimi

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

#define nextafter(X, Y) // Requires C11 or higher

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );

#define nexttoward(X, Y) // Requires C11 or higher

float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>Parametreler

*sayı*\
Başlangıçtan başlamak için kayan nokta değeri.

*Iz*\
Doğru gidilecek kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

*Y*yönünde *x* öğesinden sonra dönüş türünün sonraki gösterilemeyen kayan nokta değerini döndürür. *X* ve *y* eşitse, işlev bir özel durum Tetiklenmeyen, dönüş türüne dönüştürülmüş *y*döndürür. *X* *y*'ye eşit değilse ve sonuç bir denormal veya sıfır ise, **FE_UNDERFLOW** ve **FE_INEXACT** kayan nokta özel durum durumları ayarlanır ve doğru sonuç döndürülür. *X* veya *y* bir NaN ise, dönüş değeri, giriş nans 'lardan biridir. *X* sınırlı ise ve sonuç türden sonsuz veya gösterilemeyen bir tablo değilse, doğru imzalı bir sonsuz veya NaN döndürülür, **FE_OVERFLOW** ve **FE_INEXACT** kayan nokta özel durum durumları ayarlanır ve **errno** , **ERANGE**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

*Y*parametre türü dışında, **nextafter** ve **NexTTo** işlev aileleri eşdeğerdir. *X* ve *y* eşitse, döndürülen değer *y* , dönüş türüne dönüştürülür.

C++ aşırı yüklemeye izin verdiğinden, Eğer eklerseniz, \<cmath> Bu return ve türlerine doğru **nextafter** ve **nextaşırı** yüklerini **`float`** çağırabilirsiniz **`long double`** . C programında, \<tgmath.h> Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **nextafter** ve **nexther** zaman dönüşü **`double`** .

\<tgmath.h> `nextafter()` Veya `nexttoward()` makrosunu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

**_Nextafter** ve **_nextafterf** işlevleri Microsoft 'a özgüdür. **_Nextafterf** işlevi yalnızca x64 için derlerken kullanılabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nextnext**, **nexttowardf**, **nexttowardl**|\<math.h>|\<math.h> veya \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> veya \<cfloat>|
|**nextafter** makrosu, bir makroya **doğru Next**| \<tgmath.h> ||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)
