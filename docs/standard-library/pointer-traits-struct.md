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
ms.openlocfilehash: 6d89348867982bfb86c0bf2404a017f6a448d1a1
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687135"
---
# <a name="pointer_traits-struct"></a>pointer_traits Yapısı

@No__t_1 işaretçi türündeki bir ayırıcıyı tanımlayan `allocator_traits` türünde bir nesne için gereken bilgileri sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ptr>
    struct pointer_traits;
```

## <a name="remarks"></a>Açıklamalar

PTR, `Ty *` türünde bir ham işaretçi veya aşağıdaki özelliklere sahip bir sınıf olabilir.

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
|`typedef T2 difference_type`|@No__t_0 tür varsa `Ptr::difference_type`, aksi takdirde `ptrdiff_t`. @No__t_0 bir ham işaretçisiyse, tür `ptrdiff_t`.|
|`typedef T1 element_type`|@No__t_0 tür varsa `Ptr::element_type`, aksi takdirde `Ty`. @No__t_0 bir ham işaretçisiyse, tür `Ty`.|
|`typedef Ptr pointer`|Tür `Ptr`.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|`rebind`|Temel alınan işaretçi türünü belirtilen bir türe dönüştürmeye çalışır.|

### <a name="methods"></a>Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[pointer_to](#pointer_to)|@No__t_0 sınıfının bir nesnesine rastgele bir başvuru dönüştürür.|

### <a name="pointer_to"></a>pointer_to

Bu işlev varsa `Ptr::pointer_to(obj)` döndüren statik yöntem. Aksi takdirde, `Ptr` sınıfının bir nesnesine rastgele bir başvuru dönüştürmek mümkün değildir. @No__t_0 bir ham işaretçisiyse, bu yöntem `addressof(obj)` döndürür.

```cpp
static pointer pointer_to(element_type& obj);
```
