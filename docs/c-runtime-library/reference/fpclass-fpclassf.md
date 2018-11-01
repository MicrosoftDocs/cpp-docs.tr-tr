---
title: _fpclass, _fpclassf
ms.date: 04/05/2018
apiname:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
ms.openlocfilehash: 987c87cc7a03f4a24e47654ae52e8a2416a15184
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590976"
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf

Kayan nokta bağımsız değişken sınıflandırmasını gösteren bir değer döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _fpclass(
   double x
);

int _fpclassf(
   float x
); /* x64 only */
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**_Fpclass** ve **_fpclassf** İşlevler, bağımsız değişkenin kayan nokta sınıflandırma belirten bir tamsayı değeri döndürür *x*. Sınıflandırma içinde tanımlanan aşağıdaki değerlerden birine sahip \<float.h >.

|Değer|Açıklama|
|-----------|-----------------|
|**_FPCLASS_SNAN**|NaN sinyali|
|**_FPCLASS_QNAN**|Sessiz bir NaN|
|**_FPCLASS_NINF**|Negatif sonsuz (-INF)|
|**_FPCLASS_NN**|Negatif sıfır olmayan normalleştirilmiş|
|**_FPCLASS_ND**|Negatif normal dışı|
|**_FPCLASS_NZ**|Negatif sıfır (- 0)|
|**_FPCLASS_PZ**|Pozitif 0 (+ 0)|
|**_FPCLASS_PD**|Pozitif normal dışı|
|**_FPCLASS_PN**|Pozitif sıfır olmayan normalleştirilmiş|
|**_FPCLASS_PINF**|Pozitif sonsuz (+ INF)|

## <a name="remarks"></a>Açıklamalar

**_Fpclass** ve **_fpclassf** Microsoft'a özgü işlevlerdir. Benzemez [fpclassify](fpclassify.md), ancak bağımsız değişken ilişkin daha ayrıntılı bilgi döndürür. **_Fpclassf** işlev için x64 derlendiğinde kullanılabilir, yalnızca platform.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h >|

Daha fazla uyumluluk ve uyum için bilgi [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>