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
ms.openlocfilehash: d5bbd361dc2dedc24c2a59050ffa680517186494
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263093"
---
# <a name="concurrentqueue-class"></a>concurrent_queue Sınıfı

`concurrent_queue` Sınıfı, bir ilk sağlayan dizisi kapsayıcı sınıfı, ilk çıkar erişim öğeleri. Eşzamanlılık açısından güvenli işlemler, sınırlı sayıda gibi sağlayan `push` ve `try_pop`.

## <a name="syntax"></a>Sözdizimi

```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Kuyrukta depolanacak öğe veri türü.

*_Ax*<br/>
Ayırma ve eş zamanlı bu sıra için bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<T>`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Eşzamanlı kuyruk için ayırıcı sınıf temsil eden tür.|
|`const_iterator`|Bir iş parçacığı güvenli olmayan temsil eden bir tür `const` eşzamanlı Kuyruk öğeleri üzerinde yineleyici.|
|`const_reference`|Bir başvuru sağlayan bir tür bir `const` okumak ve gerçekleştirmek için eş zamanlı bir sıra içinde depolanan öğenin `const` operations.|
|`difference_type`|Eş zamanlı sıradaki iki öğe arasındaki imzalı uzaklığı sağlayan bir tür.|
|`iterator`|Eş zamanlı kuyruktaki öğeleri üzerinde bir iş parçacığı güvenli olmayan yineleyicisini temsil eden bir tür.|
|`reference`|Eş zamanlı kuyrukta depolanan öğeye başvuru sağlayan bir tür.|
|`size_type`|Eş zamanlı kuyruğundaki öğe sayısını sayar türü.|
|`value_type`|Eş zamanlı kuyrukta depolanan veri türünü temsil eden tür.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[concurrent_queue](#ctor)|Fazla Yüklendi. Eş zamanlı bir kuyruk oluşturur.|
|[~concurrent_queue Destructor](#dtor)|Eşzamanlı kuyruk yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Temizle](#clear)|Tüm yok etme eşzamanlı kuyruk temizler şu anda sıradaki öğeleri. Bu yöntem eşzamanlı güvenli değil.|
|[boş](#empty)|Şu anda eş zamanlı sıranın boş olup olmadığını sınar, bu yöntem çağrılır. Bu yöntem eşzamanlı güvenlidir.|
|[get_allocator](#get_allocator)|Eşzamanlı kuyruk oluşturmak için kullanılan ayırıcı bir kopyasını döndürür. Bu yöntem eşzamanlı güvenlidir.|
|[push](#push)|Fazla Yüklendi. Kaybolmamasının tail uçta eşzamanlı Kuyruk öğesi. Bu yöntem eşzamanlı güvenlidir.|
|[try_pop](#try_pop)|Sıradan bir öğe varsa dequeues. Bu yöntem eşzamanlı güvenlidir.|
|[unsafe_begin](#unsafe_begin)|Fazla Yüklendi. Türü bir yineleyici döndüren `iterator` veya `const_iterator` eşzamanlı kuyruk başlangıcına. Bu yöntem eşzamanlı güvenli değil.|
|[unsafe_end](#unsafe_end)|Fazla Yüklendi. Türü bir yineleyici döndüren `iterator` veya `const_iterator` sonuna kadar eşzamanlı kuyruk. Bu yöntem eşzamanlı güvenli değil.|
|[unsafe_size](#unsafe_size)|Kuyrukta öğe sayısını döndürür. Bu yöntem eşzamanlı güvenli değil.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`concurrent_queue`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concurrent_queue.h

**Namespace:** eşzamanlılık

##  <a name="clear"></a> Temizle

Tüm yok etme eşzamanlı kuyruk temizler şu anda sıradaki öğeleri. Bu yöntem eşzamanlı güvenli değil.

```
void clear();
```

##  <a name="ctor"></a> concurrent_queue

Eş zamanlı bir kuyruk oluşturur.

```
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
Bir aralıktaki değerleri belirten bir giriş yineleyici türü.

*_Al*<br/>
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*_OtherQ*<br/>
Kaynak `concurrent_queue` nesneyi kopyalama veya öğeleri buradan taşımak için.

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_Bitiş*<br/>
Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular ayırıcı nesnesini depolar `_Al` ve sırası başlatılamıyor.

İlk Oluşturucu boş bir başlangıç kuyruk ve kullanılacak ayırıcı türünü açıkça belirtir.

İkinci oluşturucu eşzamanlı sırasının bir kopyasını belirtir `_OtherQ`.

Üçüncü Oluşturucu, taşıma eşzamanlı kuyruğun belirtir `_OtherQ`.

Dördüncü Oluşturucu yineleyici aralığı tarafından sağlanan değerleri belirler [ `_Begin`, `_End`).

##  <a name="dtor"></a> ~ concurrent_queue

Eşzamanlı kuyruk yok eder.

```
~concurrent_queue();
```

##  <a name="empty"></a> boş

Şu anda eş zamanlı sıranın boş olup olmadığını sınar, bu yöntem çağrılır. Bu yöntem eşzamanlı güvenlidir.

```
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** eşzamanlı kuyruk incelemiştik, şu anda boşsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu yöntem eşzamanlı güvenli olsa da bu yöntemlere yapılan çağrılar göre `push`, `try_pop`, ve `empty`, onu çağıran iş parçacığı tarafından denetlenmekte zaman tarafından döndürülen değer yanlış olabilir.

##  <a name="get_allocator"></a> get_allocator

Eşzamanlı kuyruk oluşturmak için kullanılan ayırıcı bir kopyasını döndürür. Bu yöntem eşzamanlı güvenlidir.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kuyruk oluşturmak için kullanılan ayırıcı bir kopyası.

##  <a name="push"></a> anında iletme

Kaybolmamasının tail uçta eşzamanlı Kuyruk öğesi. Bu yöntem eşzamanlı güvenlidir.

```
void push(const T& _Src);

void push(T&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Kuyruğa eklenecek öğe.

### <a name="remarks"></a>Açıklamalar

`push` eşzamanlı güvenlidir yöntemlere yapılan çağrılar göre `push`, `try_pop`, ve `empty`.

##  <a name="try_pop"></a> try_pop

Sıradan bir öğe varsa dequeues. Bu yöntem eşzamanlı güvenlidir.

```
bool try_pop(T& _Dest);
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Dequeued öğe depolamak için bir konum bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

**doğru** öğeyi başarıyla dequeued olduysa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bir öğe başarıyla dequeued olduysa parametresi `_Dest` dequeued değerini alır kuyrukta tutulan özgün değeri yok ve bu işlevi döndürür **true**. Olup olmadığını sıradan bir öğe yok, bu işlevi döndürür `false` engelleme ve içeriğini olmadan `_Dest` parametre tanımlanmamış.

`try_pop` eşzamanlı güvenlidir yöntemlere yapılan çağrılar göre `push`, `try_pop`, ve `empty`.

##  <a name="unsafe_begin"></a> unsafe_begin

Türü bir yineleyici döndüren `iterator` veya `const_iterator` eşzamanlı kuyruk başlangıcına. Bu yöntem eşzamanlı güvenli değil.

```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `iterator` veya `const_iterator` başına eşzamanlı sıra nesnesi.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler için `concurrent_queue` sınıfı öncelikle yöneliktir, hata ayıklama için bunlar yavaş ve yineleme diğer kuyruk işlemleri gerçekleştireceğini eşzamanlı güvenli değil.

##  <a name="unsafe_end"></a> unsafe_end

Türü bir yineleyici döndüren `iterator` veya `const_iterator` sonuna kadar eşzamanlı kuyruk. Bu yöntem eşzamanlı güvenli değil.

```
iterator unsafe_end();

const_iterator unsafe_end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `iterator` veya `const_iterator` sonuna kadar eşzamanlı kuyruk.

### <a name="remarks"></a>Açıklamalar

Yineleyiciler için `concurrent_queue` sınıfı öncelikle yöneliktir, hata ayıklama için bunlar yavaş ve yineleme diğer kuyruk işlemleri gerçekleştireceğini eşzamanlı güvenli değil.

##  <a name="unsafe_size"></a> unsafe_size

Kuyrukta öğe sayısını döndürür. Bu yöntem eşzamanlı güvenli değil.

```
size_type unsafe_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşzamanlı kuyruk boyutu.

### <a name="remarks"></a>Açıklamalar

`unsafe_size` Eşzamanlılık açısından güvenli değildir ve yöntemlere yapılan çağrılar eşzamanlı çağrılırsa hatalı sonuçlar üretebilir `push`, `try_pop`, ve `empty`.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
