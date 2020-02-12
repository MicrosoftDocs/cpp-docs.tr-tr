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
ms.openlocfilehash: 002f1e3f691de3315810efed8f7d8f6c547cf653
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143142"
---
# <a name="concurrent_vector-class"></a>concurrent_vector Sınıfı

`concurrent_vector` sınıfı, herhangi bir öğeye rastgele erişime izin veren bir dizi kapsayıcı sınıfıdır. Eşzamanlılık açısından güvenli ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemlerine izin vermez. Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
private details::_Concurrent_vector_base_v4;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Vektörde depolanacak öğelerin veri türü.

*_Ax*<br/>
Eşzamanlı vektör için bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<T>`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Eşzamanlı vektörün ayırıcı sınıfını temsil eden bir tür.|
|`const_iterator`|Eşzamanlı vektörde bir `const` öğesini okuyabilen bir rastgele erişim yineleyici sağlayan bir tür.|
|`const_pointer`|Eşzamanlı vektörde bir `const` öğesi işaretçisi sağlayan bir tür.|
|`const_reference`|`const` işlemlerini okumak ve gerçekleştirmek için eşzamanlı vektörde depolanan `const` bir öğeye başvuru sağlayan bir tür.|
|`const_reverse_iterator`|Eşzamanlı vektörde herhangi bir `const` öğesini okuyabilen bir rastgele erişim yineleyici sağlayan bir tür.|
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
|[ata](#assign)|Fazla Yüklendi. Eş zamanlı vektörün öğelerini siler ve bu, `_Item``_N` kopyalarını ya da yineleyici aralığı [`_Begin`, `_End`) tarafından belirtilen değerleri atar. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[hızı](#at)|Fazla Yüklendi. Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda `_Index` değerin eşzamanlı vektörün boyutundan daha az olduğu sürece vektörü büyümekte de olur.|
|[Geri](#back)|Fazla Yüklendi. Eşzamanlı Vektördeki son öğeye bir başvuru veya `const` başvurusu döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[başladı](#begin)|Fazla Yüklendi. Eş zamanlı vektörün başlangıcına `iterator` veya `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[kü](#capacity)|Eşzamanlı vektörün daha fazla bellek ayırmaya gerek kalmadan büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[cbegin](#cbegin)|Eş zamanlı vektörün başlangıcına `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[cend](#cend)|Eş zamanlı vektörün sonuna `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[lediğiniz](#clear)|Eşzamanlı Vektördeki tüm öğeleri siler. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[crbegin](#crbegin)|Eş zamanlı vektörün başlangıcına `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[crend](#crend)|Eş zamanlı vektörün sonuna `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[olmamalıdır](#empty)|Bu yöntemin çağrılışında eşzamanlı vektör boş ise, sınar. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[erer](#end)|Fazla Yüklendi. Eş zamanlı vektörün sonuna `iterator` veya `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[yapılan](#front)|Fazla Yüklendi. Eşzamanlı Vektördeki ilk öğeye bir başvuru veya `const` başvurusu döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[get_allocator](#get_allocator)|Eş zamanlı vektörü oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[grow_by](#grow_by)|Fazla Yüklendi. `_Delta` öğeleri tarafından bu eşzamanlı vektörü büyürken. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[grow_to_at_least](#grow_to_at_least)|En az `_N` öğeye sahip olana kadar bu eşzamanlı vektörü büyür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[max_size](#max_size)|Eşzamanlı vektörde tutabileceğiniz en fazla öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[push_back](#push_back)|Fazla Yüklendi. Verilen öğeyi, eşzamanlı vektörün sonuna ekler. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[rbegin](#rbegin)|Fazla Yüklendi. Eş zamanlı vektörün başlangıcına `reverse_iterator` veya `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[rend](#rend)|Fazla Yüklendi. Eş zamanlı vektörün sonuna `reverse_iterator` veya `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[ayırmaya](#reserve)|Daha sonra daha fazla bellek ayırmaya gerek kalmadan `_N` için Eşzamanlı vektörü büyütmek üzere yeterli alan ayırır. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[yeniden boyutlandırma](#resize)|Fazla Yüklendi. Eşzamanlı vektörün boyutunu istenen boyut olarak değiştirir, öğeleri silin veya gerekli şekilde ekleyin. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[shrink_to_fit](#shrink_to_fit)|Parçalanmayı azaltmak ve bellek kullanımını iyileştirmek için eşzamanlı vektörün iç gösterimini sıkıştırır. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[boyutla](#size)|Eşzamanlı Vektördeki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[Kur](#swap)|İki eşzamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç\[\]](#operator_at)|Fazla Yüklendi. Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda `_Index` değerin eşzamanlı vektör boyutundan daha az olduğu sürece vektörü büyümeye devam ederken vector.|
|[işleç =](#operator_eq)|Fazla Yüklendi. Başka bir `concurrent_vector` nesnesinin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

`concurrent_vector` sınıfı hakkında ayrıntılı bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Concurrent_vector_base_v4`

`_Allocator_base`

`concurrent_vector`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** concurrent_vector. h

**Ad alanı:** eşzamanlılık

## <a name="assign"></a>ata

Eş zamanlı vektörün öğelerini siler ve bu, `_Item``_N` kopyalarını ya da yineleyici aralığı [`_Begin`, `_End`) tarafından belirtilen değerleri atar. Bu yöntem eşzamanlılık açısından güvenli değildir.

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

`assign` eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir.

## <a name="at"></a>hızı

Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda `_Index` değerin eşzamanlı vektörün boyutundan daha az olduğu sürece vektörü büyümekte de olur.

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

`const` olmayan bir başvuru döndüren `at` işlev sürümü, farklı iş parçacıklarından öğeye eşzamanlı olarak yazmak için kullanılamaz. Aynı veri öğesiyle eşzamanlı okuma ve yazma işlemlerini eşitlemek için farklı bir eşitleme nesnesi kullanılmalıdır.

`out_of_range`, `_Index` eş zamanlı vektörden büyükse veya bu boyuttan daha büyükse `range_error` ve Dizin vektör 'in bozuk bir bölümü için ise,. Vector öğesinin nasıl kopuk hale gelebilmesi hakkındaki ayrıntılar için bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="back"></a>Geri

Eşzamanlı Vektördeki son öğeye bir başvuru veya `const` başvurusu döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı Vektördeki son öğeye başvuru veya `const` başvurusu.

## <a name="begin"></a>başladı

Eş zamanlı vektörün başlangıcına `iterator` veya `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`iterator` veya eş zamanlı vektörün başlangıcına `const_iterator` bir yineleyici.

## <a name="capacity"></a>kü

Eşzamanlı vektörün daha fazla bellek ayırmaya gerek kalmadan büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı vektörün daha fazla bellek ayırmaya gerek kalmadan büyüyebileceği maksimum boyut.

### <a name="remarks"></a>Açıklamalar

C++ Standart kitaplık `vector`farklı olarak, bir `concurrent_vector` nesnesi daha fazla bellek ayırırsa mevcut öğeleri taşımaz.

## <a name="cbegin"></a>cbegin

Eş zamanlı vektörün başlangıcına `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eş zamanlı vektörün başlangıcına `const_iterator` türünde bir yineleyici.

## <a name="cend"></a>cend

Eş zamanlı vektörün sonuna `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eş zamanlı vektörün sonuna `const_iterator` türünde bir yineleyici.

## <a name="clear"></a>lediğiniz

Eşzamanlı Vektördeki tüm öğeleri siler. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

`clear` eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir. `clear` iç dizileri serbest vermez. İç dizileri serbest bırakmak için, `clear`sonra `shrink_to_fit` işlevi çağırın.

## <a name="ctor"></a>concurrent_vector

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
Öğeleri kopyalamak veya taşımak için kaynak `concurrent_vector` nesnesi.

*_N*<br/>
`concurrent_vector` nesnesinin ilk kapasitesi.

*_Item*<br/>
Oluşturulan nesnedeki öğelerin değeri.

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesne `_Al` depolar ve vektörü başlatır.

İlk Oluşturucu boş bir ilk vektör belirtiyor ve açıkça ayırıcı türünü belirtir. kullanılır.

İkinci ve üçüncü oluşturucular, eşzamanlı vektör `_Vector`bir kopyasını belirtir.

Dördüncü Oluşturucu, eşzamanlı vektör `_Vector`taşımasını belirtir.

Beşinci Oluşturucu, sınıf `T`için varsayılan değer olan öğelerin belirtilen sayı (`_N`) tekrarını belirtir.

Altıncı Oluşturucu, `_Item`değer (`_N`) öğelerinin bir tekrarından oluşur.

Son Oluşturucu yineleyici aralığı tarafından sağlanan değerleri belirtir [`_Begin`, `_End`).

## <a name="dtor"></a>~ concurrent_vector

Tüm öğeleri siler ve bu eşzamanlı vektörü yok eder.

```cpp
~concurrent_vector();
```

## <a name="crbegin"></a>crbegin

Eş zamanlı vektörün başlangıcına `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eş zamanlı vektörün başlangıcına `const_reverse_iterator` türünde bir yineleyici.

## <a name="crend"></a>crend

Eş zamanlı vektörün sonuna `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eş zamanlı vektörün sonuna `const_reverse_iterator` türünde bir yineleyici.

## <a name="empty"></a>olmamalıdır

Bu yöntemin çağrılışında eşzamanlı vektör boş ise, sınar. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

vektör, işlevin çağrıldığı sırada boşsa **true** , aksi durumda **false** .

## <a name="end"></a>erer

Eş zamanlı vektörün sonuna `iterator` veya `const_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

`iterator` veya eş zamanlı vektörün sonuna `const_iterator` türü bir yineleyici.

## <a name="front"></a>yapılan

Eşzamanlı Vektördeki ilk öğeye bir başvuru veya `const` başvurusu döndürür. Eşzamanlı vektör boşsa, dönüş değeri tanımsızdır. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı Vektördeki ilk öğeye başvuru veya `const` başvuru.

## <a name="get_allocator"></a>get_allocator

Eş zamanlı vektörü oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

`concurrent_vector` nesnesini oluşturmak için kullanılan ayırıcıın bir kopyası.

## <a name="grow_by"></a>grow_by

`_Delta` öğeleri tarafından bu eşzamanlı vektörü büyürken. Bu yöntem eşzamanlılık açısından güvenlidir.

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

`_Item` belirtilmemişse, yeni öğeler varsayılan olarak oluşturulur.

## <a name="grow_to_at_least"></a>grow_to_at_least

En az `_N` öğeye sahip olana kadar bu eşzamanlı vektörü büyür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
iterator grow_to_at_least(size_type _N);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
`concurrent_vector` nesnesinin yeni en küçük boyutu.

### <a name="return-value"></a>Dönüş Değeri

Eklenen sıranın başlangıcını işaret eden bir yineleyici veya hiçbir öğe eklenmemiş `_N` dizindeki öğe.

## <a name="max_size"></a>max_size

Eşzamanlı vektörde tutabileceğiniz en fazla öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

`concurrent_vector` nesnenin tutabileceğiniz en fazla öğe sayısı.

## <a name="operator_eq"></a>işleç =

Başka bir `concurrent_vector` nesnesinin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.

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
Kaynak `concurrent_vector` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `concurrent_vector` nesnesine bir başvuru.

## <a name="operator_at"></a>operator []

Eşzamanlı vektörde verilen dizindeki öğeye erişim sağlar. Bu yöntem, okuma işlemleri için eşzamanlılık açısından güvenlidir ve aynı zamanda `_Index` değerin eşzamanlı vektör boyutundan daha az olduğu sürece vektörü büyümeye devam ederken vector.

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

`const` olmayan bir başvuru döndüren `operator []` sürümü aynı anda farklı iş parçacıklarından öğeye yazmak için kullanılamaz. Aynı veri öğesiyle eşzamanlı okuma ve yazma işlemlerini eşitlemek için farklı bir eşitleme nesnesi kullanılmalıdır.

`_Index`, eşzamanlı vektörde geçerli bir dizin olduğundan emin olmak için hiçbir sınır denetimi yapılmaz.

## <a name="push_back"></a>push_back

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

## <a name="rbegin"></a>rbegin

Eş zamanlı vektörün başlangıcına `reverse_iterator` veya `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`reverse_iterator` veya eş zamanlı vektörün başlangıcına `const_reverse_iterator` bir yineleyici.

## <a name="rend"></a>rend

Eş zamanlı vektörün sonuna `reverse_iterator` veya `const_reverse_iterator` türünde bir yineleyici döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
reverse_iterator rend();

const_reverse_iterator rend() const;
```

### <a name="return-value"></a>Dönüş Değeri

`reverse_iterator` veya eş zamanlı vektörün sonuna `const_reverse_iterator` türü bir yineleyici.

## <a name="reserve"></a>ayırmaya

Daha sonra daha fazla bellek ayırmaya gerek kalmadan `_N` için Eşzamanlı vektörü büyütmek üzere yeterli alan ayırır. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void reserve(size_type _N);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
Alan ayrılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

`reserve` eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir. Yöntem döndürenden sonra eşzamanlı vektör kapasitesi, istenen ayırmayla daha büyük olabilir.

## <a name="resize"></a>yeniden boyutlandırma

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

Kapsayıcının boyutu istenen boyuttan küçükse, istenen boyuta ulaşıncaya kadar öğeler vektöre eklenir. Kapsayıcının boyutu istenen boyuttan daha büyükse kapsayıcının sonuna en yakın olan öğeler, kapsayıcı boyut `_N`ulaşıncaya kadar silinir. Kapsayıcının mevcut boyutu istenen boyutla aynıysa, hiçbir eylem yapılmaz.

`resize` eşzamanlılık güvenli değildir. Bu yöntemi çağırdığınızda, diğer iş parçacıklarının eşzamanlı vektörde Yöntem çağırkullanılmadığından emin olmanız gerekir.

## <a name="shrink_to_fit"></a>shrink_to_fit

Parçalanmayı azaltmak ve bellek kullanımını iyileştirmek için eşzamanlı vektörün iç gösterimini sıkıştırır. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm yineleyicilerin geçersiz kılınması için bellek taşıma öğelerini dahili olarak yeniden ayırır. `shrink_to_fit` eşzamanlılık açısından güvenli değildir. Bu işlevi çağırdığınızda eşzamanlı vektörde başka iş parçacıklarının Yöntem çağırkullanılmadığından emin olmanız gerekir.

## <a name="size"></a>boyutla

Eşzamanlı Vektördeki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `concurrent_vector` nesnesindeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Döndürülen boyut, işlev `push_back`çağrıları tarafından eklenen tüm öğeleri dahil etmek veya bu yöntemi çağırmadan önce tamamlanan işlemleri büyütmek için garanti edilir. Ancak, ayrılan öğeleri de içerebilir, ancak yine de büyüme yöntemlerinden herhangi birine eşzamanlı çağrılar tarafından hala yapım aşamasındadır.

## <a name="swap"></a>Kur

İki eşzamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void swap(concurrent_vector& _Vector);
```

### <a name="parameters"></a>Parametreler

*_Vector*<br/>
İçeriğini değiştirmek için `concurrent_vector` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)
