---
description: 'Hakkında daha fazla bilgi edinin: overwrite_buffer sınıfı'
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
ms.openlocfilehash: 20acc133a988c145546e680acb394f0cb69307f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271401"
---
# <a name="overwrite_buffer-class"></a>overwrite_buffer Sınıfı

`overwrite_buffer`İleti bloğu, `propagator_block` aynı anda tek bir ileti depolayan çok hedefli, çok kaynaklı ve sıralı bir kaynaktır. Yeni iletiler üzerine yazılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Arabellek tarafından saklanan ve yayılan iletilerin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[overwrite_buffer](#ctor)|Fazla Yüklendi. `overwrite_buffer`İleti bloğu oluşturur.|
|[~ overwrite_buffer yok edici](#dtor)|`overwrite_buffer`Mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[has_value](#has_value)|Bu `overwrite_buffer` mesajlaşma bloğunun henüz bir değere sahip olup olmadığını denetler.|
|[değer](#value)|Mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne bir başvuru alır `overwrite_buffer` .|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `overwrite_buffer` ve iletinin bir kopyasını çağırana döndürür.|
|[consume_message](#consume_message)|İleti bloğu tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu ileti, `overwrite_buffer` çağırana bir kopyasını döndürür.|
|[link_target_notification](#link_target_notification)|Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `overwrite_buffer` .|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `overwrite_buffer` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[propagate_to_any_targets](#propagate_to_any_targets)|`message _PMessage`Bu `overwrite_buffer` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `overwrite_buffer` . (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `overwrite_buffer` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source`Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için yöntemini geçersiz kılar. ( [IComparer:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

Bir `overwrite_buffer` ileti bloğu, saklı iletisinin kopyalarını her hedefine yayar.

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

## <a name="accept_message"></a><a name="accept_message"></a> accept_message

Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `overwrite_buffer` ve iletinin bir kopyasını çağırana döndürür.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İleti `overwrite_buffer` bloğu, şu anda tutulan iletinin sahipliğini aktarmak yerine, iletinin kopyalarını hedeflerine döndürür.

## <a name="consume_message"></a><a name="consume_message"></a> consume_message

İleti bloğu tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu ileti, `overwrite_buffer` çağırana bir kopyasını döndürür.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Tüketilmekte olan nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`,, Ancak, ' a benzer ancak her zaman öğesine yapılan bir çağrıdır `reserve` .

## <a name="has_value"></a><a name="has_value"></a> has_value

Bu `overwrite_buffer` mesajlaşma bloğunun henüz bir değere sahip olup olmadığını denetler.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** blok bir değer aldıysa, **`false`** tersi durumda.

## <a name="link_target_notification"></a><a name="link_target_notification"></a> link_target_notification

Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `overwrite_buffer` .

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="overwrite_buffer"></a><a name="dtor"></a> ~ overwrite_buffer

`overwrite_buffer`Mesajlaşma bloğunu yok eder.

```cpp
~overwrite_buffer();
```

## <a name="overwrite_buffer"></a><a name="ctor"></a> overwrite_buffer

`overwrite_buffer`İleti bloğu oluşturur.

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
`Scheduler` `overwrite_buffer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_PScheduleGroup*<br/>
`ScheduleGroup` `overwrite_buffer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_PScheduler` `_PScheduleGroup` .

Tür, `filter_method` `bool (T const &)` Bu `overwrite_buffer` mesajlaşma bloğu tarafından önerilen bir iletiyi kabul edip etmediğini tespit etmek için çağrılan imzaya sahip bir functor.

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `overwrite_buffer` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a> propagate_to_any_targets

`message _PMessage`Bu `overwrite_buffer` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.

```cpp
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message`Öğesinin sahipliğini aldığı nesneye yönelik bir işaretçi `overwrite_buffer` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `overwrite_buffer` yeni kabul edilen iletiyle içindeki geçerli iletinin üzerine yazar `_PMessage` .

## <a name="send_message"></a><a name="send_message"></a> send_message

Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `overwrite_buffer` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a> supports_anonymous_source

`supports_anonymous_source`Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için yöntemini geçersiz kılar.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** bloğu sunulan iletileri ertelemez.

## <a name="release_message"></a><a name="release_message"></a> release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

## <a name="reserve_message"></a><a name="reserve_message"></a> reserve_message

Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `overwrite_buffer` .

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Ayrılan nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** ileti başarıyla ayrıldıysa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan sonra `reserve` , döndürürse, **`true`** `consume` `release` iletinin sahipliğini almak ya da serbest bırakmak için ya da çağrılması gerekir.

## <a name="resume_propagation"></a><a name="resume_propagation"></a> resume_propagation

Bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation();
```

## <a name="value"></a><a name="value"></a> deeri

Mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne bir başvuru alır `overwrite_buffer` .

```cpp
T value();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda depolanmış iletinin yükü.

### <a name="remarks"></a>Açıklamalar

İçinde depolanan değer `overwrite_buffer` Bu yöntem geri döndüğünde hemen sonra değişebilir. Bu yöntem, üzerinde hiçbir ileti depolanmıyorsa bir ileti gelene kadar bekler `overwrite_buffer` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[unbounded_buffer sınıfı](unbounded-buffer-class.md)<br/>
[single_assignment sınıfı](single-assignment-class.md)
