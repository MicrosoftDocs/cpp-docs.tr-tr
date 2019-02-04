---
title: isnormal
ms.date: 01/31/2019
f1_keywords:
- isnormal
- math/isnormal
helpviewer_keywords:
- isnormal function
ms.openlocfilehash: 93e3b8912ddf20bf8e190bb42e8413e6d909bbcc
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703376"
---
# <a name="isnormal"></a>isnormal

Bir kayan nokta değeri bir sonsuzluk olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isnormal(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isnormal(
   FloatingType x
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş değeri

**isnormal** sıfır dışında bir değeri döndürür (**true** C++ kodunda), bağımsız değişken *x* sınırlı ve subnormal değil. **isnormal** 0 döndürür (**false** C++ kodunda) bağımsız değişken bir subnormal, sonsuzluk veya bir NAN ise.

## <a name="remarks"></a>Açıklamalar

**isnormal** C ve C++ derlendiğinde bir satır içi şablon işlevi olarak derlendiğinde bir makro.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------------|-------------------------------|
|**isnormal**|\<Math.h >|\<Math.h > veya \<cmath >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
