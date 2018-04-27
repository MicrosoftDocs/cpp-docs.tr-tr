---
title: cos, cosf, cosl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- cos
- cosf
- cosl
apilocation:
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
apitype: DLLExport
f1_keywords:
- cos
- cosf
- cosl
dev_langs:
- C++
helpviewer_keywords:
- cosines
- cosl function
- calculating cosine
- cosf function
- cos function
- trigonometric functions
- cosines, calculating
ms.assetid: ae90435e-6b68-4a47-a81f-be87d5c08f16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3c93d9abe3b78a34f357f9418b5d27413f2ca4d0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="cos-cosf-cosl"></a>cos, cosf, cosl

Kosinüsünü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
double cos( double x );
float cosf( float x );
long double cosl( long double x );
```

```cpp
float cos( float x );  // C++ only
long double cos( long double x );  // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Radyan cinsinden açı.

## <a name="return-value"></a>Dönüş Değeri

Kosinüsünü *x*. Varsa *x* büyük veya 263 eşit veya daha az veya buna eşit -263, sonuç anlamlı kaybı oluşur.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± QNAN, UL|yok|**_DOMAIN**|
|± INF|**GEÇERSİZ**|**_DOMAIN**|

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **cos** alın ve dönüş **float** veya **uzun** **çift** değerleri. Bir C programı **cos** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli C üstbilgisi|Gerekli C++ üstbilgisi|
|-------------|---------------------|-|
|**cos**, **cosh**, **cosf**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bkz [sin, sinf, sinl](sin-sinf-sinl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[_matherr](matherr.md)<br/>
[Sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[Bronz, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIcos](../../c-runtime-library/cicos.md)<br/>