---
description: 'Hakkında daha fazla bilgi edinin: pointer_traits struct'
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
ms.openlocfilehash: ba89d4df45517c142cad172860e4c9ab4d386ce1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340690"
---
# <a name="pointer_traits-struct"></a>pointer_traits Yapısı

`allocator_traits`İşaretçi türü olan bir ayırıcıyı tanımlayan türünde bir nesne için gereken bilgileri sağlar `Ptr` .

## <a name="syntax"></a>Syntax

```cpp
template <class Ptr>
    struct pointer_traits;
```

## <a name="remarks"></a>Açıklamalar

PTR `Ty *` , türün veya aşağıdaki özelliklere sahip bir sınıfın ham bir işaretçisi olabilir.

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

|Ad|Açıklama|
|-|-|
|`typedef T2 difference_type`|Türü `T2` `Ptr::difference_type` Bu tür varsa, aksi durumda `ptrdiff_t` . `Ptr`Bir ham işaretçisiyse tür olur `ptrdiff_t` .|
|`typedef T1 element_type`|Türü `T1` `Ptr::element_type` Bu tür varsa, aksi durumda `Ty` . `Ptr`Bir ham işaretçisiyse tür olur `Ty` .|
|`typedef Ptr pointer`|Türü `Ptr` .|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|-|-|
|`rebind`|Temel alınan işaretçi türünü belirtilen bir türe dönüştürmeye çalışır.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[pointer_to](#pointer_to)|Rastgele bir başvuruyu sınıfının nesnesine dönüştürür `Ptr` .|

### <a name="pointer_to"></a><a name="pointer_to"></a> pointer_to

Bu işlev varsa, döndüren statik yöntem `Ptr::pointer_to(obj)` . Aksi takdirde, rastgele bir başvuruyu sınıfının nesnesine dönüştürmek mümkün değildir `Ptr` . `Ptr`Bir ham işaretçisiyse, bu yöntem döndürür `addressof(obj)` .

```cpp
static pointer pointer_to(element_type& obj);
```
