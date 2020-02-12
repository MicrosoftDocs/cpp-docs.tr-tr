---
title: çağrı Sınıfı
ms.date: 11/04/2016
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
ms.openlocfilehash: 445e368ced9d9c8faf30351ecaeecc4e1b8a59f2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142842"
---
# <a name="call-class"></a>çağrı Sınıfı

`call` mesajlaşma bloğu, bir ileti alırken belirtilen bir işlevi çağıran çok kaynaklı ve sıralı bir `target_block`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Bu bloğa yayılan iletilerin yük türü.

*_FunctorType*<br/>
Bu bloğun kabul edebileceği işlevlerin imzası.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[çaðýrmak](#ctor)|Fazla Yüklendi. `call` mesajlaşma bloğu oluşturur.|
|[~ Call yıkıcı](#dtor)|`call` mesajlaşma bloğunu yok eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|Giriş iletilerinde çağırma işlevini yürütür.|
|[process_message](#process_message)|Bu `call` mesajlaşma bloğu tarafından kabul edilen bir iletiyi işler.|
|[propagate_message](#propagate_message)|Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `call` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.|
|[send_message](#send_message)|Zaman uyumlu olarak bir `ISource` bloğundan bu `call` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.|
|[supports_anonymous_source](#supports_anonymous_source)|Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için `supports_anonymous_source` yöntemini geçersiz kılar. ( [IComparer:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ITarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>çaðýrmak

`call` mesajlaşma bloğu oluşturur.

```cpp
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Func*<br/>
Kabul edilen her ileti için çağrılacak bir işlev.

*_Filter*<br/>
Sunulan iletilerin kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`call` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`call` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Tür `_Call_method`, bu `call` mesajlaşma bloğu tarafından bir iletiyi işlemek için çağrılan imza `void (T const &)` olan bir functor.

Tür `filter_method`, bu `call` mesajlaşma bloğu tarafından sunulan ve önerilen bir iletiyi kabul edip etmediğini belirlemede çağrılan, imza `bool (T const &)` olan bir functor.

## <a name="dtor"></a>~ Call

`call` mesajlaşma bloğunu yok eder.

```cpp
~call();
```

## <a name="process_input_messages"></a>process_input_messages

Giriş iletilerinde çağırma işlevini yürütür.

```cpp
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti işaretçisi.

## <a name="process_message"></a>process_message

Bu `call` mesajlaşma bloğu tarafından kabul edilen bir iletiyi işler.

```cpp
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti işaretçisi.

## <a name="propagate_message"></a>propagate_message

Zaman uyumsuz bir iletiyi `ISource` bloğundan bu `call` mesajlaşma bloğuna aktarır. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.

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

## <a name="send_message"></a>send_message

Zaman uyumlu olarak bir `ISource` bloğundan bu `call` mesajlaşma bloğuna bir ileti geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.

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

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Bu bloğun bağlantılı olmayan bir kaynak tarafından kendisine sunulan iletileri kabul edemeyeceğini belirtmek için `supports_anonymous_source` yöntemini geçersiz kılar.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**çünkü blok** sunulan iletileri ertelemez.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[transformer Sınıfı](transformer-class.md)
