---
title: cosh, coshf, coshl
ms.date: 4/2/2020
api_name:
- cosh
- coshf
- coshl
- _o_cosh
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: d7d2050be406e7f2be66ca200d1e3cfd9c2960b0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348439"
---
# <a name="cosh-coshf-coshl"></a>cosh, coshf, coshl

Hiperbolik kosinüshesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double cosh( double x );
float coshf( float x );
long double coshl( long double x );
```

```cpp
float cosh( float x );  // C++ only
long double cosh( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Radyanlarda açı.

## <a name="return-value"></a>Dönüş Değeri

*X*hiperbolik kosinüs .

Varsayılan olarak, sonuç bir **cosh**, **coshf**veya **coshl** arama çok büyükise, fonksiyon **HUGE_VAL** döndürür ve **ERANGE** **için errno** ayarlar.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|yok|**_DOMAIN**|
|*x* ≥ 7.104760e+002|**TAM OLMAYAN**+**TAŞMA**|**Taşma**|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** veya **uzun** **çift** değerleri alan ve döndüren aşırı **cosh** yüklerini arayabilirsiniz. Bir C programında, **cosh** her zaman alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgi (C)|Gerekli üstbilgi (C++)|
|-------------|---------------------|-|
|**coşf**, **cosl**, **coshl**|\<math.h>|\<cmath> \<veya math.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)örneğine bakın .

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
