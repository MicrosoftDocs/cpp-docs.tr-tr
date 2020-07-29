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
ms.openlocfilehash: 7e15a6619e584ff52c07048fcf591835b799587f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218708"
---
# <a name="isfinite-_finite-_finitef"></a>isfinite, _finite, _finitef

Kayan nokta değerinin sonlu olup olmadığını belirler.

## <a name="syntax"></a>Söz dizimi

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

## <a name="return-value"></a>Döndürülen değer

`isfinite` `_finite` `_finitef` *X* normal veya alt normal sonlu bir değer ise makro ve ve işlevleri sıfır olmayan bir değer döndürür. Bağımsız değişken sonsuz veya NaN ise 0 döndürür. C++ satır içi şablon işlevi `isfinite` aynı şekilde davranır, ancak veya döndürür **`true`** **`false`** .

## <a name="remarks"></a>Açıklamalar

`isfinite`C olarak derlendiğinde bir makro ve C++ olarak derlendiğinde bir satır içi şablon işlevidir. `_finite`Ve `_finitef` Işlevleri, Microsoft 'a özgüdür. `_finitef`İşlevi yalnızca x86, ARM veya ARM64 platformları için derlendiğinde kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|--------------|---------------------------|-------------------------------|
|`_finite`|\<float.h> veya \<math.h>|\<float.h>, \<math.h> , \<cfloat> veya\<cmath>|
|`isfinite`, `_finitef`|\<math.h>|\<math.h> veya \<cmath>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
