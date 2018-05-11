---
title: is_trivially_copy_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01c95007f1db1bcaf549398fa8865a9e51fe23d1
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
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
