---
title: shuffle_order_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
ms.openlocfilehash: 49841d0527d82bf5877322a7c4dab17e95a3360e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846205"
---
# <a name="shuffle_order_engine-class"></a>shuffle_order_engine Sınıfı

Temel altyapısından döndürülen değerleri yeniden sıralayarak rastgele bir sıra üretir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısına*\
Temel altyapı türü.

*Ek*\
**Tablo boyutu**. Arabellekteki öğelerin sayısı (tablo). **Önkoşul**: `0 < K`

## <a name="members"></a>Üyeler

`shuffle_order_engine::shuffle_order_engine`\
`shuffle_order_engine::base`\
`shuffle_order_engine::base_type`\
`shuffle_order_engine::discard`\
`shuffle_order_engine::operator()`\
`shuffle_order_engine::seed`

Altyapı üyeleri hakkında daha fazla bilgi için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, temel altyapısının döndürdüğü değerleri yeniden sıralayarak değerler üreten bir *altyapı bağdaştırıcısını* açıklar. Her Oluşturucu iç tabloyu temel altyapının döndürdüğü *K* değerleriyle doldurur ve bir değer istendiğinde, tablodan rastgele bir öğe seçilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
