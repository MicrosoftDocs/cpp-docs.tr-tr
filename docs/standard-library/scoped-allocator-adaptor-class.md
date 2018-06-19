---
title: scoped_allocator_adaptor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- scoped_allocator/std::scoped_allocator_adaptor
- scoped_allocator/std::scoped_allocator_adaptor::rebind Struct
- scoped_allocator/std::scoped_allocator_adaptor::allocate
- scoped_allocator/std::scoped_allocator_adaptor::construct
- scoped_allocator/std::scoped_allocator_adaptor::deallocate
- scoped_allocator/std::scoped_allocator_adaptor::destroy
- scoped_allocator/std::scoped_allocator_adaptor::inner_allocator
- scoped_allocator/std::scoped_allocator_adaptor::max_size
- scoped_allocator/std::scoped_allocator_adaptor::outer_allocator
- scoped_allocator/std::scoped_allocator_adaptor::select_on_container_copy_construction
dev_langs:
- C++
helpviewer_keywords:
- std::scoped_allocator_adaptor
- std::scoped_allocator_adaptor::allocate
- std::scoped_allocator_adaptor::construct
- std::scoped_allocator_adaptor::deallocate
- std::scoped_allocator_adaptor::destroy
- std::scoped_allocator_adaptor::inner_allocator
- std::scoped_allocator_adaptor::max_size
- std::scoped_allocator_adaptor::outer_allocator
- std::scoped_allocator_adaptor::select_on_container_copy_construction
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e403e0133818846deb08bb336adc98618e944bf9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861883"
---
# <a name="scopedallocatoradaptor-class"></a>scoped_allocator_adaptor Sınıfı

Allocators, iç içe temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir veya daha fazla allocators, iç içe yalıtır. Her bir sınıf türünün en dıştaki bir ayırıcı sahip `outer_allocator_type`, eşanlamlısı `Outer`, ortak bir temeli olduğu `scoped_allocator_adaptor` nesnesi. `Outer` kapsayıcı tarafından kullanılması için bellek tahsis etmek için kullanılır. Çağırarak bu ayırıcısı temel nesneye bir başvurusu elde edebileceğiniz `outer_allocator`.

İç içe geri kalanı türüne sahip `inner_allocator_type`. Bir iç ayırıcısı bir kapsayıcıdaki öğeleri için bellek tahsis etmek için kullanılır. Çağırarak bu tür saklı nesneye bir başvurusu elde edebileceğiniz `inner_allocator`. Varsa `Inner...` boş değil `inner_allocator_type` türüne sahip `scoped_allocator_adaptor<Inner...>`, ve `inner_allocator` bir üye nesnesini belirtir. Aksi takdirde, `inner_allocator_type` türüne sahip `scoped_allocator_adaptor<Outer>`, ve `inner_allocator` nesnenin tamamı belirler.

İç içe en içteki kendi kapsüllenmiş ayırıcısı gerektiği şekilde çoğaltmak rasgele derinliği sahip gibi davranır.

Bu şablon sınıfı davranışını tanımlamak için görünür arabirimi parçası olmayan birkaç kavram yardımcı. Bir *en dıştaki ayırıcısı* yapı tüm çağrıları aracılık ve yöntemleri yok. Etkili bir şekilde özyinelemeli işlev tarafından tanımlanan `OUTERMOST(X)`, burada `OUTERMOST(X)` aşağıdakilerden biridir.

- Varsa `X.outer_allocator()` doğru ardından biçimlendirildiğinden `OUTERMOST(X)` olan `OUTERMOST(X.outer_allocator())`.

- Aksi takdirde, `OUTERMOST(X)` olan `X`.

Üç tür exposition amacıyla tanımlanmıştır:

|Tür|Açıklama|
|----------|-----------------|
|`Outermost`|Türü `OUTERMOST(*this)`.|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|Oluşturan bir `scoped_allocator_adaptor` nesnesi.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bu tür için eş anlamlı olduğundan `const_pointer` ayırıcısı ile ilişkili `Outer`.|
|`const_void_pointer`|Bu tür için eş anlamlı olduğundan `const_void_pointer` ayırıcısı ile ilişkili `Outer`.|
|`difference_type`|Bu tür için eş anlamlı olduğundan `difference_type` ayırıcısı ile ilişkili `Outer`.|
|`inner_allocator_type`|Bu tür bir eş anlamlı iç içe geçmiş bağdaştırıcı türü için olan `scoped_allocator_adaptor<Inner...>`.|
|`outer_allocator_type`|Bu tür temel ayırıcısı türü için eş anlamlı olduğundan `Outer`.|
|`pointer`|Bu tür için eş anlamlı olduğundan `pointer` ayırıcısı ile ilişkili `Outer`.|
|`propagate_on_container_copy_assignment`|Türü ise true tutan `Outer_traits::propagate_on_container_copy_assignment` doğru kalıp veya `inner_allocator_type::propagate_on_container_copy_assignment` geçerlidir.|
|`propagate_on_container_move_assignment`|Türü ise true tutan `Outer_traits::propagate_on_container_move_assignment` doğru kalıp veya `inner_allocator_type::propagate_on_container_move_assignment` geçerlidir.|
|`propagate_on_container_swap`|Türü ise true tutan `Outer_traits::propagate_on_container_swap` doğru kalıp veya `inner_allocator_type::propagate_on_container_swap` geçerlidir.|
|`size_type`|Bu tür için eş anlamlı olduğundan `size_type` ayırıcısı ile ilişkili `Outer`.|
|`value_type`|Bu tür için eş anlamlı olduğundan `value_type` ayırıcısı ile ilişkili `Outer`.|
|`void_pointer`|Bu tür için eş anlamlı olduğundan `void_pointer` ayırıcısı ile ilişkili `Outer`.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor::rebind yapısı](#rebind_struct)|Türünü tanımlayan `Outer::rebind\<Other>::other` eşanlamlısı olarak `scoped_allocator_adaptor\<Other, Inner...>`.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[allocate](#allocate)|Kullanarak bellek ayırır `Outer` ayırıcısı.|
|[Yapı](#construct)|Bir nesne oluşturur.|
|[Serbest bırakma](#deallocate)|Dış ayırıcısı kullanarak nesneleri kaldırır.|
|[yok](#destroy)|Belirtilen bir nesneyi yok eder.|
|[inner_allocator](#inner_allocator)|Saklı nesne türünün bir başvuru alır `inner_allocator_type`.|
|[max_size](#max_size)|Dış ayırıcı tarafından ayrılabilen nesneleri maksimum sayısını belirler.|
|[outer_allocator](#outer_allocator)|Saklı nesne türünün bir başvuru alır `outer_allocator_type`.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Yeni bir `scoped_allocator_adaptor` nesne çağırarak başlatılan her saklı ayırıcısı nesne `select_on_container_copy_construction` karşılık gelen her ayırıcısı için.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<scoped_allocator >

**Namespace:** std

## <a name="allocate"></a>  scoped_allocator_adaptor::allocate

Kullanarak bellek ayırır `Outer` ayırıcısı.

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Parametreler

`count` İçin yeterli depolama alanı ayrılacak olan öğe sayısı.

`hint` Ayırıcı nesne önce isteği ayrılmış bir nesne adresini bularak yardımcı bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevinin döndürdüğü `Outer_traits::allocate(outer_allocator(), count)`. İkinci üye işlevinin döndürdüğü `Outer_traits::allocate(outer_allocator(), count, hint)`.

## <a name="construct"></a>  scoped_allocator_adaptor::Construct

Bir nesne oluşturur.

```cpp
template <class Ty, class... Atypes>
void construct(Ty* ptr, Atypes&&... args);

template <class Ty1, class Ty2, class... Atypes1, class... Atypes2>
void construct(pair<Ty1, Ty2>* ptr, piecewise_construct_t,
    tuple<Atypes1&&...>
first, tuple<Atypes1&&...> second);

template <class Ty1, class Ty2>
void construct(pair<Ty1, Ty2>* ptr);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr,
    class Uy1&& first, class Uy2&& second);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, const pair<Uy1, Uy2>& right);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, pair<Uy1, Uy2>&& right);
```

### <a name="parameters"></a>Parametreler

`ptr` Nesne oluşturulması olduğu bellek konuma bir işaretçi.

`args` Bağımsız değişkenler listesi.

`first` Bir çift ilk türünde bir nesne.

`second` Bir çift ikinci türünde bir nesne.

`right` Taşınamaz veya kopyalanamaz için var olan bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk yöntem nesnede yapıları `ptr` çağırarak `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`, burada `xargs...` aşağıdakilerden biridir.

- Varsa `uses_allocator<Ty, inner_allocator_type>` false tutan `xargs...` olan `args...`.

- Varsa `uses_allocator<Ty, inner_allocator_type>` geçerlidir, ve `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` true tutan `xargs...` olan `allocator_arg, inner_allocator(), args...`.

- Varsa `uses_allocator<Ty, inner_allocator_type>` geçerlidir, ve `is_constructible<Ty, args..., inner_allocator()>` true tutan `xargs...` olan `args..., inner_allocator()`.

İkinci yöntem çifti nesnede oluşturur `ptr` çağırarak `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`, burada `xargs...` olan `first...` Yukarıdaki listeye olduğu gibi değiştirilmiş ve `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`, burada `xargs...` olan `second...` olduğu gibi yukarıdaki listesini değiştirdi.

Üçüncü yöntemi olarak aynı şekilde davranır `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)`.

Dördüncü yöntemi olarak aynı şekilde davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))`.

Beşinci yöntemi olarak aynı şekilde davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))`.

Altıncı yöntemi olarak aynı şekilde davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))`.

## <a name="deallocate"></a>  scoped_allocator_adaptor::deallocate

Dış ayırıcısı kullanarak nesneleri kaldırır.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

`ptr` Bırakılmasına nesnelerin başlangıç konumu için bir işaretçi.

`count` Deallocate nesnelerin sayısı.

## <a name="destroy"></a>  scoped_allocator_adaptor::Destroy

Belirtilen bir nesneyi yok eder.

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>Parametreler

`ptr` Nesne yok edilmesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="inner_allocator"></a>  scoped_allocator_adaptor::inner_allocator

Saklı nesne türünün bir başvuru alır `inner_allocator_type`.

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Saklı nesne türünün referansı `inner_allocator_type`.

## <a name="max_size"></a>  scoped_allocator_adaptor::max_size

Dış ayırıcı tarafından ayrılabilen nesneleri maksimum sayısını belirler.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Dönüş Değeri

`Outer_traits::max_size(outer_allocator())`

## <a name="outer_allocator"></a>  scoped_allocator_adaptor::outer_allocator

Saklı nesne türünün bir başvuru alır `outer_allocator_type`.

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Saklı nesne türünün referansı `outer_allocator_type`.

## <a name="rebind_struct"></a>  scoped_allocator_adaptor::rebind yapısı

Türünü tanımlayan `Outer::rebind\<Other>::other` eşanlamlısı olarak `scoped_allocator_adaptor\<Other, Inner...>`.

Yapı yeniden bağlamasını {typedef Other_traits::rebind\<diğer > Other_alloc; typedef scoped_allocator_adaptor\<Other_alloc, iç... > diğer;};

## <a name="scoped_allocator_adaptor"></a>  scoped_allocator_adaptor::scoped_allocator_adaptor Oluşturucusu

Oluşturan bir `scoped_allocator_adaptor` nesnesi.

```cpp
scoped_allocator_adaptor();

scoped_allocator_adaptor(const scoped_allocator_adaptor& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
 const scoped_allocator_adaptor<Outer2, Inner...>& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
 scoped_allocator_adaptor<Outer2, Inner...>&& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(Outer2&& al,
    const Inner&... rest) noexcept;
```

### <a name="parameters"></a>Parametreler

`right` Var olan `scoped_allocator_adaptor`.

`al` Varolan bir ayırıcı dış ayırıcı kullanılacak.

`rest` Allocators iç allocators kullanılacak bir listesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu varsayılan saklı ayırıcısı nesnelerini oluşturur. Her bir sonraki üç oluşturucular içinde karşılık gelen nesnelerinden saklı ayırıcısı nesnelerini oluşturur `right`. Son oluşturucu bağımsız değişken listesinde karşılık gelen bağımsız değişkenleri, depolanan ayırıcısı nesneleri oluşturur.

## <a name="select_on_container_copy_construction"></a>  scoped_allocator_adaptor::select_on_container_copy_construction

Yeni bir `scoped_allocator_adaptor` nesne çağırarak başlatılan her saklı ayırıcısı nesne `select_on_container_copy_construction` karşılık gelen her ayırıcısı için.

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem etkili bir şekilde `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())`. Yeni bir sonucudur `scoped_allocator_adaptor` nesne çağırarak başlatılan her saklı ayırıcısı nesne `al.select_on_container_copy_construction()` karşılık gelen ayırıcısı için `al`.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
