---
title: fabs, fabsf, fabsl
ms.date: 4/2/2020
api_name:
- fabsf
- fabs
- fabsl
- _o_fabs
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
- api-ms-win-crt-private-l1-1-0
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
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
ms.openlocfilehash: 38648f2108b5202cbb355da3abab9e7dedf4dc47
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347547"
---
# <a name="fabs-fabsf-fabsl"></a>fabs, fabsf, fabsl

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
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Fabs** işlevleri *x*bağımsız değişkeninin mutlak değerini döndürer. Hata iadesi yok.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± QNAN,IND|yok|_DOMAIN|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verir, böylece cmath> \<üstbilgisini **eklerseniz** aşırı fabs yükleri çağırabilirsiniz. Bir C programında, **fabs** her zaman alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgi|Gerekli C++ üstbilgi|
|--------------|-----------------------|---------------------------|
|**fabs**, **fabsf**, **fabsl**|\<math.h>|\<cmath> \<veya math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Abs](abs-labs-llabs-abs64.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
