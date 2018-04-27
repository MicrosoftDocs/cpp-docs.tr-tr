---
title: shuffle_order_engine sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6f5d62394a4955e11b31b4d0b3c134cd0840d3e5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine Sınıfı

Kendi temel altyapısı döndürdüğü değer sıralayarak rastgele bir sıra oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>Parametreler

`Engine` Temel altyapısı türü.

`K` **Tablo boyutunu**. Arabellek (tablo) öğe sayısı. **Önkoşul**: `0 < K`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|

Altyapısı üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıf tanımlar bir *motoru bağdaştırıcı* , üreten değerleri kendi temel altyapı tarafından döndürülen değer sıralayarak. İç tabloyla her Oluşturucusu doldurur `K` temel altyapısı tarafından döndürülen ve bir değer istendiğinde rastgele öğesi tablosundan seçilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
