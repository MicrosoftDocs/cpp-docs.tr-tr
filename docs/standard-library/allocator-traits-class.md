---
title: "allocator_traits sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
ms.assetid: 612974b8-b5d4-4668-82fb-824bff6821d6
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
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
ms.workload: cplusplus
ms.openlocfilehash: 7d96b4a03085a2a6486fa2f2fe0d7050323682c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="allocatortraits-class"></a>allocator_traits Sınıfı
Şablon sınıfı tamamlayan bir nesneyi tanımlayan bir *ayırıcısı türü*. Depolama tahsis yönetmek için kullanılan bir ayırıcı nesneyi tanımlayan herhangi bir türü bir ayırıcı türüdür. Özellikle, herhangi bir ayırıcı türü için `Alloc`, kullanabileceğiniz `allocator_traits<Alloc>` ayırıcısı etkin bir kapsayıcı tarafından gerekli tüm bilgileri belirlemek için. Daha fazla bilgi için bkz: varsayılan [allocator sınıfı](../standard-library/allocator-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <class Alloc>
class allocator_traits;
```  
  
### <a name="typedefs"></a>Tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`allocator_traits::allocator_type`|Bu tür şablon parametresi için bir eş anlamlı olduğundan `Alloc`.|  
|`allocator_traits::const_pointer`|Bu tür `Alloc::const_pointer`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `pointer_traits<pointer>::rebind<const value_type>`.|  
|`allocator_traits::const_void_pointer`|Bu tür `Alloc::const_void_pointer`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `pointer_traits<pointer>::rebind<const void>`.|  
|`allocator_traits::difference_type`|Bu tür `Alloc::difference_type`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `pointer_traits<pointer>::difference_type`.|  
|`allocator_traits::pointer`|Bu tür `Alloc::pointer`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `value_type *`.|  
|`allocator_traits::propagate_on_container_copy_assignment`|Bu tür `Alloc::propagate_on_container_copy_assignment`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `false_type`.|  
|`allocator_traits::propagate_on_container_move_assignment`|Bu tür `Alloc::propagate_on_container_move_assignment`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `false_type`. Türü geçerlidir, bir ayırıcı etkin kapsayıcısı taşıma atama üzerinde depolanan, ayırıcı kopyalar.|  
|`allocator_traits::propagate_on_container_swap`|Bu tür `Alloc::propagate_on_container_swap`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `false_type`. Türü geçerlidir, bir ayırıcı etkin kapsayıcısı bir takas üzerinde depolanan, ayırıcı değiştirir.|  
|`allocator_traits::size_type`|Bu tür `Alloc::size_type`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `make_unsigned<difference_type>::type`.|  
|`allocator_traits::value_type`|Bu tür için eş anlamlı olduğundan `Alloc::value_type`.|  
|`allocator_traits::void_pointer`|Bu tür `Alloc::void_pointer`, türü, doğru biçimlendirilmiş; Aksi takdirde, bu tür, `pointer_traits<pointer>::rebind<void>`.|  
  
### <a name="static-methods"></a>Statik yöntemler  
 Şu statik yöntemlerini verilen ayırıcısı parametresi üzerinde karşılık gelen yöntemini çağırın.  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[allocate](#allocate)|Verilen ayırıcısı parametresini kullanarak bellek ayırır statik yöntem.|  
|[Yapı](#construct)|Bir nesne oluşturmak için belirtilen ayırıcısı kullanan statik yöntem.|  
|[serbest bırakma](#deallocate)|Belirtilen sayıda nesneleri serbest bırakma için belirtilen ayırıcısı kullanır statik yöntem.|  
|[yok](#destroy)|Kendi bellek ayırmayı kaldırma olmadan yıkıcı bir nesne üzerinde çağırmak için belirtilen ayırıcısı kullanan statik yöntem.|  
|[max_size](#max_size)|Belirtilen bir ayırıcı ayrılabilen nesneleri sayısını belirlemek için kullanır statik yöntem.|  
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Çağıran statik yöntemi `select_on_container_copy_construction` belirtilen ayırıcısı üzerinde.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<bellek >  
  
 **Namespace:** std  
  
##  <a name="allocate"></a>allocator_traits::allocate
 Verilen ayırıcısı parametresini kullanarak bellek ayırır statik yöntem.  
  
```cpp  
static pointer allocate(Alloc& al, size_type count);

static pointer allocate(Alloc& al, size_type count,
    typename allocator_traits<void>::const_pointer* hint);
```  
  
### <a name="parameters"></a>Parametreler  
 `al`  
 Bir ayırıcı nesne.  
  
 `count`  
 Ayrılacak öğe sayısı.  
  
 `hint`  
 A `const_pointer` yardımcı ayırıcısı nesne istek depolama için ayrılmış bir nesne istek önce adresini bularak çağıran. Null işaretçinin hiçbir ipucu olarak kabul edilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her yöntemin bir işaretçi ayrılmış nesnesi döndürür.  
  
 İlk statik yöntem döndürür `al.allocate(count)`.  
  
 İkinci yöntem döndürür `al.allocate(count, hint)`, ifade iyi biçimlendirilmiş; Aksi halde döndürür `al.allocate(count)`.  
  
##  <a name="construct"></a>allocator_traits::Construct
 Bir nesne oluşturmak için belirtilen ayırıcısı kullanan statik yöntem.  
  
```cpp  
template <class Uty, class Types>
static void construct(Alloc& al, Uty* ptr, Types&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
 `al`  
 Bir ayırıcı nesne.  
  
 `ptr`  
 Nesne oluşturulması bulunduğu konuma bir işaretçi.  
  
 `args`  
 Nesne oluşturucuya geçirilen bağımsız değişken listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Statik üye işlev çağrılarını `al.construct(ptr, args...)`, ifade iyi biçimlendirilmiş; Aksi takdirde değerlendirir `::new (static_cast<void *>(ptr)) Uty(std::forward<Types>(args)...)`.  
  
##  <a name="deallocate"></a>allocator_traits::deallocate
 Belirtilen sayıda nesneleri serbest bırakma için belirtilen ayırıcısı kullanır statik yöntem.  
  
```cpp  
static void deallocate(Alloc al,
    pointer ptr,
    size_type count);
```  
  
### <a name="parameters"></a>Parametreler  
 `al`  
 Bir ayırıcı nesne.  
  
 `ptr`  
 Bırakılmasına nesnelerin başlangıç konumu için bir işaretçi.  
  
 `count`  
 Deallocate nesnelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır `al.deallocate(ptr, count)`.  
  
 Bu yöntem hiçbir şey oluşturulur.  
  
##  <a name="destroy"></a>allocator_traits::Destroy
 Kendi bellek ayırmayı kaldırma olmadan yıkıcı bir nesne üzerinde çağırmak için belirtilen ayırıcısı kullanan statik yöntem.  
  
```cpp  
template <class Uty>
static void destroy(Alloc& al, Uty* ptr);
```  
  
### <a name="parameters"></a>Parametreler  
 `al`  
 Bir ayırıcı nesne.  
  
 `ptr`  
 Nesne konumu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır `al.destroy(ptr)`, ifade iyi biçimlendirilmiş; Aksi takdirde değerlendirir `ptr->~Uty()`.  
  
##  <a name="max_size"></a>allocator_traits::max_size
 Belirtilen bir ayırıcı ayrılabilen nesneleri sayısını belirlemek için kullanır statik yöntem.  
  
```cpp  
static size_type max_size(const Alloc& al);
```  
  
### <a name="parameters"></a>Parametreler  
 `al`  
 Bir ayırıcı nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `al.max_size()`, ifade iyi biçimlendirilmiş; Aksi halde döndürür `numeric_limits<size_type>::max()`.  
  
##  <a name="select_on_container_copy_construction"></a>allocator_traits::select_on_container_copy_construction
 Çağıran statik yöntemi `select_on_container_copy_construction` belirtilen ayırıcısı üzerinde.  
  
```cpp  
static Alloc select_on_container_copy_construction(const Alloc& al);
```  
  
### <a name="parameters"></a>Parametreler  
 `al`  
 Bir ayırıcı nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem `al.select_on_container_copy_construction()`, türü iyi biçimlendirilmiş; Aksi halde döndürür `al`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, ilişkili kapsayıcı kopyalama oluşturulan olduğunda bir ayırıcı belirtmek için kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<bellek >](../standard-library/memory.md)   
 [pointer_traits yapısı](../standard-library/pointer-traits-struct.md)   
 [scoped_allocator_adaptor Sınıfı](../standard-library/scoped-allocator-adaptor-class.md)
