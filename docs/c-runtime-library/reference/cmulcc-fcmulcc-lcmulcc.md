---
description: 'Hakkında daha fazla bilgi edinin: _Cmulcc, _FCmulcc, _LCmulcc'
title: _Cmulcc, _FCmulcc, _LCmulcc
ms.date: 03/30/2018
api_name:
- _Cmulcc
- _FCmulcc
- _LCmulcc
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
ms.openlocfilehash: e18f6ee0ab166cbce04d425ece43ef8ba2708a4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258739"
---
# <a name="_cmulcc-_fcmulcc-_lcmulcc"></a>_Cmulcc, _FCmulcc, _LCmulcc

İki karmaşık sayıyı çarpar.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex _Cmulcc( _Dcomplex x, _Dcomplex y );
_Fcomplex _FCmulcc( _Fcomplex x, _Fcomplex y );
_Lcomplex _LCmulcc( _Lcomplex x, _Lcomplex y );
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Çarpılacak karmaşık işlenenlerinden biri.

*Iz*<br/>
Çarpılacak diğer karmaşık işlenen.

## <a name="return-value"></a>Dönüş Değeri

*X* ve *y* karmaşık sayılarının karmaşık çarpımını temsil eden bir **_Dcomplex**, **_Fcomplex** veya **_Lcomplex** yapısı.

## <a name="remarks"></a>Açıklamalar

Yerleşik aritmetik işleçler karmaşık türlerin Microsoft uygulamasında çalışmadığından **_Cmulcc**, **_FCmulcc** ve **_LCmulcc** işlevleri karmaşık türlerin çarpmayı basitleştirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgisi|
|-------------|--------------|------------------|
|**_Cmulcc**, **_FCmulcc**, **_LCmulcc**|\<complex.h>|\<complex.h>|

Bu işlevler, Microsoft 'a özgüdür. **_Dcomplex**, **_Fcomplex** ve **_Lcomplex** türleri, uygulanmayan C99 yerel türleri için sırasıyla **çift _Complex**, **float _Complex** ve **uzun çift _Complex** için Microsoft 'a özgü eşdeğerlerine sahiptir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
