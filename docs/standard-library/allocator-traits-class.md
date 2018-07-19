---
title: allocator_traits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 9bae212ec3d8edfacc7cd3afb37ab3c13dc11aef
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962457"
---
# <a name="allocatortraits-class"></a>allocator_traits Sınıfı

Şablon sınıfı tamamlayan bir nesneyi tanımlayan bir *ayırıcı türü*. Ayrılmış depolama alanını yönetmek için kullanılan bir ayırıcı nesnesini tanımlayan herhangi bir türü bir ayırıcı türüdür. Özellikle, herhangi bir ayırıcı türü için `Alloc`, kullanabileceğiniz `allocator_traits<Alloc>` ayırıcı tarafından etkinleştirilen kapsayıcı tarafından gerek duyulan tüm bilgileri belirlemek için. Daha fazla bilgi için bkz varsayılan [allocator sınıfı](../standard-library/allocator-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Alloc>
class allocator_traits;
```

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`allocator_traits::allocator_type`|Bu tür şablon parametresi eşanlamlıdır `Alloc`.|
|`allocator_traits::const_pointer`|Bu tür `Alloc::const_pointer`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `pointer_traits<pointer>::rebind<const value_type>`.|
|`allocator_traits::const_void_pointer`|Bu tür `Alloc::const_void_pointer`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `pointer_traits<pointer>::rebind<const void>`.|
|`allocator_traits::difference_type`|Bu tür `Alloc::difference_type`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `pointer_traits<pointer>::difference_type`.|
|`allocator_traits::pointer`|Bu tür `Alloc::pointer`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `value_type *`.|
|`allocator_traits::propagate_on_container_copy_assignment`|Bu tür `Alloc::propagate_on_container_copy_assignment`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `false_type`.|
|`allocator_traits::propagate_on_container_move_assignment`|Bu tür `Alloc::propagate_on_container_move_assignment`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `false_type`. Türü korumadıkça, bir ayırıcı tarafından etkinleştirilen kapsayıcı, depolanan bir ayırıcı bir taşıma ataması üzerinde kopyalar.|
|`allocator_traits::propagate_on_container_swap`|Bu tür `Alloc::propagate_on_container_swap`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `false_type`. Türü korumadıkça, bir ayırıcı tarafından etkinleştirilen kapsayıcı, depolanan bir ayırıcı üzerinde bir takas değiştirir.|
|`allocator_traits::size_type`|Bu tür `Alloc::size_type`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `make_unsigned<difference_type>::type`.|
|`allocator_traits::value_type`|Bu tür eşanlamlıdır `Alloc::value_type`.|
|`allocator_traits::void_pointer`|Bu tür `Alloc::void_pointer`, türü doğru biçimlendirildiğinden; Aksi takdirde, bu türü, `pointer_traits<pointer>::rebind<void>`.|

### <a name="static-methods"></a>Statik yöntemler

Aşağıdaki statik yöntemler üzerinde belirli bir ayırıcı parametre karşılık gelen yöntemini çağırın.

|Ad|Açıklama|
|----------|-----------------|
|[allocate](#allocate)|Belirli bir ayırıcı parametresini kullanarak belleği ayırır statik yöntem.|
|[Yapısı](#construct)|Bir nesne oluşturmak için belirli bir ayırıcı kullanır statik yöntem.|
|[Serbest Bırak](#deallocate)|Belirli sayıda nesneleri serbest bırakma için belirli bir ayırıcı kullanır statik yöntem.|
|[yok](#destroy)|Yok edici bir nesne üzerinde onun belleğini olmadan çağırmak için belirli bir ayırıcı kullanır statik yöntem.|
|[max_size](#max_size)|Ayrılan nesneler maksimum sayısını belirlemek için belirli bir ayırıcı kullanır statik yöntem.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Çağıran statik yöntem `select_on_container_copy_construction` üzerinde belirtilen ayırıcı.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="allocate"></a>  allocator_traits::allocate

Belirli bir ayırıcı parametresini kullanarak belleği ayırır statik yöntem.

```cpp
static pointer allocate(Alloc& al, size_type count);

static pointer allocate(Alloc& al, size_type count,
    typename allocator_traits<void>::const_pointer* hint);
```

### <a name="parameters"></a>Parametreler

*Al* ayırıcı nesnesi.

*sayısı* ayrılacak öğe sayısı.

*İpucu* A `const_pointer` yardımcı olan ayırıcı nesnesini isteği önce ayrılmış bir nesneye adresini bularak depolama talebi karşılamadığınızı içinde. Bir null işaretçiyse, hiçbir ipucu olarak kabul edilir.

### <a name="return-value"></a>Dönüş Değeri

Her bir yöntemin ayrılmış bir nesneye bir işaretçi döndürür.

İlk statik yöntem döndürür `al.allocate(count)`.

İkinci yöntem döndürür `al.allocate(count, hint)`, ifade iyi biçimlendirilmiş; Aksi halde döndürür `al.allocate(count)`.

## <a name="construct"></a>  allocator_traits::Construct

Bir nesne oluşturmak için belirli bir ayırıcı kullanır statik yöntem.

```cpp
template <class Uty, class Types>
static void construct(Alloc& al, Uty* ptr, Types&&... args);
```

### <a name="parameters"></a>Parametreler

*Al* ayırıcı nesnesi.

*PTR* nesne olduğunda kendisinden oluşturulacağı konumu için bir işaretçi.

*args* nesne oluşturucuya geçirilen bağımsız değişkenlerin bir listesi.

### <a name="remarks"></a>Açıklamalar

Statik üye işlev çağrıları `al.construct(ptr, args...)`, ifade iyi biçimlendirilmiş; Aksi takdirde değerlendirir `::new (static_cast<void *>(ptr)) Uty(std::forward<Types>(args)...)`.

## <a name="deallocate"></a>  allocator_traits::deallocate

Belirli sayıda nesneleri serbest bırakma için belirli bir ayırıcı kullanır statik yöntem.

```cpp
static void deallocate(Alloc al,
    pointer ptr,
    size_type count);
```

### <a name="parameters"></a>Parametreler

*Al* ayırıcı nesnesi.

*PTR* işaretçisi serbest bırakılması nesnelerin başlangıç konumu.

*sayısı* ayırması kaldırılacak nesne sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı `al.deallocate(ptr, count)`.

Bu yöntem, hiçbir şey oluşturulur.

## <a name="destroy"></a>  allocator_traits::destroy

Yok edici bir nesne üzerinde onun belleğini olmadan çağırmak için belirli bir ayırıcı kullanır statik yöntem.

```cpp
template <class Uty>
static void destroy(Alloc& al, Uty* ptr);
```

### <a name="parameters"></a>Parametreler

*Al* ayırıcı nesnesi.

*PTR* nesnenin konumu için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı `al.destroy(ptr)`, ifade iyi biçimlendirilmiş; Aksi takdirde değerlendirir `ptr->~Uty()`.

## <a name="max_size"></a>  allocator_traits::max_size

Ayrılan nesneler maksimum sayısını belirlemek için belirli bir ayırıcı kullanır statik yöntem.

```cpp
static size_type max_size(const Alloc& al);
```

### <a name="parameters"></a>Parametreler

*Al* ayırıcı nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem döndürür `al.max_size()`, ifade iyi biçimlendirilmiş; Aksi halde döndürür `numeric_limits<size_type>::max()`.

## <a name="select_on_container_copy_construction"></a>  allocator_traits::select_on_container_copy_construction

Çağıran statik yöntem `select_on_container_copy_construction` üzerinde belirtilen ayırıcı.

```cpp
static Alloc select_on_container_copy_construction(const Alloc& al);
```

### <a name="parameters"></a>Parametreler

*Al* ayırıcı nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem döndürür `al.select_on_container_copy_construction()`, türü iyi biçimlendirilmiş; Aksi halde döndürür *al*.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir ayırıcı ilişkili kapsayıcı kopyalama oluşturulmuş olduğunda belirtmek için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
[pointer_traits Yapısı](../standard-library/pointer-traits-struct.md)<br/>
[scoped_allocator_adaptor Sınıfı](../standard-library/scoped-allocator-adaptor-class.md)<br/>
