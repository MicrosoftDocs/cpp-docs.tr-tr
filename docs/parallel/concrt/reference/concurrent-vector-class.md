---
title: concurrent_vector sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68ea93c137962e48f8a627e9a9409e4e7fceef65
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163380"
---
# <a name="concurrentvector-class"></a>concurrent_vector Sınıfı

`concurrent_vector` Herhangi bir öğeye rastgele erişim sağlayan bir sıralı kapsayıcı sınıfı. Bağlayabileceğinizi eşzamanlılık açısından güvenli sona ekleme, öğe erişimi, yineleyici erişimi ve yineleyici çapraz geçiş işlemleri.

## <a name="syntax"></a>Sözdizimi

```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
private details::_Concurrent_vector_base_v4;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Vektör içinde depolanacak öğe veri türü.

*_Ax*<br/>
Ayırma ve eşzamanlı vektör için bellek ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<T>`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`allocator_type`|Eşzamanlı vektör için ayırıcı sınıf temsil eden tür.|
|`const_iterator`|Okuyabilen rasgele erişim yineleyicisi sağlayan bir tür bir `const` eş zamanlı vektör öğe.|
|`const_pointer`|Bir işaretçi sağlayan bir tür bir `const` eş zamanlı vektör öğe.|
|`const_reference`|Bir başvuru sağlayan bir tür bir `const` okumak ve gerçekleştirmek için eş zamanlı vektör içinde depolanan öğenin `const` operations.|
|`const_reverse_iterator`|Herhangi bir rastgele erişim yineleyicisi sağlayan bir tür okuma `const` eşzamanlı vektör öğe.|
|`difference_type`|Eş zamanlı vektör içindeki iki öğe arasındaki imzalı uzaklığı sağlayan bir tür.|
|`iterator`|Eş zamanlı vektör içindeki herhangi bir öğeyi okuyabilen rasgele erişim yineleyicisi sağlayan bir tür. Yineleyici kullanarak bir öğe değiştirilmesini, eşzamanlılık açısından güvenli değildir.|
|`pointer`|Eş zamanlı vektör içindeki bir öğeye işaretçi sağlayan bir tür.|
|`reference`|Eşzamanlı vektör içinde depolanan öğeye başvuru sağlayan bir tür.|
|`reverse_iterator`|Ters çevrilen bir eş zamanlı vektör içindeki herhangi bir öğeyi okuyabilen rasgele erişim yineleyicisi sağlayan bir tür. Yineleyici kullanarak bir öğe değiştirilmesini, eşzamanlılık açısından güvenli değildir.|
|`size_type`|Eş zamanlı vektör öğelerini sayar türü.|
|`value_type`|Eşzamanlı vektör içinde depolanan veri türünü temsil eden tür.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[concurrent_vector](#ctor)|Fazla Yüklendi. Eş zamanlı vektör oluşturur.|
|[~ concurrent_vector yok Edicisi](#dtor)|Tüm öğeleri siler ve bu eş zamanlı vektör yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ata](#assign)|Fazla Yüklendi. Eşzamanlı vektör öğelerini siler ve ya da atar `_N` , kopyalar `_Item`, ya da yineleyici aralığı tarafından belirtilen değerleri [ `_Begin`, `_End`). Bu yöntem eşzamanlı güvenli değil.|
|[konumunda](#at)|Fazla Yüklendi. Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlı güvenlidir okuma işlemleri için ve ayrıca, değer belirlediniz sürece vektör büyüyen çalışırken `_Index` eşzamanlı vektör boyutu küçüktür.|
|[Geri](#back)|Fazla Yüklendi. Bir başvuru döndürür `const` son eşzamanlı vektör öğe başvurusu. Eşzamanlı vektör boş ise, dönüş değeri tanımsızdır. Bu yöntem eşzamanlı güvenlidir.|
|[başlayın](#begin)|Fazla Yüklendi. Türü bir yineleyici döndüren `iterator` veya `const_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[Kapasite](#capacity)|Daha fazla bellek ayırmak zorunda kalmadan eşzamanlı vektör büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlı güvenlidir.|
|[cbegin](#cbegin)|Türü bir yineleyici döndüren `const_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[cend](#cend)|Türü bir yineleyici döndüren `const_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[Temizle](#clear)|Eşzamanlı vektör içindeki tüm öğelerini siler. Bu yöntem eşzamanlı güvenli değil.|
|[crbegin](#crbegin)|Türü bir yineleyici döndüren `const_reverse_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[crend](#crend)|Türü bir yineleyici döndüren `const_reverse_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[boş](#empty)|Eşzamanlı vektör zaman boş olup olmadığını sınar, bu yöntem çağrılır. Bu yöntem eşzamanlı güvenlidir.|
|[Son](#end)|Fazla Yüklendi. Türü bir yineleyici döndüren `iterator` veya `const_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[Ön](#front)|Fazla Yüklendi. Bir başvuru döndürür `const` eşzamanlı vektör içindeki ilk öğeye bir başvuru. Eşzamanlı vektör boş ise, dönüş değeri tanımsızdır. Bu yöntem eşzamanlı güvenlidir.|
|[get_allocator](#get_allocator)|Eşzamanlı vektör oluşturmak için kullanılan ayırıcı bir kopyasını döndürür. Bu yöntem eşzamanlı güvenlidir.|
|[grow_by](#grow_by)|Fazla Yüklendi. Bu eşzamanlı vektör tarafından büyüdükçe `_Delta` öğeleri. Bu yöntem eşzamanlı güvenlidir.|
|[grow_to_at_least](#grow_to_at_least)|En az olana kadar bu eş zamanlı vektör büyüdükçe `_N` öğeleri. Bu yöntem eşzamanlı güvenlidir.|
|[max_size](#max_size)|En fazla eşzamanlı vektör içerebileceği öğe sayısını döndürür. Bu yöntem eşzamanlı güvenlidir.|
|[push_back](#push_back)|Fazla Yüklendi. Verilen öğe eşzamanlı vektör sonuna ekler. Bu yöntem eşzamanlı güvenlidir.|
|[rbegin](#rbegin)|Fazla Yüklendi. Türü bir yineleyici döndüren `reverse_iterator` veya `const_reverse_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[rend](#rend)|Fazla Yüklendi. Türü bir yineleyici döndüren `reverse_iterator` veya `const_reverse_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.|
|[ayırma](#reserve)|Eşzamanlı vektör için boyut büyümesi için yeterli alan ayırır `_N` daha sonra daha fazla bellek ayırmak zorunda kalmadan. Bu yöntem eşzamanlı güvenli değil.|
|[yeniden boyutlandırma](#resize)|Fazla Yüklendi. İstenen boyuta gerektiği gibi öğeleri ekleme veya silme, eş zamanlı vektör boyutunu değiştirir. Bu yöntem eşzamanlı güvenli değil.|
|[shrink_to_fit](#shrink_to_fit)|Eşzamanlı vektör parçalanmasını azaltmak ve bellek kullanımını iyileştirmek için iç gösterimine sıkıştırır. Bu yöntem eşzamanlı güvenli değil.|
|[Boyutu](#size)|Eşzamanlı vektör öğelerin sayısını döndürür. Bu yöntem eşzamanlı güvenlidir.|
|[değiştirme](#swap)|İki eş zamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlı güvenli değil.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator]](#operator_at)|Fazla Yüklendi. Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlı güvenlidir okuma işlemleri için ve ayrıca, sağlamış olduğu sürece, değeri vektör büyüyen çalışırken `_Index` eşzamanlı vektör boyutu küçüktür.|
|[operator=](#operator_eq)|Fazla Yüklendi. Başka bir deponun içeriğini atar `concurrent_vector` buna nesne. Bu yöntem eşzamanlı güvenli değil.|

## <a name="remarks"></a>Açıklamalar

Hakkında ayrıntılı bilgi için `concurrent_vector` sınıfı [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Concurrent_vector_base_v4`

`_Allocator_base`

`concurrent_vector`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concurrent_vector.h

**Namespace:** eşzamanlılık

##  <a name="assign"></a> Ata

Eşzamanlı vektör öğelerini siler ve ya da atar `_N` , kopyalar `_Item`, ya da yineleyici aralığı tarafından belirtilen değerleri [ `_Begin`, `_End`). Bu yöntem eşzamanlı güvenli değil.

```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>Parametreler

*_InputIterator*<br/>
Belirtilen yineleyici türü.

*_N*<br/>
Eş zamanlı kopyalayacak öğe sayısı.

*Öğeyi*<br/>
Eşzamanlı vektör doldurmak için kullanılan bir değerine başvuru.

*_Begin*<br/>
Kaynak aralığının ilk öğeye bir yineleyici.

*_Bitiş*<br/>
Kaynak aralığının son öğeden bir öncekine bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`assign` Eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda başka bir iş parçacıklarının eş zamanlı vektör yöntemleri çağırma emin olmanız gerekir.

##  <a name="at"></a> konumunda

Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlı güvenlidir okuma işlemleri için ve ayrıca, değer belirlediniz sürece vektör büyüyen çalışırken `_Index` eşzamanlı vektör boyutu küçüktür.

```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğeyi bir başvuru.

### <a name="remarks"></a>Açıklamalar

İşlevin sürümünü `at` olmayan bir döndüren `const` başvuru, aynı anda farklı iş parçacıklarından öğesine yazmak için kullanılamaz. Farklı bir eşitleme nesnesi, eşitleme eş zamanlı okuma ve yazma işlemleri için aynı veri öğesi için kullanılmalıdır.

Çağırılıyorsa yöntem `out_of_range` varsa `_Index` büyüktür veya eşittir eşzamanlı vektör boyutu ve `range_error` dizini vektörü bozuk bir kısmı için ise. Nasıl bir vektörü bozuk olabilir hakkında daha fazla bilgi için bkz [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).

##  <a name="back"></a> Geri

Bir başvuru döndürür `const` son eşzamanlı vektör öğe başvurusu. Eşzamanlı vektör boş ise, dönüş değeri tanımsızdır. Bu yöntem eşzamanlı güvenlidir.

```
reference back();

const_reference back() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru veya `const` son eşzamanlı vektör öğe başvurusu.

##  <a name="begin"></a> başlayın

Türü bir yineleyici döndüren `iterator` veya `const_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `iterator` veya `const_iterator` başlangıcına kadar eş zamanlı vektör.

##  <a name="capacity"></a> Kapasite

Daha fazla bellek ayırmak zorunda kalmadan eşzamanlı vektör büyüyebileceği maksimum boyutu döndürür. Bu yöntem eşzamanlı güvenlidir.

```
size_type capacity() const;
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla bellek ayırmak zorunda kalmadan eşzamanlı vektör büyüyebileceği maksimum boyutu.

### <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı aksine `vector`, `concurrent_vector` nesne hareket var olan öğeleri daha fazla bellek ayırırsa.

##  <a name="cbegin"></a> cbegin

Türü bir yineleyici döndüren `const_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
const_iterator cbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `const_iterator` başlangıcına kadar eş zamanlı vektör.

##  <a name="cend"></a> cend

Türü bir yineleyici döndüren `const_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
const_iterator cend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `const_iterator` sonuna kadar eş zamanlı vektör.

##  <a name="clear"></a> Temizle

Eşzamanlı vektör içindeki tüm öğelerini siler. Bu yöntem eşzamanlı güvenli değil.

```
void clear();
```

### <a name="remarks"></a>Açıklamalar

`clear` Eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda başka bir iş parçacıklarının eş zamanlı vektör yöntemleri çağırma emin olmanız gerekir. `clear` İç diziler boş değil. İç diziler boşaltmak için işlev çağrısı `shrink_to_fit` sonra `clear`.

##  <a name="ctor"></a> concurrent_vector

Eş zamanlı vektör oluşturur.

```
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
Kaynak vektörünün kaynak ayırıcı türü.

*_InputIterator*<br/>
Giriş yineleyicisinin türü.

*_Al*<br/>
Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.

*_Vector*<br/>
Kaynak `concurrent_vector` nesneyi kopyalama veya öğeleri buradan taşımak için.

*_N*<br/>
İlk kapasitesi `concurrent_vector` nesne.

*Öğeyi*<br/>
Oluşturulmuş nesnedeki öğelerin değeri.

*_Begin*<br/>
Kopyalanacak öğe aralığındaki ilk öğenin konumu.

*_Bitiş*<br/>
Kopyalanacak öğe aralığının dışındaki ilk öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular ayırıcı nesnesini depolar `_Al` ve vektörü başlatır.

İlk Oluşturucu boş bir başlangıç vektörü belirler ve açıkça ayırıcı türünü belirtir. kullanılacak.

İkinci ve üçüncü oluşturucular eşzamanlı vektör bir kopyasını belirtin `_Vector`.

Dördüncü Oluşturucu, taşıma eş zamanlı vektör belirtir `_Vector`.

Beşinci Oluşturucu sayının belirtilen bir yineleme belirtir ( `_N`) sınıfı için varsayılan değer öğelerinin `T`.

Altıncı Oluşturucu bir tekrarını belirtir ( `_N`) değerinin öğelerinin `_Item`.

Son Oluşturucu yineleyici aralığı tarafından sağlanan değerleri belirler [ `_Begin`, `_End`).

##  <a name="dtor"></a> ~ concurrent_vector

Tüm öğeleri siler ve bu eş zamanlı vektör yok eder.

```
~concurrent_vector();
```

##  <a name="crbegin"></a> crbegin

Türü bir yineleyici döndüren `const_reverse_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `const_reverse_iterator` başlangıcına kadar eş zamanlı vektör.

##  <a name="crend"></a> crend

Türü bir yineleyici döndüren `const_reverse_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `const_reverse_iterator` sonuna kadar eş zamanlı vektör.

##  <a name="empty"></a> boş

Eşzamanlı vektör zaman boş olup olmadığını sınar, bu yöntem çağrılır. Bu yöntem eşzamanlı güvenlidir.

```
bool empty() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** vektör boşsa, işlev çağrıldı, şu anda **false** Aksi takdirde.

##  <a name="end"></a> Son

Türü bir yineleyici döndüren `iterator` veya `const_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `iterator` veya `const_iterator` sonuna kadar eş zamanlı vektör.

##  <a name="front"></a> Ön

Bir başvuru döndürür `const` eşzamanlı vektör içindeki ilk öğeye bir başvuru. Eşzamanlı vektör boş ise, dönüş değeri tanımsızdır. Bu yöntem eşzamanlı güvenlidir.

```
reference front();

const_reference front() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru veya `const` eşzamanlı vektör içindeki ilk öğeye bir başvuru.

##  <a name="get_allocator"></a> get_allocator

Eşzamanlı vektör oluşturmak için kullanılan ayırıcı bir kopyasını döndürür. Bu yöntem eşzamanlı güvenlidir.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir kopyasını oluşturmak için kullanılan ayırıcı `concurrent_vector` nesne.

##  <a name="grow_by"></a> grow_by

Bu eşzamanlı vektör tarafından büyüdükçe `_Delta` öğeleri. Bu yöntem eşzamanlı güvenlidir.

```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```

### <a name="parameters"></a>Parametreler

*_Delta*<br/>
Nesnesine eklenecek öğe sayısı.

*Öğeyi*<br/>
Yeni öğelerle başlatmak için değer.

### <a name="return-value"></a>Dönüş Değeri

İlk öğeye bir yineleyici eklenir.

### <a name="remarks"></a>Açıklamalar

Varsa `_Item` belirtilmezse, yeni öğeler varsayılan oluşturulmuş.

##  <a name="grow_to_at_least"></a> grow_to_at_least

En az olana kadar bu eş zamanlı vektör büyüdükçe `_N` öğeleri. Bu yöntem eşzamanlı güvenlidir.

```
iterator grow_to_at_least(size_type _N);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
İçin yeni bir minimum boyut `concurrent_vector` nesne.

### <a name="return-value"></a>Dönüş Değeri

Eklenen dizisi başlangıcına veya dizinindeki öğeyi gösteren bir yineleyici `_N` hiçbir öğe eklenmiş değilse.

##  <a name="max_size"></a> max_size

En fazla eşzamanlı vektör içerebileceği öğe sayısını döndürür. Bu yöntem eşzamanlı güvenlidir.

```
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğelerinin üst limiti `concurrent_vector` nesne tutabilir.

##  <a name="operator_eq"></a> işleç =

Başka bir deponun içeriğini atar `concurrent_vector` buna nesne. Bu yöntem eşzamanlı güvenli değil.

```
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
Kaynak vektörünün kaynak ayırıcı türü.

*_Vector*<br/>
Kaynak `concurrent_vector` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `concurrent_vector` nesne.

##  <a name="operator_at"></a> operator]

Eşzamanlı vektör içinde belirtilen dizinindeki öğeyi erişim sağlar. Bu yöntem eşzamanlı güvenlidir okuma işlemleri için ve ayrıca, sağlamış olduğu sürece, değeri vektör büyüyen çalışırken `_Index` eşzamanlı vektör boyutu küçüktür.

```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğeyi bir başvuru.

### <a name="remarks"></a>Açıklamalar

Sürümü `operator []` olmayan bir döndüren `const` başvuru, aynı anda farklı iş parçacıklarından öğesine yazmak için kullanılamaz. Farklı bir eşitleme nesnesi, eşitleme eş zamanlı okuma ve yazma işlemleri için aynı veri öğesi için kullanılmalıdır.

Denetimi gerçekleştirilir emin olmak için bir sınır yoktur `_Index` eşzamanlı vektör içinde geçerli bir dizindir.

##  <a name="push_back"></a> push_back

Verilen öğe eşzamanlı vektör sonuna ekler. Bu yöntem eşzamanlı güvenlidir.

```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```

### <a name="parameters"></a>Parametreler

*Öğeyi*<br/>
Eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Öğeye bir yineleyici eklenir.

##  <a name="rbegin"></a> rbegin

Türü bir yineleyici döndüren `reverse_iterator` veya `const_reverse_iterator` başlangıcına kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `reverse_iterator` veya `const_reverse_iterator` başlangıcına kadar eş zamanlı vektör.

##  <a name="rend"></a> rend

Türü bir yineleyici döndüren `reverse_iterator` veya `const_reverse_iterator` sonuna kadar eş zamanlı vektör. Bu yöntem eşzamanlı güvenlidir.

```
reverse_iterator rend();

const_reverse_iterator rend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici türünün `reverse_iterator` veya `const_reverse_iterator` sonuna kadar eş zamanlı vektör.

##  <a name="reserve"></a> ayırma

Eşzamanlı vektör için boyut büyümesi için yeterli alan ayırır `_N` daha sonra daha fazla bellek ayırmak zorunda kalmadan. Bu yöntem eşzamanlı güvenli değil.

```
void reserve(size_type _N);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
Alan ayırmak için öğe sayısı.

### <a name="remarks"></a>Açıklamalar

`reserve` Eşzamanlılık açısından güvenli değildir. Bu yöntemi çağırdığınızda başka bir iş parçacıklarının eş zamanlı vektör yöntemleri çağırma emin olmanız gerekir. Eşzamanlı vektör yöntemin dönüşünün ardından kapasitesini istenen ayırmayı büyük olabilir.

##  <a name="resize"></a> yeniden boyutlandırma

İstenen boyuta gerektiği gibi öğeleri ekleme veya silme, eş zamanlı vektör boyutunu değiştirir. Bu yöntem eşzamanlı güvenli değil.

```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```

### <a name="parameters"></a>Parametreler

*_N*<br/>
Concurrent_vector yeni boyutu.

*VAL*<br/>
Yeni boyutu özgün boyutundan büyükse, vektör için eklenen yeni öğelerin değeri. Değer atlanırsa yeni nesneler kendi türü için varsayılan değer atanır.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı boyutu istenen boyuttan daha az ise, öğe boyutuna erişene kadar vektör kayıtlarına eklenir. Kapsayıcı boyutu istenen boyuttan daha büyük ise, kapsayıcı boyutuna erişene kadar kapsayıcı sonuna yakın öğeler silinir `_N`. Kapsayıcının mevcut boyutu istenen boyutla aynıysa hiçbir işlem yapılmaz.

`resize` Eşzamanlılık güvenli değildir. Bu yöntemi çağırdığınızda başka bir iş parçacıklarının eş zamanlı vektör yöntemleri çağırma emin olmanız gerekir.

##  <a name="shrink_to_fit"></a> shrink_to_fit

Eşzamanlı vektör parçalanmasını azaltmak ve bellek kullanımını iyileştirmek için iç gösterimine sıkıştırır. Bu yöntem eşzamanlı güvenli değil.

```
void shrink_to_fit();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi dahili olarak bellek taşıma öğelerin, tüm yineleyiciler geçersiz kılmalarını yeniden ayırır. `shrink_to_fit` Eşzamanlılık açısından güvenli değildir. Bu işlev çağırdığınızda başka bir iş parçacıklarının eş zamanlı vektör yöntemleri çağırma emin olmanız gerekir.

##  <a name="size"></a> Boyutu

Eşzamanlı vektör öğelerin sayısını döndürür. Bu yöntem eşzamanlı güvenlidir.

```
size_type size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu öğe sayısını `concurrent_vector` nesne.

### <a name="remarks"></a>Açıklamalar

İşlev çağrıları tarafından eklenen tüm öğeleri dahil etmek için döndürülen boyutu garanti `push_back`, ya da bu yöntemi çağırmadan önce tamamlanan işlemlerinin büyütün. Ancak, bu da ayrılan öğeler içerebilir ancak yine de büyüme yöntemlerden herhangi birini eş zamanlı çağrılar tarafından aşamasında.

##  <a name="swap"></a> değiştirme

İki eş zamanlı vektör içeriğini değiştirir. Bu yöntem eşzamanlı güvenli değil.

```
void swap(concurrent_vector& _Vector);
```

### <a name="parameters"></a>Parametreler

*_Vector*<br/>
`concurrent_vector` İçeriğiyle değiştirilecek nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Paralel Kapsayıcılar ve Nesneler](../../../parallel/concrt/parallel-containers-and-objects.md)

