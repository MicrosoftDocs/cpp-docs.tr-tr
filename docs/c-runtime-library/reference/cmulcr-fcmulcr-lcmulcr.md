---
title: _Cmulcr, _FCmulcr, _LCmulcr | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- _Cmulcr
- _FCmulcr
- _LCmulcr
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
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
dev_langs:
- C++
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbd42e4c543d4bc42afa023d62b328a143c90374
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395031"
---
# <a name="cmulcr-fcmulcr-lcmulcr"></a>_Cmulcr, _FCmulcr, _LCmulcr

Bir kayan noktalı sayı karmaşık sayıyla çarpar.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Çarpılacağı karmaşık işlenenler biri.

*Y*<br/>
Çarpılacağı kayan nokta işlenen.

## <a name="return-value"></a>Dönüş Değeri

A **_Dcomplex**, **_Fcomplex**, veya **_Lcomplex** karmaşık sayının karmaşık ürün temsil eden yapısı *x* ve flaoting nokta sayısı *y*.

## <a name="remarks"></a>Açıklamalar

Yerleşik aritmetik işleçler karmaşık türler Microsoft uyarlamasını çalışmadığı için **_Cmulcr**, **_FCmulcr**, ve **_LCmulcr** işlevleri kayan nokta türleri tarafından karmaşık türler çarpımı basitleştirin.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgi|
|-------------|--------------|------------------|
|**_Cmulcr**, **_FCmulcr**, **_LCmulcr**|\<Complex.h >|\<Complex.h >|

Bu işlevler Microsoft özgüdür. Türleri **_Dcomplex**, **_Fcomplex**, ve **_Lcomplex** uygulanmayan C99 yerel türlerinin Microsoft'a özgü eşdeğerleri olan **çift _Complex** , **_Complex float**, ve **uzun çift _Complex**sırasıyla. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[Norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
