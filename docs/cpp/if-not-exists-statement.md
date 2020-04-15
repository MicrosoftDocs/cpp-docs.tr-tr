---
title: __if_not_exists Deyimi
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 1118f9fcca525b2b2d5869fb507ee974d2b0d28f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374136"
---
# <a name="__if_not_exists-statement"></a>__if_not_exists Deyimi

**__if_not_exists** deyimi, belirtilen tanımlayıcının var olup olmadığını sınar. Tanımlayıcı yoksa, belirtilen deyim bloğu yürütülür.

## <a name="syntax"></a>Sözdizimi

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tanımlayıcı*|Varlığını test etmek istediğiniz tanımlayıcı.|
|*Ifa -de*|*Tanımlayıcı* yoksa yürütülecek bir veya daha fazla deyim.|

## <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> En güvenilir sonuçları elde etmek için aşağıdaki kısıtlamalar altında **__if_not_exists** deyimini kullanın.

- **__if_not_exists** deyimini şablonlara değil, yalnızca basit türlere uygulayın.

- **__if_not_exists** deyimini sınıf içinde veya dışında tanımlayıcılara uygulayın. **__if_not_exists** deyimini yerel değişkenlere uygulamayın.

- **__if_not_exists** ifadesini yalnızca bir işlevin gövdesinde kullanın. Bir işlevin gövdesi dışında, **__if_not_exists** deyimi yalnızca tam olarak tanımlanmış türleri test edebilir.

- Aşırı yüklü işlevleri test ettiğinizde, aşırı yüklemenin belirli bir formunu test edemezsiniz.

**__if_not_exists** deyiminin tamamlayıcısı [__if_exists](../cpp/if-exists-statement.md) ifadesidir.

## <a name="example"></a>Örnek

**__if_not_exists**nasıl kullanılacağı yla ilgili bir örnek için, [__if_exists Bildirimi'ne](../cpp/if-exists-statement.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[__if_exists Deyimi](../cpp/if-exists-statement.md)
