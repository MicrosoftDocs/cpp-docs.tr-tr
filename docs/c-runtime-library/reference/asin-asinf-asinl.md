---
title: asin, asinf, asinl
description: Asin, asinf ve asinl; için API başvurusu bir kayan nokta değerinin arksinüsünü hesaplar.
ms.date: 1/15/2021
api_name:
- asinf
- asinl
- asin
- _o_asin
- _o_asinf
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.openlocfilehash: 04b68e9b5933d763cecbdc06af3e34a5b7c01223
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564049"
---
# <a name="asin-asinf-asinl"></a>`asin`, `asinf`, `asinl`

Arksinüsü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
#define asin(X) // Requires C11 or higher

float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*`x`*\
Arksinüsü hesaplanacak olan değer.

## <a name="return-value"></a>Dönüş Değeri

**`asin`** İşlevi, *`x`* -π/2 ile π/2 radyan aralığında Ark sinüsü (ters sinüs işlevi) döndürür.

Varsayılan olarak, *`x`* -1 ' den küçük veya 1 ' den büyükse, **`asin`** sonsuz döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± ∞|**`INVALID`**|**`_DOMAIN`**|
|± **`QNAN`**, **`IND`**|yok|**`_DOMAIN`**|
|&#124;x&#124;>1|**`INVALID`**|**`_DOMAIN`**|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **`asin`** ve değerlerini içeren aşırı yüklerini **`float`** çağırabilirsiniz **`long double`** . C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **`asin`** her zaman bir alır ve döndürür **`double`** .

`<tgmath.h>` `asin()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------|-|
|**`asin`**, **`asinf`**, **`asinl`**|`<math.h>`|`<cmath>` veya `<math.h>`|
|**`asin()`** makroya | `<tgmath.h>` ||

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz., [ `acos` `acosf` , `acosl` ](acos-acosf-acosl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`acos`, `acosf`, `acosl`](acos-acosf-acosl.md)\
[`atan`, `atanf`, `atanl`, `atan2`, `atan2f`, `atan2l`](atan-atanf-atanl-atan2-atan2f-atan2l.md)\
[`cos`, `cosf`, `cosl`](cos-cosf-cosl.md)\
[`_matherr`](matherr.md)\
[`sin`, `sinf`, `sinl`](sin-sinf-sinl.md)\
[`tan`, `tanf`, `tanl`](tan-tanf-tanl.md)