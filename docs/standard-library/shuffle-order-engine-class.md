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
ms.openlocfilehash: bf767c12a19e4ae47c34a8f01e1b1a2f1e028eb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676661"
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine Sınıfı

Kendi temel altyapısından döndürülen değerlerden yeniden sıralayarak rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısı*<br/>
Temel altyapısı türü.

*K*<br/>
**Tablo boyutu**. ' % S'arabelleği (tablo) içindeki öğelerin sayısı. **Önkoşul**: `0 < K`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|

Altyapısı üyeleri hakkında daha fazla bilgi için bkz. [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının açıklayan bir *altyapısı bağdaştırıcısı* değerler üreten kendi temel altyapısıyla döndürülen değerlerden yeniden sıralayarak. Her Oluşturucu, iç tablo ile doldurur. *K* temel altyapısıyla döndürülen ve bir değer istendiğinde tablodan rastgele bir öğe seçilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
