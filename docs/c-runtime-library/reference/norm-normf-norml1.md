---
description: Daha fazla bilgi için bkz. norm, normf, NORML
title: norm, normf, norml
ms.date: 04/05/2018
api_name:
- norm
- normf
- norml
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
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
ms.openlocfilehash: 175cff5f9c0e31a56a86a96c3262e2c3c546fe4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256308"
---
# <a name="norm-normf-norml"></a>norm, normf, norml

Karmaşık bir sayının kare boyutunu alır.

## <a name="syntax"></a>Sözdizimi

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parametreler

*kadar*<br/>
Karmaşık bir sayı.

## <a name="return-value"></a>Dönüş Değeri

*Z* kare cinsinden büyüklüğü.

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **_Fcomplex** veya **_Lcomplex** değerlerini alan ve döndüren veya değer döndüren **norm** aşırı yüklerini çağırabilirsiniz **`float`** **`long double`** . C programında, **norm** her zaman bir **_Dcomplex** değeri alır ve bir değer döndürür **`double`** .

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgisi|
|-------------|--------------|------------------|
|**norm**, **normf**, **NORML**|\<complex.h>|\<complex.h>|

**_Fcomplex**, **_Dcomplex** ve **_Lcomplex** türler, uygulanmayan yerel C99 türlerinin (sırasıyla **float _Complex**, **çift _Complex** ve **uzun çift _Complex**) Microsoft 'a özgü eşdeğerlerine sahiptir.  Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
