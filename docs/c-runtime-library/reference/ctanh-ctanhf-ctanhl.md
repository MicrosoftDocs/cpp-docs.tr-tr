---
title: ctanh, ctanhf, ctanhl
ms.date: 11/04/2016
apiname:
- ctanh
- ctanhf
- ctanhl
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
- ctanh
- ctanhf
- ctanhl
- complex/ctanh
- complex/ctanhf
- complex/ctanhl
helpviewer_keywords:
- ctanh function
- ctanhl function
- ctanhf function
ms.assetid: 807f2cd1-8740-4988-afff-5911c346385b
ms.openlocfilehash: f63329e45fdcd3a26d613f73cd911fdf6fb10401
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702693"
---
# <a name="ctanh-ctanhf-ctanhl"></a>ctanh, ctanhf, ctanhl

Karmaşık bir sayıyı karmaşık hiperbolik tanjantını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex ctanh(
   _Dcomplex z
);
_Fcomplex ctanh(
   _Fcomplex z
);  // C++ only
_Lcomplex ctanh(
   _Lcomplex z
);  // C++ only
_Fcomplex ctanhf(
   _Fcomplex z
);
_Lcomplex ctanhl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parametreler

*z*<br/>
Radyan cinsinden açı temsil eden bir karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

Karmaşık hiperbolik tanjantını *z*.

|Giriş|SEH özel durumu|**_matherr** özel durumu|
|-----------|-------------------|--------------------------|
|± ∞, QNAN, IND|yok|_DOMAIN|
|± ∞ (tan, tanf)|GEÇERSİZ|_DOMAIN|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, aşırı yüklemesini çağırabilirsiniz **ctanh** alan ve getiren **_Fcomplex** ve **_Lcomplex** değerleri. C programında **ctanh** her zaman alan ve döndüren bir **_Dcomplex** değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üst bilgisi|
|-------------|--------------|------------------|
|**ctanh**,               **ctanhf**, **ctanhl**|\<Complex.h >|\<ccomplex >|

Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
