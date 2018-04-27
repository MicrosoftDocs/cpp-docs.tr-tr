---
title: asin, asinf, asinl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6dd1399042e1055d124cd3c53363a6979d4256d3
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

Arksinüsünü hesaplar.

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
Hesaplanacak olan arksinüsünü olduğu değeri.

## <a name="return-value"></a>Dönüş Değeri

**Asin** işlevi (ters sinüsünü işlevi) sinüsünü döndürür *x* π/2 radyan için aralığı - π/2.

Varsayılan olarak, varsa *x* -1 veya 1 ' den büyük küçük **asin** bir belirsiz döndürür.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± ∞|**GEÇERSİZ**|**_DOMAIN**|
|± **QNAN**, **UL**|yok|**_DOMAIN**|
|&#124;x&#124;>1|**GEÇERSİZ**|**_DOMAIN**|

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **asin** ile **float** ve **uzun** **çift** değerleri. Bir C programı **asin** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<Math.h >|\<cmath > veya \<math.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz: [acos, acosf, acosl](acos-acosf-acosl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[Sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[Bronz, tanf, tanl](tan-tanf-tanl.md)<br/>
