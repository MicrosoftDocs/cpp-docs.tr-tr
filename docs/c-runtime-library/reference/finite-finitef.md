---
title: isfinite, _finite, _finitef
ms.date: 01/31/2019
api_name:
- _finite
- _finitef
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: a2cde4d3a57884413f0c48aa299b171334c5f988
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957179"
---
# <a name="isfinite-_finite-_finitef"></a>isfinite, _finite, _finitef

Kayan nokta değerinin sonlu olup olmadığını belirler.

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
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş değeri

X normal veya alt `_finite` normal `_finitef` sonlu bir değer ise makroveveişlevlerisıfırolmayanbirdeğerdöndürür.`isfinite` Bağımsız değişken sonsuz veya NaN ise 0 döndürür. C++ Satır içi şablon işlevi `isfinite` aynı şekilde davranır, ancak **true** veya **false**değerini döndürür.

## <a name="remarks"></a>Açıklamalar

`isfinite`, C olarak derlendiğinde bir makro ve olarak C++derlendiğinde bir satır içi şablon işlevidir. `_finite` Ve`_finitef` işlevleri, Microsoft 'a özgüdür. `_finitef` İşlevi yalnızca x86, ARM veya ARM64 platformları için derlendiğinde kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgiC++()|
|--------------|---------------------------|-------------------------------|
|`_finite`|\<float. h > veya \<Math. h >|\<float. h >, \<Math. h >, \<cfloat > veya \<cmath >|
|`isfinite`, `_finitef`|\<Math. h >|\<Math. h > veya \<cmath >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
