---
title: concurrent_priority_queue Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::clear
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::empty
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::get_allocator
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::push
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::size
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::swap
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::try_pop
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
ms.openlocfilehash: 024bd2a100b8a0b871d98a5e6001858b55977565
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230369"
---
# <a name="concurrent_priority_queue-class"></a>concurrent_priority_queue Sınıfı

`concurrent_priority_queue`Sınıfı, birden çok iş parçacığının aynı anda gönderim ve pop öğelerine izin veren bir kapsayıcıdır. Öğelerin, bir şablon bağımsız değişkeni olarak sağlanan bir functor tarafından belirlendiği öncelik sırasına göre belirlenir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öncelik kuyruğunda depolanacak öğelerin veri türü.

*_Compare*<br/>
İki öğe değerini, öncelik kuyruğunda göreli sıralarını belirleyebilmek için sıralama anahtarları olarak karşılaştırabilen işlev nesnesinin türü. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul `less<T>` varsayılan değerdir.

*_Ax*<br/>
Eşzamanlı öncelik kuyruğu için bellek ayırma ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<T>` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Eşzamanlı öncelik sırasının ayırıcı sınıfını temsil eden bir tür.|
|`const_reference`|Eşzamanlı bir öncelik kuyruğunda depolanan türdeki bir öğeye const başvurusunu temsil eden bir tür.|
|`reference`|Eşzamanlı bir öncelik kuyruğunda depolanan türdeki bir öğeye başvuruyu temsil eden bir tür.|
|`size_type`|Eşzamanlı bir öncelik kuyruğundaki öğelerin sayısını sayan bir tür.|
|`value_type`|Eşzamanlı bir öncelik kuyruğunda depolanan veri türünü temsil eden bir tür.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[concurrent_priority_queue](#ctor)|Fazla Yüklendi. Eşzamanlı bir öncelik kuyruğu oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lediğiniz](#clear)|Eş zamanlı öncelikteki tüm öğeleri siler. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[empty](#empty)|Bu yöntemin çağrılışında eşzamanlı öncelik sırasının boş olup olmadığını sınar. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[get_allocator](#get_allocator)|Eşzamanlı öncelik sırasını oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[push](#push)|Fazla Yüklendi. Eşzamanlı öncelik kuyruğuna bir öğe ekler. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[boyutla](#size)|Eşzamanlı öncelik sırasındaki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[Kur](#swap)|İki eşzamanlı öncelik kuyruğu içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[try_pop](#try_pop)|Sıra boş değilse kuyruktaki en yüksek öncelik öğesini kaldırır ve döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Fazla Yüklendi. Başka bir `concurrent_priority_queue` nesnenin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

Sınıfıyla ilgili ayrıntılı bilgi için `concurrent_priority_queue` bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`concurrent_priority_queue`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** concurrent_priority_queue. h

**Ad alanı:** eşzamanlılık

## <a name="clear"></a><a name="clear"></a>lediğiniz

Eş zamanlı öncelikteki tüm öğeleri siler. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void clear();
```

### <a name="remarks"></a>Açıklamalar

`clear`eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda eşzamanlı öncelik sırasında başka bir iş parçacığının metot çağırkullanılmadığından emin olmanız gerekir. `clear`belleği serbest vermez.

## <a name="concurrent_priority_queue"></a><a name="ctor"></a>concurrent_priority_queue

Eşzamanlı bir öncelik kuyruğu oluşturur.

```cpp
explicit concurrent_priority_queue(
    const allocator_type& _Al = allocator_type());

explicit concurrent_priority_queue(
    size_type _Init_capacity,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_priority_queue(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());

concurrent_priority_queue(
    const concurrent_priority_queue& _Src);

concurrent_priority_queue(
    const concurrent_priority_queue& _Src,
    const allocator_type& _Al);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src,
    const allocator_type& _Al);
```

### <a name="parameters"></a>Parametreler

*_InputIterator*<br/>
Giriş yineleyicisinin türü.

*_Al*<br/>
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*_Init_capacity*<br/>
Nesnenin ilk kapasitesi `concurrent_priority_queue` .

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

*_Src*<br/>
`concurrent_priority_queue`Öğelerin kopyalanacağı veya taşınacağı kaynak nesne.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesnesi depolar `_Al` ve öncelik sırasını başlatır.

İlk Oluşturucu boş bir başlangıç önceliği sırası belirtir ve isteğe bağlı olarak bir ayırıcı belirtir.

İkinci Oluşturucu, ilk kapasiteye sahip bir öncelik sırası belirtir `_Init_capacity` ve isteğe bağlı olarak bir ayırıcı belirtir.

Üçüncü Oluşturucu yineleyici aralığı [,) tarafından sağlanan değerleri belirtir `_Begin` `_End` ve isteğe bağlı olarak bir ayırıcı belirtir.

Dördüncü ve beşinci oluşturucular, öncelik sırasının bir kopyasını belirtir `_Src` .

Altıncı ve yedinci oluşturucular, öncelik sırasının bir hareketini belirtir `_Src` .

## <a name="empty"></a><a name="empty"></a>olmamalıdır

Bu yöntemin çağrılışında eşzamanlı öncelik sırasının boş olup olmadığını sınar. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** öncelik sırası işlevin çağrıldığı sırada boşsa, **`false`** tersi durumda.

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

Eşzamanlı öncelik sırasını oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi oluşturmak için kullanılan ayırıcıın bir kopyası `concurrent_priority_queue` .

## <a name="operator"></a><a name="operator_eq"></a>işleç =

Başka bir `concurrent_priority_queue` nesnenin içeriğini buna atar. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Kaynak `concurrent_priority_queue` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `concurrent_priority_queue` .

## <a name="push"></a><a name="push"></a>hareketle

Eşzamanlı öncelik kuyruğuna bir öğe ekler. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```

### <a name="parameters"></a>Parametreler

*_Elem*<br/>
Eşzamanlı öncelik kuyruğuna eklenecek öğe.

## <a name="size"></a><a name="size"></a>boyutla

Eşzamanlı öncelik sırasındaki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesnedeki öğe sayısı `concurrent_priority_queue` .

### <a name="remarks"></a>Açıklamalar

Döndürülen boyut, işleve yapılan çağrılar tarafından eklenen tüm öğeleri dahil etmek için garanti edilir `push` . Ancak, bekleyen eşzamanlı işlemlerin sonuçlarını yansıtmayabilir.

## <a name="swap"></a><a name="swap"></a>Kur

İki eşzamanlı öncelik kuyruğu içeriğini değiştirir. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void swap(concurrent_priority_queue& _Queue);
```

### <a name="parameters"></a>Parametreler

*_Queue*<br/>
`concurrent_priority_queue`İçeriği takas edilecek nesne.

## <a name="try_pop"></a><a name="try_pop"></a>try_pop

Sıra boş değilse kuyruktaki en yüksek öncelik öğesini kaldırır ve döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
bool try_pop(reference _Elem);
```

### <a name="parameters"></a>Parametreler

*_Elem*<br/>
Sıra boş değilse, en yüksek öncelik öğesiyle doldurulacak bir değişkene başvuru.

### <a name="return-value"></a>Dönüş Değeri

**`true`** değer **`false`** yoksa, aksi takdirde.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Paralel Kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)
