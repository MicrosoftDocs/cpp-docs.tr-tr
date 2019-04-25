---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 04/05/2018
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
ms.openlocfilehash: 0e0a60dc9f7c068d8c18c10f3c6b819b9e06d3b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156193"
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

Gösterilebilir sıradaki kayan nokta değeri döndürür.

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

Dönüş türü sonra sonraki gösterilebilir kayan nokta değeri döndürür *x* yönünde *y*. Varsa *x* ve *y* işlevi döndürür eşit olup olmadığını *y*, hiçbir özel durum harekete dönüş türüyle dönüştürülür. Varsa *x* eşit değildir *y*, ve sonucu bir denormal veya sıfır olan **FE_UNDERFLOW** ve **FE_INEXACT** kayan nokta özel durumları ayarlanır, ve doğru bir sonuç döndürdü. Ya da *x* veya *y* dönüş değeri bir giriş NaN'ler ise bir NAN olup. Varsa *x* sınırlıdır ve sonucu sonsuz veya türü içinde gösterilebilir değil, doğru şekilde imzalanmış sonsuz veya NAN döndürülür, **FE_OVERFLOW** ve **FE_INEXACT** kayan nokta özel durumlarını ayarlanır ve **errno** ayarlanır **ERANGE**.

## <a name="remarks"></a>Açıklamalar

**Nextafter** ve **nexttoward** dışında parametre türü, eşdeğer işlev aileleri *y*. Varsa *x* ve *y* döndürülen değer eşit olan *y* dönüş türüne dönüştürülür.

Aşırı yükleme, C++ eklerseniz izin verdiğinden \<cmath > aşırı yüklemesini çağırabilirsiniz **nextafter** ve **nexttoward** döndüren **float** ve **uzun** **çift** türleri. C programında **nextafter** ve **nexttoward** her zaman dönüş **çift**.

**_Nextafter** ve **_nextafterf** Microsoft'a özgü işlevlerdir. **_Nextafterf** işlevi, yalnızca kullanılabilir x64 için derleme yaparken.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık (C)|Gerekli başlık (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf** , **nexttowardl**|\<Math.h >|\<Math.h > veya \<cmath >|
|**_nextafter**|\<float.h >|\<float.h > veya \<cfloat >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
