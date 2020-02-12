---
title: dönüştürücü Sınıfı
ms.date: 11/04/2016
f1_keywords:
- transformer
- AGENTS/concurrency::transformer
- AGENTS/concurrency::transformer::transformer
- AGENTS/concurrency::transformer::accept_message
- AGENTS/concurrency::transformer::consume_message
- AGENTS/concurrency::transformer::link_target_notification
- AGENTS/concurrency::transformer::propagate_message
- AGENTS/concurrency::transformer::propagate_to_any_targets
- AGENTS/concurrency::transformer::release_message
- AGENTS/concurrency::transformer::reserve_message
- AGENTS/concurrency::transformer::resume_propagation
- AGENTS/concurrency::transformer::send_message
- AGENTS/concurrency::transformer::supports_anonymous_source
helpviewer_keywords:
- transformer class
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
ms.openlocfilehash: 75c7697087b8b3ad8ff15ae4d08f2b4701aaa36a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142363"
---
# <a name="transformer-class"></a>dönüştürücü Sınıfı

`transformer` mesajlaşma bloğu, tek bir türde iletileri kabul edebilecek ve farklı bir türden sınırsız sayıda ileti saklayabilen tek hedefli, çok kaynaklı ve sıralı `propagator_block`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```

### <a name="parameters"></a>Parametreler

*_Input*<br/>
Arabellek tarafından kabul edilen iletilerin yük türü.

*_Output*<br/>
Arabellek tarafından saklanan ve yayılan iletilerin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[dönüştürücü](#ctor)|Fazla Yüklendi. `transformer` mesajlaşma bloğu oluşturur.|
|[~ Transformatör yıkıcısı](#dtor)|`transformer` mesajlaşma bloğunu yok eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu `transformer` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[consume_message](#consume_message)|, `transformer` tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve sahipliği çağırana aktarmıştır.|
|[link_target_notification](#link_target_notification)|Yeni bir hedefin bu `transformer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `transformer` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Giriş iletilerinde transformatör işlevini yürütür.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu `transformer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır. (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu olarak bir `ISource` bloğundan bu `transformer` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.|
|[supports_anonymous_source](#supports_anonymous_source)|Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için `supports_anonymous_source` yöntemini geçersiz kılar. ( [IComparer:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`transformer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept_message"></a>accept_message

Bu `transformer` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

## <a name="consume_message"></a>consume_message

, `transformer` tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Tüketilmekte olan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`benzerdir, ancak her zaman bir `reserve`çağrısıyla yapılır.

## <a name="link_target_notification"></a>link_target_notification

Yeni bir hedefin bu `transformer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```

## <a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `transformer` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

Giriş iletilerinde transformatör işlevini yürütür.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
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

Daha önce bu `transformer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

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

Zaman uyumlu olarak bir `ISource` bloğundan bu `transformer` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
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

## <a name="ctor"></a>dönüştürücü

`transformer` mesajlaşma bloğu oluşturur.

```cpp
transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Func*<br/>
Kabul edilen her ileti için çağrılacak bir işlev.

*_PTarget*<br/>
Transformatör ile bağlantı için hedef blok işaretçisi.

*_Filter*<br/>
Sunulan iletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`transformer` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`transformer` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Tür `_Transform_method`, bu `transformer` mesajlaşma bloğu tarafından bir iletiyi işlemek için çağrılan imza `_Output (_Input const &)` olan bir functor.

Tür `filter_method`, bu `transformer` mesajlaşma bloğu tarafından sunulan ve önerilen bir iletiyi kabul edip etmediğini belirlemede çağrılan, imza `bool (_Input const &)` olan bir functor.

## <a name="dtor"></a>~ Transformatör

`transformer` mesajlaşma bloğunu yok eder.

```cpp
~transformer();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[call Sınıfı](call-class.md)
