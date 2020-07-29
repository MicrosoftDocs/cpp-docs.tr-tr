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
ms.openlocfilehash: 0020acfda7b506bf9f0547b9daedff34d80204f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182765"
---
# <a name="accelerator_view-class"></a>accelerator_view Sınıfı

C++ AMP veri paralel hızlandırıcıda sanal cihaz soyutlamasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class accelerator_view;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[accelerator_view Oluşturucusu](#ctor)|`accelerator_view` sınıfının yeni bir örneğini başlatır.|
|[~ accelerator_view yok edici](#dtor)|Nesneyi yok eder `accelerator_view` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[create_marker](#create_marker)|Bu nesneye şimdiye kadar gönderilen tüm komutların tamamlandığını izlemek için gelecekteki bir döndürür `accelerator_view` .|
|[flush](#flush)|Yürütmek için nesneye sıraya alınan tüm bekleyen komutları gönderir `accelerator_view` .|
|[get_accelerator](#get_accelerator)|`accelerator`Nesnenin nesnesini döndürür `accelerator_view` .|
|[get_is_auto_selection](#get_is_auto_selection)|`accelerator_view`Nesne bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri döndürür.|
|[get_is_debug](#get_is_debug)|`accelerator_view`Nesnenin, kapsamlı hata raporlaması IÇIN hata ayıklama katmanının etkinleştirilip etkinleştirilmediğini belirten bir Boole değeri döndürür.|
|[get_queuing_mode](#get_queuing_mode)|Nesne için sıraya alma modunu döndürür `accelerator_view` .|
|[get_version](#get_version)|Sürümünü döndürür `accelerator_view` .|
|[bekleneceğini](#wait)|Nesneye gönderilen tüm komutların `accelerator_view` bitmesini bekler.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç! =](#operator_neq)|Bu `accelerator_view` nesneyi diğeri ile karşılaştırır ve **`false`** aynı ise öğesini döndürür; Aksi takdirde, döndürür **`true`** .|
|[işleç =](#operator_eq)|Belirtilen `accelerator_view` nesnenin içeriğini buna kopyalar.|
|[işleç = =](#operator_eq_eq)|Bu `accelerator_view` nesneyi diğeri ile karşılaştırır ve **`true`** aynı ise öğesini döndürür; Aksi takdirde, döndürür **`false`** .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[hızlandır](#accelerator)|`accelerator`Nesne için nesneyi alır `accelerator_view` .|
|[is_auto_selection](#is_auto_selection)|`accelerator_view`Nesne bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri alır.|
|[is_debug](#is_debug)|`accelerator_view`Nesnenin, kapsamlı hata raporlaması IÇIN hata ayıklama katmanının etkinleştirilip etkinleştirilmediğini gösteren bir Boole değeri alır.|
|[queuing_mode](#queuing_mode)|Nesne için sıraya alma modunu alır `accelerator_view` .|
|[Sürüm](#version)|Hızlandırıcının sürümünü alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`accelerator_view`

### <a name="remarks"></a>Açıklamalar

Bir `accelerator_view` nesne, hızlandırıcının mantıksal, yalıtılmış bir görünümünü temsil eder. Tek bir fiziksel işlem cihazında birçok mantıksal, yalıtılmış nesne bulunabilir `accelerator_view` . Her hızlandırıcının varsayılan bir `accelerator_view` nesnesi vardır. Ek `accelerator_view` nesneler oluşturulabilir.

Fiziksel cihazlar, birçok istemci iş parçacığı arasında paylaşılabilir. İstemci iş parçacıkları `accelerator_view` bir hızlandırıcının aynı nesnesini birlikte kullanabilir veya her bir istemci, `accelerator_view` diğer istemci iş parçacıklarından yalıtılmış bir bağımsız nesne aracılığıyla bir işlem aygıtıyla iletişim kurabilir.

Bir `accelerator_view` nesne iki [queuing_mode numaralandırma](concurrency-namespace-enums-amp.md#queuing_mode) durumlarından birine sahip olabilir. Sıraya alma modu ise `immediate` , ve gibi komutlar `copy` , `parallel_for_each` çağırana geri döndükten hemen sonra karşılık gelen Hızlandırıcı cihazına gönderilir. Sıraya alma modu ise `deferred` , bu tür komutlar nesnesine karşılık gelen bir komut kuyruğu üzerinde sıralanır `accelerator_view` . Komutlar, çağrılana kadar cihaza gönderilmez `flush()` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** Zamanlı

## <a name="accelerator"></a><a name="accelerator"></a>hızlandır

Accelerator_view nesnesi için Hızlandırıcı nesnesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="accelerator_view"></a><a name="ctor"></a>accelerator_view

Varolan bir nesneyi kopyalayarak accelerator_view sınıfının yeni bir örneğini başlatır `accelerator_view` .

### <a name="syntax"></a>Söz dizimi

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
`accelerator_view`Kopyalanacak nesne.

## <a name="create_marker"></a><a name="create_marker"></a>create_marker

Bu nesneye şimdiye kadar gönderilen tüm komutların tamamlandığını izlemek için gelecekteki bir döndürür `accelerator_view` .

### <a name="syntax"></a>Sözdizimi

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Dönüş Değeri

Şimdiye kadar bu nesneye gönderilen tüm komutların tamamlandığını izlemek için bir sonraki `accelerator_view` .

## <a name="flush"></a>flush

Accelerator_view nesnesine sıraya alınan bekleyen tüm komutları, yürütme için hızlandırıcıya gönderir.

### <a name="syntax"></a>Sözdizimi

```cpp
void flush();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür **`void`** .

## <a name="get_accelerator"></a><a name="get_accelerator"></a>get_accelerator

Accelerator_view nesnesi için Hızlandırıcı nesnesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Accelerator_view nesnesi için Hızlandırıcı nesnesi.

## <a name="get_is_auto_selection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection

Accelerator_view bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçip seçmeyecektir. Aksi takdirde, **`false`** .

## <a name="get_is_debug"></a><a name="get_is_debug"></a>get_is_debug

Accelerator_view nesnesinin, yoğun hata raporlama için etkin hata ayıklama katmanına sahip olup olmadığını gösteren bir Boole değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator_view`Nesnenin, kapsamlı hata raporlaması IÇIN hata ayıklama katmanının etkinleştirilip etkinleştirilmediğini belirten bir Boolean değer.

## <a name="get_queuing_mode"></a><a name="get_queuing_mode"></a>get_queuing_mode

Accelerator_view nesnesinin sıraya alma modunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne için sıraya alma modu `accelerator_view` .

## <a name="get_version"></a><a name="get_version"></a>get_version

Accelerator_view sürümünü döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğesinin sürümü `accelerator_view` .

## <a name="is_auto_selection"></a><a name="is_auto_selection"></a>is_auto_selection

Accelerator_view bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)geçirildiğinde, çalışma zamanının otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a><a name="is_debug"></a>is_debug

Accelerator_view nesnesinin, yoğun hata raporlama için etkin hata ayıklama katmanına sahip olup olmadığını gösteren bir Boole değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator"></a><a name="operator_neq"></a>işleç! =

Bu accelerator_view nesnesini diğeri ile karşılaştırır ve **`false`** aynı ise döndürür; Aksi takdirde, döndürür **`true`** .

### <a name="syntax"></a>Söz dizimi

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Bununla `accelerator_view` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`false`** iki nesne aynı ise, Aksi takdirde, **`true`** .

## <a name="operator"></a><a name="operator_eq"></a>işleç =

Belirtilen accelerator_view nesnesinin içeriğini buna kopyalar.

### <a name="syntax"></a>Söz dizimi

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
`accelerator_view`Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen nesneye bir başvuru `accelerator_view` .

## <a name="operator"></a><a name="operator_eq_eq"></a>işleç = =

Bu accelerator_view nesnesini diğeri ile karşılaştırır ve **`true`** aynı ise döndürür; Aksi takdirde, döndürür **`false`** .

### <a name="syntax"></a>Söz dizimi

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Bununla `accelerator_view` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** iki nesne aynı ise, Aksi takdirde, **`false`** .

## <a name="queuing_mode"></a><a name="queuing_mode"></a>queuing_mode

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

Döndürür **`void`** .

### <a name="remarks"></a>Açıklamalar

[Queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) ise `immediate` , bu yöntem doğrudan engellenmeden döndürülür.

## <a name="accelerator_view"></a><a name="dtor"></a>~ accelerator_view

Accelerator_view nesnesini yok eder.

### <a name="syntax"></a>Sözdizimi

```cpp
~accelerator_view();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
