---
title: signbit
ms.date: 01/31/2019
f1_keywords:
- signbit
- math/signbit
helpviewer_keywords:
- signbit function
ms.openlocfilehash: ce2f632f11296bf71036011a57f242365951d7f2
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703374"
---
# <a name="signbit"></a>signbit

Bir kayan nokta değeri negatif olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int signbit(
   /* floating-point */ x
); /* C-only macro */

inline bool signbit(
   float x
) throw(); /* C++-only overloaded function */

inline bool signbit(
   double x
) throw(); /* C++-only overloaded function */

inline bool signbit(
   long double x
) throw(); /* C++-only overloaded function */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş değeri

**signbit** sıfır olmayan bir değer döndürür (**true** C++'ta), bağımsız değişken *x* negatif veya negatif sonsuz. 0 döndürür (**false** C++'ta) bağımsız değişken negatif olmayan, Pozitif sonsuz veya bir NAN ise.

## <a name="remarks"></a>Açıklamalar

**signbit** C ve C++ derlendiğinde aşırı yüklenmiş bir satır içi işlev olarak derlendiğinde bir makro.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------------|-------------------------------|
|**signbit**|\<Math.h >|\<Math.h > veya \<cmath >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
