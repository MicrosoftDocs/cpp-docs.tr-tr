---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs:
- C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c68d039ff1318ea082d409078a55c8d337a48de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

Sonraki gösterilebilir kayan nokta değeri döndürür.

## <a name="syntax"></a>Sözdizimi

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );
```

```cpp
float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Başlamak için kayan nokta değeri.

*Y*<br/>
Doğru gitmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

Dönüş türü sonra sonraki gösterilebilir kayan nokta değerini döndürür *x* yönünde *y*. Varsa *x* ve *y* işlevi döndürür eşit olup olmadığını *y*, dönüş türüyle tetiklenen durum dönüştürülür. Varsa *x* eşit değil *y*, ve sonucu bir denormal veya sıfır **FE_UNDERFLOW** ve **FE_INEXACT** kayan nokta özel durumları ayarlanmış olan ve doğru bir sonuç döndürdü. Her iki *x* veya *y* dönüş değeri giriş NaN biri bir NAN olduğundan. Varsa *x* sınırlıdır ve sonucu sonsuz veya türünde gösterilebilir değil, doğru şekilde imzalanmış sonsuz veya NAN döndürülür, **FE_OVERFLOW** ve **FE_INEXACT** kayan nokta özel durumları olarak ayarlanır ve **errno** ayarlanır **ERANGE**.

## <a name="remarks"></a>Açıklamalar

**Nextafter** ve **nexttoward** işlevi aileleri dışında parametre türü eşdeğer *y*. Varsa *x* ve *y* döndürülen değer eşit olan *y* dönüş türüne dönüştürülemiyor.

Aşırı yüklemesi, C++ dahil ederseniz izin verdiğinden \<cmath > aşırı çağırabilirsiniz **nextafter** ve **nexttoward** bu iade **float** ve **uzun** **çift** türleri. Bir C programı **nextafter** ve **nexttoward** her zaman geri **çift**.

**_Nextafter** ve **_nextafterf** Microsoft belirli işlevlerdir. **_Nextafterf** işlevi yalnızca kullanılabilir x64 için derlerken.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf** , **nexttowardl**|\<Math.h >|\<Math.h > veya \<cmath >|
|**_nextafter**|\<float.h >|\<float.h > veya \<cfloat >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
