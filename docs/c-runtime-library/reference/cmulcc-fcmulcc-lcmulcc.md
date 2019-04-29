---
title: _Cmulcc, _FCmulcc, _LCmulcc
ms.date: 03/30/2018
apiname:
- _Cmulcc
- _FCmulcc
- _LCmulcc
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
- _Cmulcc
- _FCmulcc
- _LCmulcc
- complex/_Cmulcc
- complex/_FCmulcc
- complex/_LCmulcc
helpviewer_keywords:
- _Cmulcc function
- _FCmulcc function
- _LCmulcc function
ms.openlocfilehash: f81ccb641a80ab264e8bc54ba1987e2c2c8469f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335398"
---
# <a name="cmulcc-fcmulcc-lcmulcc"></a>_Cmulcc, _FCmulcc, _LCmulcc

İki karmaşık sayıyı çarpar.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex _Cmulcc( _Dcomplex x, _Dcomplex y );
_Fcomplex _FCmulcc( _Fcomplex x, _Fcomplex y );
_Lcomplex _LCmulcc( _Lcomplex x, _Lcomplex y );
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Çarpılacak karmaşık işlenenler biri.

*Y*<br/>
Çarpılacak diğer karmaşık işlenen.

## <a name="return-value"></a>Dönüş Değeri

A **_Dcomplex**, **_Fcomplex**, veya **_Lcomplex** karmaşık karmaşık sayıların çarpımını gösteren yapısı *x* ve *y*.

## <a name="remarks"></a>Açıklamalar

Yerleşik aritmetik işleçler karmaşık türler, Microsoft uygulaması üzerinde çalışmadığı için **_Cmulcc**, **_FCmulcc**, ve **_LCmulcc** işlevleri karmaşık türler çarpımı basitleştirin.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üst bilgisi|
|-------------|--------------|------------------|
|**_Cmulcc**, **_FCmulcc**, **_LCmulcc**|\<Complex.h >|\<Complex.h >|

Bu işlevler Microsoft özgüdür. Türleri **_Dcomplex**, **_Fcomplex**, ve **_Lcomplex** uygulanmayan C99 yerel türler için Microsoft'a özgü eşdeğeri olan **çift _Complex** , **_Complex float**, ve **uzun çift _Complex**sırasıyla. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
