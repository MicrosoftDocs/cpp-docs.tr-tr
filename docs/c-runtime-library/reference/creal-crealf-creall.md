---
title: creal, crealf, creall
ms.date: 03/30/2018
api_name:
- creal
- crealf
- creall
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
- creal
- crealf
- creall
- complex/creal
- complex/crealf
- complex/creall
helpviewer_keywords:
- creal function
- crealf function
- creall function
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
ms.openlocfilehash: 4dcdf60fee6d57b5561b72b477aa1a8bb31f35f4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171222"
---
# <a name="creal-crealf-creall"></a>creal, crealf, creall

Karmaşık bir sayının gerçek bölümünü alır.

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

*kadar*<br/>
Karmaşık bir sayı.

## <a name="return-value"></a>Dönüş Değeri

*Z*'nin gerçek bölümü.

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **_Fcomplex** veya **_Lcomplex** değerlerini alan ve **float** veya **Long Double** değerlerini döndüren **creal** 'ın aşırı yüklerini çağırabilirsiniz. C programında, **creal** her zaman bir **_Dcomplex** değeri alır ve bir **Double** değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++üst bilgi|
|-------------|--------------|------------------|
|**creal**, **crealf**, **Creall**|\<Complex. h >|\<ccomplex >|

**_Fcomplex**, **_Dcomplex**ve **_Lcomplex** türler, uygulanmayan yerel C99 türlerinin (sırasıyla **float _Complex**, **çift _Complex**ve **uzun çift _Complex**) Microsoft 'a özgü eşdeğerlerine sahiptir. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
