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
ms.openlocfilehash: d72cfaae2e7f6768a68439fbc30aa5ab0d38f270
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686424"
---
# <a name="shuffle_order_engine-class"></a>shuffle_order_engine Sınıfı

Temel altyapısından döndürülen değerleri yeniden sıralayarak rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>Parametreler

*Motor* \
Temel altyapı türü.

*K* \
**Tablo boyutu**. Arabellekteki öğelerin sayısı (tablo). **Önkoşul**: `0 < K`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|

Altyapı üyeleri hakkında daha fazla bilgi için bkz. [\<random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, temel altyapısının döndürdüğü değerleri yeniden sıralayarak değerler üreten bir *altyapı bağdaştırıcısını* açıklar. Her Oluşturucu iç tabloyu temel altyapının döndürdüğü *K* değerleriyle doldurur ve bir değer istendiğinde, tablodan rastgele bir öğe seçilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<random >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random >](../standard-library/random.md)
