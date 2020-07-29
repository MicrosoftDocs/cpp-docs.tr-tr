---
title: concurrent_vector Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::assign
- CONCURRENT_VECTOR/concurrency::concurrent_vector::at
- CONCURRENT_VECTOR/concurrency::concurrent_vector::back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::begin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::capacity
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::clear
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::empty
- CONCURRENT_VECTOR/concurrency::concurrent_vector::end
- CONCURRENT_VECTOR/concurrency::concurrent_vector::front
- CONCURRENT_VECTOR/concurrency::concurrent_vector::get_allocator
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_by
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_to_at_least
- CONCURRENT_VECTOR/concurrency::concurrent_vector::max_size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::push_back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::reserve
- CONCURRENT_VECTOR/concurrency::concurrent_vector::resize
- CONCURRENT_VECTOR/concurrency::concurrent_vector::shrink_to_fit
- CONCURRENT_VECTOR/concurrency::concurrent_vector::size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::swap
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
ms.openlocfilehash: 9144fd0870bfb72e923a7271ffdd655e03a9bd57
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215848"
---
# <a name="concurrent_vector-class"></a>concurrent_vector Sınıfı

`concurrent_vector`Sınıfı herhangi bir öğeye rastgele erişime izin veren bir dizi kapsayıcı sınıfıdır. Eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine izin vermez. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
private details::_Concurrent_vector_base_v4;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Vektörde depolanacak öğelerin veri türü.

*_Ax*<br/>
Eşzamanlı vektör için bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<T>` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Eşzamanlı vektörün ayırıcı sınıfını temsil eden bir tür.|
|`const_iterator`|Eşzamanlı vektörde bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .|
|`const_pointer`|Eşzamanlı vektörde bir öğeye işaretçi sağlayan bir tür **`const`** .|
|`const_reference`|**`const`** İşlemleri okumak ve gerçekleştirmek için eşzamanlı vektörde depolanan bir öğeye başvuru sağlayan bir tür **`const`** .|
|`const_reverse_iterator`|Eşzamanlı vektörde herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür **`const`** .|
|`difference_type`|Eşzamanlı bir vektörde iki öğe arasındaki işaretli mesafeyi sağlayan bir tür.|
|`iterator`|Eşzamanlı vektörde herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür. Yineleyici kullanan bir öğe değişikliği eşzamanlılık açısından güvenli değildir.|
|`pointer`|Eşzamanlı vektörde bir öğeye işaretçi sağlayan bir tür.|
|`reference`|Eşzamanlı vektörde depolanan bir öğeye başvuru sağlayan bir tür.|
|`reverse_iterator`|Tersine çevrilmiş bir vektörde herhangi bir öğeyi okuyabilen bir rastgele erişim yineleyici sağlayan bir tür. Yineleyici kullanan bir öğe değişikliği eşzamanlılık açısından güvenli değildir.|
|`size_type`|Eşzamanlı Vektördeki öğelerin sayısını sayan bir tür.|
|`value_type`|Eşzamanlı vektörde depolanan veri türünü temsil eden bir tür.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[concurrent_vector](#ctor)|Fazla Yüklendi. Eşzamanlı bir vektör oluşturur.|
|[~ concurrent_vector yok edici](#dtor)|Tüm öğeleri siler ve bu eşzamanlı vektörü yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[assign (atamak)](#assign) |Fazla Yüklendi. Eş zamanlı vektörün öğelerini siler ve bu ya da ya da `_N` `_Item` yineleyici aralığı [,) tarafından belirtilen değerler veya kopya atar `_Begin` `_End` . Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[hızı](#at)|Fazla Yüklendi. Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda, değerin `_Index` eşzamanlı vektör boyutundan daha az olduğu sürece vektörü büyüyordur.|
|[Geri](#back)|Fazla Yüklendi. **`const`** Eşzamanlı Vektördeki son öğeye bir başvuru veya başvuru döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[başladı](#begin)|Fazla Yüklendi. `iterator` `const_iterator` Eş zamanlı vektörün türü veya başına bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[kü](#capacity)|Eşzamanlı vektörün daha fazla bellek ayırmaya gerek kalmadan büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[cbegin](#cbegin)|`const_iterator`Eş zamanlı vektörün başına türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[cend](#cend)|`const_iterator`Eş zamanlı vektörün sonuna türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[lediğiniz](#clear)|Eşzamanlı Vektördeki tüm öğeleri siler. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[crbegin](#crbegin)|`const_reverse_iterator`Eş zamanlı vektörün başına türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[crend](#crend)|`const_reverse_iterator`Eş zamanlı vektörün sonuna türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[empty](#empty)|Bu yöntemin çağrılışında eşzamanlı vektör boş ise, sınar. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[erer](#end)|Fazla Yüklendi. `iterator` `const_iterator` Eş zamanlı vektörün türü veya sonuna bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[yapılan](#front)|Fazla Yüklendi. **`const`** Eşzamanlı Vektördeki ilk öğenin başvurusunu veya başvurusunu döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[get_allocator](#get_allocator)|Eş zamanlı vektörü oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[grow_by](#grow_by)|Fazla Yüklendi. Bu eşzamanlı vektörü öğelere göre büyürken `_Delta` . Bu yöntem eşzamanlılık açısından güvenlidir.|
|[grow_to_at_least](#grow_to_at_least)|En az öğelere sahip olana kadar bu eşzamanlı vektörü büyürken `_N` . Bu yöntem eşzamanlılık açısından güvenlidir.|
|[max_size](#max_size)|Eşzamanlı vektörde tutabileceğiniz en fazla öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[push_back](#push_back)|Fazla Yüklendi. Verilen öğeyi, eşzamanlı vektörün sonuna ekler. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[rbegin](#rbegin)|Fazla Yüklendi. `reverse_iterator` `const_reverse_iterator` Eş zamanlı vektörün türü veya başına bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[rend](#rend)|Fazla Yüklendi. `reverse_iterator` `const_reverse_iterator` Eş zamanlı vektörün türü veya sonuna bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[Rezerve et](#reserve)|Daha `_N` sonra daha fazla bellek ayırmaya gerek kalmadan, eşzamanlı vektörün boyutunu büyütmek için yeterli alan ayırır. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[yeniden boyutlandırma](#resize)|Fazla Yüklendi. Eşzamanlı vektörün boyutunu istenen boyut olarak değiştirir, öğeleri silin veya gerekli şekilde ekleyin. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[shrink_to_fit](#shrink_to_fit)|Parçalanmayı azaltmak ve bellek kullanımını iyileştirmek için eşzamanlı vektörün iç gösterimini sıkıştırır. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[boyutla](#size)|Eşzamanlı Vektördeki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[Kur](#swap)|İki eşzamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç\[\]](#operator_at)|Fazla Yüklendi. Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda değerin `_Index` eşzamanlı vektörün boyutundan daha az olduğu sürece vektörü büyümekte.|
|[işleç =](#operator_eq)|Fazla Yüklendi. Başka bir `concurrent_vector` nesnenin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

Sınıfıyla ilgili ayrıntılı bilgi için `concurrent_vector` bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Concurrent_vector_base_v4`

`_Allocator_base`

`concurrent_vector`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** concurrent_vector. h

**Ad alanı:** eşzamanlılık

## <a name="assign"></a><a name="assign"></a>ata

Eş zamanlı vektörün öğelerini siler ve bu ya da ya da `_N` `_Item` yineleyici aralığı [,) tarafından belirtilen değerler veya kopya atar `_Begin` `_End` . Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>Parametreler

*_InputIterator*<br/>
Belirtilen yineleyicinin türü.

*_N*<br/>
Eşzamanlı vektöre kopyalanacak öğe sayısı.

*_Item*<br/>
Eşzamanlı vektörü dolduracak şekilde kullanılan bir değere başvuru.

*_Begin*<br/>
Kaynak aralığın ilk öğesine bir yineleyici.

*_End*<br/>
Kaynak aralığın son öğesini aşan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`assign`eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir.

## <a name="at"></a><a name="at"></a>hızı

Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda, değerin `_Index` eşzamanlı vektör boyutundan daha az olduğu sürece vektörü büyüyordur.

```cpp
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Verilen dizindeki öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

`at`Başvuruya ait olmayan bir başvuru döndüren işlevin sürümü, **`const`** farklı iş parçacıklarından öğeye eşzamanlı olarak yazmak için kullanılamaz. Aynı veri öğesiyle eşzamanlı okuma ve yazma işlemlerini eşitlemek için farklı bir eşitleme nesnesi kullanılmalıdır.

Yöntemi, `out_of_range` `_Index` eş zamanlı vektörün boyutundan büyük veya ona eşit ise ve `range_error` Dizin, vector öğesinin bozuk bir bölümü için ise bu oluşur. Vector öğesinin nasıl kopuk hale gelebilmesi hakkındaki ayrıntılar için bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="back"></a><a name="back"></a>Geri

**`const`** Eşzamanlı Vektördeki son öğeye bir başvuru veya başvuru döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Eşzamanlı Vektördeki son öğeye başvuru veya başvuru.

## <a name="begin"></a><a name="begin"></a>başladı

`iterator` `const_iterator` Eş zamanlı vektörün türü veya başına bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`iterator` `const_iterator` Eş zamanlı vektörün türü veya başına bir yineleyici.

## <a name="capacity"></a><a name="capacity"></a>kü

Eşzamanlı vektörün daha fazla bellek ayırmaya gerek kalmadan büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı vektörün daha fazla bellek ayırmaya gerek kalmadan büyüyebileceği maksimum boyut.

### <a name="remarks"></a>Açıklamalar

C++ standart kitaplığının aksine `vector` , bir `concurrent_vector` nesne daha fazla bellek ayırırsa mevcut öğeleri taşımaz.

## <a name="cbegin"></a><a name="cbegin"></a>cbegin

`const_iterator`Eş zamanlı vektörün başına türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`const_iterator`Eş zamanlı vektörün başına türünde bir yineleyici.

## <a name="cend"></a><a name="cend"></a>cend

`const_iterator`Eş zamanlı vektörün sonuna türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

`const_iterator`Eş zamanlı vektörün sonuna türünde bir yineleyici.

## <a name="clear"></a><a name="clear"></a>lediğiniz

Eşzamanlı Vektördeki tüm öğeleri siler. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

`clear`eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir. `clear`iç dizileri serbest vermez. İç dizileri serbest bırakmak için, `shrink_to_fit` öğesinden sonra işlevini çağırın `clear` .

## <a name="concurrent_vector"></a><a name="ctor"></a>concurrent_vector

Eşzamanlı bir vektör oluşturur.

```cpp
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```

### <a name="parameters"></a>Parametreler

*M*<br/>
Kaynak vektörünün ayırıcı türü.

*_InputIterator*<br/>
Giriş yineleyicisinin türü.

*_Al*<br/>
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*_Vector*<br/>
`concurrent_vector`Öğelerin kopyalanacağı veya taşınacağı kaynak nesne.

*_N*<br/>
Nesnenin ilk kapasitesi `concurrent_vector` .

*_Item*<br/>
Oluşturulan nesnedeki öğelerin değeri.

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesnesi depolar `_Al` ve vektörü başlatır.

İlk Oluşturucu boş bir ilk vektör belirtiyor ve açıkça ayırıcı türünü belirtir. kullanılır.

İkinci ve üçüncü oluşturucular, eşzamanlı vektörün bir kopyasını belirtir `_Vector` .

Dördüncü Oluşturucu, eşzamanlı vektörün bir hareketini belirtir `_Vector` .

Beşinci Oluşturucu, `_N` sınıfının varsayılan değerinin belirtilen () öğelerinin bir tekrarını belirtir `T` .

Altıncı Oluşturucu değer () öğelerinin tekrarından oluşan bir `_N` değeri belirtir `_Item` .

Son Oluşturucu yineleyici aralığı [,) tarafından sağlanan değerleri belirtir `_Begin` `_End` .

## <a name="concurrent_vector"></a><a name="dtor"></a>~ concurrent_vector

Tüm öğeleri siler ve bu eşzamanlı vektörü yok eder.

```cpp
~concurrent_vector();
```

## <a name="crbegin"></a><a name="crbegin"></a>crbegin

`const_reverse_iterator`Eş zamanlı vektörün başına türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`const_reverse_iterator`Eş zamanlı vektörün başına türünde bir yineleyici.

## <a name="crend"></a><a name="crend"></a>crend

`const_reverse_iterator`Eş zamanlı vektörün sonuna türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

`const_reverse_iterator`Eş zamanlı vektörün sonuna türünde bir yineleyici.

## <a name="empty"></a><a name="empty"></a>olmamalıdır

Bu yöntemin çağrılışında eşzamanlı vektör boş ise, sınar. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** vektör, işlevin çağrıldığı anda boşsa, **`false`** tersi durumda.

## <a name="end"></a><a name="end"></a>erer

`iterator` `const_iterator` Eş zamanlı vektörün türü veya sonuna bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

`iterator` `const_iterator` Eş zamanlı vektörün türü veya sonuna bir yineleyici.

## <a name="front"></a><a name="front"></a>yapılan

**`const`** Eşzamanlı Vektördeki ilk öğenin başvurusunu veya başvurusunu döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** Eşzamanlı Vektördeki ilk öğeye başvuru veya başvuru.

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

Eş zamanlı vektörü oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi oluşturmak için kullanılan ayırıcıın bir kopyası `concurrent_vector` .

## <a name="grow_by"></a><a name="grow_by"></a>grow_by

Bu eşzamanlı vektörü öğelere göre büyürken `_Delta` . Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```

### <a name="parameters"></a>Parametreler

*_Delta*<br/>
Nesneye eklenecek öğe sayısı.

*_Item*<br/>
Yeni öğelerin başlangıç değeri.

### <a name="return-value"></a>Dönüş Değeri

İlk öğeye eklenen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`_Item`Belirtilmemişse, yeni öğeler varsayılan olarak oluşturulur.

## <a name="grow_to_at_least"></a><a name="grow_to_at_least"></a>grow_to_at_least

En az öğelere sahip olana kadar bu eşzamanlı vektörü büyürken `_N` . Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator grow_to_at_least(size_type _N);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
Nesnenin yeni en küçük boyutu `concurrent_vector` .

### <a name="return-value"></a>Dönüş Değeri

Eklenen sıranın başlangıcını işaret eden bir yineleyici veya `_N` hiçbir öğe eklenmemiş ise dizindeki öğe.

## <a name="max_size"></a><a name="max_size"></a>max_size

Eşzamanlı vektörde tutabileceğiniz en fazla öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin tutabileceğiniz en fazla öğe sayısı `concurrent_vector` .

## <a name="operator"></a><a name="operator_eq"></a>işleç =

Başka bir `concurrent_vector` nesnenin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```

### <a name="parameters"></a>Parametreler

*M*<br/>
Kaynak vektörünün ayırıcı türü.

*_Vector*<br/>
Kaynak `concurrent_vector` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `concurrent_vector` .

## <a name="operator"></a><a name="operator_at"></a>operator []

Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda değerin `_Index` eşzamanlı vektörün boyutundan daha az olduğu sürece vektörü büyümekte.

```cpp
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Verilen dizindeki öğeye başvuru.

### <a name="remarks"></a>Açıklamalar

Bu öğesinin sürümü, `operator []` **`const`** farklı iş parçacıklarında aynı anda öğeye yazmak için kullanılamaz. Aynı veri öğesiyle eşzamanlı okuma ve yazma işlemlerini eşitlemek için farklı bir eşitleme nesnesi kullanılmalıdır.

`_Index`Yinelenen vektörde geçerli bir dizin olduğundan emin olmak için hiçbir sınır denetimi yapılmaz.

## <a name="push_back"></a><a name="push_back"></a>push_back

Verilen öğeyi, eşzamanlı vektörün sonuna ekler. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```

### <a name="parameters"></a>Parametreler

*_Item*<br/>
Eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Öğe için bir yineleyici eklendi.

## <a name="rbegin"></a><a name="rbegin"></a>rbegin

`reverse_iterator` `const_reverse_iterator` Eş zamanlı vektörün türü veya başına bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`reverse_iterator` `const_reverse_iterator` Eş zamanlı vektörün türü veya başına bir yineleyici.

## <a name="rend"></a><a name="rend"></a>rend

`reverse_iterator` `const_reverse_iterator` Eş zamanlı vektörün türü veya sonuna bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reverse_iterator rend();

const_reverse_iterator rend() const;
```

### <a name="return-value"></a>Dönüş Değeri

`reverse_iterator` `const_reverse_iterator` Eş zamanlı vektörün türü veya sonuna bir yineleyici.

## <a name="reserve"></a><a name="reserve"></a>ayırmaya

Daha `_N` sonra daha fazla bellek ayırmaya gerek kalmadan, eşzamanlı vektörün boyutunu büyütmek için yeterli alan ayırır. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void reserve(size_type _N);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
Alan ayrılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

`reserve`eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir. Yöntem döndürenden sonra eşzamanlı vektör kapasitesi, istenen ayırmayla daha büyük olabilir.

## <a name="resize"></a><a name="resize"></a>yeniden boyutlandırma

Eşzamanlı vektörün boyutunu istenen boyut olarak değiştirir, öğeleri silin veya gerekli şekilde ekleyin. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
Concurrent_vector yeni boyutu.

*Acil*<br/>
Yeni boyut orijinal boyuttan daha büyükse, vektöre eklenen yeni öğelerin değeri. Değer atlanırsa, yeni nesnelere türleri için varsayılan değer atanır.

### <a name="remarks"></a>Açıklamalar

Kapsayıcının boyutu istenen boyuttan küçükse, istenen boyuta ulaşıncaya kadar öğeler vektöre eklenir. Kapsayıcının boyutu istenen boyuttan daha büyükse kapsayıcının sonuna en yakın olan öğeler, kapsayıcı boyuta ulaşıncaya kadar silinir `_N` . Kapsayıcının mevcut boyutu istenen boyutla aynıysa, hiçbir eylem yapılmaz.

`resize`Eşzamanlılık güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir.

## <a name="shrink_to_fit"></a><a name="shrink_to_fit"></a>shrink_to_fit

Parçalanmayı azaltmak ve bellek kullanımını iyileştirmek için eşzamanlı vektörün iç gösterimini sıkıştırır. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm yineleyicilerin geçersiz kılınması için bellek taşıma öğelerini dahili olarak yeniden ayırır. `shrink_to_fit`eşzamanlılık açısından güvenli değildir. Bu işlevi çağırdığınızda eşzamanlı vektörde başka iş parçacıklarının Yöntem çağırkullanılmadığından emin olmanız gerekir.

## <a name="size"></a><a name="size"></a>boyutla

Eşzamanlı Vektördeki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesnedeki öğe sayısı `concurrent_vector` .

### <a name="remarks"></a>Açıklamalar

Döndürülen boyut, işleve yapılan çağrılar tarafından eklenen tüm öğeleri dahil etmek `push_back` veya bu yöntemi çağırmadan önce tamamlanan işlemleri büyütmek için garanti edilir. Ancak, ayrılan öğeleri de içerebilir, ancak yine de büyüme yöntemlerinden herhangi birine eşzamanlı çağrılar tarafından hala yapım aşamasındadır.

## <a name="swap"></a><a name="swap"></a>Kur

İki eşzamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void swap(concurrent_vector& _Vector);
```

### <a name="parameters"></a>Parametreler

*_Vector*<br/>
`concurrent_vector`İçeriği takas edilecek nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Paralel Kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)
