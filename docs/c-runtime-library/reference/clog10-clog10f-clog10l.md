---
title: clog10, clog10f, clog10l
ms.date: 11/04/2016
apiname:
- clog10
- clog10f
- clog10l
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
- clog10
- clog10f
- clog10l
- complex/clog10
- complex/clog10f
- complex/clog10l
helpviewer_keywords:
- clog10 function
- clog10f function
- clog10l function
ms.assetid: 2ddae00d-ef93-4441-add3-f4d58358401b
ms.openlocfilehash: 195f4be80f0320e83cc9455a598185ce281bbf59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335463"
---
# <a name="clog10-clog10f-clog10l"></a>clog10, clog10f, clog10l

Karmaşık bir sayının 10 tabanındaki logaritmasını alır.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex clog10( _Dcomplex z );
_Fcomplex clog10f( _Fcomplex z );
_Lcomplex clog10l( _Lcomplex z );
```

```cpp
_Fcomplex clog10( _Fcomplex z );  // C++ only
_Lcomplex clog10( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parametreler

*z*<br/>
Logaritmanın tabanı.

## <a name="return-value"></a>Dönüş Değeri

Olası dönüş değerleri şunlardır:

|z parametresi|Dönüş değeri|
|-----------------|------------------|
|Pozitif|Z 10 tabanındaki logaritmasını|
|Sıfır|- ∞|
|Negatif|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Açıklamalar

Çünkü C++ aşırı yüklemesi, sağlayan yüklerini çağırabilirsiniz **clog10** alan ve getiren **_Fcomplex** ve **_Lcomplex** değerleri. C programında **clog10** her zaman alan ve döndüren bir **_Dcomplex** değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üst bilgisi|
|-------------|--------------|------------------|
|**clog10**, **clog10f**, **clogl**|\<Complex.h >|\<ccomplex >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>
