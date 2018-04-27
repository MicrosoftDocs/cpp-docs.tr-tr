---
title: independent_bits_engine sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::independent_bits_engine
dev_langs:
- C++
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01979567e29796288c124e6e5a55dcf9b44ee6e0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="independentbitsengine-class"></a>independent_bits_engine Sınıfı

BITS repacking BITS tarafından belirtilen sayıda numaralarıyla rastgele bir dizi kendi temel altyapı tarafından döndürülen değer oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Parametreler

`Engine` Temel altyapısı türü.

`W` **Word boyutu**. Oluşturulan her sayının bit cinsinden boyutu. **Önkoşul**: `0 < W ≤ numeric_limits<UIntType>::digits`

`UIntType` İşaretsiz tamsayı sonuç türü. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="members"></a>Üyeler

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

Altyapısı üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıf tanımlar bir *motoru bağdaştırıcı* , üreten değerleri bunun sonucunda, temel altyapısı tarafından döndürülen değerler bitten repacking tarafından `W`-bit değerleri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
