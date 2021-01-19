---
title: logb, logbf, logbl, _logb, _logbf
description: Logb, logbf, logbl, _logb ve _logbf için API başvurusu bir kayan nokta bağımsız değişkeninin üs değerini çıkaran.
ms.date: 1/15/2021
api_name:
- logb
- _logb
- _logbl
- logbf
- _logbf
- logbl
- _o__logb
- _o_logb
- _o_logbf
- _o_logbl
- _o__logbf
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
- logb
- logbl
- _logb
- _logbf
- logbf
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.openlocfilehash: 5d64b315a502f7d1794d7726f14a94ed66a67cd5
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98564036"
---
# <a name="logb-logbf-logbl-_logb-_logbf"></a>`logb`, `logbf`, `logbl`, `_logb`, `_logbf`

Kayan nokta bağımsız değişkeninin üs değerini ayıklar.

## <a name="syntax"></a>Sözdizimi

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
#define logb(X) // Requires C11 or higher
```

### <a name="parameters"></a>Parametreler

*`x`*\
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**`logb`***`x`* kayan noktalı değer olarak temsil edilen işaretli bir tamsayı olarak taraflı olmayan üs değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**`logb`** İşlevleri *`x`* , *`x`* sonsuz aralıkla temsil edilen kayan nokta bağımsız değişkeninin üstel değerini ayıklar. Bağımsız değişken *`x`* normalleştirilmiş ise, normalleştirilmiş gibi davranır.

C++ aşırı yüklemeye izin verdiğinden, **`logb`** alan veya değer alma ve döndürme yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, `<tgmath.h>` Bu işlevi çağırmak için makroyu kullanmadığınız müddetçe, **`logb`** her zaman bir alır ve döndürür **`double`** .

`<tgmath.h>` `logb()` Makroyu kullanırsanız, bağımsız değişkenin türü, işlevin hangi sürümünün seçili olduğunu belirler. Ayrıntılar için bkz. [tür-genel matematik](../../c-runtime-library/tgmath.md) .

|Giriş|SEH özel durumu|`Matherr` duruma|
|-----------|-------------------|-----------------------|
|`± QNAN`,`IND`|Yok|`_DOMAIN`|
|± 0|`ZERODIVIDE`|`_SING`|

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`_logb`**|`<float.h>`|
|**`logb`**, **`logbf`**, **`logbl`**, **`_logbf`**|`<math.h>`|
|**`logb`** makroya | `<tgmath.h>` |

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`frexp`](frexp.md)