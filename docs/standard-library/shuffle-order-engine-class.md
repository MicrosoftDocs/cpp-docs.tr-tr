---
title: shuffle_order_engine sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13b46bcd29624d696ae22494c394fa028d58fa8a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961980"
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine Sınıfı

Kendi temel altyapısından döndürülen değerlerden yeniden sıralayarak rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısı* temel altyapısı türü.

*K* **tablo boyutu**. ' % S'arabelleği (tablo) içindeki öğelerin sayısı. **Önkoşul**: `0 < K`

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
