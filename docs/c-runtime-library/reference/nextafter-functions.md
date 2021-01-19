---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
description: Nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, NexTTo, nexttowardf ve nexttowardl; için API başvurusu bir sonraki gösterilemeyen kayan nokta değeri döndürür.
ms.date: 1/15/2021
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
- _o__nextafterf
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
ms.openlocfilehash: 664ddb204fa089f83acebf6a9042b17a776ea306
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564140"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>`nextafter`, `nextafterf`, `nextafterl`, `_nextafter`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`

Sonraki gösterilemeyen kayan noktalı değeri döndürür.

## <a name="syntax"></a>Sözdizimi

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

*`x`*\
Başlangıçtan başlamak için kayan nokta değeri.

*`y`*\
Doğru gidilecek kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

Yönü sonrasında dönüş türünün sonraki gösterilemeyen kayan nokta değerini döndürür *`x`* *`y`* . *`x`* Ve *`y`* eşitse, işlev, *`y`* hiçbir özel durum Tetiklenmeyen dönüş türüne dönüştürülür. *`x`* Değerine eşit değilse *`y`* ve sonuç bir denormal veya sıfır ise, **`FE_UNDERFLOW`** ve **`FE_INEXACT`** kayan nokta özel durum durumları ayarlanır ve doğru sonuç döndürülür. Ya da *`x`* *`y`* bir NaN ise, dönüş değeri giriş nans 'lardan biridir. *`x`* Sonlu ise ve sonuç tür içinde sonsuz veya gösterilemeyen bir tablo değilse, doğru bir işaretli sonsuzluk veya NaN döndürülür, **`FE_OVERFLOW`** ve **`FE_INEXACT`** kayan nokta özel durum durumları ayarlanır ve **`errno`** olarak ayarlanır **`ERANGE`** .

## <a name="remarks"></a>Açıklamalar

**`nextafter`** Ve **`nexttoward`** işlev aileleri, parametre türü hariç eşdeğerdir *`y`* . *`x`* Ve *`y`* eşitse, döndürülen değer *`y`* dönüş türüne dönüştürülür.

C++ aşırı yüklemeye izin verdiğinden, eklerseniz ve `<cmath>` **`nextafter`** **`nexttoward`** Bu döndürme ve türleri içeren aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız **`nextafter`** ve **`nexttoward`** her zaman döndüren **`double`** .

`<tgmath.h>` `nextafter()` Veya `nexttoward()` makrosunu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

**_Nextafter** ve **_nextafterf** işlevleri Microsoft 'a özgüdür. **_Nextafterf** işlevi yalnızca x64 için derlerken kullanılabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------------|-------------------------------|
|**`nextafter`**, **`nextafterf`**, **`nextafterl`**, **`_nextafterf`**, **`nexttoward`**, **`nexttowardf`**, **`nexttowardl`**|`<math.h>`|`<math.h>` veya `<cmath>`|
|**`_nextafter`**|`<float.h>`|`<float.h>` veya `<cfloat>`|
|**`nextafter`** makro,  **`nexttoward`** makro| `<tgmath.h>` ||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`isnan`, `_isnan`, `_isnanf`](isnan-isnan-isnanf.md)
