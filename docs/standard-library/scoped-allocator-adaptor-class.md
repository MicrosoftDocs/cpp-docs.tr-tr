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
ms.openlocfilehash: 62bdeeddf0e81cf017c49eac51ca0e2eaaf046c1
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104073"
---
# <a name="scopedallocatoradaptor-class"></a>scoped_allocator_adaptor Sınıfı

Ayırıcılar, bir iç içe temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir veya daha fazla ayırıcılar bir iç içe kapsüller. Her bir sınıf türünün en dıştaki bir ayırıcı sahip `outer_allocator_type`, ilişkin bir eşanlam `Outer`, ortak bir taban olduğu `scoped_allocator_adaptor` nesne. `Outer` bir kapsayıcı tarafından kullanılan bellek ayırmak için kullanılır. Bu ayırıcı temel nesnesine bir başvuru çağırarak elde edebileceğiniz `outer_allocator`.

İç içe geri kalanında türünde `inner_allocator_type`. Bir iç ayırıcı bir kapsayıcı içindeki öğelere için bellek ayırmak için kullanılır. Bu türü depolanmış nesne başvuru çağırarak elde edebileceğiniz `inner_allocator`. Varsa `Inner...` boş değildir `inner_allocator_type` türünde `scoped_allocator_adaptor<Inner...>`, ve `inner_allocator` üye nesnesi atar. Aksi takdirde, `inner_allocator_type` türünde `scoped_allocator_adaptor<Outer>`, ve `inner_allocator` tüm nesnesi atar.

İç içe geçirme, en içteki kapsüllenmiş ayırıcı gerektiği şekilde çoğaltmak rastgele derinliği yokmuş gibi davranır.

Görünür arabiriminin bir parçası olmayan birkaç kavram Bu şablon sınıfının davranışını tanımlamak için yardımcı. Bir *en dıştaki ayırıcı* yapısı için tüm çağrıları aracılık ve yöntemleri yok. Etkili bir şekilde özyinelemeli işlev tarafından tanımlanan `OUTERMOST(X)`burada `OUTERMOST(X)` aşağıdakilerden biridir.

- Varsa `X.outer_allocator()` , ardından biçimlendirilmemiş `OUTERMOST(X)` olduğu `OUTERMOST(X.outer_allocator())`.

- Aksi takdirde, `OUTERMOST(X)` olduğu `X`.

Üç tür exposition amacıyla tanımlanmıştır:

|Tür|Açıklama|
|----------|-----------------|
|`Outermost`|Türünü `OUTERMOST(*this)`.|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|Oluşturur bir `scoped_allocator_adaptor` nesne.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bu tür eşanlamlıdır `const_pointer` ayırıcı ile ilişkili `Outer`.|
|`const_void_pointer`|Bu tür eşanlamlıdır `const_void_pointer` ayırıcı ile ilişkili `Outer`.|
|`difference_type`|Bu tür eşanlamlıdır `difference_type` ayırıcı ile ilişkili `Outer`.|
|`inner_allocator_type`|Bu tür iç içe geçmiş bağdaştırıcı türünü eşanlamlıdır `scoped_allocator_adaptor<Inner...>`.|
|`outer_allocator_type`|Bu tür temel ayırıcı türünü eşanlamlıdır `Outer`.|
|`pointer`|Bu tür eşanlamlıdır `pointer` ayırıcı ile ilişkili `Outer`.|
|`propagate_on_container_copy_assignment`|Türü ise true tutar `Outer_traits::propagate_on_container_copy_assignment` korumadıkça veya `inner_allocator_type::propagate_on_container_copy_assignment` geçerlidir.|
|`propagate_on_container_move_assignment`|Türü ise true tutar `Outer_traits::propagate_on_container_move_assignment` korumadıkça veya `inner_allocator_type::propagate_on_container_move_assignment` geçerlidir.|
|`propagate_on_container_swap`|Türü ise true tutar `Outer_traits::propagate_on_container_swap` korumadıkça veya `inner_allocator_type::propagate_on_container_swap` geçerlidir.|
|`size_type`|Bu tür eşanlamlıdır `size_type` ayırıcı ile ilişkili `Outer`.|
|`value_type`|Bu tür eşanlamlıdır `value_type` ayırıcı ile ilişkili `Outer`.|
|`void_pointer`|Bu tür eşanlamlıdır `void_pointer` ayırıcı ile ilişkili `Outer`.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor::rebind yapısı](#rebind_struct)|Türü tanımlayan `Outer::rebind\<Other>::other` eşanlamlısı olarak `scoped_allocator_adaptor\<Other, Inner...>`.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[allocate](#allocate)|Kullanarak belleği ayırır `Outer` ayırıcı.|
|[Yapısı](#construct)|Bir nesne oluşturur.|
|[Serbest Bırak](#deallocate)|Nesneleri, dış ayırıcı kullanılarak serbest bırakılır.|
|[yok](#destroy)|Belirtilen bir nesnenin yok eder.|
|[inner_allocator](#inner_allocator)|Bir başvuru türü depolanmış nesne alır `inner_allocator_type`.|
|[max_size](#max_size)|En fazla dış ayırıcısı ayrılabilen nesne sayısını belirler.|
|[outer_allocator](#outer_allocator)|Bir başvuru türü depolanmış nesne alır `outer_allocator_type`.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Yeni bir oluşturur `scoped_allocator_adaptor` çağırarak başlatılan her saklı ayırıcı nesnesini nesnesiyle `select_on_container_copy_construction` için karşılık gelen her ayırıcı.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<scoped_allocator >

**Namespace:** std

## <a name="allocate"></a>  scoped_allocator_adaptor::allocate

Kullanarak belleği ayırır `Outer` ayırıcı.

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Yeterli depolama alanı ayrılacak olan öğe sayısı.

*İpucu*<br/>
Ayırıcı nesnesini, istek önce ayrılmış bir nesne adresi bularak yardımcı bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi döndürür `Outer_traits::allocate(outer_allocator(), count)`. İkinci üye işlevi döndürür `Outer_traits::allocate(outer_allocator(), count, hint)`.

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

*ptr*<br/>
Nesnenin oluşturulması olduğu bellek konumu için bir işaretçi.

*bağımsız değişken*<br/>
Bağımsız değişken listesi.

*ilk*<br/>
Bir çift ilk türünden bir nesne.

*Saniye*<br/>
Bir çift ikinci türünden bir nesne.

*sağ*<br/>
Taşınamaz veya kopyalanamaz için var olan bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk yöntem, bir nesne oluşturur *ptr* çağırarak `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`burada `xargs...` aşağıdakilerden biridir.

- Varsa `uses_allocator<Ty, inner_allocator_type>` false'ı tutan `xargs...` olduğu `args...`.

- Varsa `uses_allocator<Ty, inner_allocator_type>` korumadıkça, ve `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` ardından, korumadıkça `xargs...` olduğu `allocator_arg, inner_allocator(), args...`.

- Varsa `uses_allocator<Ty, inner_allocator_type>` korumadıkça, ve `is_constructible<Ty, args..., inner_allocator()>` ardından, korumadıkça `xargs...` olduğu `args..., inner_allocator()`.

İkinci yöntem çifti nesne oluşturur *ptr* çağırarak `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`burada `xargs...` olan `first...` Yukarıdaki listeye olduğu gibi değişiklik ve `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`burada `xargs...` olan `second...` değiştirildi Yukarıdaki listenin olduğu gibi.

Üçüncü yöntem gibi davranır `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)`.

Dördüncü yöntem gibi davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))`.

Beşinci yöntem gibi davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))`.

Altıncı yöntem gibi davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))`.

## <a name="deallocate"></a>  scoped_allocator_adaptor::deallocate

Nesneleri, dış ayırıcı kullanılarak serbest bırakılır.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Serbest bırakılması nesnelerin başlangıç konumu için bir işaretçi.

*Sayısı*<br/>
Serbest bırakmak nesne sayısı.

## <a name="destroy"></a>  scoped_allocator_adaptor::Destroy

Belirtilen bir nesnenin yok eder.

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Yok edilecek nesneye bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="inner_allocator"></a>  scoped_allocator_adaptor::inner_allocator

Bir başvuru türü depolanmış nesne alır `inner_allocator_type`.

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru türü depolanmış nesne `inner_allocator_type`.

## <a name="max_size"></a>  scoped_allocator_adaptor::max_size

En fazla dış ayırıcısı ayrılabilen nesne sayısını belirler.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Dönüş Değeri

`Outer_traits::max_size(outer_allocator())`

## <a name="outer_allocator"></a>  scoped_allocator_adaptor::outer_allocator

Bir başvuru türü depolanmış nesne alır `outer_allocator_type`.

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru türü depolanmış nesne `outer_allocator_type`.

## <a name="rebind_struct"></a>  scoped_allocator_adaptor::rebind yapısı

Türü tanımlayan `Outer::rebind\<Other>::other` eşanlamlısı olarak `scoped_allocator_adaptor\<Other, Inner...>`.

Yapı yeniden bağlamasını {typedef Other_traits::rebind\<diğer > Other_alloc; typedef scoped_allocator_adaptor\<Other_alloc, iç... > diğer;};

## <a name="scoped_allocator_adaptor"></a>  scoped_allocator_adaptor::scoped_allocator_adaptor Oluşturucusu

Oluşturur bir `scoped_allocator_adaptor` nesne.

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

*sağ*<br/>
Mevcut bir `scoped_allocator_adaptor`.

*Al*<br/>
Dış ayırıcı kullanılacak mevcut bir ayırıcı.

*REST*<br/>
Ayırıcılar iç ayırıcılar kullanılacak bir listesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan saklı ayırıcı nesneleri oluşturur. Her bir sonraki üç oluşturucular ilgili nesnelerin saklı ayırıcı nesneleri oluşturur *doğru*. Son oluşturucu bağımsız değişken listesinde karşılık gelen bağımsız değişkenler, saklı ayırıcı nesneleri oluşturur.

## <a name="select_on_container_copy_construction"></a>  scoped_allocator_adaptor::select_on_container_copy_construction

Yeni bir oluşturur `scoped_allocator_adaptor` çağırarak başlatılan her saklı ayırıcı nesnesini nesnesiyle `select_on_container_copy_construction` için karşılık gelen her ayırıcı.

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem etkili bir şekilde döndürür `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())`. Yeni bir sonucudur `scoped_allocator_adaptor` çağırarak başlatılan her saklı ayırıcı nesnesini nesnesiyle `al.select_on_container_copy_construction()` karşılık gelen ayırıcı için *al*.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
