---
title: _Cbuild, _FCbuild, _LCbuild
ms.date: 03/30/2018
api_name:
- _Cbuild
- _FCbuild
- _LCbuild
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
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: b0ae50f40f0ca0a926e1eef586c6610a04b6ea7a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943224"
---
# <a name="_cbuild-_fcbuild-_lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

Gerçek ve sanal bölümlerden karmaşık bir sayı oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>Parametreler

*gerçek*<br/>
Yapı için karmaşık sayının gerçek bölümü.

*sanal*<br/>
Oluşturmak için karmaşık sayının sanal bölümü.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen kayan nokta türünün değerleri için karmaşık sayıyı (*gerçek*, *sanal* \* i) temsil eden **_dcomplex**, **_fcomplex**veya **_lcomplex** yapısı.

## <a name="remarks"></a>Açıklamalar

**_Cbuild**, **_Fcbuild**ve **_lcbuild** işlevleri karmaşık türlerin oluşturulmasını basitleştirir. Temsil edilen karmaşık sayıların gerçek ve sanal kısımlarını almak için [creal, crealf, Creall](creal-crealf-creall.md) ve [cımag, cımıknatıf, cımagl](cimag-cimagf-cimagl.md) işlevlerini kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++üst bilgi|
|-------------|--------------|------------------|
|**_Cbuild**, **_fcbuild**, **_lcbuild**|\<karmaşık. h >|\<ccomplex >|

Bu işlevler, Microsoft 'a özgüdür. **_Dcomplex**, **_Fcomplex**ve **_lcomplex** türleri, uygulanmayan C99 yerel türlerine, sırasıyla **_complex**, **float _complex**ve **Long Double _complex**için Microsoft 'a özgü eşdeğerlerdir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
