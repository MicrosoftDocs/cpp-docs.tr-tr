---
title: overwrite_buffer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
ms.openlocfilehash: 5b222170112f43ae9700054f42e1368545612d00
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138794"
---
# <a name="overwrite_buffer-class"></a>overwrite_buffer Sınıfı

`overwrite_buffer` mesajlaşma bloğu, aynı anda tek bir iletiyi depolayan çok hedefli, çok kaynaklı ve sıralı `propagator_block`. Yeni iletiler üzerine yazılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Arabellek tarafından saklanan ve yayılan iletilerin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[overwrite_buffer](#ctor)|Fazla Yüklendi. `overwrite_buffer` mesajlaşma bloğu oluşturur.|
|[~ overwrite_buffer yok edici](#dtor)|`overwrite_buffer` mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[has_value](#has_value)|Bu `overwrite_buffer` mesajlaşma bloğunun henüz bir değere sahip olup olmadığını denetler.|
|[value](#value)|`overwrite_buffer` mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne yönelik bir başvuru alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu `overwrite_buffer` mesajlaşma bloğu tarafından sunulan ve iletiyi çağırana bir kopyasını döndüren bir iletiyi kabul eder.|
|[consume_message](#consume_message)|Daha önce `overwrite_buffer` mesajlaşma bloğunun sunduğu ve hedef tarafından ayrılmış bir ileti tüketir ve bu ileti, çağırana bir kopyasını döndürür.|
|[link_target_notification](#link_target_notification)|Yeni bir hedefin bu `overwrite_buffer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `overwrite_buffer` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.|
|[propagate_to_any_targets](#propagate_to_any_targets)|`message _PMessage` bu `overwrite_buffer` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu `overwrite_buffer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır. (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu olarak bir `ISource` bloğundan bu `overwrite_buffer` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.|
|[supports_anonymous_source](#supports_anonymous_source)|Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için `supports_anonymous_source` yöntemini geçersiz kılar. ( [IComparer:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

`overwrite_buffer` bir mesajlaşma bloğu, depolanan iletinin kopyalarını hedeflerine her birine yayar.

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept_message"></a>accept_message

Bu `overwrite_buffer` mesajlaşma bloğu tarafından sunulan ve iletiyi çağırana bir kopyasını döndüren bir iletiyi kabul eder.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`overwrite_buffer` mesajlaşma bloğu, şu anda tutulan iletinin sahipliğini aktarmak yerine, iletinin kopyalarını hedeflerine döndürür.

## <a name="consume_message"></a>consume_message

Daha önce `overwrite_buffer` mesajlaşma bloğunun sunduğu ve hedef tarafından ayrılmış bir ileti tüketir ve bu ileti, çağırana bir kopyasını döndürür.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Tüketilmekte olan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`benzerdir, ancak her zaman bir `reserve`çağrısıyla yapılır.

## <a name="has_value"></a>has_value

Bu `overwrite_buffer` mesajlaşma bloğunun henüz bir değere sahip olup olmadığını denetler.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

blok bir değer aldıysa **true** , aksi takdirde **false** .

## <a name="link_target_notification"></a>link_target_notification

Yeni bir hedefin bu `overwrite_buffer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="dtor"></a>~ overwrite_buffer

`overwrite_buffer` mesajlaşma bloğunu yok eder.

```cpp
~overwrite_buffer();
```

## <a name="ctor"></a>overwrite_buffer

`overwrite_buffer` mesajlaşma bloğu oluşturur.

```cpp
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Filter*<br/>
Sunulan iletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`overwrite_buffer` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`overwrite_buffer` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Tür `filter_method`, bu `overwrite_buffer` mesajlaşma bloğu tarafından sunulan ve önerilen bir iletiyi kabul edip etmediğini belirlemede çağrılan, imza `bool (T const &)` olan bir functor.

## <a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `overwrite_buffer` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

`message _PMessage` bu `overwrite_buffer` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.

```cpp
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bu `overwrite_buffer` sahipliğini aldığı `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yeni kabul edilen ileti `_PMessage``overwrite_buffer` geçerli iletinin üzerine yazar.

## <a name="send_message"></a>send_message

Zaman uyumlu olarak bir `ISource` bloğundan bu `overwrite_buffer` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için `supports_anonymous_source` yöntemini geçersiz kılar.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**çünkü blok** sunulan iletileri ertelemez.

## <a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

## <a name="reserve_message"></a>reserve_message

Daha önce bu `overwrite_buffer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

`reserve` çağrıldıktan sonra, **doğru**döndürürse, iletinin sahipliğini almak ya da serbest bırakmak için `consume` veya `release` çağrılmalıdır.

## <a name="resume_propagation"></a>resume_propagation

Bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation();
```

## <a name="value"></a>deeri

`overwrite_buffer` mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne yönelik bir başvuru alır.

```cpp
T value();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda depolanmış iletinin yükü.

### <a name="remarks"></a>Açıklamalar

`overwrite_buffer` depolanan değer bu yöntemin döndürdüğü hemen sonra değişebilir. Bu yöntem, şu anda `overwrite_buffer`bir ileti depolanmıyorsa bir ileti gelene kadar bekler.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[unbounded_buffer Sınıfı](unbounded-buffer-class.md)<br/>
[single_assignment Sınıfı](single-assignment-class.md)
