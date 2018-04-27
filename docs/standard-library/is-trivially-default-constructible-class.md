---
title: is_trivially_default_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 581ebc488e733bfb149f9074126ce721b78df156
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible Sınıfı

Testleri Önemsiz varsayılan oluşturucu türüne sahip.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bir önemsiz oluşturucusu, aksi durumda olan bir sınıftır.

Bir sınıf için varsayılan bir oluşturucu `Ty` deyimle varsa:

- örtük olarak bildirilen varsayılan bir oluşturucu olduğu

- sınıf `Ty` hiçbir sanal işleve sahip

- sınıf `Ty` hiçbir sanal temellerine sahip

- tüm doğrudan taban sınıfının `Ty` Önemsiz oluşturucular sahip

- sınıf türü tüm statik olmayan veri üyeleri sınıflarını Önemsiz oluşturucular sahip

- sınıf türü dizisi tüm statik olmayan veri üyeleri sınıflarını Önemsiz oluşturucular sahip

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
