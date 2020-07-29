---
title: concurrent_queue Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::clear
- CONCURRENT_QUEUE/concurrency::concurrent_queue::empty
- CONCURRENT_QUEUE/concurrency::concurrent_queue::get_allocator
- CONCURRENT_QUEUE/concurrency::concurrent_queue::push
- CONCURRENT_QUEUE/concurrency::concurrent_queue::try_pop
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_begin
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_end
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_size
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
ms.openlocfilehash: a117a040adbf7f3aa316c346489bd2731d6c2402
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230356"
---
# <a name="concurrent_queue-class"></a>concurrent_queue Sınıfı

`concurrent_queue`Sınıfı, öğeleri için ilk ın, ilk çıkar erişimine izin veren bir dizi kapsayıcı sınıfıdır. Ve gibi sınırlı sayıda eşzamanlılık güvenli işlem kümesi sunar `push` `try_pop` . Burada eşzamanlılık açısından güvenli, işaretçiler veya yineleyiciler her zaman geçerlidir. Bu, öğe başlatma garantisi veya belirli bir geçiş düzeni değildir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Kuyrukta depolanacak öğelerin veri türü.

*_Ax*<br/>
Bu eşzamanlı sıra için bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları kapsülleyen saklı ayırıcı nesnesini temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `allocator<T>` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Eşzamanlı sıranın ayırıcı sınıfını temsil eden bir tür.|
|`const_iterator`|Eşzamanlı bir kuyruktaki öğeler üzerinde iş parçacığı olmayan güvenli bir yineleyiciyi temsil eden bir tür **`const`** .|
|`const_reference`|**`const`** İşlemleri okumak ve gerçekleştirmek için eşzamanlı sırada depolanan bir öğeye başvuru sağlayan bir tür **`const`** .|
|`difference_type`|Eşzamanlı bir kuyruktaki iki öğe arasındaki işaretli mesafeyi sağlayan bir tür.|
|`iterator`|Eşzamanlı bir kuyruktaki öğeler üzerinde iş parçacığı olmayan güvenli bir yineleyiciyi temsil eden bir tür.|
|`reference`|Eşzamanlı sırada depolanan bir öğeye başvuru sağlayan bir tür.|
|`size_type`|Eşzamanlı bir kuyruktaki öğelerin sayısını sayan bir tür.|
|`value_type`|Eşzamanlı sırada depolanan veri türünü temsil eden bir tür.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[concurrent_queue](#ctor)|Fazla Yüklendi. Eşzamanlı bir kuyruk oluşturur.|
|[~ concurrent_queue yok edici](#dtor)|Eşzamanlı kuyruğu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[lediğiniz](#clear)|Şu anda sıraya alınmış öğelerin yok edilirken, eşzamanlı kuyruğu temizler. Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[empty](#empty)|Bu yöntemin çağrıldığı anda eşzamanlı sıranın boş olup olmadığını sınar. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[get_allocator](#get_allocator)|Eş zamanlı kuyruğu oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[push](#push)|Fazla Yüklendi. Bir öğeyi, eşzamanlı sıranın kuyruklu sonuna kadar sıraya alın. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[try_pop](#try_pop)|Varsa, bir öğeyi kuyruktan kaldırır. Bu yöntem eşzamanlılık açısından güvenlidir.|
|[unsafe_begin](#unsafe_begin)|Fazla Yüklendi. `iterator`Eşzamanlı kuyruğun türü veya başına bir yineleyici döndürür `const_iterator` . Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[unsafe_end](#unsafe_end)|Fazla Yüklendi. `iterator`Eşzamanlı kuyruğun türü veya sonuna bir yineleyici döndürür `const_iterator` . Bu yöntem eşzamanlılık açısından güvenli değildir.|
|[unsafe_size](#unsafe_size)|Kuyruktaki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`concurrent_queue`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** concurrent_queue. h

**Ad alanı:** eşzamanlılık

## <a name="clear"></a><a name="clear"></a>lediğiniz

Şu anda sıraya alınmış öğelerin yok edilirken, eşzamanlı kuyruğu temizler. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
void clear();
```

## <a name="concurrent_queue"></a><a name="ctor"></a>concurrent_queue

Eşzamanlı bir kuyruk oluşturur.

```cpp
explicit concurrent_queue(
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    const concurrent_queue& _OtherQ,
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    concurrent_queue&& _OtherQ,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_queue(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>Parametreler

*_InputIterator*<br/>
Değer aralığını belirten giriş yineleyicisinin türü.

*_Al*<br/>
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*_OtherQ*<br/>
`concurrent_queue`Öğelerin kopyalanacağı veya taşınacağı kaynak nesne.

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_End*<br/>
Kopyalanacak öğe aralığının ötesinde ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular bir ayırıcı nesnesi depolar `_Al` ve kuyruğu başlatır.

İlk Oluşturucu boş bir başlangıç kuyruğu belirtir ve açıkça kullanılacak ayırıcı türünü belirtir.

İkinci Oluşturucu, eşzamanlı sıranın bir kopyasını belirtir `_OtherQ` .

Üçüncü Oluşturucu, eşzamanlı sıranın bir hareketini belirtir `_OtherQ` .

Dördüncü Oluşturucu yineleyici aralığı [,) tarafından sağlanan değerleri belirtir `_Begin` `_End` .

## <a name="concurrent_queue"></a><a name="dtor"></a>~ concurrent_queue

Eşzamanlı kuyruğu yok eder.

```cpp
~concurrent_queue();
```

## <a name="empty"></a><a name="empty"></a>olmamalıdır

Bu yöntemin çağrıldığı anda eşzamanlı sıranın boş olup olmadığını sınar. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** baktığımız anda eşzamanlı sıra boşsa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ve yöntemlerine yapılan çağrılara göre eşzamanlılık açısından güvende olsa da, `push` `try_pop` `empty` döndürülen değer çağıran iş parçacığı tarafından incelenen zaman hatalı olabilir.

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

Eş zamanlı kuyruğu oluşturmak için kullanılan ayırıcının bir kopyasını döndürür. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eş zamanlı kuyruğu oluşturmak için kullanılan ayırıcıın bir kopyası.

## <a name="push"></a><a name="push"></a>hareketle

Bir öğeyi, eşzamanlı sıranın kuyruklu sonuna kadar sıraya alın. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
void push(const T& _Src);

void push(T&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Sıraya eklenecek öğe.

### <a name="remarks"></a>Açıklamalar

`push`, ve yöntemlerine yapılan çağrılara göre eşzamanlılık açısından güvenlidir `push` `try_pop` `empty` .

## <a name="try_pop"></a><a name="try_pop"></a>try_pop

Varsa, bir öğeyi kuyruktan kaldırır. Bu yöntem eşzamanlılık açısından güvenlidir.

```cpp
bool try_pop(T& _Dest);
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Kuyruğa atılmış öğeyi depolamak için bir konuma başvuru.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bir öğe başarıyla kuyruğa alınmışsa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Bir öğe başarıyla kuyruğa alınmışsa, parametre `_Dest` sıraya alınmış değeri alır, kuyrukta tutulan özgün değer yok edilir ve bu işlev döndürür **`true`** . Sıradan çıkarma için bir öğe yoksa, bu işlev **`false`** engellenmeden döner ve `_Dest` parametresinin içeriği tanımsızdır.

`try_pop`, ve yöntemlerine yapılan çağrılara göre eşzamanlılık açısından güvenlidir `push` `try_pop` `empty` .

## <a name="unsafe_begin"></a><a name="unsafe_begin"></a>unsafe_begin

`iterator`Eşzamanlı kuyruğun türü veya başına bir yineleyici döndürür `const_iterator` . Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

`iterator` `const_iterator` Eşzamanlı sıra nesnesinin türü veya başına bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Sınıf için yineleyiciler `concurrent_queue` öncelikle hata ayıklama için tasarlanmıştır, yavaş olur ve yineleme diğer kuyruk işlemlerine göre eşzamanlılık açısından güvenli değildir.

## <a name="unsafe_end"></a><a name="unsafe_end"></a>unsafe_end

`iterator`Eşzamanlı kuyruğun türü veya sonuna bir yineleyici döndürür `const_iterator` . Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
iterator unsafe_end();

const_iterator unsafe_end() const;
```

### <a name="return-value"></a>Dönüş Değeri

`iterator`Eşzamanlı kuyruğun türü veya sonuna bir yineleyici `const_iterator` .

### <a name="remarks"></a>Açıklamalar

Sınıf için yineleyiciler `concurrent_queue` öncelikle hata ayıklama için tasarlanmıştır, yavaş olur ve yineleme diğer kuyruk işlemlerine göre eşzamanlılık açısından güvenli değildir.

## <a name="unsafe_size"></a><a name="unsafe_size"></a>unsafe_size

Kuyruktaki öğe sayısını döndürür. Bu yöntem eşzamanlılık açısından güvenli değildir.

```cpp
size_type unsafe_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı sıranın boyutu.

### <a name="remarks"></a>Açıklamalar

`unsafe_size`eşzamanlılık açısından güvenli değildir ve yöntemlere, ve çağrılarıyla aynı anda çağrılırsa hatalı sonuçlar üretebilir `push` `try_pop` `empty` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
