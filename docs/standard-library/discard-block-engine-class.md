---
title: discard_block_engine sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b814f64f340577508add6bf3c0f85ffac0786db7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="discardblockengine-class"></a>discard_block_engine Sınıfı

Kendi temel altyapı tarafından döndürülen değer atarak rastgele bir sıra oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>Parametreler

`Engine` Temel altyapısı türü.

`P` **Bloğu boyutunu**. Her bloğundaki değerlerinin sayısı.

`R` **Kullanılan blok**. Kullanılan değerleri her bloğundaki sayısı. Rest atılır ( `P`  -  `R`). **Önkoşul**: `0 < R ≤ P`

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|

Altyapısı üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıf kendi temel altyapı tarafından döndürülen değerlerin bazılarını atarak değerleri üreten bir motoru bağdaştırıcı açıklar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
