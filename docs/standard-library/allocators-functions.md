---
title: '&lt;ayrıcılar&gt; makroları'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::ALLOCATOR_DECL
- allocators/std::CACHE_CHUNKLIST
- allocators/std::CACHE_FREELIST
- allocators/std::CACHE_SUBALLOC
- allocators/std::SYNC_DEFAULT
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
helpviewer_keywords:
- std::ALLOCATOR_DECL [C++]
- std::CACHE_CHUNKLIST [C++]
- std::CACHE_FREELIST [C++]
- std::CACHE_SUBALLOC [C++]
- std::SYNC_DEFAULT [C++]
ms.openlocfilehash: 10cd1d51c2cd6053dcbaa0f5bf1548f80ed01659
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448233"
---
# <a name="ltallocatorsgt-macros"></a>&lt;ayrıcılar&gt; makroları

||||
|-|-|-|
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|

## <a name="allocator_decl"></a>  ALLOCATOR_DECL

Ayırıcı şablon sınıfı verir.

```cpp
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```

### <a name="remarks"></a>Açıklamalar

`template <class Type> class name {.....}` Makro bir şablon tanımı ve bir özelleşmenin `template <> class name<void> {.....}` birlikte, eşitleme filtresini `sync` kullanan bir ayırıcı şablon sınıfını ve türü `cache`bir önbelleği tanımlar.

Yeniden bağlama derleyemeyen derleyiciler için, sonuçta elde edilen şablon tanımı şöyle görünür:

```cpp
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };
```

Yeniden bağlama Derlenemeyen derleyiciler için, sonuçta elde edilen şablon tanımı şöyle görünür:

```cpp
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```

## <a name="cache_chunklist"></a>CACHE_CHUNKLIST

Verir `stdext::allocators::cache_chunklist<sizeof(Type)>`.

```cpp
#define CACHE_CHUNKLIST <cache_class>
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_freelist"></a>CACHE_FREELIST

Verir `stdext::allocators::cache_freelist<sizeof(Type), max>`.

```cpp
#define CACHE_FREELIST(max) <cache_class>
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_suballoc"></a>  CACHE_SUBALLOC

Verir `stdext::allocators::cache_suballoc<sizeof(Type)>`.

```cpp
#define CACHE_SUBALLOC <cache_class>
```

### <a name="remarks"></a>Açıklamalar

## <a name="sync_default"></a>SYNC_DEFAULT

Bir eşitleme filtresi verir.

```cpp
#define SYNC_DEFAULT <sync_template>
```

### <a name="remarks"></a>Açıklamalar

Bir derleyici, tek iş parçacıklı ve çok iş parçacıklı uygulamaları derlemeyi destekliyorsa, makronun `stdext::allocators::sync_none` `stdext::allocators::sync_shared`yaptığı tek iş parçacıklı uygulamalar için, yaptığı tüm diğer durumlarda.

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
