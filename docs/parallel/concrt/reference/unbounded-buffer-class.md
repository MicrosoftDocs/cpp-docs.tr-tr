---
title: unbounded_buffer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
ms.openlocfilehash: 79bab3c41df2f3cbc5b11522b394a2785e64cddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495244"
---
Bir `unbounded_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` iletilerin sınırsız sayıda depolama özelliğine sahip.

## <a name="syntax"></a>Sözdizimi

```
template<
   class             _Type
>
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;
```

#### <a name="parameters"></a>Parametreler

*_Türü*<br/>
İletileri depolanır ve arabellek tarafından yayılan yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unbounded_buffer](#ctor)|Fazla Yüklendi. Oluşturur bir `unbounded_buffer` ileti bloğu.|
|[~ unbounded_buffer yok Edicisi](#dtor)|Yok eder `unbounded_buffer` ileti bloğu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Sıradan Çıkarma](#dequeue)|Bir öğe kaldırır `unbounded_buffer` ileti bloğu.|
|[Sıraya alma](#enqueue)|Bir öğe ekleyen `unbounded_buffer` ileti bloğu.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `unbounded_buffer` çağırana sahipliğini aktarma ileti bloğu.|
|[consume_message](#consume_message)|Daha önce tarafından sunulan iletiyi tüketir `unbounded_buffer` blok Mesajlaşma ve çağırana sahipliğini aktarma hedefi tarafından ayrılmış.|
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `unbounded_buffer` ileti bloğu.|
|[process_input_messages](#process_input_messages)|Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedeflerin sağlamaya çalışır.|
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `unbounded_buffer` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[propagate_output_messages](#propagate_output_messages)|Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedeflerin sağlamaya çalışır. (Geçersiz kılmaları [source_block::propagate_output_messages](source-block-class.md#propagate_output_messages).)|
|[release_message](#release_message)|Bir önceki ileti ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `unbounded_buffer` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Rezervasyon piyasaya sürüldükten sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `unbounded_buffer` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmalar `supports_anonymous_source` bu blok için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntemi. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

[Itarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`unbounded_buffer`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept_message"></a> accept_message

Bu tarafından sunulan bir iletiyi kabul `unbounded_buffer` çağırana sahipliğini aktarma ileti bloğu.

```
virtual message<_Type> * accept_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

##  <a name="consume_message"></a> consume_message

Daha önce tarafından sunulan iletiyi tüketir `unbounded_buffer` blok Mesajlaşma ve çağırana sahipliğini aktarma hedefi tarafından ayrılmış.

```
virtual message<_Type> * consume_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

Benzer şekilde `accept`, ancak her zaman bir çağrı tarafından öncesinde `reserve`.

##  <a name="dequeue"></a> Sıradan Çıkarma

Bir öğe kaldırır `unbounded_buffer` ileti bloğu.

```
_Type dequeue();
```

### <a name="return-value"></a>Dönüş Değeri

Kaldırıldığında iletinin yükü `unbounded_buffer`.

##  <a name="enqueue"></a> Sıraya alma

Bir öğe ekleyen `unbounded_buffer` ileti bloğu.

```
bool enqueue(
   _Type const&                 _Item
);
```

### <a name="parameters"></a>Parametreler

*Öğeyi*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

**doğru** öğesi kabul edildiyse **false** Aksi takdirde.

##  <a name="link_target_notification"></a> link_target_notification

Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `unbounded_buffer` ileti bloğu.

```
virtual void link_target_notification(
   _Inout_ ITarget<_Type> *                 _PTarget
);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefi için bir işaretçi.

##  <a name="propagate_message"></a> propagate_message

Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `unbounded_buffer` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status propagate_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md#message_status) hedef iletinin yapmak karar göstergesi.

##  <a name="propagate_output_messages"></a> propagate_output_messages

Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedeflerin sağlamaya çalışır.

```
virtual void propagate_output_messages();
```

### <a name="remarks"></a>Açıklamalar

Başka bir ileti zaten bu önüne ise `unbounded_buffer`, bağlantılı hedeflere yayma daha önceki iletileri kabul veya tüketilen kadar gerçekleşmez. Birinci bağlantılı hedefine başarıyla `accept` veya `consume` ileti sahiplenir ve başka bir hedef ardından iletiyi alabilirsiniz.

##  <a name="process_input_messages"></a> process_input_messages

Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedeflerin sağlamaya çalışır.

```
virtual void process_input_messages(
   _Inout_ message<_Type> *                 _PMessage
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek iletisi için bir işaretçi.

##  <a name="release_message"></a> release_message

Bir önceki ileti ayırma serbest bırakır.

```
virtual void release_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

##  <a name="reserve_message"></a> reserve_message

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `unbounded_buffer` ileti bloğu.

```
virtual bool reserve_message(
   runtime_object_identity                 _MsgId
);
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

Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `unbounded_buffer` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status send_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md#message_status) hedef iletinin yapmak karar göstergesi.

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

Geçersiz kılmalar `supports_anonymous_source` bu blok için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntemi.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** iletileri blok değil ertelemek için sunulan.

##  <a name="ctor"></a> unbounded_buffer

Oluşturur bir `unbounded_buffer` ileti bloğu.

```
unbounded_buffer();

unbounded_buffer(
   filter_method const&                 _Filter
);

unbounded_buffer(
   Scheduler&                 _PScheduler
);

unbounded_buffer(
   Scheduler&                 _PScheduler,
   filter_method const&                 _Filter
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup,
   filter_method const&                 _Filter
);
```

### <a name="parameters"></a>Parametreler

*_Filtreyi*<br/>
Sunulan iletileri kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `unbounded_buffer` ileti bloğu zamanlandı.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `unbounded_buffer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.

Türü `filter_method` bir functor imzaya sahip olduğu `bool (_Type const &)` , çağrıldığında bu `unbounded_buffer` sunulan bir iletiye kabul etmelidir olup olmadığını belirlemek için ileti bloğu.

##  <a name="dtor"></a> ~ unbounded_buffer

Yok eder `unbounded_buffer` ileti bloğu.

```
~unbounded_buffer();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[overwrite_buffer Sınıfı](overwrite-buffer-class.md)<br/>
[single_assignment Sınıfı](single-assignment-class.md)

