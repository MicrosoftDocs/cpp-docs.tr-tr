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
ms.openlocfilehash: 5804675ffdaf6de2e73327103398316566b41627
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304788"
---
# <a name="concurrentpriorityqueue-class"></a>concurrent_priority_queue Sınıfı

`concurrent_priority_queue` Sınıfı, birden çok iş parçacığı aynı anda anında iletme ve açılır öğelere izin veren bir kapsayıcıdır. Öğeleri, öncelik sırasına göre öncelik bir şablon bağımsız değişken olarak sağlanan bir functor tarafından belirlendiği POP.

## <a name="syntax"></a>Sözdizimi

```
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Öncelikli kuyruk içinde depolanacak öğe veri türü.

*_Karşılaştır*<br/>
İki öğenin değerlerini öncelikli kuyruk kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi türü. Bu bağımsız değişken isteğe bağlıdır ve ikili koşul `less<T>` varsayılan değerdir.

*_Ax*<br/>
Ayırma ve eş zamanlı öncelikli kuyruk için bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<T>`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Eş zamanlı öncelikli kuyruk için ayırıcı sınıf temsil eden tür.|
|`const_reference`|Bir eş zamanlı öncelik sırasına depolanan türünde bir öğe için bir const temsil başvuru türü.|
|`reference`|Bir eş zamanlı öncelik sırasına depolanan türünde bir öğe için bir başvuru temsil eden tür.|
|`size_type`|Eş zamanlı öncelikli bir kuyruk öğeleri sayar türü.|
|`value_type`|Eş zamanlı öncelikli bir kuyruk içinde depolanan veri türünü temsil eden tür.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[concurrent_priority_queue](#ctor)|Fazla Yüklendi. Eş zamanlı öncelikli bir kuyruk oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Temizle](#clear)|Eş zamanlı öncelik tüm öğelerini siler. Bu yöntem eşzamanlı güvenli değil.|
|[boş](#empty)|Eş zamanlı öncelikli kuyruk zamanında boş olup olmadığını sınar, bu yöntem çağrılır. Bu yöntem eşzamanlı güvenlidir.|
|[get_allocator](#get_allocator)|Eş zamanlı öncelikli kuyruk oluşturmak için kullanılan ayırıcı bir kopyasını döndürür. Bu yöntem eşzamanlı güvenlidir.|
|[push](#push)|Fazla Yüklendi. Bir öğeyi eşzamanlı öncelik sırasına ekler. Bu yöntem eşzamanlı güvenlidir.|
|[Boyutu](#size)|Eş zamanlı öncelik sırasındaki öğelerin sayısını döndürür. Bu yöntem eşzamanlı güvenlidir.|
|[değiştirme](#swap)|İki eşzamanlı öncelikli kuyruk içeriğini değiştirir. Bu yöntem eşzamanlı güvenli değil.|
|[try_pop](#try_pop)|Kaldırır ve sıranın boş ise sıradan en yüksek öncelikli öğeyi döndürür. Bu yöntem eşzamanlı güvenlidir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Fazla Yüklendi. Başka bir deponun içeriğini atar `concurrent_priority_queue` buna nesne. Bu yöntem eşzamanlı güvenli değil.|

## <a name="remarks"></a>Açıklamalar

Hakkında ayrıntılı bilgi için `concurrent_priority_queue` sınıfı [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`concurrent_priority_queue`

## <a name="requirements"></a>Gereksinimler

**Header:** concurrent_priority_queue.h

**Namespace:** eşzamanlılık

##  <a name="clear"></a> Temizle

Eş zamanlı öncelik tüm öğelerini siler. Bu yöntem eşzamanlı güvenli değil.

```
void clear();
```

### <a name="remarks"></a>Açıklamalar

`clear` Eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda başka bir iş parçacıklarının eş zamanlı öncelikli kuyruk yöntemleri çağırma emin olmanız gerekir. `clear` belleği boşaltmak değil.

##  <a name="ctor"></a> concurrent_priority_queue

Eş zamanlı öncelikli bir kuyruk oluşturur.

```
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
İlk kapasitesi `concurrent_priority_queue` nesne.

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_Bitiş*<br/>
Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.

*_Src*<br/>
Kaynak `concurrent_priority_queue` nesneyi kopyalama veya öğeleri buradan taşımak için.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular ayırıcı nesnesini depolar `_Al` ve öncelik sırası başlatılamıyor.

İlk Oluşturucu bir boş ilk öncelikli kuyruk ve isteğe bağlı olarak bir ayırıcı belirtir.

İkinci Oluşturucu, öncelikli bir kuyruk bir başlangıç kapasitesi ile belirtir. `_Init_capacity` ve isteğe bağlı olarak bir ayırıcı belirtir.

Üçüncü Oluşturucu yineleyici aralığı tarafından sağlanan değerleri belirler [ `_Begin`, `_End`) ve isteğe bağlı olarak bir ayırıcı belirtir.

Dördüncü ve beşinci oluşturucular bir kopyasını bir öncelik sırası belirtin `_Src`.

Altıncı ve yedinci oluşturucular bir taşıma öncelik sırası belirtin `_Src`.

##  <a name="empty"></a> boş

Eş zamanlı öncelikli kuyruk zamanında boş olup olmadığını sınar, bu yöntem çağrılır. Bu yöntem eşzamanlı güvenlidir.

```
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** öncelikli kuyruk boşsa, işlev çağrıldı, şu anda **false** Aksi takdirde.

##  <a name="get_allocator"></a> get_allocator

Eş zamanlı öncelikli kuyruk oluşturmak için kullanılan ayırıcı bir kopyasını döndürür. Bu yöntem eşzamanlı güvenlidir.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir kopyasını oluşturmak için kullanılan ayırıcı `concurrent_priority_queue` nesne.

##  <a name="operator_eq"></a> işleç =

Başka bir deponun içeriğini atar `concurrent_priority_queue` buna nesne. Bu yöntem eşzamanlı güvenli değil.

```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
Kaynak `concurrent_priority_queue` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `concurrent_priority_queue` nesne.

##  <a name="push"></a> anında iletme

Bir öğeyi eşzamanlı öncelik sırasına ekler. Bu yöntem eşzamanlı güvenlidir.

```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```

### <a name="parameters"></a>Parametreler

*_Elem*<br/>
Eş zamanlı öncelikli kuyruğa eklenecek öğe.

##  <a name="size"></a> Boyutu

Eş zamanlı öncelik sırasındaki öğelerin sayısını döndürür. Bu yöntem eşzamanlı güvenlidir.

```
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu öğe sayısını `concurrent_priority_queue` nesne.

### <a name="remarks"></a>Açıklamalar

İşlev çağrıları tarafından eklenen tüm öğeleri dahil etmek için döndürülen boyutu garanti `push`. Ancak, sonuçları bekleyen işlemler eşzamanlı yansıtmayabilir.

##  <a name="swap"></a> değiştirme

İki eşzamanlı öncelikli kuyruk içeriğini değiştirir. Bu yöntem eşzamanlı güvenli değil.

```
void swap(concurrent_priority_queue& _Queue);
```

### <a name="parameters"></a>Parametreler

*_Sıraya alın*<br/>
`concurrent_priority_queue` İçeriğiyle değiştirilecek nesne.

##  <a name="try_pop"></a> try_pop

Kaldırır ve sıranın boş ise sıradan en yüksek öncelikli öğeyi döndürür. Bu yöntem eşzamanlı güvenlidir.

```
bool try_pop(reference _Elem);
```

### <a name="parameters"></a>Parametreler

*_Elem*<br/>
Sıranın boş olması durumunda yüksek öncelikli öğeyle doldurulur bir değişken başvuru.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bir değer POP, **false** Aksi takdirde.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)
