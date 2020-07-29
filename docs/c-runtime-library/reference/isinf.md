---
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: 7366f340477bf1bb50ebe1e53bcec1f3e16e0863
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234100"
---
# <a name="isinf"></a>isinf

Kayan nokta değerinin sonsuzluk olup olmadığını belirler.

## <a name="syntax"></a>Söz dizimi

```C
int isinf(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isinf(
   FloatingType x
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Döndürülen değer

**isinf** **`true`** *x* bağımsız değişkeni pozitif veya negatif sonsuzluk ise ısinf sıfır dışında bir değer döndürür (C++ kodunda). bağımsız değişken sonlu veya NAN ise **ısinf** 0 döndürür ( **`false`** C++ kodunda). Hem normal hem de alt normal kayan nokta değerleri sonlu kabul edilir.

## <a name="remarks"></a>Açıklamalar

**ısinf** , C olarak derlendiğinde bir makrodur ve C++ olarak derlendiğinde bir satır içi şablon işlevidir.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|--------------|---------------------------|-------------------------------|
|**isinf**|\<math.h>|\<math.h> veya \<cmath>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
