---
title: signbit
ms.date: 01/31/2019
f1_keywords:
- signbit
- math/signbit
helpviewer_keywords:
- signbit function
ms.openlocfilehash: 7f8399c16d2abc70a50740b0629bc5d9b3a1f067
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216745"
---
# <a name="signbit"></a>signbit

Kayan nokta değerinin negatif olup olmadığını belirler.

## <a name="syntax"></a>Söz dizimi

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
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Döndürülen değer

**signbit** **`true`** *x* bağımsız değişkeni negatif veya negatif sonsuzluk ise, signbit sıfır olmayan bir değer (C++ olarak) döndürür. **`false`** Bağımsız değişken negatif olmayan, pozitif sonsuz veya NaN ise 0 döndürür (C++ ' ta).

## <a name="remarks"></a>Açıklamalar

**signbit** , C olarak derlendiğinde bir makrodur ve C++ olarak derlendiğinde aşırı yüklenmiş bir satır içi işlevdir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|--------------|---------------------------|-------------------------------|
|**signbit**|\<math.h>|\<math.h> veya \<cmath>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
