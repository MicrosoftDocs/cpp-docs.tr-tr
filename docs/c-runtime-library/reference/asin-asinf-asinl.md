---
title: asin, asinf, asinl
ms.date: 04/05/2018
apiname:
- asinf
- asinl
- asin
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
ms.openlocfilehash: 20a2ffc37ea666207b9558cb5c282c414cfd4838
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476056"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

Ark sinüsünü hesaplar.

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

**Asin** işlevi döndürür (ters sinüsünü işlevi) sinüsünü *x* π/2 radyan için aralığı - π/2.

Varsayılan olarak, *x* -1'den küçük veya 1 ' den büyük olan **asin** bir sonsuz döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± ∞|**GEÇERSİZ**|**_ETKİ ALANI**|
|± **QNAN**, **ONRAKİNİ BUL**|yok|**_ETKİ ALANI**|
|&#124;x&#124;>1|**GEÇERSİZ**|**_ETKİ ALANI**|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **asin** ile **float** ve **uzun** **çift** değerleri. C programında **asin** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık (C)|Gerekli başlık (C++)|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<Math.h >|\<cmath > veya \<math.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için [acos, acosf, acosl](acos-acosf-acosl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
