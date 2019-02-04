---
title: isfinite, _finite, _finitef
ms.date: 01/31/2019
apiname:
- _finite
- _finitef
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
- isfinite
- finite
- _finite
- _finitef
- math/isfinite
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: 1be5aa204a7db3054a49c2e05a8fd77b12ae8a3d
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702758"
---
# <a name="isfinite-finite-finitef"></a>isfinite, _finite, _finitef

Bir kayan nokta değeri sınırlı olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isfinite(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isfinite(
   FloatingType x
) throw(); /* C++-only template function */

int _finite(
   double x
);

int _finitef(
   float x
); /* x64 and ARM/ARM64 only */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş değeri

`isfinite` Makrosu ve `_finite` ve `_finitef` işlevler ise sıfır olmayan bir değer döndürür *x* ya da bir normal veya subnormal sınırlı bir değer. Bunlar, bağımsız değişken sonsuz ise 0 ya da bir NaN döndürür. C++ satır içi şablon işlevi `isfinite` aynı şekilde davranır, ancak döndürür **true** veya **false**.

## <a name="remarks"></a>Açıklamalar

`isfinite` C ve C++ derlendiğinde bir satır içi şablon işlevi olarak derlendiğinde bir makrodur. `_finite` Ve `_finitef` Microsoft'a özgü işlevlerdir. `_finitef` İşlevi, yalnızca kullanılabilir platformları x86, ARM ve ARM64 için derlenmiş.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------------|-------------------------------|
|`_finite`|\<float.h > veya \<math.h >|\<float.h >, \<math.h >, \<cfloat >, veya \<cmath >|
|`isfinite`, `_finitef`|\<Math.h >|\<Math.h > veya \<cmath >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
