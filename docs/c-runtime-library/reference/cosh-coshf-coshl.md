---
title: COSH, coshf, coshl
ms.date: 04/11/2018
apiname:
- cosh
- coshf
- coshl
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
- cosh
- coshf
- coshl
helpviewer_keywords:
- cosh function
- coshf function
- coshl function
- trigonometric functions
- hyperbolic functions
ms.openlocfilehash: 0f55e084e760cb6d04dbe7ec4fefb5e2ac1d79fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347450"
---
# <a name="cosh-coshf-coshl"></a>COSH, coshf, coshl

Hiperbolik kosinüsünü hesaplar.

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

Hiperbolik kosinüsünü *x*.

Varsayılan olarak sonuç çok büyükse bir **cosh**, **coshf**, veya **coshl** işlevi döndürür, çağrı **HUGE_VAL** ve Ayarlar**errno** için **ERANGE**.

|Giriş|SEH özel durumu|Matherr özel durumu|
|-----------|-------------------|-----------------------|
|± **QNAN**, **ONRAKİNİ BUL**|yok|**_DOMAIN**|
|*x* ≥ 7.104760e + 002|**FİLTRESİNİN**+**TAŞMASI**|**TAŞMA**|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **cosh** alan ve getiren **float** veya **uzun** **çift** değerleri. C programında **cosh** her zaman alan ve döndüren bir **çift**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık (C)|Gerekli başlık (C++)|
|-------------|---------------------|-|
|**coshf**, **cosl**, **coshl**|\<Math.h >|\<cmath > veya \<math.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [sinh, sinhf, sinhl](sinh-sinhf-sinhl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[_matherr](matherr.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
