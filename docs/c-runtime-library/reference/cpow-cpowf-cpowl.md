---
title: cpow, cpowf, cpowl
ms.date: 11/04/2016
api_name:
- cpow
- cpowf
- cpowl
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
- cpow
- cpowf
- cpowl
- complex/cpow
- complex/cpowf
- complex/copwl
helpviewer_keywords:
- cpow function
- cpowf function
- complex/cpowl function
ms.assetid: 83fe2187-22b7-4295-ab16-4d77abdbb80b
ms.openlocfilehash: 005bafd4b19164f5c85be839a90fc7d5259d61bf
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942697"
---
# <a name="cpow-cpowf-cpowl"></a>cpow, cpowf, cpowl

Belirtilen üssün çıkarılan bir sayının değerini alır, burada taban ve üs karmaşık sayılardır. Bu işlev, negatif gerçek eksen boyunca üs için kesilmiş bir dala sahiptir.

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
Temel.

*Iz*<br/>
Üs.

## <a name="return-value"></a>Dönüş Değeri

X değeri negatif gerçek eksen boyunca *x* için kesilmiş bir dala sahip *x* *değerinin üssü* .

## <a name="remarks"></a>Açıklamalar

Aşırı C++ yüklemeye izin verdiğinden, **_Fcomplex** ve **_lcomplex** değerlerini alıp döndüren **cpow** aşırı yüklerini çağırabilirsiniz. C programında **cpow** her zaman **_dcomplex** değeri alır ve döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|C üstbilgisi|C++üst bilgi|
|-------------|--------------|------------------|
|**cpow**, **cpowf**, **cpowl**|\<karmaşık. h >|\<ccomplex >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[clog10, clog10f, clog10l](clog10-clog10f-clog10l.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>
