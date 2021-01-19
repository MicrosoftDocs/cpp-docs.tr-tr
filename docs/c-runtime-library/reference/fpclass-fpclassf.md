---
description: 'Hakkında daha fazla bilgi edinin: _fpclass _fpclassf'
title: _fpclass, _fpclassf
ms.date: 1/15/2021
api_name:
- _fpclass
- _fpclassf
- _o__fpclass
- _o__fpclassf
api_location:
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 3fb97c5aa787c4c102e787fa3b08650f23ca546a
ms.sourcegitcommit: 92dc6d99ba5dcf3b64dee164df2d29beb1e608da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2021
ms.locfileid: "98563997"
---
# <a name="_fpclass-_fpclassf"></a>`_fpclass`, `_fpclassf`

Bağımsız değişkenin kayan nokta sınıflandırmasını gösteren bir değer döndürür.

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

*`x`*\
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**`_fpclass`** Ve **`_fpclassf`** işlevleri, bağımsız değişkenin kayan nokta sınıflandırmasını gösteren bir tamsayı değeri döndürür *`x`* . Sınıflandırma, içinde tanımlanan aşağıdaki değerlerden birine sahip olabilir `<float.h>` .

|Değer|Açıklama|
|-----------|-----------------|
|**`_FPCLASS_SNAN`**|Sinyal NaN|
|**`_FPCLASS_QNAN`**|Sessiz NaN|
|**`_FPCLASS_NINF`**|Negatif sonsuzluk ( `-INF` )|
|**`_FPCLASS_NN`**|Negatif normalleştirilmiş sıfır olmayan|
|**`_FPCLASS_ND`**|Negatif Normalleştirilmemiş|
|**`_FPCLASS_NZ`**|Negatif sıfır (-0)|
|**`_FPCLASS_PZ`**|Pozitif 0 (+ 0)|
|**`_FPCLASS_PD`**|Olumlu olarak yoğun|
|**`_FPCLASS_PN`**|Pozitif normalleştirilmiş sıfır olmayan|
|**`_FPCLASS_PINF`**|Pozitif sonsuzluk ( `+INF` )|

## <a name="remarks"></a>Açıklamalar

**`_fpclass`** Ve **`_fpclassf`** Işlevleri, Microsoft 'a özgüdür. Bunlara benzerdir [`fpclassify`](fpclassify.md) , ancak bağımsız değişkenle ilgili daha ayrıntılı bilgi geri döndürür. **`_fpclassf`** İşlevi yalnızca x64 platformu için derlendikleri zaman kullanılabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**`_fpclass`**, **`_fpclassf`**|`<float.h>`|

Daha fazla uyumluluk ve uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[`isnan`, `_isnan`, `_isnanf`](isnan-isnan-isnanf.md)\
[`fpclassify`](fpclassify.md)