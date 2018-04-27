---
title: discard_block_engine sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::discard_block_engine
dev_langs:
- C++
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59136111b6d4f594d84040c02270b219ad55ae0f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
