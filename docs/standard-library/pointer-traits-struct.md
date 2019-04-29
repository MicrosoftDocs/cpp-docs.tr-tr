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
ms.openlocfilehash: b661d4b36ce48a08faba6638c5114f3f4e6981a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370391"
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
   static pointer pointer_to(element_type& obj);
   // optional
   };
```

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`typedef T2 difference_type`|Türü `T2` olduğu `Ptr::difference_type` türü varsa, aksi takdirde, `ptrdiff_t`. Varsa `Ptr` ham bir işaretçi türü `ptrdiff_t`.|
|`typedef T1 element_type`|Türü `T1` olduğu `Ptr::element_type` türü varsa, aksi takdirde, `Ty`. Varsa `Ptr` ham bir işaretçi türü `Ty`.|
|`typedef Ptr pointer`|Türü `Ptr`.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|`pointer_traits::rebind`|Temel alınan işaretçiye dönüştürmek için girişimleri için belirtilen bir türün yazın.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[pointer_to](#pointer_to)|Rastgele bir başvuru sınıfının bir nesnesi için dönüştürür `Ptr`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="pointer_to"></a>  pointer_to

Döndüren statik yöntem `Ptr::pointer_to(obj)`, bu işlev zaten varsa. Aksi takdirde, rastgele bir başvuru sınıfının bir nesnesi için dönüştürülmesi mümkün değil `Ptr`. Varsa `Ptr` bu yöntemi döndürür bir ham işaretçi olan `addressof(obj)`.

```cpp
static pointer pointer_to(element_type& obj);
```

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
[allocator_traits Sınıfı](../standard-library/allocator-traits-class.md)<br/>
