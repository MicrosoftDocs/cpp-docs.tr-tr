---
title: allocator_traits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::allocator_traits
- memory/std::allocator_traits::propagate_on_container_move_assignment
- memory/std::allocator_traits::const_pointer
- memory/std::allocator_traits::propagate_on_container_swap
- memory/std::allocator_traits::propagate_on_container_copy_assignment
- memory/std::allocator_traits::difference_type
- memory/std::allocator_traits::allocator_type
- memory/std::allocator_traits::value_type
- memory/std::allocator_traits::pointer
- memory/std::allocator_traits::size_type
- memory/std::allocator_traits::const_void_pointer
- memory/std::allocator_traits::void_pointer
- memory/std::allocator_traits::allocate
- memory/std::allocator_traits::construct
- memory/std::allocator_traits::deallocate
- memory/std::allocator_traits::destroy
- memory/std::allocator_traits::max_size
- memory/std::allocator_traits::select_on_container_copy_construction
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
helpviewer_keywords:
- std::allocator_traits [C++]
- std::allocator_traits [C++], propagate_on_container_move_assignment
- std::allocator_traits [C++], const_pointer
- std::allocator_traits [C++], propagate_on_container_swap
- std::allocator_traits [C++], propagate_on_container_copy_assignment
- std::allocator_traits [C++], difference_type
- std::allocator_traits [C++], allocator_type
- std::allocator_traits [C++], value_type
- std::allocator_traits [C++], pointer
- std::allocator_traits [C++], size_type
- std::allocator_traits [C++], const_void_pointer
- std::allocator_traits [C++], void_pointer
- std::allocator_traits [C++], allocate
- std::allocator_traits [C++], construct
- std::allocator_traits [C++], deallocate
- std::allocator_traits [C++], destroy
- std::allocator_traits [C++], max_size
- std::allocator_traits [C++], select_on_container_copy_construction
ms.openlocfilehash: c9c03eb688a71e0587ca4faa14d89d8487d4ec59
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617408"
---
# <a name="allocator_traits-class"></a>allocator_traits Sınıfı

Sınıf şablonu, *ayırıcı türünü*tamamlayan bir nesneyi tanımlar. Ayırıcı türü, ayrılmış depolamayı yönetmek için kullanılan bir ayırıcı nesnesini tanımlayan herhangi bir türdür. Özellikle, her ayırıcı türü için `Alloc` , `allocator_traits<Alloc>` ayırıcı özellikli bir kapsayıcı tarafından ihtiyaç duyulan tüm bilgileri belirtmek için kullanabilirsiniz. Daha fazla bilgi için bkz. varsayılan [ayırıcı sınıfı](allocator-class.md).

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Alloc>
    class allocator_traits;
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|`allocator_type`|Bu tür, şablon parametresi için bir eş anlamlı `Alloc` .|
|`const_pointer`|Bu tür `Alloc::const_pointer` , doğru biçimlendirilmişse, aksi durumda bu tür olur `pointer_traits<pointer>::rebind<const value_type>` .|
|`const_void_pointer`|Bu tür `Alloc::const_void_pointer` , doğru biçimlendirilmişse, aksi durumda bu tür olur `pointer_traits<pointer>::rebind<const void>` .|
|`difference_type`|Bu tür `Alloc::difference_type` , doğru biçimlendirilmişse, aksi durumda bu tür olur `pointer_traits<pointer>::difference_type` .|
|`pointer`|Bu tür `Alloc::pointer` , doğru biçimlendirilmişse, aksi durumda bu tür olur `value_type *` .|
|`propagate_on_container_copy_assignment`|Bu tür `Alloc::propagate_on_container_copy_assignment` , doğru biçimlendirilmişse, aksi durumda bu tür olur `false_type` .|
|`propagate_on_container_move_assignment`|Bu tür `Alloc::propagate_on_container_move_assignment` , doğru biçimlendirilmişse, aksi durumda bu tür olur `false_type` . Tür true olursa, ayırıcı özellikli bir kapsayıcı, depolanan ayırıcıyı bir taşıma atamasında kopyalar.|
|`propagate_on_container_swap`|Bu tür `Alloc::propagate_on_container_swap` , doğru biçimlendirilmişse, aksi durumda bu tür olur `false_type` . Tür true olursa, ayırıcı özellikli bir kapsayıcı, bir takas üzerinde depolanan ayırıcıyı değiştirir.|
|`size_type`|Bu tür `Alloc::size_type` , doğru biçimlendirilmişse, aksi durumda bu tür olur `make_unsigned<difference_type>::type` .|
|`value_type`|Bu tür için bir eş anlamlı `Alloc::value_type` .|
|`void_pointer`|Bu tür `Alloc::void_pointer` , doğru biçimlendirilmişse, aksi durumda bu tür olur `pointer_traits<pointer>::rebind<void>` .|

### <a name="static-methods"></a>Statik yöntemler

Aşağıdaki statik yöntemler, belirtilen bir ayırıcı parametresinde karşılık gelen yöntemi çağırır.

|||
|-|-|
|[allocate](#allocate)|Belirtilen ayırıcı parametresini kullanarak belleği ayıran statik yöntem.|
|[oluşturma](#construct)|Bir nesne oluşturmak için belirtilen ayırıcıyı kullanan statik yöntem.|
|[kaldırmak](#deallocate)|Belirtilen sayıda nesneyi serbest bırakmak için belirtilen ayırıcıyı kullanan statik yöntem.|
|[kaldırılır](#destroy)|Bir nesne üzerinde yıkıcıyı çağırmak için bellek ayırmayı kaldırmadan belirtilen ayırıcıyı kullanan statik yöntem.|
|[max_size](#max_size)|Ayrılabilen en fazla nesne sayısını belirleyebilmek için belirtilen ayırıcıyı kullanan statik yöntem.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|`select_on_container_copy_construction`Belirtilen ayırıcı üzerinde çağıran statik yöntem.|

### <a name="allocate"></a><a name="allocate"></a>allocate

Belirtilen ayırıcı parametresini kullanarak belleği ayıran statik yöntem.

```cpp
static pointer allocate(Alloc& al, size_type count);

static pointer allocate(Alloc& al, size_type count,
    typename allocator_traits<void>::const_pointer* hint);
```

#### <a name="parameters"></a>Parametreler

*Eşkenar*\
Ayırıcı nesne.

*biriktirme*\
Ayrılacak öğe sayısı.

*OPTI*\
`const_pointer`Bu, istek öncesinde ayrılmış bir nesnenin adresini bularak, depolama için isteği karşılarken yer alan ayırıcı nesnesine yardımcı olabilir. Null işaretçi hiçbir ipucu olarak değerlendirilir.

#### <a name="return-value"></a>Dönüş Değeri

Her yöntem, ayrılan nesneye bir işaretçi döndürür.

İlk statik yöntem döndürür `al.allocate(count)` .

İkinci yöntem `al.allocate(count, hint)` , bu ifade doğru biçimlendirilmişse, aksi takdirde döndürülür `al.allocate(count)` .

### <a name="construct"></a><a name="construct"></a>oluşturma

Bir nesne oluşturmak için belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
template <class Uty, class Types>
static void construct(Alloc& al, Uty* ptr, Types&&... args);
```

#### <a name="parameters"></a>Parametreler

*Eşkenar*\
Ayırıcı nesne.

*kaydetmeye*\
Nesnenin oluşturulması gereken konuma yönelik bir işaretçi.

*args*\
Nesne oluşturucusuna geçirilen bağımsız değişkenlerin listesi.

#### <a name="remarks"></a>Açıklamalar

Statik üye işlevi çağırır `al.construct(ptr, args...)` , bu ifade iyi biçimlendirilmişse, aksi takdirde değerlendirilir `::new (static_cast<void *>(ptr)) Uty(std::forward<Types>(args)...)` .

### <a name="deallocate"></a><a name="deallocate"></a>kaldırmak

Belirtilen sayıda nesneyi serbest bırakmak için belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
static void deallocate(Alloc al,
    pointer ptr,
    size_type count);
```

#### <a name="parameters"></a>Parametreler

*Eşkenar*\
Ayırıcı nesne.

*kaydetmeye*\
Serbest bırakmak için nesnelerin başlangıç konumuna yönelik bir işaretçi.

*biriktirme*\
Serbest bırakmak için nesne sayısı.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem çağırır `al.deallocate(ptr, count)` .

Bu yöntem hiçbir şey yapmaz.

### <a name="destroy"></a><a name="destroy"></a>kaldırılır

Bir nesne üzerinde yıkıcıyı çağırmak için bellek ayırmayı kaldırmadan belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
template <class Uty>
    static void destroy(Alloc& al, Uty* ptr);
```

#### <a name="parameters"></a>Parametreler

*Eşkenar*\
Ayırıcı nesne.

*kaydetmeye*\
Nesnenin konumuna yönelik bir işaretçi.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem `al.destroy(ptr)` , bu ifade düzgün biçimlendirilmişse, aksi takdirde değerlendirilir `ptr->~Uty()` .

### <a name="max_size"></a><a name="max_size"></a>max_size

Ayrılabilen en fazla nesne sayısını belirleyebilmek için belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
static size_type max_size(const Alloc& al);
```

#### <a name="parameters"></a>Parametreler

*Eşkenar*\
Ayırıcı nesne.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem `al.max_size()` , bu ifade düzgün biçimlendirilmişse, aksi takdirde döndürür `numeric_limits<size_type>::max()` .

### <a name="select_on_container_copy_construction"></a><a name="select_on_container_copy_construction"></a>select_on_container_copy_construction

`select_on_container_copy_construction`Belirtilen ayırıcı üzerinde çağıran statik yöntem.

```cpp
static Alloc select_on_container_copy_construction(const Alloc& al);
```

#### <a name="parameters"></a>Parametreler

*Eşkenar*\
Ayırıcı nesne.

#### <a name="return-value"></a>Dönüş Değeri

Bu yöntem `al.select_on_container_copy_construction()` , bu tür doğru biçimlendirilmişse, tersi durumda *Al*' ı döndürür.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem, ilişkili kapsayıcı kopyalama tarafından oluşturulan bir ayırıcıyı belirtmek için kullanılır.
