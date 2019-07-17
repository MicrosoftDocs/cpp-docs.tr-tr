---
title: pointer_traits Yapısı
ms.date: 11/04/2016
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
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
ms.openlocfilehash: 109e51ad9eba54f31b90da9b8b85bec105c7dce6
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240417"
---
# <a name="pointertraits-struct"></a>pointer_traits Yapısı

Şablon sınıfın bir nesnesinin gerektirdiği bilgileri sağlar `allocator_traits` bir ayırıcı işaretçi türü ile açıklamak için `Ptr`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ptr>
    struct pointer_traits;
```

## <a name="remarks"></a>Açıklamalar

PTR, bir ham işaretçi türü olabilir `Ty *` veya aşağıdaki özelliklere sahip bir sınıf.

```cpp
struct Ptr
{ // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj); // optional
};
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|`typedef T2 difference_type`|Türü `T2` olduğu `Ptr::difference_type` türü varsa, aksi takdirde, `ptrdiff_t`. Varsa `Ptr` ham bir işaretçi türü `ptrdiff_t`.|
|`typedef T1 element_type`|Türü `T1` olduğu `Ptr::element_type` türü varsa, aksi takdirde, `Ty`. Varsa `Ptr` ham bir işaretçi türü `Ty`.|
|`typedef Ptr pointer`|Türü `Ptr`.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|`rebind`|Temel alınan işaretçiye dönüştürmek için girişimleri için belirtilen bir türün yazın.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[pointer_to](#pointer_to)|Rastgele bir başvuru sınıfının bir nesnesi için dönüştürür `Ptr`.|

### <a name="pointer_to"></a> pointer_to

Döndüren statik yöntem `Ptr::pointer_to(obj)`, bu işlev zaten varsa. Aksi takdirde, rastgele bir başvuru sınıfının bir nesnesi için dönüştürülmesi mümkün değil `Ptr`. Varsa `Ptr` bu yöntemi döndürür bir ham işaretçi olan `addressof(obj)`.

```cpp
static pointer pointer_to(element_type& obj);
```
