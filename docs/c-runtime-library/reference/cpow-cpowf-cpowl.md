---
title: cpow, cpowf, cpowl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- cpow
- cpowf
- cpowl
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
- cpow
- cpowf
- cpowl
- complex/cpow
- complex/cpowf
- complex/copwl
dev_langs:
- C++
helpviewer_keywords:
- cpow function
- cpowf function
- complex/cpowl function
ms.assetid: 83fe2187-22b7-4295-ab16-4d77abdbb80b
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9ae1fd2d71e3876be8c814d531dfdfe6b434fde
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="cpow-cpowf-cpowl"></a>cpow, cpowf, cpowl

Bir sayının tabanı ve üs karmaşık numaralar nerede belirtilen üssüne yükseltilmiş değerini alır. Bu işlev negatif gerçek ekseni boyunca üs için kesin bir dal sahiptir.

## <a name="syntax"></a>Sözdizimi

```C
_Dcomplex cpow(
   _Dcomplex x, _Dcomplex y
);
_Fcomplex cpow(
   _Fcomplex x, _Fcomplex y
);  // C++ only
_Lcomplex cpow(
   _Lcomplex x, _Lcomplex y
);  // C++ only
_Fcomplex cpowf(
   _Fcomplex x, _Fcomplex y
);
_Lcomplex cpowl(
   _Lcomplex x, _Lcomplex y
);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Tabanı.

*Y*<br/>
Üs.

## <a name="return-value"></a>Dönüş Değeri

Değeri *x* üssünü *y* için kesin bir dal ile *x* negatif gerçek ekseni boyunca.

## <a name="remarks"></a>Açıklamalar

Aşırı yükleme C++ izin verdiğinden, aşırı çağırabilirsiniz **cpow** alın ve dönüş **_Fcomplex** ve **_Lcomplex** değerleri. Bir C programı **cpow** her zaman alan ve döndüren bir **_Dcomplex** değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++ üstbilgi|
|-------------|--------------|------------------|
|**cpow**, **cpowf**, **cpowl**|\<Complex.h >|\<ccomplex >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>
