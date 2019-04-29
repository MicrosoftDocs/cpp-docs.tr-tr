---
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: be99970a0c7b152ba213eabd59b53a7503cd3c54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331616"
---
# <a name="isinf"></a>isinf

Bir kayan nokta değeri bir sonsuzluk olup olmadığını belirler.

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
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş değeri

**isinf** sıfır dışında bir değeri döndürür (**true** C++ kodunda), bağımsız değişken *x* pozitif veya negatif sonsuz. **isinf** 0 döndürür (**false** C++ kodunda) bağımsız değişken sınırlı ise veya NAN. Hem normal hem de subnormal kayan nokta değerleri sınırlı olarak kabul edilir.

## <a name="remarks"></a>Açıklamalar

**isinf** C ve C++ derlendiğinde bir satır içi şablon işlevi olarak derlendiğinde bir makro.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------------|-------------------------------|
|**isinf**|\<Math.h >|\<Math.h > veya \<cmath >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
