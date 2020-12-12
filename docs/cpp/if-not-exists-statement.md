---
description: 'Hakkında daha fazla bilgi edinin: __if_not_exists ekstresi'
title: __if_not_exists Deyimi
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 29f98c2d07858077207c10dfcdd45b9ce51268e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113954"
---
# <a name="__if_not_exists-statement"></a>__if_not_exists Deyimi

**`__if_not_exists`** İfade, belirtilen tanımlayıcının mevcut olup olmadığını test eder. Tanımlayıcı yoksa, belirtilen ifade bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Parametreler

*Tanımlayıcısını*\
Varlığını test etmek istediğiniz tanımlayıcı.

*deyimler*\
*Tanımlayıcı* yoksa yürütülecek bir veya daha fazla deyim.

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> En güvenilir sonuçlara ulaşmak için **`__if_not_exists`** aşağıdaki kısıtlamaların altındaki ifadesini kullanın.

- **`__if_not_exists`** İfadeyi şablonlara değil yalnızca basit türlere uygulayın.

- İfadeyi, **`__if_not_exists`** bir sınıfın içindeki veya dışındaki tanımlayıcılara uygulayın. **`__if_not_exists`** İfadeyi yerel değişkenlere uygulamayın.

- **`__if_not_exists`** Yalnızca bir işlevin gövdesinde ifadesini kullanın. Bir işlevin gövdesi dışında, **`__if_not_exists`** ifade yalnızca tam olarak tanımlanmış türleri test edebilir.

- Aşırı yüklenmiş işlevler için test ettiğinizde, belirli bir aşırı yükleme formu için test edilemez.

**`__if_not_exists`** Deyimden tamamlama [__if_exists](../cpp/if-exists-statement.md) deyimidir.

## <a name="example"></a>Örnek

Kullanımı hakkında bir örnek için **`__if_not_exists`** , bkz. [__if_exists bildirisi](../cpp/if-exists-statement.md).

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[__if_exists ekstresi](../cpp/if-exists-statement.md)
