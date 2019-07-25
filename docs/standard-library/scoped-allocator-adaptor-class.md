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
ms.openlocfilehash: 1fb2842df50b0e803419e3cccdeb921c9b4fa591
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458004"
---
# <a name="scopedallocatoradaptor-class"></a>scoped_allocator_adaptor Sınıfı

Ayırıcıların iç içe geçmiş olduğunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir veya daha fazla ayırıcıdan oluşan bir iç içe geçmiş saklar. Bu tür bir sınıfın en dıştaki türü `outer_allocator_type`, için `Outer`bir genel bakış olan, `scoped_allocator_adaptor` nesnenin ortak tabanı olan. `Outer`bir kapsayıcı tarafından kullanılacak belleği ayırmak için kullanılır. Çağırarak `outer_allocator`, bu ayırıcı temel nesnesine bir başvuru elde edebilirsiniz.

İç içe geçmiş 'nin geri kalanı türünde `inner_allocator_type`. Bir iç ayırıcı, bir kapsayıcı içindeki öğelere bellek ayırmak için kullanılır. Çağırarak `inner_allocator`, bu türün saklı nesnesine bir başvuru elde edebilirsiniz. Boş değilse, `inner_allocator_type` türüne `scoped_allocator_adaptor<Inner...>`sahiptir ve`inner_allocator` bir üye nesnesi belirler. `Inner...` Aksi takdirde `inner_allocator_type` , türüne `scoped_allocator_adaptor<Outer>`sahiptir ve `inner_allocator` tüm nesneyi belirtir.

İç içe geçmiş, rastgele derinliğe sahip gibi davranır ve en içteki kapsüllenmiş ayırıcıyı gerektiği gibi çoğaltmıştır.

Bu şablon sınıfının davranışını tanımlamaya yardımcı olan görünür arabirimin bir parçası olmayan birkaç kavram. En *dıştaki ayırıcı* , yapı ve yok yöntemlerine yapılan tüm çağrıları gösterir. Özyinelemeli işlev `OUTERMOST(X)`tarafından etkin bir şekilde tanımlanır, burada `OUTERMOST(X)` aşağıdakilerden biridir.

- `X.outer_allocator()` Düzgün biçimlendirilmişse `OUTERMOST(X)` , .`OUTERMOST(X.outer_allocator())`

- Aksi halde `OUTERMOST(X)` , `X`.

, Exposition 'ın sake 'ı için üç tür tanımlanmıştır:

|Tür|Açıklama|
|----------|-----------------|
|`Outermost`|Türü `OUTERMOST(*this)`.|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|Bir `scoped_allocator_adaptor` nesnesi oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bu tür, `const_pointer` ayırıcıyla `Outer`ilişkili olan için bir eş anladır.|
|`const_void_pointer`|Bu tür, `const_void_pointer` ayırıcıyla `Outer`ilişkili olan için bir eş anladır.|
|`difference_type`|Bu tür, `difference_type` ayırıcıyla `Outer`ilişkili olan için bir eş anladır.|
|`inner_allocator_type`|Bu tür, iç içe geçmiş bağdaştırıcı `scoped_allocator_adaptor<Inner...>`türü için bir eş anlamlı.|
|`outer_allocator_type`|Bu tür, temel ayırıcı `Outer`türünün bir eş anlamlısıdır.|
|`pointer`|Bu tür, ayırıcıyla `pointer` `Outer`ilişkili için bir eş anladır.|
|`propagate_on_container_copy_assignment`|Tür true, ancak `Outer_traits::propagate_on_container_copy_assignment` doğru tutuyorsa ya da `inner_allocator_type::propagate_on_container_copy_assignment` doğru tutuyorsa geçerlidir.|
|`propagate_on_container_move_assignment`|Tür true, ancak `Outer_traits::propagate_on_container_move_assignment` doğru tutuyorsa ya da `inner_allocator_type::propagate_on_container_move_assignment` doğru tutuyorsa geçerlidir.|
|`propagate_on_container_swap`|Tür true, ancak `Outer_traits::propagate_on_container_swap` doğru tutuyorsa ya da `inner_allocator_type::propagate_on_container_swap` doğru tutuyorsa geçerlidir.|
|`size_type`|Bu tür, ayırıcıyla `size_type` `Outer`ilişkili için bir eş anladır.|
|`value_type`|Bu tür, ayırıcıyla `value_type` `Outer`ilişkili için bir eş anladır.|
|`void_pointer`|Bu tür, ayırıcıyla `void_pointer` `Outer`ilişkili için bir eş anladır.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[scoped_allocator_adaptor:: yeniden bağlama yapısı](#rebind_struct)|Türü `Outer::rebind\<Other>::other` için`scoped_allocator_adaptor\<Other, Inner...>`bir eş anlamlı olarak tanımlar.|

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[allocate](#allocate)|`Outer` Ayırıcıyı kullanarak belleği ayırır.|
|[oluşturma](#construct)|Bir nesnesi oluşturur.|
|[kaldırmak](#deallocate)|Nesneleri dış ayırıcıyı kullanarak ayırır.|
|[kaldırılır](#destroy)|Belirtilen nesneyi yok eder.|
|[inner_allocator](#inner_allocator)|Türündeki `inner_allocator_type`saklı nesneye bir başvuru alır.|
|[max_size](#max_size)|Dış ayırıcı tarafından ayrılabilen en fazla nesne sayısını belirler.|
|[outer_allocator](#outer_allocator)|Türündeki `outer_allocator_type`saklı nesneye bir başvuru alır.|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|Her bir saklı `scoped_allocator_adaptor` ayırıcı nesnesi ile her ilgili ayırıcı için çağırarak `select_on_container_copy_construction` başlatılan yeni bir nesne oluşturur.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_as)||
|[operator==](#op_eq_eq)||
|[operator!=](#op_noeq)||

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<scoped_allocator >

**Ad alanı:** std

## <a name="allocate"></a>scoped_allocator_adaptor:: allocate

`Outer` Ayırıcıyı kullanarak belleği ayırır.

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Yeterli depolamanın ayrılabileceği öğe sayısı.

*OPTI*\
İstekten önce ayrılan nesnenin adresini bularak ayırıcı nesnesine yardımcı olabilecek bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi döndürür `Outer_traits::allocate(outer_allocator(), count)`. İkinci üye işlevi döndürür `Outer_traits::allocate(outer_allocator(), count, hint)`.

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

İlk yöntem, aşağıdaki yöntemlerden biri `xargs...` olan  öğesini çağırarak `Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)`nesne PTR 'de oluşturur.

- Yanlış `uses_allocator<Ty, inner_allocator_type>` tutuyorsa `xargs...` , .`args...`

- Doğru tutuyorsa ve doğru tutuyorsa `is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` , ve ' `xargs...` dir `allocator_arg, inner_allocator(), args...`. `uses_allocator<Ty, inner_allocator_type>`

- Doğru tutuyorsa ve doğru tutuyorsa `is_constructible<Ty, args..., inner_allocator()>` , ve ' `xargs...` dir `args..., inner_allocator()`. `uses_allocator<Ty, inner_allocator_type>`

İkinci yöntem, öğesini çağırarak, yukarıdaki listede  `Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)` `Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)` `xargs...` `first...` olarak değiştirildiği ve yukarıdaki listede olduğu gibi değiştirildiği,öğesiniçağırarakPTR'deçiftnesneyioluşturur.`second...` `xargs...`

Üçüncü yöntem ile aynı şekilde `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)`davranır.

Dördüncü yöntem ile aynı şekilde `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))`davranır.

Beşinci yöntem ile aynı şekilde `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))`davranır.

Altıncı yöntem ile aynı şekilde `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))`davranır.

## <a name="deallocate"></a>scoped_allocator_adaptor::d eallocate

Nesneleri dış ayırıcıyı kullanarak ayırır.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Serbest bırakmak için nesnelerin başlangıç konumuna yönelik bir işaretçi.

*biriktirme*\
Serbest bırakmak için nesne sayısı.

## <a name="destroy"></a>scoped_allocator_adaptor::d estroy

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

## <a name="inner_allocator"></a>scoped_allocator_adaptor::inner_allocator

Türündeki `inner_allocator_type`saklı nesneye bir başvuru alır.

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Türündeki `inner_allocator_type`saklı nesneye bir başvuru.

## <a name="max_size"></a>scoped_allocator_adaptor::max_size

Dış ayırıcı tarafından ayrılabilen en fazla nesne sayısını belirler.

```cpp
size_type max_size();
```

### <a name="return-value"></a>Dönüş Değeri

`Outer_traits::max_size(outer_allocator())`

## <a name="a-nameopas--scopedallocatoradaptoroperator"></a><a name="op_as">scoped_allocator_adaptor:: operator =

```cpp
scoped_allocator_adaptor& operator=(const scoped_allocator_adaptor&) = default;
scoped_allocator_adaptor& operator=(scoped_allocator_adaptor&&) = default;
```

## <a name="a-nameopeqeq--scopedallocatoradaptoroperator"></a><a name="op_eq_eq">scoped_allocator_adaptor:: operator = =

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator==(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="a-nameopnoeq--scopedallocatoradaptoroperator"></a><a name="op_noeq">scoped_allocator_adaptor:: operator! =

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator!=(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="outer_allocator"></a>scoped_allocator_adaptor::outer_allocator

Türündeki `outer_allocator_type`saklı nesneye bir başvuru alır.

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Türündeki `outer_allocator_type`saklı nesneye bir başvuru.

## <a name="rebind_struct"></a>scoped_allocator_adaptor:: yeniden bağlama yapısı

Türü `Outer::rebind\<Other>::other` için`scoped_allocator_adaptor\<Other, Inner...>`bir eş anlamlı olarak tanımlar.

struct yeniden bağlama {typedef Other_traits::\<diğer > Other_alloc; typedef scoped_allocator_adaptor\<Other_alloc, iç... > diğer; };

## <a name="scoped_allocator_adaptor"></a>scoped_allocator_adaptor:: scoped_allocator_adaptor Oluşturucusu

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
Mevcut `scoped_allocator_adaptor`bir.

*Eşkenar*\
Dış ayırıcı olarak kullanılacak mevcut bir ayırıcı.

*kalanı*\
İç ayırıcılar olarak kullanılacak ayrıcılar listesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan, depolanan ayırıcı nesnelerini oluşturur. Sonraki üç oluşturucuların her biri, saklı ayırıcı nesnelerini *sağ taraftaki*ilgili nesnelerden oluşturur. Son Oluşturucu, bağımsız değişken listesindeki ilgili bağımsız değişkenlerden saklı ayırıcı nesnelerini oluşturur.

## <a name="select_on_container_copy_construction"></a>scoped_allocator_adaptor::select_on_container_copy_construction

Her bir saklı `scoped_allocator_adaptor` ayırıcı nesnesi ile her ilgili ayırıcı için çağırarak `select_on_container_copy_construction` başlatılan yeni bir nesne oluşturur.

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem etkin bir `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())`şekilde döndürür. Sonuç, ilgili ayırıcı `scoped_allocator_adaptor` *Al*için çağırarak `al.select_on_container_copy_construction()` , depolanan her ayırıcı nesnesi ile başlatılan yeni bir nesnedir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
