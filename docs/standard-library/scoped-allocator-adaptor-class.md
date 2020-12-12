---
description: 'Hakkında daha fazla bilgi edinin: scoped_allocator_adaptor sınıfı'
title: scoped_allocator_adaptor Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 95e216743e99df96aa096435e11b86b36247fe9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197185"
---
# <a name="scoped_allocator_adaptor-class"></a>scoped_allocator_adaptor Sınıfı

Ayırıcıların iç içe geçmiş olduğunu temsil eder.

## <a name="syntax"></a>Syntax

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir veya daha fazla ayırıcıların iç içe bir kısmını kapsar. Bu tür bir sınıfın en dıştaki türü `outer_allocator_type` , için bir genel bakış olan `Outer` , nesnenin ortak tabanı olan `scoped_allocator_adaptor` . `Outer` bir kapsayıcı tarafından kullanılacak belleği ayırmak için kullanılır. Çağırarak, bu ayırıcı temel nesnesine bir başvuru elde edebilirsiniz `outer_allocator` .

İç içe geçmiş 'nin geri kalanı türünde `inner_allocator_type` . Bir iç ayırıcı, bir kapsayıcı içindeki öğelere bellek ayırmak için kullanılır. Çağırarak, bu türün saklı nesnesine bir başvuru elde edebilirsiniz `inner_allocator` . `Inner...`Boş değilse, `inner_allocator_type` türüne sahiptir `scoped_allocator_adaptor<Inner...>` ve `inner_allocator` bir üye nesnesi belirler. Aksi takdirde, `inner_allocator_type` türüne sahiptir `scoped_allocator_adaptor<Outer>` ve `inner_allocator` tüm nesneyi belirtir.

İç içe geçmiş, rastgele derinliğe sahip gibi davranır ve en içteki kapsüllenmiş ayırıcıyı gerektiği gibi çoğaltmıştır.

Görünür arabirimin bir parçası olmayan çeşitli kavramlar, bu sınıf şablonunun davranışını tanımlamaya yardımcı olur. En *dıştaki ayırıcı* , yapı ve yok yöntemlerine yapılan tüm çağrıları gösterir. Özyinelemeli işlev tarafından etkin bir şekilde tanımlanır `OUTERMOST(X)` , burada `OUTERMOST(X)` aşağıdakilerden biridir.

- `X.outer_allocator()`Düzgün biçimlendirilmişse, `OUTERMOST(X)` `OUTERMOST(X.outer_allocator())` .

- Aksi halde `OUTERMOST(X)` , `X` .

, Exposition 'ın sake 'ı için üç tür tanımlanmıştır:

|Tür|Açıklama|
|----------|-----------------|
|`Outermost`|Türü `OUTERMOST(*this)` .|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|Bir `scoped_allocator_adaptor` nesnesi oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bu tür, `const_pointer` ayırıcıyla ilişkili olan için bir eş anladır `Outer` .|
|`const_void_pointer`|Bu tür, `const_void_pointer` ayırıcıyla ilişkili olan için bir eş anladır `Outer` .|
|`difference_type`|Bu tür, `difference_type` ayırıcıyla ilişkili olan için bir eş anladır `Outer` .|
|`inner_allocator_type`|Bu tür, iç içe geçmiş bağdaştırıcı türü için bir eş anlamlı `scoped_allocator_adaptor<Inner...>` .|
|`outer_allocator_type`|Bu tür, temel ayırıcı türünün bir eş anlamlısıdır `Outer` .|
|`pointer`|Bu tür, ayırıcıyla ilişkili için bir eş anladır `pointer` `Outer` .|
|`propagate_on_container_copy_assignment`|Tür true, ancak doğru tutuyorsa `Outer_traits::propagate_on_container_copy_assignment` ya da doğru tutuyorsa geçerlidir `inner_allocator_type::propagate_on_container_copy_assignment` .|
|`propagate_on_container_move_assignment`|Tür true, ancak doğru tutuyorsa `Outer_traits::propagate_on_container_move_assignment` ya da doğru tutuyorsa geçerlidir `inner_allocator_type::propagate_on_container_move_assignment` .|
|`propagate_on_container_swap`|Tür true, ancak doğru tutuyorsa `Outer_traits::propagate_on_container_swap` ya da doğru tutuyorsa geçerlidir `inner_allocator_type::propagate_on_container_swap` .|
|`size_type`|Bu tür, ayırıcıyla ilişkili için bir eş anladır `size_type` `Outer` .|
|`value_type`|Bu tür, ayırıcıyla ilişkili için bir eş anladır `value_type` `Outer` .|
|`void_pointer`|Bu tür, ayırıcıyla ilişkili için bir eş anladır `void_pointer` `Outer` .|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor:: yeniden bağlama yapısı](#rebind_struct)|Türü `Outer::rebind\<Other>::other` için bir eş anlamlı olarak tanımlar `scoped_allocator_adaptor\<Other, Inner...>` .|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[allocate](#allocate)|Ayırıcıyı kullanarak belleği ayırır `Outer` .|
|[oluşturma](#construct)|Bir nesnesi oluşturur.|
|[kaldırmak](#deallocate)|Nesneleri dış ayırıcıyı kullanarak ayırır.|
|[kaldırılır](#destroy)|Belirtilen nesneyi yok eder.|
|[inner_allocator](#inner_allocator)|Türündeki saklı nesneye bir başvuru alır `inner_allocator_type` .|
|[max_size](#max_size)|Dış ayırıcı tarafından ayrılabilen en fazla nesne sayısını belirler.|
|[outer_allocator](#outer_allocator)|Türündeki saklı nesneye bir başvuru alır `outer_allocator_type` .|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Her bir `scoped_allocator_adaptor` saklı ayırıcı nesnesi ile her ilgili ayırıcı için çağırarak başlatılan yeni bir nesne oluşturur `select_on_container_copy_construction` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_as)||
|[işleç = =](#op_eq_eq)||
|[işleç! =](#op_noeq)||

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<scoped_allocator>

**Ad alanı:** std

## <a name="scoped_allocator_adaptorallocate"></a><a name="allocate"></a> scoped_allocator_adaptor:: ayır

Ayırıcıyı kullanarak belleği ayırır `Outer` .

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Yeterli depolamanın ayrılabileceği öğe sayısı.

*OPTI*\
İstekten önce ayrılan nesnenin adresini bularak ayırıcı nesnesine yardımcı olabilecek bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi döndürür `Outer_traits::allocate(outer_allocator(), count)` . İkinci üye işlevi döndürür `Outer_traits::allocate(outer_allocator(), count, hint)` .

## <a name="scoped_allocator_adaptorconstruct"></a><a name="construct"></a> scoped_allocator_adaptor:: yapı

Bir nesnesi oluşturur.

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

*kaydetmeye*\
Nesnenin oluşturulması gereken bellek konumuna yönelik bir işaretçi.

*args*\
Bağımsız değişkenlerin listesi.

*adı*\
Bir çiftin ilk türündeki nesne.

*İkincisi*\
Çiftteki ikinci türdeki bir nesne.

*Right*\
Taşınacak veya Kopyalanacak varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk yöntem, aşağıdaki yöntemlerden  `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)` `xargs...` biri olan öğesini çağırarak nesne PTR 'de oluşturur.

- `uses_allocator<Ty, inner_allocator_type>`Yanlış tutuyorsa, `xargs...` `args...` .

- `uses_allocator<Ty, inner_allocator_type>`Doğru tutuyorsa ve `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` doğru tutuyorsa, ve ' `xargs...` dir `allocator_arg, inner_allocator(), args...` .

- `uses_allocator<Ty, inner_allocator_type>`Doğru tutuyorsa ve `is_constructible<Ty, args..., inner_allocator()>` doğru tutuyorsa, ve ' `xargs...` dir `args..., inner_allocator()` .

İkinci yöntem, öğesini çağırarak,  `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)` `xargs...` `first...` Yukarıdaki listede olarak değiştirildiği ve `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)` `xargs...` `second...` Yukarıdaki listede olduğu gibi değiştirildiği, öğesini çağırarak PTR 'de çift nesneyi oluşturur.

Üçüncü yöntem ile aynı şekilde davranır `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)` .

Dördüncü yöntem ile aynı şekilde davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))` .

Beşinci yöntem ile aynı şekilde davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))` .

Altıncı yöntem ile aynı şekilde davranır `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))` .

## <a name="scoped_allocator_adaptordeallocate"></a><a name="deallocate"></a> scoped_allocator_adaptor::d eallocate

Nesneleri dış ayırıcıyı kullanarak ayırır.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Serbest bırakmak için nesnelerin başlangıç konumuna yönelik bir işaretçi.

*biriktirme*\
Serbest bırakmak için nesne sayısı.

## <a name="scoped_allocator_adaptordestroy"></a><a name="destroy"></a> scoped_allocator_adaptor::d estroy

Belirtilen nesneyi yok eder.

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Yok edilecek nesneye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="scoped_allocator_adaptorinner_allocator"></a><a name="inner_allocator"></a> scoped_allocator_adaptor:: inner_allocator

Türündeki saklı nesneye bir başvuru alır `inner_allocator_type` .

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Türündeki saklı nesneye bir başvuru `inner_allocator_type` .

## <a name="scoped_allocator_adaptormax_size"></a><a name="max_size"></a> scoped_allocator_adaptor:: max_size

Dış ayırıcı tarafından ayrılabilen en fazla nesne sayısını belirler.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Dönüş Değeri

`Outer_traits::max_size(outer_allocator())`

## <a name="a-nameop_as--scoped_allocator_adaptoroperator"></a><a name="op_as">  scoped_allocator_adaptor:: operator =

```cpp
scoped_allocator_adaptor& operator=(const scoped_allocator_adaptor&) = default;
scoped_allocator_adaptor& operator=(scoped_allocator_adaptor&&) = default;
```

## <a name="a-nameop_eq_eq--scoped_allocator_adaptoroperator"></a><a name="op_eq_eq">  scoped_allocator_adaptor:: operator = =

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator==(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="a-nameop_noeq--scoped_allocator_adaptoroperator"></a><a name="op_noeq">  scoped_allocator_adaptor:: operator! =

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator!=(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="scoped_allocator_adaptorouter_allocator"></a><a name="outer_allocator"></a> scoped_allocator_adaptor:: outer_allocator

Türündeki saklı nesneye bir başvuru alır `outer_allocator_type` .

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Türündeki saklı nesneye bir başvuru `outer_allocator_type` .

## <a name="scoped_allocator_adaptorrebind-struct"></a><a name="rebind_struct"></a> scoped_allocator_adaptor:: yeniden bağlama yapısı

Türü `Outer::rebind\<Other>::other` için bir eş anlamlı olarak tanımlar `scoped_allocator_adaptor\<Other, Inner...>` .

struct yeniden bağlama {typedef Other_traits:: yeniden bağlama \<Other> Other_alloc; typedef scoped_allocator_adaptor \<Other_alloc, Inner...> Other;};

## <a name="scoped_allocator_adaptorscoped_allocator_adaptor-constructor"></a><a name="scoped_allocator_adaptor"></a> scoped_allocator_adaptor:: scoped_allocator_adaptor Oluşturucusu

Bir `scoped_allocator_adaptor` nesnesi oluşturur. Ayrıca bir yıkıcı içerir.

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

~scoped_allocator_adaptor();
```

### <a name="parameters"></a>Parametreler

*Right*\
Mevcut bir `scoped_allocator_adaptor` .

*Eşkenar*\
Dış ayırıcı olarak kullanılacak mevcut bir ayırıcı.

*kalanı*\
İç ayırıcılar olarak kullanılacak ayrıcılar listesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan, depolanan ayırıcı nesnelerini oluşturur. Sonraki üç oluşturucuların her biri, saklı ayırıcı nesnelerini *sağ taraftaki* ilgili nesnelerden oluşturur. Son Oluşturucu, bağımsız değişken listesindeki ilgili bağımsız değişkenlerden saklı ayırıcı nesnelerini oluşturur.

## <a name="scoped_allocator_adaptorselect_on_container_copy_construction"></a><a name="select_on_container_copy_construction"></a> scoped_allocator_adaptor:: select_on_container_copy_construction

Her bir `scoped_allocator_adaptor` saklı ayırıcı nesnesi ile her ilgili ayırıcı için çağırarak başlatılan yeni bir nesne oluşturur `select_on_container_copy_construction` .

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem etkin bir şekilde döndürür `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())` . Sonuç, `scoped_allocator_adaptor` `al.select_on_container_copy_construction()` ilgili ayırıcı *Al* için çağırarak, depolanan her ayırıcı nesnesi ile başlatılan yeni bir nesnedir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
