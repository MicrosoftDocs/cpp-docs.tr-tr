---
title: Matematik Hatası Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
ms.openlocfilehash: f51d9a3a28118d922f81a44e31c9abc610645f13
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51525002"
---
# <a name="math-error-constants"></a>Matematik Hatası Sabitleri

## <a name="syntax"></a>Sözdizimi

```

#include <math.h>
```

## <a name="remarks"></a>Açıklamalar

Matematik hatası sabitleri çalışma zamanı kitaplığının matematik yordamlarını üretebilir.

Açıklandığı gibi bu hata, MATEMATİK tanımlanan özel durum türlerine karşılık gelir. Tarafından döndürülen H ve bu `_matherr` matematik hata oluştuğunda işlev.

|Sabit|Açıklama|
|--------------|-------------|
|`_DOMAIN`|İşlev bağımsız değişkeni, dışında işlevinin etki alanıdır.|
|`_OVERFLOW`|Sonuç, işlevin dönüş türü gösterilemeyecek kadar çok büyük.|
|`_PLOSS`|Anlam kısmi kaybı oluştu.|
|`_SING`|Bağımsız değişken singularity: işlev bağımsız değişkeni geçersiz bir değere sahip. (Örneğin, değeri 0 sıfır olmayan bir değer gerektiren işleve geçirilir.)|
|`_TLOSS`|Anlam toplam kaybı oluştu.|
|`_UNDERFLOW`|Sonuç gösterilemeyecek kadar çok küçüktür.|

## <a name="see-also"></a>Ayrıca Bkz.

[_matherr](../c-runtime-library/reference/matherr.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)