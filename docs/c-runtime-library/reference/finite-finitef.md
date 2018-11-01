---
title: _finite, _finitef
ms.date: 04/05/2018
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: 7b1bce6f1b2da77ed9de255f49dd8d0160e33e31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431683"
---
# <a name="finite-finitef"></a>_finite, _finitef

Bir kayan nokta değeri sınırlı olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
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

## <a name="return-value"></a>Dönüş Değeri

Her ikisi de **_finite** ve **_finitef** sıfır olmayan bir değer döndürür bağımsız değişken *x* olduğu sınırlı; olduğundan, -INF < *x* < + INF. Bağımsız değişken sonsuz ise 0 ya da bir NAN döndürür.

## <a name="remarks"></a>Açıklamalar

**_Finite** ve **_finitef** Microsoft'a özgü işlevlerdir. **_Finitef** işlevi, yalnızca kullanılabilir platformları x86, ARM ve ARM64 için derlenmiş.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------------|-------------------------------|
|**_finite**|\<float.h > veya \<math.h >|\<float.h >, \<math.h >, \<cfloat >, veya \<cmath >|
|**_finitef**|\<Math.h >|\<Math.h > veya \<cmath >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
