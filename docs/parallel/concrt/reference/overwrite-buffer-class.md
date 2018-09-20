---
title: overwrite_buffer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 622f439355c9d8b059ac48f0bdc1f57c1b32e5eb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387672"
---
# <a name="overwritebuffer-class"></a>overwrite_buffer Sınıfı

Bir `overwrite_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` özellikli bir kerede tek bir ileti depolama. Yeni iletileri, daha önce tutulan olanları üzerine yazın.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
İletileri depolanır ve arabellek tarafından yayılan yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[overwrite_buffer](#ctor)|Fazla Yüklendi. Oluşturur bir `overwrite_buffer` ileti bloğu.|
|[~ overwrite_buffer yok Edicisi](#dtor)|Yok eder `overwrite_buffer` ileti bloğu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[has_value](#has_value)|Denetler olup bu `overwrite_buffer` değerine henüz sahip ileti bloğu.|
|[value](#value)|Depolanmakta olan iletinin geçerli yükü bir başvuru edinir `overwrite_buffer` ileti bloğu.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `overwrite_buffer` çağırana iletinin bir kopyasını döndüren ileti bloğu.|
|[consume_message](#consume_message)|Daha önce tarafından sunulan iletiyi tüketir `overwrite_buffer` blok Mesajlaşma ve iletinin bir kopyasını döndüren çağırana hedef tarafından ayrılmış.|
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `overwrite_buffer` ileti bloğu.|
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `overwrite_buffer` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Basamak `message _PMessage` bu `overwrite_buffer` blok Mesajlaşma ve tüm bağlı hedeflerin sunar.|
|[release_message](#release_message)|Bir önceki ileti ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `overwrite_buffer` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Rezervasyon piyasaya sürüldükten sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `overwrite_buffer` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmalar `supports_anonymous_source` bu blok için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntemi. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Açıklamalar

Bir `overwrite_buffer` hedeflerinin her biri için saklı iletisini kopyalarını ileti bloğu yayar.

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

[Itarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept_message"></a> accept_message

Bu tarafından sunulan bir iletiyi kabul `overwrite_buffer` çağırana iletinin bir kopyasını döndüren ileti bloğu.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

`overwrite_buffer` Şu anda tutulan iletinin sahipliğini aktarma yerine bloğu döndürür hedeflerine iletinin kopyasını Mesajlaşma.

##  <a name="consume_message"></a> consume_message

Daha önce tarafından sunulan iletiyi tüketir `overwrite_buffer` blok Mesajlaşma ve iletinin bir kopyasını döndüren çağırana hedef tarafından ayrılmış.

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

Denetler olup bu `overwrite_buffer` değerine henüz sahip ileti bloğu.

```
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

`true` blok bir değer aldıysa `false` Aksi takdirde.

##  <a name="link_target_notification"></a> link_target_notification

Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `overwrite_buffer` ileti bloğu.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefi için bir işaretçi.

##  <a name="dtor"></a> ~ overwrite_buffer

Yok eder `overwrite_buffer` ileti bloğu.

```
~overwrite_buffer();
```

##  <a name="ctor"></a> overwrite_buffer

Oluşturur bir `overwrite_buffer` ileti bloğu.

```
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

*_Filtreyi*<br/>
Sunulan iletileri kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `overwrite_buffer` ileti bloğu zamanlandı.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `overwrite_buffer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.

Türü `filter_method` bir functor imzaya sahip olduğu `bool (T const &)` , çağrıldığında bu `overwrite_buffer` sunulan bir iletiye kabul etmelidir olup olmadığını belirlemek için ileti bloğu.

##  <a name="propagate_message"></a> propagate_message

Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `overwrite_buffer` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.

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

Basamak `message _PMessage` bu `overwrite_buffer` blok Mesajlaşma ve tüm bağlı hedeflerin sunar.

```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi bir `message` nesne bu `overwrite_buffer` sahipliğini sürdü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem geçerli iletiye üzerine yazar `overwrite_buffer` yeni kabul edilen iletisiyle `_PMessage`.

##  <a name="send_message"></a> send_message

Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `overwrite_buffer` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.

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

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

Geçersiz kılmalar `supports_anonymous_source` bu blok için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntemi.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

`true` blok, sunulan ileti erteleme değil çünkü.

##  <a name="release_message"></a> release_message

Bir önceki ileti ayırma serbest bırakır.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

##  <a name="reserve_message"></a> reserve_message

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `overwrite_buffer` ileti bloğu.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Ayrılan nesne.

### <a name="return-value"></a>Dönüş Değeri

`true` iletinin başarıyla ayrıldı, `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sonra `reserve` çağrılır, döndürürse `true`, ya da `consume` veya `release` alın veya iletinin sahipliğini serbest bırakmak için çağrılmalıdır.

##  <a name="resume_propagation"></a> resume_propagation

Rezervasyon piyasaya sürüldükten sonra yayma sürdürür.

```
virtual void resume_propagation();
```

##  <a name="value"></a> Değer

Depolanmakta olan iletinin geçerli yükü bir başvuru edinir `overwrite_buffer` ileti bloğu.

```
T value();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda saklı iletinin yükü.

### <a name="remarks"></a>Açıklamalar

Depolanan değere `overwrite_buffer` hemen bu yöntemin dönüşünün ardından değiştirebilirsiniz. Bu yöntem, ileti içinde depolanıyorsa, bir ileti gelene kadar bekler `overwrite_buffer`.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[unbounded_buffer sınıfı](unbounded-buffer-class.md)<br/>
[single_assignment Sınıfı](single-assignment-class.md)
