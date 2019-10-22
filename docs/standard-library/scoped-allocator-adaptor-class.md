---
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
ms.openlocfilehash: 6ba135d0c3a69293415d1c46d70679d9f8bc8a37
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686548"
---
# <a name="scoped_allocator_adaptor-class"></a>scoped_allocator_adaptor Sınıfı

Ayırıcıların iç içe geçmiş olduğunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir veya daha fazla ayırıcıların iç içe bir kısmını kapsar. Bu tür bir sınıfın en dıştaki türü `outer_allocator_type`, `scoped_allocator_adaptor` nesnenin ortak tabanı olan `Outer` için bir eş anlamlı. `Outer` bir kapsayıcı tarafından kullanılacak belleği ayırmak için kullanılır. @No__t_0 çağırarak, bu ayırıcı temel nesnesine bir başvuru elde edebilirsiniz.

İç içe geçme geri kalanı `inner_allocator_type` türünde. Bir iç ayırıcı, bir kapsayıcı içindeki öğelere bellek ayırmak için kullanılır. @No__t_0 çağırarak, bu türün saklı nesnesine bir başvuru elde edebilirsiniz. @No__t_0 boş değilse, `inner_allocator_type` tür `scoped_allocator_adaptor<Inner...>` ve `inner_allocator` bir üye nesnesi belirler. Aksi takdirde, `inner_allocator_type` `scoped_allocator_adaptor<Outer>` tür ve `inner_allocator` tüm nesneyi belirtir.

İç içe geçmiş, rastgele derinliğe sahip gibi davranır ve en içteki kapsüllenmiş ayırıcıyı gerektiği gibi çoğaltmıştır.

Görünür arabirimin bir parçası olmayan çeşitli kavramlar, bu sınıf şablonunun davranışını tanımlamaya yardımcı olur. En *dıştaki ayırıcı* , yapı ve yok yöntemlerine yapılan tüm çağrıları gösterir. Özyinelemeli işlev `OUTERMOST(X)` tarafından etkili bir şekilde tanımlanır; burada `OUTERMOST(X)` aşağıdakilerden biridir.

- @No__t_0 iyi biçimlendirilmişse `OUTERMOST(X)` `OUTERMOST(X.outer_allocator())`.

- Aksi takdirde, `OUTERMOST(X)` `X`.

, Exposition 'ın sake 'ı için üç tür tanımlanmıştır:

|Tür|Açıklama|
|----------|-----------------|
|`Outermost`|@No__t_0 türü.|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|@No__t_0 nesnesi oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Name|Açıklama|
|----------|-----------------|
|`const_pointer`|Bu tür, ayırıcı `Outer` ilişkili `const_pointer` için bir eş anladır.|
|`const_void_pointer`|Bu tür, ayırıcı `Outer` ilişkili `const_void_pointer` için bir eş anladır.|
|`difference_type`|Bu tür, ayırıcı `Outer` ilişkili `difference_type` için bir eş anladır.|
|`inner_allocator_type`|Bu tür, iç içe geçmiş bağdaştırıcı türü için bir eş anlamlı `scoped_allocator_adaptor<Inner...>`.|
|`outer_allocator_type`|Bu tür, `Outer` temel ayırıcı türü için bir eş anlamlı.|
|`pointer`|Bu tür, ayırıcı `Outer` ilişkili `pointer` için bir eş anladır.|
|`propagate_on_container_copy_assignment`|Tür true, yalnızca `Outer_traits::propagate_on_container_copy_assignment` true ise true, `inner_allocator_type::propagate_on_container_copy_assignment` saklar.|
|`propagate_on_container_move_assignment`|Tür true, yalnızca `Outer_traits::propagate_on_container_move_assignment` true ise true, `inner_allocator_type::propagate_on_container_move_assignment` saklar.|
|`propagate_on_container_swap`|Tür true, yalnızca `Outer_traits::propagate_on_container_swap` true ise true, `inner_allocator_type::propagate_on_container_swap` saklar.|
|`size_type`|Bu tür, ayırıcı `Outer` ilişkili `size_type` için bir eş anladır.|
|`value_type`|Bu tür, ayırıcı `Outer` ilişkili `value_type` için bir eş anladır.|
|`void_pointer`|Bu tür, ayırıcı `Outer` ilişkili `void_pointer` için bir eş anladır.|

### <a name="structs"></a>Yapılar

|Name|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor:: yeniden bağlama yapısı](#rebind_struct)|@No__t_1 için bir eş anlamlı `Outer::rebind\<Other>::other` türünü tanımlar.|

### <a name="methods"></a>Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[allocate](#allocate)|@No__t_0 ayırıcıyı kullanarak belleği ayırır.|
|[oluşturma](#construct)|Bir nesnesi oluşturur.|
|[kaldırmak](#deallocate)|Nesneleri dış ayırıcıyı kullanarak ayırır.|
|[kaldırılır](#destroy)|Belirtilen nesneyi yok eder.|
|[inner_allocator](#inner_allocator)|@No__t_0 türündeki saklı nesneye bir başvuru alır.|
|[max_size](#max_size)|Dış ayırıcı tarafından ayrılabilen en fazla nesne sayısını belirler.|
|[outer_allocator](#outer_allocator)|@No__t_0 türündeki saklı nesneye bir başvuru alır.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Her ilgili ayırıcı için `select_on_container_copy_construction` çağırarak her bir Depolanan ayırıcı nesnesi ile başlatılan yeni bir `scoped_allocator_adaptor` nesnesi oluşturur.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_as)||
|[işleç = =](#op_eq_eq)||
|[operator!=](#op_noeq)||

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<scoped_allocator >

**Ad alanı:** std

## <a name="allocate"></a>scoped_allocator_adaptor:: allocate

@No__t_0 ayırıcıyı kullanarak belleği ayırır.

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Parametreler

*sayı* \
Yeterli depolamanın ayrılabileceği öğe sayısı.

*ipucu* \
İstekten önce ayrılan nesnenin adresini bularak ayırıcı nesnesine yardımcı olabilecek bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi `Outer_traits::allocate(outer_allocator(), count)` döndürür. İkinci üye işlevi `Outer_traits::allocate(outer_allocator(), count, hint)` döndürür.

## <a name="construct"></a>scoped_allocator_adaptor:: yapısı

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

*ptr* \
Nesnenin oluşturulması gereken bellek konumuna yönelik bir işaretçi.

*bağımsız değişkenler* \
Bağımsız değişkenlerin listesi.

*ilk* \
Bir çiftin ilk türündeki nesne.

*ikinci* \
Çiftteki ikinci türdeki bir nesne.

*sağ* \
Taşınacak veya Kopyalanacak varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk yöntem, `xargs...` aşağıdakilerden biri olan `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)` çağırarak nesneyi *PTR* 'de oluşturur.

- @No__t_0 yanlış tutuyorsa `xargs...` `args...`.

- @No__t_0 true olursa ve `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` doğru tutuyorsa `xargs...` `allocator_arg, inner_allocator(), args...`.

- @No__t_0 true olursa ve `is_constructible<Ty, args..., inner_allocator()>` doğru tutuyorsa `xargs...` `args..., inner_allocator()`.

İkinci yöntem, `xargs...` *`Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)` çağırarak ve* yukarıdaki listede olduğu gibi `first...` değiştirildiği ve `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`, yukarıdaki listede olduğu gibi `xargs...` değiştirilen.

Üçüncü yöntem `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)` ile aynı şekilde davranır.

Dördüncü Yöntem `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))` ile aynı şekilde davranır.

Beşinci Yöntem `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))` ile aynı şekilde davranır.

Altıncı Yöntem `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))` ile aynı şekilde davranır.

## <a name="deallocate"></a>scoped_allocator_adaptor::d eallocate

Nesneleri dış ayırıcıyı kullanarak ayırır.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

*ptr* \
Serbest bırakmak için nesnelerin başlangıç konumuna yönelik bir işaretçi.

*sayı* \
Serbest bırakmak için nesne sayısı.

## <a name="destroy"></a>scoped_allocator_adaptor::d estroy

Belirtilen nesneyi yok eder.

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>Parametreler

*ptr* \
Yok edilecek nesneye yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="inner_allocator"></a>scoped_allocator_adaptor::inner_allocator

@No__t_0 türündeki saklı nesneye bir başvuru alır.

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 türünde depolanan nesneye bir başvuru.

## <a name="max_size"></a>scoped_allocator_adaptor::max_size

Dış ayırıcı tarafından ayrılabilen en fazla nesne sayısını belirler.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Dönüş Değeri

`Outer_traits::max_size(outer_allocator())`

## <a name="a-nameop_as--scoped_allocator_adaptoroperator"></a><a name="op_as"> scoped_allocator_adaptor:: operator =

```cpp
scoped_allocator_adaptor& operator=(const scoped_allocator_adaptor&) = default;
scoped_allocator_adaptor& operator=(scoped_allocator_adaptor&&) = default;
```

## <a name="a-nameop_eq_eq--scoped_allocator_adaptoroperator"></a><a name="op_eq_eq"> scoped_allocator_adaptor:: operator = =

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator==(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="a-nameop_noeq--scoped_allocator_adaptoroperator"></a><a name="op_noeq"> scoped_allocator_adaptor:: operator! =

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator!=(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="outer_allocator"></a>scoped_allocator_adaptor::outer_allocator

@No__t_0 türündeki saklı nesneye bir başvuru alır.

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 türünde depolanan nesneye bir başvuru.

## <a name="rebind_struct"></a>scoped_allocator_adaptor:: yeniden bağlama yapısı

@No__t_1 için bir eş anlamlı `Outer::rebind\<Other>::other` türünü tanımlar.

struct yeniden bağlama {typedef Other_traits:: yeniden bağlama \<Other > Other_alloc; typedef scoped_allocator_adaptor \<Other_alloc, Iç... > diğer; };

## <a name="scoped_allocator_adaptor"></a>scoped_allocator_adaptor:: scoped_allocator_adaptor Oluşturucusu

@No__t_0 nesnesi oluşturur. Ayrıca bir yıkıcı içerir.

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

*sağ* \
Mevcut bir `scoped_allocator_adaptor`.

*al* \
Dış ayırıcı olarak kullanılacak mevcut bir ayırıcı.

*rest* \
İç ayırıcılar olarak kullanılacak ayrıcılar listesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan, depolanan ayırıcı nesnelerini oluşturur. Sonraki üç oluşturucuların her biri, saklı ayırıcı nesnelerini *sağ taraftaki*ilgili nesnelerden oluşturur. Son Oluşturucu, bağımsız değişken listesindeki ilgili bağımsız değişkenlerden saklı ayırıcı nesnelerini oluşturur.

## <a name="select_on_container_copy_construction"></a>scoped_allocator_adaptor::select_on_container_copy_construction

Her ilgili ayırıcı için `select_on_container_copy_construction` çağırarak her bir Depolanan ayırıcı nesnesi ile başlatılan yeni bir `scoped_allocator_adaptor` nesnesi oluşturur.

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())` etkin bir şekilde döndürür. Sonuç, karşılık gelen ayırıcı *Al*için `al.select_on_container_copy_construction()` çağırarak, depolanan her ayırıcı nesnesi ile başlatılan yeni bir `scoped_allocator_adaptor` nesnesidir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
