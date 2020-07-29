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
ms.openlocfilehash: e02fa1ffbf4c3e2c7d17dfe2d6ae66758945d9de
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219527"
---
# <a name="unbounded_buffer-class"></a>unbounded_buffer Sınıfı

`unbounded_buffer`İleti bloğu, `propagator_block` sınırsız sayıda iletiyi depolayan çok kaynaklı ve çok kaynaklı, sıralı bir kaynaktır.

## <a name="syntax"></a>Söz dizimi

```cpp
template<
   class             _Type
>
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;
```

### <a name="parameters"></a>Parametreler

*_Type*<br/>
Arabellek tarafından saklanan ve yayılan iletilerin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[unbounded_buffer](#ctor)|Fazla Yüklendi. `unbounded_buffer`İleti bloğu oluşturur.|
|[~ unbounded_buffer yok edici](#dtor)|`unbounded_buffer`Mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[sıradan çıkarma](#dequeue)|`unbounded_buffer`İleti bloğu bloğundan bir öğeyi kaldırır.|
|[alma](#enqueue)|Mesajlaşma bloğuna bir öğe ekler `unbounded_buffer` .|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `unbounded_buffer` ve sahipliği çağırana aktarmakta.|
|[consume_message](#consume_message)|İleti bloğu tarafından daha önce sunulan `unbounded_buffer` ve hedef tarafından ayrılmış bir ileti tüketir ve sahipliği çağırana aktarmıştır.|
|[link_target_notification](#link_target_notification)|Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `unbounded_buffer` .|
|[process_input_messages](#process_input_messages)|`message` `_PMessage` Bu `unbounded_buffer` mesajlaşma bloğuna girer ve bunu tüm bağlantılı hedeflere sunmaya çalışır.|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `unbounded_buffer` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[propagate_output_messages](#propagate_output_messages)|`message` `_PMessage` Bu `unbounded_buffer` mesajlaşma bloğuna girer ve bunu tüm bağlantılı hedeflere sunmaya çalışır. (Geçersiz kılmalar [source_block::p ropagate_output_messages](source-block-class.md#propagate_output_messages).)|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `unbounded_buffer` . (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `unbounded_buffer` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[supports_anonymous_source](#supports_anonymous_source)|`supports_anonymous_source`Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için yöntemini geçersiz kılar. ( [IComparer:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)geçersiz kılar.)|

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`unbounded_buffer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `unbounded_buffer` ve sahipliği çağırana aktarmakta.

```cpp
virtual message<_Type> * accept_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

İleti bloğu tarafından daha önce sunulan `unbounded_buffer` ve hedef tarafından ayrılmış bir ileti tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<_Type> * consume_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Tüketilmekte olan nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`,, Ancak, ' a benzer ancak her zaman öğesine yapılan bir çağrıdır `reserve` .

## <a name="dequeue"></a><a name="dequeue"></a>sıradan çıkarma

`unbounded_buffer`İleti bloğu bloğundan bir öğeyi kaldırır.

```cpp
_Type dequeue();
```

### <a name="return-value"></a>Dönüş Değeri

Öğesinden kaldırılan iletinin yükü `unbounded_buffer` .

## <a name="enqueue"></a><a name="enqueue"></a>alma

Mesajlaşma bloğuna bir öğe ekler `unbounded_buffer` .

```cpp
bool enqueue(
   _Type const&                 _Item
);
```

### <a name="parameters"></a>Parametreler

*_Item*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

**`true`** öğe kabul edildiyse, **`false`** tersi durumda.

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `unbounded_buffer` .

```cpp
virtual void link_target_notification(
   _Inout_ ITarget<_Type> *                 _PTarget
);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="propagate_message"></a><a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi bir `ISource` bloğundan bu `unbounded_buffer` mesajlaşma bloğuna geçirir. `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md#message_status) göstergesi.

## <a name="propagate_output_messages"></a><a name="propagate_output_messages"></a>propagate_output_messages

`message` `_PMessage` Bu `unbounded_buffer` mesajlaşma bloğuna girer ve bunu tüm bağlantılı hedeflere sunmaya çalışır.

```cpp
virtual void propagate_output_messages();
```

### <a name="remarks"></a>Açıklamalar

Daha önce başka bir ileti zaten varsa `unbounded_buffer` , daha önceki tüm iletiler kabul edilene veya tüketilene kadar bağlantılı hedeflere yayma gerçekleşmeyecektir. Başarıyla bağlanılan ilk bağlantılı hedef `accept` veya `consume` ileti sahiplik alır ve başka hiçbir hedef daha sonra iletiyi alamaz.

## <a name="process_input_messages"></a><a name="process_input_messages"></a>process_input_messages

`message` `_PMessage` Bu `unbounded_buffer` mesajlaşma bloğuna girer ve bunu tüm bağlantılı hedeflere sunmaya çalışır.

```cpp
virtual void process_input_messages(
   _Inout_ message<_Type> *                 _PMessage
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

## <a name="release_message"></a><a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `unbounded_buffer` .

```cpp
virtual bool reserve_message(
   runtime_object_identity                 _MsgId
);
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

Zaman uyumlu bir iletiyi bir `ISource` bloktan bu mesajlaşma bloğuna eşzamanlı olarak geçirir `unbounded_buffer` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md#message_status) göstergesi.

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a>supports_anonymous_source

`supports_anonymous_source`Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için yöntemini geçersiz kılar.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** bloğu sunulan iletileri ertelemez.

## <a name="unbounded_buffer"></a><a name="ctor"></a>unbounded_buffer

`unbounded_buffer`İleti bloğu oluşturur.

```cpp
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

*_Filter*<br/>
Sunulan iletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`Scheduler` `unbounded_buffer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_PScheduleGroup*<br/>
`ScheduleGroup` `unbounded_buffer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_PScheduler` `_PScheduleGroup` .

Tür, `filter_method` `bool (_Type const &)` Bu `unbounded_buffer` mesajlaşma bloğu tarafından önerilen bir iletiyi kabul edip etmediğini tespit etmek için çağrılan imzaya sahip bir functor.

## <a name="unbounded_buffer"></a><a name="dtor"></a>~ unbounded_buffer

`unbounded_buffer`Mesajlaşma bloğunu yok eder.

```cpp
~unbounded_buffer();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[overwrite_buffer sınıfı](overwrite-buffer-class.md)<br/>
[single_assignment sınıfı](single-assignment-class.md)
