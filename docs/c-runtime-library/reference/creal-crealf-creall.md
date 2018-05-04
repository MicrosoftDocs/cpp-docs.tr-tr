---
title: creal, crealf, creall | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- creal
- crealf
- creall
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
- creal
- crealf
- creall
- complex/creal
- complex/crealf
- complex/creall
dev_langs:
- C++
helpviewer_keywords:
- creal function
- crealf function
- creall function
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8d3ca02aeb0f3f9b12c8b82cbb27d9bd3ad3aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="creal-crealf-creall"></a>creal, crealf, creall

Karmaşık bir sayının gerçek bölüm alır.

## <a name="syntax"></a>Sözdizimi

```C
double creal( _Dcomplex z );
float crealf( _Fcomplex z );
long double creall( _Lcomplex z );
```

```cpp
float creal( _Fcomplex z );  // C++ only
long double creal( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parametreler

*z*<br/>
Bir karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

Gerçek parçası *z*.

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **creal** Süren **_Fcomplex** veya **_Lcomplex** değerleri ve return **float** veya **uzun çift** değerleri. Bir C programı **creal** her zaman alan bir **_Dcomplex** değeri ve döndürür bir **çift** değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgi|
|-------------|--------------|------------------|
|**creal**, **crealf**, **creall**|\<Complex.h >|\<ccomplex >|

**_Fcomplex**, **_Dcomplex**, ve **_Lcomplex** türleridir uygulanmayan yerel C99 türleri Microsoft'a özgü eşdeğerlerini **_Complex float** , **çift _Complex**, ve **uzun çift _Complex**sırasıyla. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[Norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>