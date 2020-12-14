---
description: 'Hakkında daha fazla bilgi edinin: single_assignment sınıfı'
title: single_assignment Sınıfı
ms.date: 11/04/2016
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
ms.openlocfilehash: d01426843f2e9fe1106f7cb68c103c392cdf1ebd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188670"
---
# <a name="single_assignment-class"></a>single_assignment Sınıfı

Bir `single_assignment` mesajlaşma bloğu, `propagator_block` tek bir kez yazılabilir bir çoklu kaynak olan çok kaynaklı, çok kaynaklı, sıralı bir `message` .

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Arabellek tarafından depolanan ve yayılan iletinin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[single_assignment](#ctor)|Fazla Yüklendi. `single_assignment`İleti bloğu oluşturur.|
|[~ single_assignment yok edici](#dtor)|`single_assignment`Mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[has_value](#has_value)|Bu `single_assignment` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.|
|[değer](#value)|Mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne bir başvuru alır `single_assignment` .|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `single_assignment` ve iletinin bir kopyasını çağırana döndürür.|
|[consume_message](#consume_message)|, Hedef tarafından daha önce sunulan ve ayrılmış bir ileti tüketir `single_assignment` ve bu ileti, çağırana bir kopyasını döndürür.|
|[link_target_notification](#link_target_notification)|Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `single_assignment` .|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `single_assignment` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[propagate_to_any_targets](#propagate_to_any_targets)|`message _PMessage`Bu `single_assignment` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `single_assignment` . (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `single_assignment` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

İleti `single_assignment` bloğu, iletinin kopyalarını her hedefe yayar.

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept_message"></a><a name="accept_message"></a> accept_message

Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `single_assignment` ve iletinin bir kopyasını çağırana döndürür.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İleti `single_assignment` bloğu, şu anda tutulan iletinin sahipliğini aktarmak yerine, iletinin kopyalarını hedeflerine döndürür.

## <a name="consume_message"></a><a name="consume_message"></a> consume_message

, Hedef tarafından daha önce sunulan ve ayrılmış bir ileti tüketir `single_assignment` ve bu ileti, çağırana bir kopyasını döndürür.

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

Bu `single_assignment` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** blok bir değer aldıysa, **`false`** tersi durumda.

## <a name="link_target_notification"></a><a name="link_target_notification"></a> link_target_notification

Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `single_assignment` .

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `single_assignment` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

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

`message` `_PMessage` Bu `single_assignment` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message`Bu `single_assignment` mesajlaşma bloğunun sahipliğini aldığı bir işaretçi.

## <a name="release_message"></a><a name="release_message"></a> release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

## <a name="reserve_message"></a><a name="reserve_message"></a> reserve_message

Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `single_assignment` .

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

## <a name="send_message"></a><a name="send_message"></a> send_message

Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `single_assignment` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

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

## <a name="single_assignment"></a><a name="ctor"></a> single_assignment

`single_assignment`İleti bloğu oluşturur.

```cpp
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Filter*<br/>
Sunulan iletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`Scheduler` `single_assignment` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_PScheduleGroup*<br/>
`ScheduleGroup` `single_assignment` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_PScheduler` `_PScheduleGroup` .

Tür, `filter_method` `bool (T const &)` Bu `single_assignment` mesajlaşma bloğu tarafından önerilen bir iletiyi kabul edip etmediğini tespit etmek için çağrılan imzaya sahip bir functor.

## <a name="single_assignment"></a><a name="dtor"></a> ~ single_assignment

`single_assignment`Mesajlaşma bloğunu yok eder.

```cpp
~single_assignment();
```

## <a name="value"></a><a name="value"></a> deeri

Mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne bir başvuru alır `single_assignment` .

```cpp
T const& value();
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan iletinin yükü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, mesajlaşma bloğunda Şu anda bir ileti depolanmıyorsa bir ileti gelene kadar bekler `single_assignment` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[overwrite_buffer sınıfı](overwrite-buffer-class.md)<br/>
[unbounded_buffer sınıfı](unbounded-buffer-class.md)
