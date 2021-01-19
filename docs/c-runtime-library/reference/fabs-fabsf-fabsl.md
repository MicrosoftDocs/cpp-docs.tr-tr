---
title: fabs, fabsf, fabsl
description: Fabs, fabsf ve fabsl; için API başvurusu bir kayan nokta değerinin mutlak değerini hesaplar.
ms.date: 1/15/2021
api_name:
- fabsf
- fabs
- fabsl
- _o_fabs
- _o_fabsf
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
- fabs
- fabsf
- fabsl
- "math\fabs"
- "math\fabsf"
- "math\fabsl"
helpviewer_keywords:
- absolute values
- fabsf function
- calculating absolute values
- fabs function
- fabsl function
ms.openlocfilehash: 453965b846dff9affb3fa6dce99ea8b6189a5d6c
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563945"
---
# <a name="fabs-fabsf-fabsl"></a>`fabs`, `fabsf`, `fabsl`

Kayan nokta bağımsız değişkeninin mutlak değerini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double fabs(
   double x
);
float fabs(
   float x
); // C++ only
long double fabs(
   long double x
); // C++ only
float fabsf(
   float x
);
long double fabsl(
   long double x
);

#define fabs(X) // Requires C11 or higher
```

### <a name="parameters"></a>Parametreler

*`x`*\
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**`fabs`** İşlevler *x* bağımsız değişkeninin mutlak değerini döndürür. Hata döndürme yok.

|Giriş|SEH özel durumu|`Matherr` duruma|
|-----------|-------------------|-----------------------|
|± `QNAN`,`IND`|yok|`_DOMAIN`|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, üstbilgiyi dahil ediyorsanız aşırı yüklerini çağırabilirsiniz **`fabs`** `<cmath>` . C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **`fabs`** her zaman bir alır ve döndürür **`double`** .

`<tgmath.h>` `fabs()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|--------------|-----------------------|---------------------------|
|**`fabs`**, **`fabsf`**, **`fabsl`**|`<math.h>`|`<cmath>` veya `<math.h>`|
|**`fabs`** makroya | `<tgmath.h>` ||

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

İçin örneğe bakın [`abs`](abs-labs-llabs-abs64.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`abs, labs, llabs, _abs64`](abs-labs-llabs-abs64.md)\
[`_cabs`](cabs.md)
