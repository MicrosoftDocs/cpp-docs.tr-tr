---
title: clog, clogf, clogl
description: CLOG, clogf ve clogl; için API başvurusu karmaşık bir sayının doğal logaritmasını elde eden bir dalı negatif gerçek eksen üzerinde keser.
ms.date: 11/04/2016
api_name:
- clog
- clogf
- clogl
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
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
ms.openlocfilehash: 255f83a93c5c7a0c724fad143f028c2832be3173
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555078"
---
# <a name="clog-clogf-clogl"></a>clog, clogf, clogl

Karmaşık bir sayının doğal logaritmasını alır ve bir dal negatif gerçek eksen üzerinde kesilir.

## <a name="syntax"></a>Söz dizimi

```C
_Dcomplex clog(
   _Dcomplex z
);
_Fcomplex clog(
   _Fcomplex z
);  // C++ only
_Lcomplex clog(
   _Lcomplex z
);  // C++ only
_Fcomplex clogf(
   _Fcomplex z
);
_Lcomplex clogl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parametreler

*kadar*\
Logaritmanın tabanıdır.

## <a name="return-value"></a>Dönüş Değeri

*Z*'nin doğal logaritması. Sonuç, gerçek eksen ve [-iπ, + iπ] aralığında, sanal eksen üzerinde sınırsız olarak yapılır.

Olası dönüş değerleri şunlardır:

|z parametresi|Döndürülen değer|
|-----------------|------------------|
|Pozitif|Z 'nin 10 tabanında logaritmasını|
|Sıfır|- ∞|
|Negatif|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Açıklamalar

C++ aşırı yüklemeye izin verdiğinden, **_Fcomplex** ve **_Lcomplex** değerleri alıp döndüren **CLOG** aşırı yüklerini çağırabilirsiniz. C programında **CLOG** her zaman bir **_Dcomplex** değeri alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgisi|
|-------------|--------------|------------------|
|**CLOG**,               **clogf**, **clogl**|\<complex.h>|\<ccomplex>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
