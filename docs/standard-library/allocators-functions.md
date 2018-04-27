---
title: '&lt;allocators&gt; makroları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/std::ALLOCATOR_DECL
- allocators/std::CACHE_CHUNKLIST
- allocators/std::CACHE_FREELIST
- allocators/std::CACHE_SUBALLOC
- allocators/std::SYNC_DEFAULT
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
caps.latest.revision: 12
manager: ghogen
helpviewer_keywords:
- std::ALLOCATOR_DECL [C++]
- std::CACHE_CHUNKLIST [C++]
- std::CACHE_FREELIST [C++]
- std::CACHE_SUBALLOC [C++]
- std::SYNC_DEFAULT [C++]
ms.openlocfilehash: b06ede32746c13244db622788e7e9c6f7cbe4cc9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltallocatorsgt-macros"></a>&lt;allocators&gt; makroları

||||
|-|-|-|
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|

## <a name="allocator_decl"></a>  ALLOCATOR_DECL

Bir ayırıcı Şablon sınıfı verir.

```cpp
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```

### <a name="remarks"></a>Açıklamalar

Bir şablon tanımı makrosu verir `template <class Type> class name {.....}` ve bir uzmanlık `template <> class name<void> {.....}` eşitleme filtresi kullanan bir ayırıcı Şablon sınıfı birlikte tanımlayan `sync` ve bir önbellek türü `cache`.

Yeniden bağlamasını derleyebilirsiniz derleyicileri elde edilen şablon tanımının şöyle görünür:

```cpp
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };
```

Yeniden bağlamasını derlenemiyor derleyicileri için sonuçta elde edilen şablon tanımının şöyle görünür:

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

Derleyici tek iş parçacıklı hem çok iş parçacıklı uygulamalar derleme destekliyorsa, tek iş parçacıklı uygulamalar için makrosu verir `stdext::allocators::sync_none`; bunu verir tüm durumlarda `stdext::allocators::sync_shared`.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
