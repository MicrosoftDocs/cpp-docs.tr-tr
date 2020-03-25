---
title: __if_not_exists Deyimi
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 7372ac127a7b4dd5c05d58cfecca25f87690b0ae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178204"
---
# <a name="__if_not_exists-statement"></a>__if_not_exists Deyimi

**__İf_not_exists** ifade, belirtilen tanımlayıcının mevcut olup olmadığını test eder. Tanımlayıcı yoksa, belirtilen ifade bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tanımlayıcısını*|Varlığını test etmek istediğiniz tanımlayıcı.|
|*deyimler*|*Tanımlayıcı* yoksa yürütülecek bir veya daha fazla deyim.|

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  En güvenilir sonuçlara ulaşmak için aşağıdaki kısıtlamalarda **__if_not_exists** ifadesini kullanın.

- **__İf_not_exists** deyiminizi şablonlara değil yalnızca basit türlere uygulayın.

- **__İf_not_exists** ifadesini, bir sınıfın içindeki veya dışındaki tanımlayıcılara uygulayın. **__İf_not_exists** ifadesini yerel değişkenlere uygulamayın.

- **__İf_not_exists** ifadesini yalnızca bir işlevin gövdesinde kullanın. Bir işlevin gövdesi dışında, **__if_not_exists** deyimleri yalnızca tam olarak tanımlanmış türleri test edebilir.

- Aşırı yüklenmiş işlevler için test ettiğinizde, belirli bir aşırı yükleme formu için test edilemez.

**__İf_not_exists** deyimin tamamlaması [__if_exists](../cpp/if-exists-statement.md) deyimidir.

## <a name="example"></a>Örnek

**__İf_not_exists**kullanma hakkında bir örnek için bkz. [__if_exists bildirisi](../cpp/if-exists-statement.md).

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[__if_exists Deyimi](../cpp/if-exists-statement.md)
