---
title: discard_block_engine Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: a0df754f53b52c134b9eb1126f90882ceaaf1e2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386206"
---
# <a name="discardblockengine-class"></a>discard_block_engine Sınıfı

Değerleri kendi temel altyapısıyla döndürülen atarak rastgele bir sıra üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Parametreler

*Altyapısı*<br/>
Temel altyapısı türü.

*P*<br/>
**Bloğu boyutunu**. Değerleri blokların sayısı.

*R*<br/>
**Kullanılan blok**. Her bir blok içinde kullanılan değerleri sayısı. Rest atılır (`P` - `R`). **Önkoşul**: `0 < R ≤ P`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

Altyapısı üyeleri hakkında daha fazla bilgi için bkz. [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfı, değerleri kendi temel altyapısıyla döndürülen değerlerden bazıları atarak üreten bir altyapısı bağdaştırıcısını açıklar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
