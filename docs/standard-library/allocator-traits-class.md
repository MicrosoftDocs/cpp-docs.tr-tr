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
ms.openlocfilehash: 470b3086b4bdfa776558122eda9e496fa6c4bcdc
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690068"
---
# <a name="allocator_traits-class"></a>allocator_traits Sınıfı

Sınıf şablonu, *ayırıcı türünü*tamamlayan bir nesneyi tanımlar. Ayırıcı türü, ayrılmış depolamayı yönetmek için kullanılan bir ayırıcı nesnesini tanımlayan herhangi bir türdür. Özellikle, `Alloc` ayırıcı türü için, ayırıcı özellikli bir kapsayıcı tarafından ihtiyaç duyulan tüm bilgileri belirtmek için `allocator_traits<Alloc>` kullanabilirsiniz. Daha fazla bilgi için bkz. varsayılan [ayırıcı sınıfı](../standard-library/allocator-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Alloc>
    class allocator_traits;
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|`allocator_type`|Bu tür, `Alloc` şablon parametresi için bir eş anlamlı.|
|`const_pointer`|Bu tür iyi biçimlendirilmişse `Alloc::const_pointer`. Aksi takdirde, bu tür `pointer_traits<pointer>::rebind<const value_type>`.|
|`const_void_pointer`|Bu tür iyi biçimlendirilmişse `Alloc::const_void_pointer`. Aksi takdirde, bu tür `pointer_traits<pointer>::rebind<const void>`.|
|`difference_type`|Bu tür iyi biçimlendirilmişse `Alloc::difference_type`. Aksi takdirde, bu tür `pointer_traits<pointer>::difference_type`.|
|`pointer`|Bu tür iyi biçimlendirilmişse `Alloc::pointer`. Aksi takdirde, bu tür `value_type *`.|
|`propagate_on_container_copy_assignment`|Bu tür iyi biçimlendirilmişse `Alloc::propagate_on_container_copy_assignment`. Aksi takdirde, bu tür `false_type`.|
|`propagate_on_container_move_assignment`|Bu tür iyi biçimlendirilmişse `Alloc::propagate_on_container_move_assignment`. Aksi takdirde, bu tür `false_type`. Tür true olursa, ayırıcı özellikli bir kapsayıcı, depolanan ayırıcıyı bir taşıma atamasında kopyalar.|
|`propagate_on_container_swap`|Bu tür iyi biçimlendirilmişse `Alloc::propagate_on_container_swap`. Aksi takdirde, bu tür `false_type`. Tür true olursa, ayırıcı özellikli bir kapsayıcı, bir takas üzerinde depolanan ayırıcıyı değiştirir.|
|`size_type`|Bu tür iyi biçimlendirilmişse `Alloc::size_type`. Aksi takdirde, bu tür `make_unsigned<difference_type>::type`.|
|`value_type`|Bu tür `Alloc::value_type` için bir eş anlamlı.|
|`void_pointer`|Bu tür iyi biçimlendirilmişse `Alloc::void_pointer`. Aksi takdirde, bu tür `pointer_traits<pointer>::rebind<void>`.|

### <a name="static-methods"></a>Statik yöntemler

Aşağıdaki statik yöntemler, belirtilen bir ayırıcı parametresinde karşılık gelen yöntemi çağırır.

|||
|-|-|
|[allocate](#allocate)|Belirtilen ayırıcı parametresini kullanarak belleği ayıran statik yöntem.|
|[oluşturma](#construct)|Bir nesne oluşturmak için belirtilen ayırıcıyı kullanan statik yöntem.|
|[kaldırmak](#deallocate)|Belirtilen sayıda nesneyi serbest bırakmak için belirtilen ayırıcıyı kullanan statik yöntem.|
|[kaldırılır](#destroy)|Bir nesne üzerinde yıkıcıyı çağırmak için bellek ayırmayı kaldırmadan belirtilen ayırıcıyı kullanan statik yöntem.|
|[max_size](#max_size)|Ayrılabilen en fazla nesne sayısını belirleyebilmek için belirtilen ayırıcıyı kullanan statik yöntem.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Belirtilen ayırıcı üzerinde `select_on_container_copy_construction` çağıran statik yöntem.|

### <a name="allocate"></a>allocate

Belirtilen ayırıcı parametresini kullanarak belleği ayıran statik yöntem.

```cpp
static pointer allocate(Alloc& al, size_type count);

static pointer allocate(Alloc& al, size_type count,
    typename allocator_traits<void>::const_pointer* hint);
```

#### <a name="parameters"></a>Parametreler

*al* \
Ayırıcı nesne.

*sayı* \
Ayrılacak öğe sayısı.

*ipucu* \
İstek öncesinde ayrılmış bir nesnenin adresini bularak, depolama için isteği karşılarken yer alan ayırıcı nesnesine yardımcı olabilecek bir `const_pointer`. Null işaretçi hiçbir ipucu olarak değerlendirilir.

#### <a name="return-value"></a>Dönüş Değeri

Her yöntem, ayrılan nesneye bir işaretçi döndürür.

İlk statik yöntem `al.allocate(count)` döndürür.

İkinci yöntem `al.allocate(count, hint)` döndürür, bu ifade iyi biçimlendirilmiş olur; Aksi takdirde `al.allocate(count)` döndürür.

### <a name="construct"></a>oluşturma

Bir nesne oluşturmak için belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
template <class Uty, class Types>
static void construct(Alloc& al, Uty* ptr, Types&&... args);
```

#### <a name="parameters"></a>Parametreler

*al* \
Ayırıcı nesne.

*ptr* \
Nesnenin oluşturulması gereken konuma yönelik bir işaretçi.

*bağımsız değişkenler* \
Nesne oluşturucusuna geçirilen bağımsız değişkenlerin listesi.

#### <a name="remarks"></a>Açıklamalar

Statik üye işlevi, bu ifade düzgün biçimlendirilmişse `al.construct(ptr, args...)` çağırır; Aksi takdirde `::new (static_cast<void *>(ptr)) Uty(std::forward<Types>(args)...)` değerlendirir.

### <a name="deallocate"></a>kaldırmak

Belirtilen sayıda nesneyi serbest bırakmak için belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
static void deallocate(Alloc al,
    pointer ptr,
    size_type count);
```

#### <a name="parameters"></a>Parametreler

*al* \
Ayırıcı nesne.

*ptr* \
Serbest bırakmak için nesnelerin başlangıç konumuna yönelik bir işaretçi.

*sayı* \
Serbest bırakmak için nesne sayısı.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem `al.deallocate(ptr, count)` çağırır.

Bu yöntem hiçbir şey yapmaz.

### <a name="destroy"></a>kaldırılır

Bir nesne üzerinde yıkıcıyı çağırmak için bellek ayırmayı kaldırmadan belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
template <class Uty>
    static void destroy(Alloc& al, Uty* ptr);
```

#### <a name="parameters"></a>Parametreler

*al* \
Ayırıcı nesne.

*ptr* \
Nesnenin konumuna yönelik bir işaretçi.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem iyi biçimlendirilmişse `al.destroy(ptr)` çağırır; Aksi takdirde `ptr->~Uty()` değerlendirir.

### <a name="max_size"></a>max_size

Ayrılabilen en fazla nesne sayısını belirleyebilmek için belirtilen ayırıcıyı kullanan statik yöntem.

```cpp
static size_type max_size(const Alloc& al);
```

#### <a name="parameters"></a>Parametreler

*al* \
Ayırıcı nesne.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu ifade düzgün biçimlendirilmişse `al.max_size()` döndürür; Aksi takdirde `numeric_limits<size_type>::max()` döndürür.

### <a name="select_on_container_copy_construction"></a>select_on_container_copy_construction

Belirtilen ayırıcı üzerinde `select_on_container_copy_construction` çağıran statik yöntem.

```cpp
static Alloc select_on_container_copy_construction(const Alloc& al);
```

#### <a name="parameters"></a>Parametreler

*al* \
Ayırıcı nesne.

#### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, bu tür iyi biçimlendirilmişse `al.select_on_container_copy_construction()` döndürür; Aksi takdirde *Al*döndürür.

#### <a name="remarks"></a>Açıklamalar

Bu yöntem, ilişkili kapsayıcı kopyalama tarafından oluşturulan bir ayırıcıyı belirtmek için kullanılır.
