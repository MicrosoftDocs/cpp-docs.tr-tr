---
title: asin, asinf, asinl
ms.date: 04/05/2018
api_name:
- asinf
- asinl
- asin
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
ms.openlocfilehash: 1e70c9b2187b97d3dea589c1757081da8bf2bd10
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943645"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

Arksinüsü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
```

```cpp
float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Arksinüsü hesaplanacak olan değer.

## <a name="return-value"></a>Dönüş Değeri

**Asin** işlevi,-π/2 ile π/2 radyan aralığında *x* 'in ark sinüsünü (ters sinüs işlevi) döndürür.

Varsayılan olarak, *x* -1 ' den küçük veya 1 ' den büyükse, **asin** sonsuz döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± ∞|**GEÇERSİZ**|**_ETKI ALANI**|
|± **QNAN**, **IND**|yok|**_ETKI ALANI**|
|&#124;x&#124;>1|**GEÇERSİZ**|**_ETKI ALANI**|

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **float** ve **Long** **Double** değerleri ile **asin** aşırı yüklerini çağırabilirsiniz. C programında, **asin** her zaman bir **Double**alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgiC++()|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<Math. h >|\<cmath > veya \<Math. h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [acos, acosf, acosl](acos-acosf-acosl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
