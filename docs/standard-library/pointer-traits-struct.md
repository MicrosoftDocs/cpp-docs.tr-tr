---
title: pointer_traits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
dev_langs:
- C++
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e6e6f6ca6c62e0dcb1d44d5f86a19e8a339a6b1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="pointertraits-struct"></a>pointer_traits Yapısı

Şablon sınıfın bir nesnesi tarafından gereken tek bilgi sağlayan `allocator_traits` işaretçi türü ile bir ayırıcı açıklamak için `Ptr`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ptr>
struct pointer_traits;
```

## <a name="remarks"></a>Açıklamalar

PTR türündeki ham bir işaretçi olabilir `Ty *` veya aşağıdaki özelliklerle bir sınıf.

```cpp
struct Ptr
   { // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj);
   // optional
   };
```

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`typedef T2 difference_type`|Türü `T2` olan `Ptr::difference_type` türü varsa, aksi takdirde, `ptrdiff_t`. Varsa `Ptr` ham işaretçi türü `ptrdiff_t`.|
|`typedef T1 element_type`|Türü `T1` olan `Ptr::element_type` türü varsa, aksi takdirde, `Ty`. Varsa `Ptr` ham işaretçi türü `Ty`.|
|`typedef Ptr pointer`|Tür `Ptr`.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|`pointer_traits::rebind`|Temel alınan işaretçi Dönüştür girişimleri için belirtilen bir türün yazın.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[pointer_to](#pointer_to)|Sınıfın bir nesnesi için rasgele bir başvuru dönüştürür `Ptr`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="pointer_to"></a>  pointer_to

Döndüren statik yöntem `Ptr::pointer_to(obj)`, bu işlevin varsa. Aksi takdirde, sınıfın bir nesnesi için rasgele bir başvuru dönüştürülmesi mümkün değil `Ptr`. Varsa `Ptr` bir ham, bu yöntem işaretçidir `addressof(obj)`.

```cpp
static pointer pointer_to(element_type& obj);
```

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
[allocator_traits Sınıfı](../standard-library/allocator-traits-class.md)<br/>
