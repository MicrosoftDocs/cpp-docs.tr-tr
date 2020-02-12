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
ms.openlocfilehash: d0f2f81957ee88d4263c6acd879bd286c95631eb
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142328"
---
# <a name="unbounded_buffer-class"></a>unbounded_buffer Sınıfı

`unbounded_buffer` mesajlaşma bloğu, sınırsız sayıda iletiyi depolayan çok hedefli, çok kaynaklı ve sıralı `propagator_block`.

## <a name="syntax"></a>Sözdizimi

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
|[unbounded_buffer](#ctor)|Fazla Yüklendi. `unbounded_buffer` mesajlaşma bloğu oluşturur.|
|[~ unbounded_buffer yok edici](#dtor)|`unbounded_buffer` mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[sıradan çıkarma](#dequeue)|`unbounded_buffer` mesajlaşma bloğundan bir öğeyi kaldırır.|
|[alma](#enqueue)|`unbounded_buffer` mesajlaşma bloğuna bir öğe ekler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu `unbounded_buffer` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[consume_message](#consume_message)|Daha önce `unbounded_buffer` mesajlaşma bloğu tarafından sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu, sahipliği çağırana aktarılarak.|
|[link_target_notification](#link_target_notification)|Yeni bir hedefin bu `unbounded_buffer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.|
|[process_input_messages](#process_input_messages)|`message` `_PMessage` bu `unbounded_buffer` mesajlaşma bloğuna koyar ve bunu tüm bağlantılı hedeflere sunmaya çalışır.|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `unbounded_buffer` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.|
|[propagate_output_messages](#propagate_output_messages)|`message` `_PMessage` bu `unbounded_buffer` mesajlaşma bloğuna koyar ve bunu tüm bağlantılı hedeflere sunmaya çalışır. (Geçersiz kılmalar [source_block::p ropagate_output_messages](source-block-class.md#propagate_output_messages).)|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu `unbounded_buffer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır. (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Zaman uyumlu olarak bir `ISource` bloğundan bu `unbounded_buffer` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.|
|[supports_anonymous_source](#supports_anonymous_source)|Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için `supports_anonymous_source` yöntemini geçersiz kılar. ( [IComparer:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)geçersiz kılar.)|

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

## <a name="accept_message"></a>accept_message

Bu `unbounded_buffer` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<_Type> * accept_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

## <a name="consume_message"></a>consume_message

Daha önce `unbounded_buffer` mesajlaşma bloğu tarafından sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve bu, sahipliği çağırana aktarılarak.

```cpp
virtual message<_Type> * consume_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Tüketilmekte olan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`benzerdir, ancak her zaman bir `reserve`çağrısıyla yapılır.

## <a name="dequeue"></a>sıradan çıkarma

`unbounded_buffer` mesajlaşma bloğundan bir öğeyi kaldırır.

```cpp
_Type dequeue();
```

### <a name="return-value"></a>Dönüş Değeri

`unbounded_buffer`kaldırılan iletinin yükü.

## <a name="enqueue"></a>alma

`unbounded_buffer` mesajlaşma bloğuna bir öğe ekler.

```cpp
bool enqueue(
   _Type const&                 _Item
);
```

### <a name="parameters"></a>Parametreler

*_Item*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

öğe kabul edildiyse **true** , aksi takdirde **false** .

## <a name="link_target_notification"></a>link_target_notification

Yeni bir hedefin bu `unbounded_buffer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.

```cpp
virtual void link_target_notification(
   _Inout_ ITarget<_Type> *                 _PTarget
);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `unbounded_buffer` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md#message_status) göstergesi.

## <a name="propagate_output_messages"></a>propagate_output_messages

`message` `_PMessage` bu `unbounded_buffer` mesajlaşma bloğuna koyar ve bunu tüm bağlantılı hedeflere sunmaya çalışır.

```cpp
virtual void propagate_output_messages();
```

### <a name="remarks"></a>Açıklamalar

`unbounded_buffer`başka bir ileti zaten varsa, daha önceki iletiler kabul edilene veya tüketilene kadar, bağlantılı hedeflere yayma gerçekleşmeyecektir. Başarılı bir şekilde `accept` veya `consume` ileti sahipliğe sahip olan ilk bağlantılı hedef, daha sonra başka bir hedef iletiyi alamaz.

## <a name="process_input_messages"></a>process_input_messages

`message` `_PMessage` bu `unbounded_buffer` mesajlaşma bloğuna koyar ve bunu tüm bağlantılı hedeflere sunmaya çalışır.

```cpp
virtual void process_input_messages(
   _Inout_ message<_Type> *                 _PMessage
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

## <a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

## <a name="reserve_message"></a>reserve_message

Daha önce bu `unbounded_buffer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

```cpp
virtual bool reserve_message(
   runtime_object_identity                 _MsgId
);
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

Zaman uyumlu olarak bir `ISource` bloğundan bu `unbounded_buffer` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md#message_status) göstergesi.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için `supports_anonymous_source` yöntemini geçersiz kılar.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**çünkü blok** sunulan iletileri ertelemez.

## <a name="ctor"></a>unbounded_buffer

`unbounded_buffer` mesajlaşma bloğu oluşturur.

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
`unbounded_buffer` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`unbounded_buffer` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Tür `filter_method`, bu `unbounded_buffer` mesajlaşma bloğu tarafından sunulan ve önerilen bir iletiyi kabul edip etmediğini belirlemede çağrılan, imza `bool (_Type const &)` olan bir functor.

## <a name="dtor"></a>~ unbounded_buffer

`unbounded_buffer` mesajlaşma bloğunu yok eder.

```cpp
~unbounded_buffer();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[overwrite_buffer Sınıfı](overwrite-buffer-class.md)<br/>
[single_assignment Sınıfı](single-assignment-class.md)
