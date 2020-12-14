---
description: 'Daha fazla bilgi edinin: matematik hata sabitleri'
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
ms.openlocfilehash: e5f94f94a28543f0405cce57941a872c416d0c20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258752"
---
# <a name="math-error-constants"></a>Matematik Hatası Sabitleri

## <a name="syntax"></a>Syntax

```
#include <math.h>
```

## <a name="remarks"></a>Açıklamalar

Çalışma zamanı kitaplığının matematik yordamları matematik hatası sabitleri oluşturabilir.

Aşağıdaki gibi açıklanan bu hatalar, matematık bölümünde tanımlanan özel durum türlerine karşılık gelir. Ve `_matherr` bir matematik hatası oluştuğunda işlev tarafından döndürülür.

|Sabit|Anlamı|
|--------------|-------------|
|`_DOMAIN`|İşlevin bağımsız değişkeni işlevin etki alanının dışında.|
|`_OVERFLOW`|Sonuç işlevin dönüş türünde gösterilemeyecek kadar büyük.|
|`_PLOSS`|Kısmi anlamlı kaybı oluştu.|
|`_SING`|Bağımsız değişken Singular: işlevin bağımsız değişkeni geçersiz değere sahip. (Örneğin, 0 değeri sıfır dışında bir değer gerektiren işleve geçirilir.)|
|`_TLOSS`|Toplam anlam kaybı oluştu.|
|`_UNDERFLOW`|Sonuç gösterilemeyecek kadar küçük.|

## <a name="see-also"></a>Ayrıca bkz.

[_matherr](../c-runtime-library/reference/matherr.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
