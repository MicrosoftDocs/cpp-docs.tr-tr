---
title: single_assignment sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee06d9a30339a72bd7137db6f277a1eb41028d50
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163096"
---
# <a name="singleassignment-class"></a>single_assignment Sınıfı

A `single_assignment` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` özelliğine sahip tek bir depolama yazma-sonra `message`.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
İletinin yükü türünü depolanır ve arabellek yayılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[single_assignment](#ctor)|Fazla Yüklendi. Oluşturur bir `single_assignment` ileti bloğu.|
|[~ single_assignment yok Edicisi](#dtor)|Yok eder `single_assignment` ileti bloğu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[has_value](#has_value)|Denetler olup bu `single_assignment` ileti bloğu başlatıldıysa bir değerle henüz.|
|[value](#value)|Depolanmakta olan iletinin geçerli yükü bir başvuru edinir `single_assignment` ileti bloğu.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `single_assignment` çağırana iletinin bir kopyasını döndüren ileti bloğu.|
|[consume_message](#consume_message)|Daha önce tarafından sunulan iletiyi tüketir `single_assignment` ve iletinin bir kopyasını döndüren çağırana hedef tarafından ayrılmış.|
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `single_assignment` ileti bloğu.|
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `single_assignment` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Basamak `message _PMessage` bu `single_assignment` blok Mesajlaşma ve tüm bağlı hedeflerin sunar.|
|[release_message](#release_message)|Bir önceki ileti ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `single_assignment` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Rezervasyon piyasaya sürüldükten sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `single_assignment` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.|

## <a name="remarks"></a>Açıklamalar

A `single_assignment` ileti bloğu, kendi ileti her hedef için bir kopyasını yayar.

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

[Itarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept_message"></a> accept_message

Bu tarafından sunulan bir iletiyi kabul `single_assignment` çağırana iletinin bir kopyasını döndüren ileti bloğu.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

`single_assignment` Şu anda tutulan iletinin sahipliğini aktarma yerine bloğu döndürür hedeflerine iletinin kopyasını Mesajlaşma.

##  <a name="consume_message"></a> consume_message

Daha önce tarafından sunulan iletiyi tüketir `single_assignment` ve iletinin bir kopyasını döndüren çağırana hedef tarafından ayrılmış.

```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

Benzer şekilde `accept`, ancak her zaman bir çağrı tarafından öncesinde `reserve`.

##  <a name="has_value"></a> has_value

Denetler olup bu `single_assignment` ileti bloğu başlatıldıysa bir değerle henüz.

```
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** blok bir değer aldıysa **false** Aksi takdirde.

##  <a name="link_target_notification"></a> link_target_notification

Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `single_assignment` ileti bloğu.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefi için bir işaretçi.

##  <a name="propagate_message"></a> propagate_message

Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `single_assignment` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Basamak `message` `_PMessage` bu `single_assignment` blok Mesajlaşma ve tüm bağlı hedeflerin sunar.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi bir `message` bu `single_assignment` ileti bloğu sahipliğini geçen.

##  <a name="release_message"></a> release_message

Bir önceki ileti ayırma serbest bırakır.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

##  <a name="reserve_message"></a> reserve_message

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `single_assignment` ileti bloğu.

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

Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `single_assignment` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

##  <a name="ctor"></a> single_assignment

Oluşturur bir `single_assignment` ileti bloğu.

```
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

*_Filtreyi*<br/>
Sunulan iletileri kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `single_assignment` ileti bloğu zamanlandı.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `single_assignment` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.

Türü `filter_method` bir functor imzaya sahip olduğu `bool (T const &)` , çağrıldığında bu `single_assignment` sunulan bir iletiye kabul etmelidir olup olmadığını belirlemek için ileti bloğu.

##  <a name="dtor"></a> ~ single_assignment

Yok eder `single_assignment` ileti bloğu.

```
~single_assignment();
```

##  <a name="value"></a> Değer

Depolanmakta olan iletinin geçerli yükü bir başvuru edinir `single_assignment` ileti bloğu.

```
T const& value();
```

### <a name="return-value"></a>Dönüş Değeri

Saklı iletinin yükü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ileti içinde depolanıyorsa, bir ileti gelene kadar bekler `single_assignment` ileti bloğu.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[overwrite_buffer Sınıfı](overwrite-buffer-class.md)<br/>
[unbounded_buffer sınıfı](unbounded-buffer-class.md)

