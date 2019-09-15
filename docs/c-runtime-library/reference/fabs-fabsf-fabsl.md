---
title: fabs, fabsf, fabsl
ms.date: 04/05/2018
api_name:
- fabsf
- fabs
- fabsl
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
ms.openlocfilehash: 155b0e4ced7eb4ea0ade5445a62fc385f0c157e9
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941489"
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

*x*<br/>
Kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**Fabs** işlevleri *x*bağımsız değişkeninin mutlak değerini döndürür. Hata döndürme yok.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± QNAN, IND|yok|_DOMAIN|

## <a name="remarks"></a>Açıklamalar

C++aşırı yüklemeye izin verir, böylece \<cmath > üst bilgisini dahil ediyorsanız **fabs** aşırı yüklerini çağırabilirsiniz. C programında **fabs** her zaman bir **Double**alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli C üstbilgisi|Gerekli C++ üst bilgi|
|--------------|-----------------------|---------------------------|
|**fabs**, **fabsf**, **fabsl**|\<Math. h >|\<cmath > veya \<Math. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[ABS](abs-labs-llabs-abs64.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
