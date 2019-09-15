---
title: _Cmulcr, _FCmulcr, _LCmulcr
ms.date: 03/30/2018
api_name:
- _Cmulcr
- _FCmulcr
- _LCmulcr
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
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
ms.openlocfilehash: cbff1c2cb0e66da77b6fdc8127b78fb475aa5080
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942895"
---
# <a name="_cmulcr-_fcmulcr-_lcmulcr"></a>_Cmulcr, _FCmulcr, _LCmulcr

Karmaşık bir sayıyı kayan noktalı bir sayı ile çarpar.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Çarpılacak karmaşık işlenenlerinden biri.

*Iz*<br/>
Çarpılacak kayan nokta işleneni.

## <a name="return-value"></a>Dönüş Değeri

Karmaşık sayının *x* ve flaşın nokta numarası *y*'nin karmaşık çarpımını temsil eden **_dcomplex**, **_fcomplex**veya **_lcomplex** yapısı.

## <a name="remarks"></a>Açıklamalar

Yerleşik aritmetik işleçler karmaşık türlerin Microsoft uygulamasında çalışmadığından, **_Cmulcr**, **_Fcmulcr**ve **_lcmulcr** işlevleri, kayan nokta türlerine göre karmaşık türlerin çarptiğini basitleştirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++üst bilgi|
|-------------|--------------|------------------|
|**_Cmulcr**, **_fcmulcr**, **_lcmulcr**|\<karmaşık. h >|\<karmaşık. h >|

Bu işlevler, Microsoft 'a özgüdür. **_Dcomplex**, **_Fcomplex**ve **_lcomplex** türleri, uygulanmayan C99 yerel türlerine, sırasıyla **_complex**, **float _complex**ve **Long Double _complex**için Microsoft 'a özgü eşdeğerlerdir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
