---
title: Norm, normf, norml | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- norm
- normf
- norml
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
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
dev_langs:
- C++
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e485c609054021fbdb8563ded539aa8f19cc868e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="norm-normf-norml"></a>Norm, normf, norml

Karmaşık bir sayının kare büyüklük alır.

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

*z*<br/>
Bir karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

Kare büyüklüğünü *z*.

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **norm** Süren **_Fcomplex** veya **_Lcomplex** değerleri ve return **float** veya **uzun çift** değerleri. Bir C programı **norm** her zaman alan bir **_Dcomplex** değeri ve döndürür bir **çift** değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgi|
|-------------|--------------|------------------|
|**Norm**, **normf**, **norml**|\<Complex.h >|\<Complex.h >|

**_Fcomplex**, **_Dcomplex**, ve **_Lcomplex** türleridir uygulanmayan yerel C99 türleri Microsoft'a özgü eşdeğerlerini **_Complex float** , **çift _Complex**, ve **uzun çift _Complex**sırasıyla.  Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
