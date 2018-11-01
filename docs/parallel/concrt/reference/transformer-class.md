---
title: transformer Sınıfı
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
ms.openlocfilehash: cc35a4e2de2b29bb6d437dfcbf48ef361fefdfa3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618289"
---
# <a name="transformer-class"></a>transformer Sınıfı

A `transformer` ileti bloğu tek-hedef birden çok kaynak, sıralı `propagator_block` bir türden iletileri kabul edebilir ve sınırsız sayıda farklı türden iletileri depolayabilen özelliğine sahiptir.

## <a name="syntax"></a>Sözdizimi

```
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```

#### <a name="parameters"></a>Parametreler

*_Giriş*<br/>
Arabellek kabul iletileri yük türü.

*Çı_kış*<br/>
İletileri depolanır ve çıkış arabelleği tarafından yayılan yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Transformer](#ctor)|Fazla Yüklendi. Oluşturur bir `transformer` ileti bloğu.|
|[~ transformer yok Edicisi](#dtor)|Yok eder `transformer` ileti bloğu.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `transformer` çağırana sahipliğini aktarma ileti bloğu.|
|[consume_message](#consume_message)|Daha önce tarafından sunulan iletiyi tüketir `transformer` ve çağırana sahipliğini aktarma hedefi tarafından ayrılmış.|
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `transformer` ileti bloğu.|
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `transformer` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Transformer işlevi, giriş iletileri yürütür.|
|[release_message](#release_message)|Bir önceki ileti ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `transformer` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Rezervasyon piyasaya sürüldükten sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `transformer` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmalar `supports_anonymous_source` bu blok için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntemi. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

[Itarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`transformer`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept_message"></a> accept_message

Bu tarafından sunulan bir iletiyi kabul `transformer` çağırana sahipliğini aktarma ileti bloğu.

```
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

##  <a name="consume_message"></a> consume_message

Daha önce tarafından sunulan iletiyi tüketir `transformer` ve çağırana sahipliğini aktarma hedefi tarafından ayrılmış.

```
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

Benzer şekilde `accept`, ancak her zaman bir çağrı tarafından öncesinde `reserve`.

##  <a name="link_target_notification"></a> link_target_notification

Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `transformer` ileti bloğu.

```
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```

##  <a name="propagate_message"></a> propagate_message

Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `transformer` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Transformer işlevi, giriş iletileri yürütür.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```

##  <a name="release_message"></a> release_message

Bir önceki ileti ayırma serbest bırakır.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

##  <a name="reserve_message"></a> reserve_message

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `transformer` ileti bloğu.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Ayrılan nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ileti başarıyla ayrıldı, **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sonra `reserve` çağrılır, döndürürse **true**, ya da `consume` veya `release` alın veya iletinin sahipliğini serbest bırakmak için çağrılmalıdır.

##  <a name="resume_propagation"></a> resume_propagation

Rezervasyon piyasaya sürüldükten sonra yayma sürdürür.

```
virtual void resume_propagation();
```

##  <a name="send_message"></a> send_message

Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `transformer` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

Geçersiz kılmalar `supports_anonymous_source` bu blok için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntemi.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** iletileri blok değil ertelemek için sunulan.

##  <a name="ctor"></a> Transformer

Oluşturur bir `transformer` ileti bloğu.

```
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
Kabul edilen her ileti için çağrılacak işlev.

*_PTarget*<br/>
Transformer ile bağlamak için bir hedef blok için işaretçi.

*_Filtreyi*<br/>
Sunulan iletileri kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `transformer` ileti bloğu zamanlandı.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `transformer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.

Türü `_Transform_method` bir functor imzaya sahip olduğu `_Output (_Input const &)` , çağrıldığında bu `transformer` bir iletiyi, ileti bloğu.

Türü `filter_method` bir functor imzaya sahip olduğu `bool (_Input const &)` , çağrıldığında bu `transformer` sunulan bir iletiye kabul etmelidir olup olmadığını belirlemek için ileti bloğu.

##  <a name="dtor"></a> ~ transformer

Yok eder `transformer` ileti bloğu.

```
~transformer();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[call Sınıfı](call-class.md)
