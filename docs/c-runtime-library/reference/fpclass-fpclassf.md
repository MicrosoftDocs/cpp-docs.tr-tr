---
title: _fpclass, _fpclassf | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79895cf19c188addee45236df5dc47d3f4ebf6a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf

Kayan nokta sınıflandırma bağımsız değişkenin belirten bir değer döndürür.

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

**_Fpclass** ve **_fpclassf** işlevleri bağımsız değişkenin kayan nokta sınıflandırma belirten bir tamsayı değeri döndürmek *x*. Sınıflandırma tanımlanan aşağıdaki değerlerden birine sahip \<float.h >.

|Değer|Açıklama|
|-----------|-----------------|
|**_FPCLASS_SNAN**|NaN sinyali|
|**_FPCLASS_QNAN**|Sessiz NaN|
|**_FPCLASS_NINF**|Negatif sonsuz (-INF)|
|**_FPCLASS_NN**|Sıfır olmayan negatif normalleştirilmiş|
|**_FPCLASS_ND**|Normal dışı negatif|
|**_FPCLASS_NZ**|Negatif sıfır (- 0)|
|**_FPCLASS_PZ**|Pozitif 0 (+ 0)|
|**_FPCLASS_PD**|Normal dışı pozitif|
|**_FPCLASS_PN**|Sıfır olmayan pozitif normalleştirilmiş|
|**_FPCLASS_PINF**|Pozitif sonsuzluk (+ INF)|

## <a name="remarks"></a>Açıklamalar

**_Fpclass** ve **_fpclassf** Microsoft belirli işlevlerdir. Benzer şekilde [fpclassify](fpclassify.md), ancak bağımsız değişken ilgili ayrıntılı bilgileri döndürür. **_Fpclassf** işlevi için x64 derlendiğinde kullanılabilir yalnızca platform.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h >|

Daha fazla uyumluluk ve uyum için bilgi [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>