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
ms.openlocfilehash: b08cf1858cb0f9bf4dc6201edc2502d48754ff77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373394"
---
# <a name="scoped_allocator_adaptor-class"></a>scoped_allocator_adaptor Sınıfı

Ayırıcıların yuvasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, bir veya daha fazla ayırıcının yuvasını kapsar. Bu sınıfların, `outer_allocator_type` `Outer` `scoped_allocator_adaptor` nesnenin ortak tabanı olan bir eşanlamlı türüne sahip en dışa sahip bir ayırıcısı vardır. `Outer`bir kapsayıcı tarafından kullanılmak üzere bellek ayırmak için kullanılır. Bu ayırıcı temel nesneye başvuru olarak `outer_allocator`' ı arayarak alabilirsiniz.

Yuvanın geri kalanı `inner_allocator_type`türü vardır. Bir iç ayırıcı, bir kapsayıcı içindeki öğeler için bellek ayırmak için kullanılır. Bu türde depolanan nesneye başvuru yu `inner_allocator`tutarak . Boş `Inner...` değilse, `inner_allocator_type` türü `scoped_allocator_adaptor<Inner...>`vardır `inner_allocator` ve bir üye nesne belirler. Aksi `inner_allocator_type` takdirde, `scoped_allocator_adaptor<Outer>`türü `inner_allocator` vardır ve tüm nesneyi belirler.

Yuva rasgele derinliğe sahipmiş gibi görünür ve en içteki kapsüllü ayırıcısını gerektiği gibi çoğaltır.

Bu sınıf şablonunun davranışını açıklarken görünür arabirim yardımının bir parçası olmayan çeşitli kavramlar. En dıştaki bir *ayırıcı,* tüm çağrılara yapı ve yok etme yöntemlerine aracılık eder. Bu etkili özyinelemeli işlevi `OUTERMOST(X)`tarafından tanımlanır , `OUTERMOST(X)` aşağıdakilerden biri olan.

- Eğer `X.outer_allocator()` iyi biçimlendirilmişse, o `OUTERMOST(X)` `OUTERMOST(X.outer_allocator())`zaman .

- Aksi `OUTERMOST(X)` takdirde, . `X`

Sergi uğruna üç tür tanımlanmıştır:

|Tür|Açıklama|
|----------|-----------------|
|`Outermost`|Türü `OUTERMOST(*this)`.|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|Bir `scoped_allocator_adaptor` nesne inşa eder.|

### <a name="typedefs"></a>Tür tanımları

|Adı|Açıklama|
|----------|-----------------|
|`const_pointer`|Bu tür ayırıcı `const_pointer` `Outer`ile ilişkili bir eşanlamlıdır.|
|`const_void_pointer`|Bu tür ayırıcı `const_void_pointer` `Outer`ile ilişkili bir eşanlamlıdır.|
|`difference_type`|Bu tür ayırıcı `difference_type` `Outer`ile ilişkili bir eşanlamlıdır.|
|`inner_allocator_type`|Bu tür iç içe bağdaştırıcı türü için `scoped_allocator_adaptor<Inner...>`eşanlamlıdır.|
|`outer_allocator_type`|Bu tür, temel ayırıcının `Outer`türüyle eş anlamlıdır.|
|`pointer`|Bu tür ayırıcı `pointer` `Outer`ile ilişkili için eşanlamlıdır.|
|`propagate_on_container_copy_assignment`|Tür yalnızca doğru `Outer_traits::propagate_on_container_copy_assignment` veya doğru `inner_allocator_type::propagate_on_container_copy_assignment` tutar geçerlidir.|
|`propagate_on_container_move_assignment`|Tür yalnızca doğru `Outer_traits::propagate_on_container_move_assignment` veya doğru `inner_allocator_type::propagate_on_container_move_assignment` tutar geçerlidir.|
|`propagate_on_container_swap`|Tür yalnızca doğru `Outer_traits::propagate_on_container_swap` veya doğru `inner_allocator_type::propagate_on_container_swap` tutar geçerlidir.|
|`size_type`|Bu tür ayırıcı `size_type` `Outer`ile ilişkili için eşanlamlıdır.|
|`value_type`|Bu tür ayırıcı `value_type` `Outer`ile ilişkili için eşanlamlıdır.|
|`void_pointer`|Bu tür ayırıcı `void_pointer` `Outer`ile ilişkili için eşanlamlıdır.|

### <a name="structs"></a>Yapılar

|Adı|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor::rebind Yapı](#rebind_struct)|Türü `Outer::rebind\<Other>::other` eş anlamlı olarak `scoped_allocator_adaptor\<Other, Inner...>`tanımlar.|

### <a name="methods"></a>Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[allocate](#allocate)|Ayırıcıyı kullanarak `Outer` belleği ayırır.|
|[Oluşturmak](#construct)|Bir nesne inşa eder.|
|[Ayırması](#deallocate)|Dış ayırıcıyı kullanarak nesneleri yerle bir eder.|
|[destroy](#destroy)|Belirtilen nesneyi yok eder.|
|[inner_allocator](#inner_allocator)|Türünde depolanan nesneye bir `inner_allocator_type`başvuru alır.|
|[max_size](#max_size)|Dış ayırıcı tarafından ayrılabilecek en fazla nesne sayısını belirler.|
|[outer_allocator](#outer_allocator)|Türünde depolanan nesneye bir `outer_allocator_type`başvuru alır.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Her ilgili `scoped_allocator_adaptor` ayırıcı için çağırarak `select_on_container_copy_construction` baş harfe çevrilmiş her depolanan ayırıcı nesneile yeni bir nesne oluşturur.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_as)||
|[işleç==](#op_eq_eq)||
|[işleç!=](#op_noeq)||

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<scoped_allocator>

**Ad alanı:** std

## <a name="scoped_allocator_adaptorallocate"></a><a name="allocate"></a>scoped_allocator_adaptor::allocate

Ayırıcıyı kullanarak `Outer` belleği ayırır.

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
Yeterli depolama nın tahsis edilmesi gereken eleman sayısı.

*Ipucu*\
İstekten önce ayrılan bir nesnenin adresini bularak ayırıcı nesneye yardımcı olabilecek bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlev `Outer_traits::allocate(outer_allocator(), count)`döndürür. İkinci üye işlev `Outer_traits::allocate(outer_allocator(), count, hint)`döndürür.

## <a name="scoped_allocator_adaptorconstruct"></a><a name="construct"></a>scoped_allocator_adaptor::yapı

Bir nesne inşa eder.

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

*Ptr*\
Nesnenin oluşturulacağı bellek konumuna işaretçi.

*Args*\
Bağımsız değişkenlerin listesi.

*Ilk*\
Bir çiftteki ilk türdeki bir nesne.

*Ikinci*\
Bir çift ikinci türde bir nesne.

*Doğru*\
Taşınacak veya kopyalanacak varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk *yöntem, aşağıdakilerden* biri olan `xargs...` `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`ptr'deki nesneyi çağırarak yapıldır.

- Eğer `uses_allocator<Ty, inner_allocator_type>` yanlış tutarsa, o zaman `xargs...` . `args...`

- Eğer `uses_allocator<Ty, inner_allocator_type>` doğru tutar `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` ve doğru `xargs...` `allocator_arg, inner_allocator(), args...`tutar, o zaman .

- Eğer `uses_allocator<Ty, inner_allocator_type>` doğru tutar `is_constructible<Ty, args..., inner_allocator()>` ve doğru `xargs...` `args..., inner_allocator()`tutar, o zaman .

İkinci yöntem, yukarıdaki listede olduğu gibi `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`değiştirildiği `xargs...` `first...` ve `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)`yukarıdaki listede olduğu gibi `xargs...` değiştirildiği `second...` *ptr'de* çift nesnesini oluşturarak yapılır.

Üçüncü yöntem aynı şekilde `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)`olur.

Dördüncü yöntem aynı şekilde `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))`olur.

Beşinci yöntem aynı şekilde `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))`olur.

Altıncı yöntem aynı şekilde `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))`olur.

## <a name="scoped_allocator_adaptordeallocate"></a><a name="deallocate"></a>scoped_allocator_adaptor::deallocate

Dış ayırıcıyı kullanarak nesneleri yerle bir eder.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Ayrılacak nesnelerin başlangıç konumuna işaretçi.

*Sayısı*\
Anlaşma için nesnelerin sayısı.

## <a name="scoped_allocator_adaptordestroy"></a><a name="destroy"></a>scoped_allocator_adaptor::destroy

Belirtilen nesneyi yok eder.

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Yok edilecek nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="scoped_allocator_adaptorinner_allocator"></a><a name="inner_allocator"></a>scoped_allocator_adaptor:inner_allocator

Türünde depolanan nesneye bir `inner_allocator_type`başvuru alır.

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Türünde `inner_allocator_type`depolanan nesneye bir başvuru.

## <a name="scoped_allocator_adaptormax_size"></a><a name="max_size"></a>scoped_allocator_adaptor:max_size

Dış ayırıcı tarafından ayrılabilecek en fazla nesne sayısını belirler.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Dönüş Değeri

`Outer_traits::max_size(outer_allocator())`

## <a name="a-nameop_as--scoped_allocator_adaptoroperator"></a><a name="op_as">scoped_allocator_adaptor::operator=

```cpp
scoped_allocator_adaptor& operator=(const scoped_allocator_adaptor&) = default;
scoped_allocator_adaptor& operator=(scoped_allocator_adaptor&&) = default;
```

## <a name="a-nameop_eq_eq--scoped_allocator_adaptoroperator"></a><a name="op_eq_eq">scoped_allocator_adaptor::operator==

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator==(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="a-nameop_noeq--scoped_allocator_adaptoroperator"></a><a name="op_noeq">scoped_allocator_adaptor::operator!=

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator!=(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="scoped_allocator_adaptorouter_allocator"></a><a name="outer_allocator"></a>scoped_allocator_adaptor:outer_allocator

Türünde depolanan nesneye bir `outer_allocator_type`başvuru alır.

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Türünde `outer_allocator_type`depolanan nesneye bir başvuru.

## <a name="scoped_allocator_adaptorrebind-struct"></a><a name="rebind_struct"></a>scoped_allocator_adaptor::rebind Yapı

Türü `Outer::rebind\<Other>::other` eş anlamlı olarak `scoped_allocator_adaptor\<Other, Inner...>`tanımlar.

struct rebind{ typedef Other_traits::rebind\<Other>\<Other_alloc; typedef scoped_allocator_adaptor Other_alloc, Inner...> other; };

## <a name="scoped_allocator_adaptorscoped_allocator_adaptor-constructor"></a><a name="scoped_allocator_adaptor"></a>scoped_allocator_adaptor::scoped_allocator_adaptor Yapıcı

Bir `scoped_allocator_adaptor` nesne inşa eder. Ayrıca bir yıkıcı içerir.

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

*Doğru*\
Varolan `scoped_allocator_adaptor`bir .

*al*\
Dış ayırıcı olarak kullanılacak varolan bir ayırıcı.

*Geri kalanı*\
İç ayırıcıolarak kullanılacak ayırıcıların listesi.

### <a name="remarks"></a>Açıklamalar

İlk kurucu varsayılan, depolanan ayırıcı nesnelerini oluşturuyor. Sonraki üç kurucunun her biri, depolanan ayırıcı nesnelerini *sağdaki*ilgili nesnelerden inşa eder. Son oluşturucu, depolanan ayırıcı nesnelerini bağımsız değişken listesindeki ilgili bağımsız değişkenlerden oluşturuyor.

## <a name="scoped_allocator_adaptorselect_on_container_copy_construction"></a><a name="select_on_container_copy_construction"></a>scoped_allocator_adaptor:select_on_container_copy_construction

Her ilgili `scoped_allocator_adaptor` ayırıcı için çağırarak `select_on_container_copy_construction` baş harfe çevrilmiş her depolanan ayırıcı nesneile yeni bir nesne oluşturur.

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem etkili `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())`bir şekilde döndürür. Sonuç, ilgili `scoped_allocator_adaptor` ayırıcı `al.select_on_container_copy_construction()` *al*çağırarak baş harfe çevrilmiş her depolanan ayırıcı nesneile yeni bir nesnedir.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)
