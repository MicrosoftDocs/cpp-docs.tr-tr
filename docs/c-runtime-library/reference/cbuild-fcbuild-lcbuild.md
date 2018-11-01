---
title: _Cbuild, _FCbuild, _LCbuild
ms.date: 03/30/2018
apiname:
- _Cbuild
- _FCbuild
- _LCbuild
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
ms.openlocfilehash: 5565c87a3cccd1715a1357f417238587f3fba4d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511806"
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

Karmaşık bir sayıyı reel ve sanal parçalarından oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>Parametreler

*Gerçek*<br/>
Karmaşık sayıyı oluşturmak için gerçek parçası.

*sanal*<br/>
Karmaşık sayıyı oluşturmak için sanal parçası.

## <a name="return-value"></a>Dönüş Değeri

A **_Dcomplex**, **_Fcomplex**, veya **_Lcomplex** karmaşık sayıyı temsil eden yapısı (*gerçek*, *sanal*  \* miyim) belirtilen kayan nokta türü değerlerinin.

## <a name="remarks"></a>Açıklamalar

**_Cbuild**, **_FCbuild**, ve **_LCbuild** işlevleri karmaşık türler oluşturulmasını basitleştirir. Kullanım [creal, crealf, creall](creal-crealf-creall.md) ve [cimag, cimagf, cimagl](cimag-cimagf-cimagl.md) gösterilen karmaşık sayıların reel ve sanal kısımlarını almak için işlevleri.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üst bilgisi|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<Complex.h >|\<ccomplex >|

Bu işlevler Microsoft özgüdür. Türleri **_Dcomplex**, **_Fcomplex**, ve **_Lcomplex** uygulanmayan C99 yerel türler için Microsoft'a özgü eşdeğeri olan **çift _Complex** , **_Complex float**, ve **uzun çift _Complex**sırasıyla. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[Norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
