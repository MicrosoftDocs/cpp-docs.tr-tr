---
title: '&lt;Ayırıcılar&gt; makroları'
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
ms.openlocfilehash: 736e587a41fa1006801dcf6930b33ee434c9a5ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179217"
---
# <a name="ltallocatorsgt-macros"></a>&lt;Ayırıcılar&gt; makroları

||||
|-|-|-|
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|

## <a name="allocator_decl"></a>  ALLOCATOR_DECL

Şablon sınıfı bir ayırıcı verir.

```cpp
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```

### <a name="remarks"></a>Açıklamalar

Bir şablon tanımı makro verir `template <class Type> class name {.....}` ve özelleştirmesi `template <> class name<void> {.....}` eşitleme filtresi kullanan bir ayırıcı şablon sınıf birlikte tanımlayan `sync` ve bir önbellek türü `cache`.

Yeniden bağlamasını derleyebilirsiniz derleyiciler, sonuçta elde edilen şablon tanımı şöyle görünür:

```cpp
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };
```

Yeniden bağlamasını derlenemez derleyicileri için ortaya çıkan şablon tanımı şöyle görünür:

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

## <a name="cache_chunklist"></a>  CACHE_CHUNKLIST

Verir `stdext::allocators::cache_chunklist<sizeof(Type)>`.

```cpp
#define CACHE_CHUNKLIST <cache_class>
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_freelist"></a>  CACHE_FREELIST

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

## <a name="sync_default"></a>  SYNC_DEFAULT

Eşitleme filtresi verir.

```cpp
#define SYNC_DEFAULT <sync_template>
```

### <a name="remarks"></a>Açıklamalar

Derleyici, hem tek iş parçacıklı ve çok iş parçacıklı uygulamalar derleme destekliyorsa, tek iş parçacıklı uygulamalar için makro verir `stdext::allocators::sync_none`; verir, diğer tüm durumlarda `stdext::allocators::sync_shared`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
