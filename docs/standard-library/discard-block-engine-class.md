---
description: 'Hakkında daha fazla bilgi edinin: discard_block_engine sınıfı'
title: discard_block_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: 0879dacac70afc78a9c77314ce5042580c6cbb39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324522"
---
# <a name="discard_block_engine-class"></a>discard_block_engine Sınıfı

Temel altyapısının döndürdüğü değerleri atarak rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısına*\
Temel altyapı türü.

*Lama*\
**Blok boyutu**. Her bloktaki değer sayısı.

*Sağ*\
**Kullanılan blok**. Kullanılan her bloktaki değer sayısı. Rest atılır ( `P`  -  `R` ). **Önkoşul**: `0 < R ≤ P`

## <a name="members"></a>Üyeler

`discard_block_engine::discard_block_engine`\
`discard_block_engine::base`\
`discard_block_engine::base_type`\
`discard_block_engine::discard`\
`discard_block_engine::operator()`\
`discard_block_engine::seed`

Altyapı üyeleri hakkında daha fazla bilgi için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, temel altyapısının döndürdüğü bazı değerleri atarak değer üreten bir altyapı bağdaştırıcısını açıklar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
