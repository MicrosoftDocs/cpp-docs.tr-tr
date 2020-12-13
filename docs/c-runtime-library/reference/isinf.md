---
description: 'Şu konuda daha fazla bilgi edinin: ısinf'
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: f174855ddbb8cc43fd7338d4254c0f03bf53967d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332638"
---
# <a name="isinf"></a>isinf

Kayan nokta değerinin sonsuzluk olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

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

 **`true`** *x* bağımsız değişkeni pozitif veya negatif sonsuzluk ise ısinf sıfır dışında bir değer döndürür (C++ kodunda). bağımsız değişken sonlu veya NAN ise **ısinf** 0 döndürür ( **`false`** C++ kodunda). Hem normal hem de alt normal kayan nokta değerleri sonlu kabul edilir.

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
