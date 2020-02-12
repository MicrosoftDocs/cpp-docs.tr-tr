---
title: join Sınıfı
ms.date: 11/04/2016
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
ms.openlocfilehash: f75cf8483e7d6d65d118cc8f0ea756302d1b1d7c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139843"
---
# <a name="join-class"></a>join Sınıfı

`join` mesajlaşma bloğu, kaynaklarından her birinden `T` türündeki iletileri birleştiren tek hedef, çok kaynaklı ve sıralı `propagator_block`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Blok tarafından birleştirilen ve yayılan iletilerin yük türü.

*_Jtype*<br/>
`join` bloğunun türü, `greedy` ya da `non_greedy`

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[join](#ctor)|Fazla Yüklendi. `join` mesajlaşma bloğu oluşturur.|
|[~ JOIN yıkıcısı](#dtor)|`join` bloğunu yok eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu `join` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[consume_message](#consume_message)|Daha önce `join` mesajlaşma bloğu tarafından sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu, sahipliği çağırana aktarılarak.|
|[link_target_notification](#link_target_notification)|Yeni bir hedefin bu `join` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `join` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Her kaynaktan bir ileti yayıldığında giriş iletisi içeren bir çıkış iletisi oluşturur. Bu çıkış iletisini, hedeflerine her birine gönderir.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu `join` mesajlaşma bloğunun sunduğu bir iletiyi ayırır. (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`join`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept_message"></a>accept_message

Bu `join` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

## <a name="consume_message"></a>consume_message

Daha önce `join` mesajlaşma bloğu tarafından sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu, sahipliği çağırana aktarılarak.

```cpp
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Tüketilmekte olan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`benzerdir, ancak her zaman bir `reserve`çağrısıyla yapılır.

## <a name="ctor"></a>ayrılma

`join` mesajlaşma bloğu oluşturur.

```cpp
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_NumInputs*<br/>
Bu `join` bloğunun izin verilecek giriş sayısı.

*_Filter*<br/>
Sunulan iletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`join` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`join` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Tür `filter_method`, bu `join` mesajlaşma bloğu tarafından sunulan ve önerilen bir iletiyi kabul edip etmediğini belirlemede çağrılan, imza `bool (T const &)` olan bir functor.

## <a name="dtor"></a>~ JOIN

`join` bloğunu yok eder.

```cpp
~join();
```

## <a name="link_target_notification"></a>link_target_notification

Yeni bir hedefin bu `join` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.

```cpp
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```

## <a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `join` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.

```cpp
message_status propagate_message(
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

Her kaynaktan bir ileti yayıldığında giriş iletisi içeren bir çıkış iletisi oluşturur. Bu çıkış iletisini, hedeflerine her birine gönderir.

```cpp
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
```

## <a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

## <a name="reserve_message"></a>reserve_message

Daha önce bu `join` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

`reserve` çağrıldıktan sonra, **doğru**döndürürse, iletinin sahipliğini almak ya da serbest bırakmak için `consume` veya `release` çağrılmalıdır.

## <a name="resume_propagation"></a>resume_propagation

Bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[choice Sınıfı](choice-class.md)<br/>
[multitype_join Sınıfı](multitype-join-class.md)
