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
ms.openlocfilehash: 8990566fb3a700d61de324f725dea3ec00006d04
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127182"
---
# <a name="accelerator_view-class"></a>accelerator_view Sınıfı

Bir C++ amp veri paralel hızlandırıcısında bir sanal cihaz soyutlamasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class accelerator_view;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[accelerator_view Oluşturucusu](#ctor)|`accelerator_view` sınıfının yeni bir örneğini başlatır.|
|[~ accelerator_view yok edici](#dtor)|`accelerator_view` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[create_marker](#create_marker)|Şimdiye kadar bu `accelerator_view` nesnesine gönderilen tüm komutların tamamlandığını izlemek için gelecekteki bir sonuç döndürür.|
|[temizlenemiyor](#flush)|`accelerator_view` nesnesine sıraya alınan bekleyen tüm komutları, yürütme için hızlandırıcıya gönderir.|
|[get_accelerator](#get_accelerator)|`accelerator_view` nesnesi için `accelerator` nesnesini döndürür.|
|[get_is_auto_selection](#get_is_auto_selection)|`accelerator_view` nesnesi bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri döndürür.|
|[get_is_debug](#get_is_debug)|`accelerator_view` nesnesinin, yoğun hata raporlama için etkin hata ayıklama katmanına sahip olup olmadığını gösteren bir Boole değeri döndürür.|
|[get_queuing_mode](#get_queuing_mode)|`accelerator_view` nesnesinin sıraya alma modunu döndürür.|
|[get_version](#get_version)|`accelerator_view`sürümünü döndürür.|
|[bekleneceğini](#wait)|`accelerator_view` nesnesine gönderilen tüm komutların bitmesini bekler.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|Bu `accelerator_view` nesnesini diğeri ile karşılaştırır ve aynı ise **false** değerini döndürür; Aksi takdirde, **true**döndürür.|
|[işleç =](#operator_eq)|Belirtilen `accelerator_view` nesnesinin içeriğini buna kopyalar.|
|[işleç = =](#operator_eq_eq)|Bu `accelerator_view` nesnesini diğeri ile karşılaştırır ve aynı olursa **true** değerini döndürür; Aksi takdirde, **false**döndürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[hızlandır](#accelerator)|`accelerator_view` nesnesi için `accelerator` nesnesini alır.|
|[is_auto_selection](#is_auto_selection)|`accelerator_view` nesnesi bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri alır.|
|[is_debug](#is_debug)|`accelerator_view` nesnesinin, yoğun hata raporlama için etkin hata ayıklama katmanına sahip olup olmadığını gösteren bir Boole değeri alır.|
|[queuing_mode](#queuing_mode)|`accelerator_view` nesnesinin sıraya alma modunu alır.|
|[version](#version)|Hızlandırıcının sürümünü alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`accelerator_view`

### <a name="remarks"></a>Açıklamalar

`accelerator_view` nesnesi bir hızlandırıcının mantıksal, yalıtılmış bir görünümünü temsil eder. Tek bir fiziksel işlem cihazında birçok mantıksal, yalıtılmış `accelerator_view` nesnesi olabilir. Her Hızlandırıcı varsayılan bir `accelerator_view` nesnesine sahiptir. Ek `accelerator_view` nesneleri oluşturulabilir.

Fiziksel cihazlar, birçok istemci iş parçacığı arasında paylaşılabilir. İstemci iş parçacıkları, hızlandırıcının aynı `accelerator_view` nesnesini birlikte kullanabilir veya her bir istemci, diğer istemci iş parçacıklarından yalıtımına yönelik bağımsız bir `accelerator_view` nesnesi aracılığıyla bir işlem aygıtıyla iletişim kurabilir.

`accelerator_view` nesnesi iki [Queuing_mode numaralandırma](concurrency-namespace-enums-amp.md#queuing_mode) durumlarından birine sahip olabilir. Sıraya alma modu `immediate`, `copy` ve `parallel_for_each` gibi komutlar, çağırana geri dönerken ilgili Hızlandırıcı cihazına gönderilir. Sıraya alma modu `deferred`, bu komutlar `accelerator_view` nesnesine karşılık gelen bir komut kuyruğu üzerinde sıralanır. Komutlar, `flush()` çağrılana kadar cihaza gönderilmez.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="accelerator"></a>hızlandır

Accelerator_view nesnesi için Hızlandırıcı nesnesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="ctor"></a>accelerator_view

Varolan bir `accelerator_view` nesnesini kopyalayarak accelerator_view sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Kopyalanacak `accelerator_view` nesnesi.

## <a name="create_marker"></a>create_marker

Şimdiye kadar bu `accelerator_view` nesnesine gönderilen tüm komutların tamamlandığını izlemek için gelecekteki bir sonuç döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Dönüş Değeri

Şimdiye kadar bu `accelerator_view` nesnesine gönderilen tüm komutların tamamlandığını izlemek için gelecekte.

## <a name="flush"></a>flush

Accelerator_view nesnesine sıraya alınan bekleyen tüm komutları, yürütme için hızlandırıcıya gönderir.

### <a name="syntax"></a>Sözdizimi

```cpp
void flush();
```

### <a name="return-value"></a>Dönüş Değeri

`void` döndürür.

## <a name="get_accelerator"></a>get_accelerator

Accelerator_view nesnesi için Hızlandırıcı nesnesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Accelerator_view nesnesi için Hızlandırıcı nesnesi.

## <a name="get_is_auto_selection"></a>get_is_auto_selection

Accelerator_view bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Dönüş Değeri

çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçse **true** . Aksi takdirde, **false**.

## <a name="get_is_debug"></a>get_is_debug

Accelerator_view nesnesinin, yoğun hata raporlama için etkin hata ayıklama katmanına sahip olup olmadığını gösteren bir Boole değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator_view` nesnesinin, yoğun hata raporlama için etkin hata ayıklama katmanına sahip olup olmadığını belirten bir Boolean değer.

## <a name="get_queuing_mode"></a>get_queuing_mode

Accelerator_view nesnesinin sıraya alma modunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator_view` nesnesinin sıraya alma modu.

## <a name="get_version"></a>get_version

Accelerator_view sürümünü döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator_view`sürümü.

## <a name="is_auto_selection"></a>is_auto_selection

Accelerator_view bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a>is_debug

Accelerator_view nesnesinin, yoğun hata raporlama için etkin hata ayıklama katmanına sahip olup olmadığını gösteren bir Boole değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator_neq"></a>işleç! =

Bu accelerator_view nesnesini diğeri ile karşılaştırır ve aynı ise **false** değerini döndürür; Aksi takdirde, **true**döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
`accelerator_view` nesne bununla Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

iki nesne aynı ise **false** ; Aksi takdirde, **doğru**.

## <a name="operator_eq"></a>işleç =

Belirtilen accelerator_view nesnesinin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Kopyalamanın `accelerator_view` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen `accelerator_view` nesnesine bir başvuru.

## <a name="operator_eq_eq"></a>işleç = =

Bu accelerator_view nesnesini diğeri ile karşılaştırır ve aynı olursa **true** değerini döndürür; Aksi takdirde, **false**döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
`accelerator_view` nesne bununla Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

iki nesne aynı ise **doğru** ; Aksi takdirde, **false**.

## <a name="queuing_mode"></a>queuing_mode

Accelerator_view nesnesinin sıraya alma modunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>sürüm

Accelerator_view sürümünü alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>bekleneceğini

Accelerator_view nesnesine gönderilen tüm komutların bitmesini bekler.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait();
```

### <a name="return-value"></a>Dönüş Değeri

`void` döndürür.

### <a name="remarks"></a>Açıklamalar

[Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) `immediate`ise, bu yöntem doğrudan engellenmeden döndürülür.

## <a name="dtor"></a>~ accelerator_view

Accelerator_view nesnesini yok eder.

### <a name="syntax"></a>Sözdizimi

```cpp
~accelerator_view();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
