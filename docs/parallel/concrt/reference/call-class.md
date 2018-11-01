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
ms.openlocfilehash: 5164d2787c86e6c909418f353c15c876d1397afe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566107"
---
# <a name="call-class"></a>çağrı Sınıfı

A `call` ileti bloğu, bir çok kaynak sıralı `target_block` , çağıran belirtilen işlev bir ileti alındığında.

## <a name="syntax"></a>Sözdizimi

```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Bu bloğu yayılan iletileri yük türü.

*_FunctorType*<br/>
Bu bloğu kabul edebilen işlev imzası.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Çağrı](#ctor)|Fazla Yüklendi. Oluşturur bir `call` ileti bloğu.|
|[~ call yok Edicisi](#dtor)|Yok eder `call` ileti bloğu.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|Arama işlevi, giriş iletileri yürütür.|
|[process_message](#process_message)|Bu tarafından kabul edilen iletiyi işleyen `call` ileti bloğu.|
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `call` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[send_message](#send_message)|Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `call` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmalar `supports_anonymous_source` bu blok için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntemi. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Itarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> Çağrı

Oluşturur bir `call` ileti bloğu.

```
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
Kabul edilen her ileti için çağrılacak işlev.

*_Filtreyi*<br/>
Sunulan iletileri kabul edilip edilmeyeceğini belirleyen bir filtre işlevi.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `call` ileti bloğu zamanlandı.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `call` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.

Türü `_Call_method` bir functor imzaya sahip olduğu `void (T const &)` , çağrıldığında bu `call` bir iletiyi, ileti bloğu.

Türü `filter_method` bir functor imzaya sahip olduğu `bool (T const &)` , çağrıldığında bu `call` sunulan bir iletiye kabul etmelidir olup olmadığını belirlemek için ileti bloğu.

##  <a name="dtor"></a> ~ çağırın

Yok eder `call` ileti bloğu.

```
~call();
```

##  <a name="process_input_messages"></a> process_input_messages

Arama işlevi, giriş iletileri yürütür.

```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

##  <a name="process_message"></a> process_message

Bu tarafından kabul edilen iletiyi işleyen `call` ileti bloğu.

```
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

##  <a name="propagate_message"></a> propagate_message

Zaman uyumsuz olarak bir ileti geçirir bir `ISource` bu blok `call` ileti bloğu. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.

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

##  <a name="send_message"></a> send_message

Eş zamanlı olarak gelen bir ileti geçirir bir `ISource` bu blok `call` ileti bloğu. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.

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

**doğru** iletileri blok değil ertelemek için sunulan.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[transformer Sınıfı](transformer-class.md)
