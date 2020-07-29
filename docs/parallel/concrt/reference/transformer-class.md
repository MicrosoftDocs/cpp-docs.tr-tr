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
ms.openlocfilehash: adc83ab2d8268460b3a35be44f5733c8b6fa1c43
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217902"
---
# <a name="transformer-class"></a>dönüştürücü Sınıfı

Bir `transformer` mesajlaşma bloğu, tek bir `propagator_block` türden iletileri kabul edebilecek ve farklı türde sınırsız sayıda iletiyi depolayan bir tek hedeftir, birden çok kaynaktır.

## <a name="syntax"></a>Söz dizimi

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
|[dönüştürücü](#ctor)|Fazla Yüklendi. `transformer`İleti bloğu oluşturur.|
|[~ Transformatör yıkıcısı](#dtor)|`transformer`Mesajlaşma bloğunu yok eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `transformer` ve sahipliği çağırana aktarmakta.|
|[consume_message](#consume_message)|, Hedef tarafından daha önce sunulan ve ayrılmış bir ileti tüketir `transformer` ve sahipliği çağırana aktarmıştır.|
|[link_target_notification](#link_target_notification)|Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `transformer` .|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `transformer` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Giriş iletilerinde transformatör işlevini yürütür.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `transformer` . (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `transformer` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source`Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için yöntemini geçersiz kılar. ( [IComparer:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)geçersiz kılar.)|

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

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `transformer` ve sahipliği çağırana aktarmakta.

```cpp
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

, Hedef tarafından daha önce sunulan ve ayrılmış bir ileti tüketir `transformer` ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Tüketilmekte olan nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`,, Ancak, ' a benzer ancak her zaman öğesine yapılan bir çağrıdır `reserve` .

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `transformer` .

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```

## <a name="propagate_message"></a><a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `transformer` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

Giriş iletilerinde transformatör işlevini yürütür.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```

## <a name="release_message"></a><a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `transformer` .

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

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

Bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation();
```

## <a name="send_message"></a><a name="send_message"></a>send_message

Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `transformer` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a>supports_anonymous_source

`supports_anonymous_source`Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için yöntemini geçersiz kılar.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** bloğu sunulan iletileri ertelemez.

## <a name="transformer"></a><a name="ctor"></a>dönüştürücü

`transformer`İleti bloğu oluşturur.

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
`Scheduler` `transformer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_PScheduleGroup*<br/>
`ScheduleGroup` `transformer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_PScheduler` `_PScheduleGroup` .

Tür, `_Transform_method` `_Output (_Input const &)` Bu `transformer` mesajlaşma bloğu tarafından bir iletiyi işlemek için çağrılan imzaya sahip olan bir functor.

Tür, `filter_method` `bool (_Input const &)` Bu `transformer` mesajlaşma bloğu tarafından önerilen bir iletiyi kabul edip etmediğini tespit etmek için çağrılan imzaya sahip bir functor.

## <a name="transformer"></a><a name="dtor"></a>~ Transformatör

`transformer`Mesajlaşma bloğunu yok eder.

```cpp
~transformer();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Call sınıfı](call-class.md)
