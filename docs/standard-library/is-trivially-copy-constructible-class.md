---
title: is_trivially_copy_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73928574f2c96da952b7f18908c6b7a175549981
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible Sınıfı

Önemsiz kopya Oluşturucu türündeyse testleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` false tuttuğu Önemsiz kopya Oluşturucu, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir kopya Oluşturucu `T` bu örtülü olarak bildirilen, sınıf deyimle `T` hiçbir sanal işlevleri veya sanal tabanları, sınıfın tüm doğrudan temellerine sahip `T` Önemsiz kopya oluşturucuları, tüm statik olmayan sınıflarını sahip veri üyeleri sınıf türü Önemsiz kopya oluşturucuları, ve önemsiz kopya oluşturucuları dizisi türünde sınıfı tüm statik olmayan veri üyeleri sınıflarını sahiptir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
