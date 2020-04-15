---
title: accelerator_view Sınıfı
ms.date: 03/27/2019
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view::accelerator_view
- AMPRT/Concurrency::accelerator_view::create_marker
- AMPRT/Concurrency::accelerator_view::flush
- AMPRT/Concurrency::accelerator_view::get_accelerator
- AMPRT/Concurrency::accelerator_view::get_is_auto_selection
- AMPRT/Concurrency::accelerator_view::get_is_debug
- AMPRT/Concurrency::accelerator_view::get_queuing_mode
- AMPRT/Concurrency::accelerator_view::get_version
- AMPRT/Concurrency::accelerator_view::wait
- AMPRT/Concurrency::accelerator_view::accelerator
- AMPRT/Concurrency::accelerator_view::is_auto_selection
- AMPRT/Concurrency::accelerator_view::is_debug
- AMPRT/Concurrency::accelerator_view::queuing_mode
- AMPRT/Concurrency::accelerator_view::version
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
ms.openlocfilehash: f3be8cc3ab9a0f36027cc38c88f026570d1fdb55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370884"
---
# <a name="accelerator_view-class"></a>accelerator_view Sınıfı

C++ AMP veri paralel hızlandırıcıda sanal aygıt soyutlamayı temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class accelerator_view;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[accelerator_view Yapıcı](#ctor)|`accelerator_view` sınıfının yeni bir örneğini başlatır.|
|[~accelerator_view Yıkıcı](#dtor)|Nesneyi `accelerator_view` yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[create_marker](#create_marker)|Şimdiye kadar bu `accelerator_view` nesneye gönderilen tüm komutların tamamlanmasını izlemek için bir gelecek döndürür.|
|[flush](#flush)|`accelerator_view` Nesneye sıralanan bekleyen tüm komutları yürütme için hızlandırıcıya gönderir.|
|[get_accelerator](#get_accelerator)|Nesne `accelerator` için nesneyi döndürür. `accelerator_view`|
|[get_is_auto_selection](#get_is_auto_selection)|Nesne bir parallel_for_each geçirildiğinde çalışma zamanının otomatik olarak uygun bir hızlandırıcı seçip seçmeyeceğini belirten bir Boolean değeri döndürür. [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) `accelerator_view`|
|[get_is_debug](#get_is_debug)|Nesnenin `accelerator_view` kapsamlı hata raporlaması için HATA Ayıklama katmanının etkin olup olmadığını gösteren bir Boolean değeri döndürür.|
|[get_queuing_mode](#get_queuing_mode)|Nesne için kuyruk modunu `accelerator_view` döndürür.|
|[get_version](#get_version)|Sürümünü `accelerator_view`verir.|
|[Bekle](#wait)|Nesneye gönderilen tüm komutların `accelerator_view` tamamlanmasını bekler.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[işleç!=](#operator_neq)|Bu `accelerator_view` nesneyi başka bir nesneyle karşılaştırır ve aynıysa **yanlış** döndürür; aksi takdirde, **doğru**döndürür.|
|[işleç=](#operator_eq)|Belirtilen `accelerator_view` nesnenin içeriğini buna kopyalar.|
|[işleç==](#operator_eq_eq)|Bu `accelerator_view` nesneyi başka bir nesneyle karşılaştırır ve aynıysa **doğru** döndürür; aksi takdirde, **yanlış**döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[Hızlandırıcı](#accelerator)|Nesne `accelerator` için nesne `accelerator_view` alır.|
|[is_auto_selection](#is_auto_selection)|Nesne bir parallel_for_each geçirildiğinde çalışma zamanının otomatik olarak uygun bir hızlandırıcı seçip seçmeyeceğini gösteren bir Boolean değeri alır. [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) `accelerator_view`|
|[is_debug](#is_debug)|Nesnenin `accelerator_view` kapsamlı hata raporlaması için HATA Ayıklama katmanının etkin olup olmadığını gösteren bir Boolean değeri alır.|
|[queuing_mode](#queuing_mode)|Nesne için kuyruk modunu `accelerator_view` alır.|
|[Sürüm](#version)|Hızlandırıcının sürümünü alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`accelerator_view`

### <a name="remarks"></a>Açıklamalar

Bir `accelerator_view` nesne, hızlandırıcının mantıksal, yalıtılmış görünümünü temsil eder. Tek bir fiziksel bilgi işlem aygıtının birçok `accelerator_view` mantıksal, yalıtılmış nesnesi olabilir. Her hızlandırıcının `accelerator_view` varsayılan bir nesnesi vardır. Ek `accelerator_view` nesneler oluşturulabilir.

Fiziksel aygıtlar birçok istemci iş parçacığı arasında paylaşılabilir. İstemci iş parçacıkları bir `accelerator_view` hızlandırıcının aynı nesnesini birlikte kullanabilir veya her istemci `accelerator_view` diğer istemci iş parçacığından yalıtım için bağımsız bir nesne üzerinden bir bilgi işlem aygıtıyla iletişim kurabilir.

Bir `accelerator_view` nesne, [Numaralandırma](concurrency-namespace-enums-amp.md#queuing_mode) queuing_mode iki durum olabilir. Kuyruk modu ise, `immediate`çağırana döner `copy` `parallel_for_each` dönmez ilgili hızlandırıcı aygıtına gönderilir ve komutları kullanır. Kuyruk modu ise, `deferred`bu tür komutlar `accelerator_view` nesneye karşılık gelen bir komut kuyruğunda sıraya alınır. Komutlar çağrılana kadar `flush()` aygıta gönderilmez.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt.h

**Ad alanı:** Eşzamanlılık

## <a name="accelerator"></a><a name="accelerator"></a>Hızlandırıcı

accelerator_view nesneiçin hızlandırıcı nesnealır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="accelerator_view"></a><a name="ctor"></a>Accelerator_view

Varolan `accelerator_view` bir nesneyi kopyalayarak accelerator_view sınıfının yeni bir örneğini başolarak adlandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Kopyalanması `accelerator_view` gereken nesne.

## <a name="create_marker"></a><a name="create_marker"></a>create_marker

Şimdiye kadar bu `accelerator_view` nesneye gönderilen tüm komutların tamamlanmasını izlemek için bir gelecek döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Dönüş Değeri

Şimdiye kadar bu `accelerator_view` nesneye gönderilen tüm komutların tamamlanmasını izlemek için bir gelecek.

## <a name="flush"></a>flush

Yürütme için hızlandırıcıya accelerator_view nesneye sıralanmış bekleyen tüm komutları gönderir.

### <a name="syntax"></a>Sözdizimi

```cpp
void flush();
```

### <a name="return-value"></a>Dönüş Değeri

`void` döndürür.

## <a name="get_accelerator"></a><a name="get_accelerator"></a>get_accelerator

accelerator_view nesneiçin hızlandırıcı nesnesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Dönüş Değeri

accelerator_view nesnenin hızlandırıcı nesnesi.

## <a name="get_is_auto_selection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection

accelerator_view bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde çalışma zamanının otomatik olarak uygun bir hızlandırıcı seçip seçmeyeceğini belirten bir Boolean değeri verir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Dönüş Değeri

çalışma süresi otomatik olarak uygun bir hızlandırıcı seçilecekse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="get_is_debug"></a><a name="get_is_debug"></a>get_is_debug

accelerator_view nesnesinin kapsamlı hata raporlaması için HATA Ayıklama katmanına sahip olup olmadığını gösteren bir Boolean değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `accelerator_view` kapsamlı hata raporlaması için HATA Ayıklama katmanının etkin olup olmadığını gösteren bir Boolean değeri.

## <a name="get_queuing_mode"></a><a name="get_queuing_mode"></a>get_queuing_mode

accelerator_view nesnesi için kuyruk modunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator_view` Nesne için kuyruk modu.

## <a name="get_version"></a><a name="get_version"></a>get_version

accelerator_view sürümünü döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sürümü `accelerator_view`.

## <a name="is_auto_selection"></a><a name="is_auto_selection"></a>is_auto_selection

accelerator_view bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde çalışma zamanının otomatik olarak uygun bir hızlandırıcı seçip seçmeyeceğini belirten bir Boolean değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a><a name="is_debug"></a>is_debug

accelerator_view nesnesinin kapsamlı hata raporlaması için HATA Ayıklama katmanının etkin olup olmadığını gösteren bir Boolean değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator"></a><a name="operator_neq"></a>işleç!=

Bu accelerator_view nesneyle başka bir nesneyle karşılaştırır ve aynıysa **yanlış** döndürür; aksi takdirde, **doğru**döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bu `accelerator_view` ile karşılaştırmak için nesne.

### <a name="return-value"></a>Dönüş Değeri

iki nesne aynıysa **yanlış;** aksi takdirde, **doğru**.

## <a name="operator"></a><a name="operator_eq"></a>işleç=

Belirtilen accelerator_view nesnenin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Kopyalanması `accelerator_view` gereken nesne.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen `accelerator_view` nesneye bir başvuru.

## <a name="operator"></a><a name="operator_eq_eq"></a>işleç==

Bu accelerator_view nesneyle başka bir nesneyle karşılaştırır ve aynıysa **doğru** döndürür; aksi takdirde, **yanlış**döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Bu `accelerator_view` ile karşılaştırmak için nesne.

### <a name="return-value"></a>Dönüş Değeri

iki nesne aynıysa **doğrudur;** aksi takdirde, **yanlış**.

## <a name="queuing_mode"></a><a name="queuing_mode"></a>queuing_mode

accelerator_view nesnesi için kuyruk modunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>version

accelerator_view sürümünü alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>Bekle

accelerator_view nesneye gönderilen tüm komutların tamamlanmasını bekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait();
```

### <a name="return-value"></a>Dönüş Değeri

`void` döndürür.

### <a name="remarks"></a>Açıklamalar

[queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) ise, `immediate`bu yöntem engellemeden hemen döner.

## <a name="accelerator_view"></a><a name="dtor"></a>~accelerator_view

accelerator_view nesneyi yok eder.

### <a name="syntax"></a>Sözdizimi

```cpp
~accelerator_view();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
