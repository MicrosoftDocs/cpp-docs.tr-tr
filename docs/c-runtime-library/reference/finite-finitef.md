---
title: _finite, _finitef | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3367f13e68aa85e53d9f5f0ee83521ef465d3996
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396647"
---
# <a name="finite-finitef"></a>_finite, _finitef

Kayan noktalı bir sayıyı sınırlı olup olmadığını belirler.

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

Her ikisi de **_finite** ve **_finitef** sıfır olmayan bir değer döndürür bağımsız değişkeni *x* olduğu sınırlı; olduğundan, -INF < *x* < + INF. Bağımsız değişken sonsuz ise 0 veya bir NaN değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Finite** ve **_finitef** Microsoft belirli işlevlerdir. **_Finitef** işlevi, yalnızca kullanılabilir platformları ARM veya ARM64 x86 için derlenmiş.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üstbilgisi (C)|Gerekli üstbilgisi (C++)|
|--------------|---------------------------|-------------------------------|
|**_finite**|\<float.h > veya \<math.h >|\<float.h >, \<math.h >, \<cfloat >, veya \<cmath >|
|**_finitef**|\<Math.h >|\<Math.h > veya \<cmath >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
