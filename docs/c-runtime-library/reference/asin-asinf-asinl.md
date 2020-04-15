---
title: asin, asinf, asinl
ms.date: 4/2/2020
api_name:
- asinf
- asinl
- asin
- _o_asin
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
ms.openlocfilehash: 424fee6995fae4a7f878054ede1bb85d33d1706d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334123"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

Arcsine hesaplar.

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

*X*<br/>
Arcsine hesaplanacak değer.

## <a name="return-value"></a>Dönüş Değeri

**Asin** fonksiyonu x'in (ters sinüs fonksiyonu) *x* -π/2 ile π/2 radyanaralığında ki arcsine (ters sinüs fonksiyonu) döndürür.

Varsayılan olarak, *x* -1'den küçük veya 1'den büyükse, **asin** belirsiz bir şekilde döndürür.

|Girdi|SEH Özel Durumu|Matherr İstisnası|
|-----------|-------------------|-----------------------|
|± ∞|**Geçersiz**|**_DOMAIN**|
|± **QNAN**, **IND**|yok|**_DOMAIN**|
|&#124;x&#124;>1|**Geçersiz**|**_DOMAIN**|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **float** ve **uzun** **çift** değerleri ile aşırı **asin** yükleri arayabilirsiniz. Bir C programında, **asin** her zaman alır ve bir **çift**döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgi (C)|Gerekli üstbilgi (C++)|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<math.h>|\<cmath> \<veya math.h>|

## <a name="example"></a>Örnek

Daha fazla bilgi için, [acos, acosf, acosl](acos-acosf-acosl.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
