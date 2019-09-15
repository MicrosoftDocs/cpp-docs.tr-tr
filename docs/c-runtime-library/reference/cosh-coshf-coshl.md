---
title: cosh, coshf, coshl
ms.date: 04/11/2018
api_name:
- cosh
- coshf
- coshl
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: 446988e67ca6e3b4a3839a9336f1ea4e2755c124
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938992"
---
# <a name="cosh-coshf-coshl"></a>cosh, coshf, coshl

Hiperbolik kosinüsü hesaplar.

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

*x*<br/>
Radyan cinsinden açı.

## <a name="return-value"></a>Dönüş Değeri

*X*'in hiperbolik kosinüsü.

Varsayılan olarak, sonuç bir **cosh**, **coshf**veya **coshl** çağrısında çok büyükse, işlev **HUGE_VAL** döndürür ve **errno** 'ı **ERANGE**olarak ayarlar.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|yok|**_ETKI ALANI**|
|*x* ≥ 7.104760 e + 002|**TAM**TAŞMA+|**TAŞMA**|

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** veya **Long** **Double** değerleri alıp döndüren **cosh** aşırı yüklerini çağırabilirsiniz. C programında, **cosh** her zaman bir **Double**alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgiC++()|
|-------------|---------------------|-|
|**coshf**, **COSL**, **coshl**|\<Math. h >|\<cmath > veya \<Math. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)içindeki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
