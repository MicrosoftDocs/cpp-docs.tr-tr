---
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
ms.openlocfilehash: 0d302f4f7f85737d9c3b2368e3ae04d88bc1a370
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142735"
---
# <a name="single_assignment-class"></a>single_assignment Sınıfı

`single_assignment` mesajlaşma bloğu, tek bir kez yazılabilir `message`saklayabilen çok hedefli, çok kaynaklı ve sıralı `propagator_block`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Arabellek tarafından depolanan ve yayılan iletinin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[single_assignment](#ctor)|Fazla Yüklendi. `single_assignment` mesajlaşma bloğu oluşturur.|
|[~ single_assignment yok edici](#dtor)|`single_assignment` mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[has_value](#has_value)|Bu `single_assignment` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.|
|[value](#value)|`single_assignment` mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne yönelik bir başvuru alır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu `single_assignment` mesajlaşma bloğu tarafından sunulan ve iletiyi çağırana bir kopyasını döndüren bir iletiyi kabul eder.|
|[consume_message](#consume_message)|, `single_assignment` tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu ileti, çağırana bir kopyasını döndürür.|
|[link_target_notification](#link_target_notification)|Yeni bir hedefin bu `single_assignment` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `single_assignment` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.|
|[propagate_to_any_targets](#propagate_to_any_targets)|`message _PMessage` bu `single_assignment` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu `single_assignment` mesajlaşma bloğunun sunduğu bir iletiyi ayırır. (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu olarak bir `ISource` bloğundan bu `single_assignment` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

`single_assignment` bir ileti bloğu, iletinin kopyalarını her hedefe yayar.

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

## <a name="accept_message"></a>accept_message

Bu `single_assignment` mesajlaşma bloğu tarafından sunulan ve iletiyi çağırana bir kopyasını döndüren bir iletiyi kabul eder.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`single_assignment` mesajlaşma bloğu, şu anda tutulan iletinin sahipliğini aktarmak yerine, iletinin kopyalarını hedeflerine döndürür.

## <a name="consume_message"></a>consume_message

, `single_assignment` tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu ileti, çağırana bir kopyasını döndürür.

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

Bu `single_assignment` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

blok bir değer aldıysa **true** , aksi takdirde **false** .

## <a name="link_target_notification"></a>link_target_notification

Yeni bir hedefin bu `single_assignment` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `single_assignment` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.

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

`message` `_PMessage` bu `single_assignment` mesajlaşma bloğuna koyar ve tüm bağlantılı hedeflere sunar.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bu `single_assignment` mesajlaşma bloğunun sahipliğini aldığı `message` için bir işaretçi.

## <a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

## <a name="reserve_message"></a>reserve_message

Daha önce bu `single_assignment` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

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

## <a name="send_message"></a>send_message

Zaman uyumlu olarak bir `ISource` bloğundan bu `single_assignment` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.

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

## <a name="ctor"></a>single_assignment

`single_assignment` mesajlaşma bloğu oluşturur.

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
`single_assignment` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`single_assignment` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Tür `filter_method`, bu `single_assignment` mesajlaşma bloğu tarafından sunulan ve önerilen bir iletiyi kabul edip etmediğini belirlemede çağrılan, imza `bool (T const &)` olan bir functor.

## <a name="dtor"></a>~ single_assignment

`single_assignment` mesajlaşma bloğunu yok eder.

```cpp
~single_assignment();
```

## <a name="value"></a>deeri

`single_assignment` mesajlaşma bloğunda depolanmakta olan iletinin geçerli yüküne yönelik bir başvuru alır.

```cpp
T const& value();
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan iletinin yükü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, şu anda `single_assignment` mesajlaşma bloğunda bir ileti depolanmıyorsa bir ileti gelene kadar bekler.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[overwrite_buffer Sınıfı](overwrite-buffer-class.md)<br/>
[unbounded_buffer Sınıfı](unbounded-buffer-class.md)
