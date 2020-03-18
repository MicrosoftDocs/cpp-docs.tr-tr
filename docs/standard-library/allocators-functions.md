---
title: '&lt;ayrıcılar&gt; makrolar'
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
ms.openlocfilehash: 5355661e370daf8826541c036f7301e5c25788d7
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416930"
---
# <a name="ltallocatorsgt-macros"></a>&lt;ayrıcılar&gt; makrolar

||||
|-|-|-|
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|

## <a name="allocator_decl"></a>ALLOCATOR_DECL

Ayırıcı sınıf şablonu verir.

```cpp
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```

### <a name="remarks"></a>Açıklamalar

Makro `template <class Type> class name {.....}` bir şablon tanımı ve bir özelleştirme `template <> class name<void> {.....}` ve bu, birlikte eşitleme filtresi `sync` ve `cache`türünde bir önbellek kullanan bir ayırıcı sınıfı şablonu tanımlar.

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

`stdext::allocators::cache_chunklist<sizeof(Type)>`verir.

```cpp
#define CACHE_CHUNKLIST <cache_class>
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_freelist"></a>CACHE_FREELIST

`stdext::allocators::cache_freelist<sizeof(Type), max>`verir.

```cpp
#define CACHE_FREELIST(max) <cache_class>
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_suballoc"></a>CACHE_SUBALLOC

`stdext::allocators::cache_suballoc<sizeof(Type)>`verir.

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

Bir derleyici, tek iş parçacıklı ve çok iş parçacıklı uygulamalar derlemeyi destekliyorsa, makro `stdext::allocators::sync_none`verir; diğer tüm durumlarda `stdext::allocators::sync_shared`verir.

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
