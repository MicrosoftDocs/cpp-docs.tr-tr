---
title: fpclassify
ms.date: 04/05/2018
api_name:
- fpclassify
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
api_type:
- HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: 75cfdc33c21059e190fd04f4cd1b73716e74ac42
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213586"
---
# <a name="fpclassify"></a>fpclassify

Bağımsız değişkenin kayan nokta sınıflandırmasını döndürür.

## <a name="syntax"></a>Söz dizimi

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**fpsınıflandır** *x*bağımsız değişkeninin kayan nokta sınıfını gösteren bir tamsayı değeri döndürür. Bu tablo, içinde tanımlanan **fpsınıflandır**tarafından döndürülen olası değerleri gösterir \<math.h> .

|Değer|Açıklama|
|-----------|-----------------|
|**FP_NAN**|Sessiz, sinyal veya belirsiz NaN|
|**FP_INFINITE**|Pozitif veya negatif sonsuzluk|
|**FP_NORMAL**|Pozitif veya negatif normalleştirilmiş sıfır olmayan bir değer|
|**FP_SUBNORMAL**|Pozitif veya negatif bir eşit değer|
|**FP_ZERO**|Pozitif veya negatif sıfır değeri|

## <a name="remarks"></a>Açıklamalar

C 'de, **fpsınıflandır** bir makrodur; C++ ' da, **fpsınıflandır** , veya bağımsız değişken türleri kullanılarak aşırı yüklenmiş bir işlevdir **`float`** **`double`** **`long double`** . Her iki durumda da, döndürülen değer, herhangi bir ara gösterimde değil, bağımsız değişken ifadesinin etkin türüne bağlıdır. Örneğin, normal **`double`** veya değer, **`long double`** bir sonsuza dönüştürüldüğünde bir Infinity, denormal veya sıfır değeri olabilir **`float`** .

## <a name="requirements"></a>Gereksinimler

|İşlev/makro|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> veya \<cmath>|

**Fpsınıflandır** makrosu ve **fpsınıflandır** Işlevleri ISO C99 ve c++ 11 belirtimlerine uyar. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
