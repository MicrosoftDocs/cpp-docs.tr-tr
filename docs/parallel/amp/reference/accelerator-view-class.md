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
ms.openlocfilehash: 4075051ec07fc1331d815534a715c0411160fe14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405644"
---
# <a name="acceleratorview-class"></a>accelerator_view Sınıfı

C++ AMP paralel Veri Hızlandırıcı üzerinde bir sanal cihaz soyutlamayı temsil eder.

### <a name="syntax"></a>Sözdizimi

```
class accelerator_view;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[accelerator_view Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `accelerator_view` sınıfı.|
|[~ accelerator_view yok Edicisi](#dtor)|Yok eder `accelerator_view` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[create_marker](#create_marker)|Şu ana kadar için verilmiş tüm komutların tamamlanmasını izlemek için bir gelecek döndürür `accelerator_view` nesne.|
|[Temizleme](#flush)|Tüm bekleyen komutları kuyruğa gönderen `accelerator_view` hızlandırıcıya yürütülmesi için nesne.|
|[get_accelerator](#get_accelerator)|Döndürür `accelerator` nesnesi `accelerator_view` nesne.|
|[get_is_auto_selection](#get_is_auto_selection)|Çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri döndürür, `accelerator_view` nesnesi bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[get_is_debug](#get_is_debug)|Belirten bir Boole değeri döndürür olmadığını `accelerator_view` nesne ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.|
|[get_queuing_mode](#get_queuing_mode)|Sıralama modunu döndürür `accelerator_view` nesne.|
|[get_version](#get_version)|Sürümünü döndürür `accelerator_view`.|
|[bekleme](#wait)|Verilmiş tüm komutların bekler `accelerator_view` tamamlamak için nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator!=](#operator_neq)|Bu karşılaştırır `accelerator_view` döndürür ve başka nesnesi **false** aynı; olmaları durumunda döndürür, aksi takdirde, **true**.|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `accelerator_view` bu nesne içine.|
|[operator==](#operator_eq_eq)|Bu karşılaştırır `accelerator_view` döndürür ve başka nesnesi **true** aynı; olmaları durumunda döndürür, aksi takdirde, **false**.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Hızlandırıcı](#accelerator)|Alır `accelerator` nesnesi `accelerator_view` nesne.|
|[is_auto_selection](#is_auto_selection)|Çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri alır, `accelerator_view` nesnesi bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[is_debug](#is_debug)|Gösteren bir Boole değeri alır olmadığını `accelerator_view` nesne ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.|
|[queuing_mode](#queuing_mode)|Kuyruklama modunu alır `accelerator_view` nesne.|
|[version](#version)|Hızlandırıcının sürümünü alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`accelerator_view`

### <a name="remarks"></a>Açıklamalar

Bir `accelerator_view` nesnesi, bir hızlandırıcının mantıksal, ayrık görünümünü temsil eder. Bir tek bir fiziksel hesaplama cihazının birden çok mantıksal, yalıtılmış olabilir `accelerator_view` nesneleri. Her hızlandırıcının varsayılan sahip `accelerator_view` nesne. Ek `accelerator_view` nesneleri oluşturulabilir.

Fiziksel cihazlar, çok sayıda istemci iş parçacıkları arasında paylaşılabilir. İstemci iş parçacıklarını işbirliği ile kullanabileceğiniz aynı `accelerator_view` Hızlandırıcı ya da her istemci nesnesi bağımsız aracılığıyla bir hesaplama cihazı ile iletişim kurabilir `accelerator_view` diğer istemci iş parçacıklarından yalıtımı için nesne.

Bir `accelerator_view` nesne iki birine sahip olabilir [queuing_mode numaralandırması](concurrency-namespace-enums-amp.md#queuing_mode) durumları. Sıralama modu ise `immediate`, gibi komutlar `copy` ve `parallel_for_each` bunlar çağırana dönmez ilgili Hızlandırıcı cihaza gönderilir. Sıralama modu ise `deferred`, tür komutlar üzerinde karşılık gelen bir komut kuyruğuna eklenirler `accelerator_view` nesne. Komutları çağırılana kadar cihaza `flush()` çağrılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** Eşzamanlılık

## <a name="accelerator"></a> Hızlandırıcı

Accelerator_view nesne için Hızlandırıcı nesnesini alır.

### <a name="syntax"></a>Sözdizimi

```
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="ctor"></a> accelerator_view

Mevcut bir kopyalayarak accelerator_view sınıfının yeni bir örneğini başlatır `accelerator_view` nesne.

### <a name="syntax"></a>Sözdizimi

```
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
`accelerator_view` Kopyalanacak nesne.

## <a name="createmarker"></a>create_marker

Şu ana kadar için verilmiş tüm komutların tamamlanmasını izlemek için bir gelecek döndürür `accelerator_view` nesne.

### <a name="syntax"></a>Sözdizimi

```
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Dönüş Değeri

Şu ana kadar için verilmiş tüm komutların tamamlanmasını izlemek için bir gelecek `accelerator_view` nesne.

## <a name="flush"></a>flush

Tüm bekleyen komutları hızlandırıcıya yürütülmesi için accelerator_view nesneye kuyruğa gönderir.

### <a name="syntax"></a>Sözdizimi

```
void flush();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür `void`.

## <a name="getaccelerator"></a>get_accelerator

Hızlandırıcı görünümü nesnesindeki için Hızlandırıcı nesnesini döndürür.
### <a name="syntax"></a>Sözdizimi

```
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hızlandırıcı görünümü nesnesindeki için Hızlandırıcı nesnesi.

## <a name="getisautoselection"></a>get_is_auto_selection

Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri döndürür bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Sözdizimi

```
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** çalışma zamanı otomatik olarak uygun bir Hızlandırıcı; seçer, aksi takdirde, **false**.

## <a name="getisdebug"></a>get_is_debug

Hızlandırıcı görünümü nesnesindeki ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip olup olmadığını gösteren bir Boole değeri döndürür.

### <a name="syntax"></a>Sözdizimi

```
bool get_is_debug() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirten Boolean bir değer olup olmadığını `accelerator_view` nesne ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip.

## <a name="getqueuingmode"></a>get_queuing_mode

Accelerator_view nesnesinin sıralama modunu döndürür.

### <a name="syntax"></a>Sözdizimi

```
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kuyruklama modunu `accelerator_view` nesne.

## <a name="getversion"></a>get_version

Accelerator_view sürümünü döndürür.

### <a name="syntax"></a>Sözdizimi

```
unsigned int get_version() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sürümü `accelerator_view`.

## <a name="isautoselection"></a>is_auto_selection

Accelerator_view geçirildiğinde çalışma zamanı otomatik olarak uygun bir Hızlandırıcı seçip seçmediğini gösteren bir Boole değeri alır bir [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Sözdizimi

```
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="isdebug"></a>is_debug

Hızlandırıcı görünümü nesnesindeki ayrıntılı hata raporlama için etkinleştirilen DEBUG katmanına sahip olup olmadığını gösteren bir Boole değeri alır.

### <a name="syntax"></a>Sözdizimi

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator_neq"></a> işleç! =

Bu Hızlandırıcı görünümü nesnesindeki başka ile karşılaştırır ve döndürür **false** aynı; olmaları durumunda döndürür, aksi takdirde, **true**.

### <a name="syntax"></a>Sözdizimi

```
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
`accelerator_view` İle Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**false** ise iki nesnenin aynı; Aksi takdirde, **true**.

## <a name="operator_eq"></a> işleç =

Belirtilen Hızlandırıcı görünümü nesnesindeki içeriği bunun kopyalar.

### <a name="syntax"></a>Sözdizimi

```
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
`accelerator_view` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilmiş başvuru `accelerator_view` nesne.

## <a name="operator_eq_eq"></a> işleç ==

Bu Hızlandırıcı görünümü nesnesindeki başka ile karşılaştırır ve döndürür **true** aynı; olmaları durumunda döndürür, aksi takdirde, **false**.

### <a name="syntax"></a>Sözdizimi

```
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
`accelerator_view` İle Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ise iki nesnenin aynı; Aksi takdirde, **false**.

## <a name="queuingmode"></a>queuing_mode

Sıralama modu için accelerator_view nesnesi alır.

### <a name="syntax"></a>Sözdizimi

```
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>sürüm

Accelerator_view sürümünü alır.

### <a name="syntax"></a>Sözdizimi

```
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>bekleme

Tamamlanması için Hızlandırıcı görünümü nesnesindeki gönderilen tüm komutlar için bekler.

### <a name="syntax"></a>Sözdizimi

```
void wait();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür `void`.

### <a name="remarks"></a>Açıklamalar

Varsa [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) olduğu `immediate`, engellemeden bu yöntem hemen döner.

##  <a name="dtor"></a> ~ accelerator_view

Accelerator_view nesnesini yok eder.

### <a name="syntax"></a>Sözdizimi

```
~accelerator_view();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
