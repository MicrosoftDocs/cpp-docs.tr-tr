---
title: ordered_message_processor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
ms.openlocfilehash: c6e09ff862f0725cc508e3e390dbfa3cc12f7daa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545970"
---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor Sınıfı

Bir `ordered_message_processor` olduğu bir `message_processor` sırada alınan iletileri işleyecek şekilde ileti blokları sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ordered_message_processor : public message_processor<T>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Processor tarafından işlenen iletilerin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`type`|Bir tür diğer adı için `T`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ordered_message_processor](#ctor)|Oluşturur bir `ordered_message_processor` nesne.|
|[~ ordered_message_processor yok Edicisi](#dtor)|Yok eder `ordered_message_processor` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[async_send](#async_send)|Zaman uyumsuz olarak iletileri kuyruğa alır ve bu zaten yapılmadıysa bir işleme görevi başlar. (Geçersiz kılmaları [message_processor::async_send](message-processor-class.md#async_send).)|
|[başlatma](#initialize)|Başlatır `ordered_message_processor` uygun geri çağırma işlevi, Zamanlayıcı ve zamanlama grubu nesnesi.|
|[initialize_batched_processing](#initialize_batched_processing)|Başlatma toplu ileti işleme|
|[sync_send](#sync_send)|Zaman uyumlu iletileri kuyruğa alır ve bu zaten yapılmadıysa bir işleme görevi başlar. (Geçersiz kılmaları [message_processor::sync_send](message-processor-class.md#sync_send).)|
|[bekleme](#wait)|İleti blokları yıkıcılarda tüm zaman uyumsuz işleme görevlerini blok yok etme öncesinde tamamlanması zaman sahip olduğunuzdan emin olmak için kullanılan bir işlemciye özgü dönmesini bekleyin. (Geçersiz kılmaları [message_processor::wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Çağrılan zaman uyumsuz işleme işlev. Bu iletileri dequeues ve bunları işlemeye başlar. (Geçersiz kılmaları [message_processor::process_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="async_send"></a> async_send

Zaman uyumsuz olarak iletileri kuyruğa alır ve bu zaten yapılmadıysa bir işleme görevi başlar.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Bir ileti için bir işaretçi.

##  <a name="initialize"></a> başlatma

Başlatır `ordered_message_processor` uygun geri çağırma işlevi, Zamanlayıcı ve zamanlama grubu nesnesi.

```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Hafif görevleri zamanlamak için kullanılacak Zamanlayıcı işaretçisi.

*_PScheduleGroup*<br/>
Hafif görevleri zamanlamak için kullanılacak zamanlama grubu için bir işaretçi.

*_Handler*<br/>
Geri çağırma sırasında çağrılan işleyici functor.

##  <a name="initialize_batched_processing"></a> initialize_batched_processing

Başlatma toplu ileti işleme

```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>Parametreler

*_Processor*<br/>
İşlemci functor geri çağırma sırasında çağrılır.

*_Propagator*<br/>
Bir Yayıcı functor geri çağırma sırasında çağrılır.

##  <a name="ctor"></a> ordered_message_processor

Oluşturur bir `ordered_message_processor` nesne.

```
ordered_message_processor();
```

### <a name="remarks"></a>Açıklamalar

Bu `ordered_message_processor` kadar zaman uyumlu veya zaman uyumsuz işleyiciler zamanlamaz `initialize` işlevi çağrılır.

##  <a name="dtor"></a> ~ ordered_message_processor

Yok eder `ordered_message_processor` nesne.

```
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>Açıklamalar

İşlemci yok etme önce tüm bekleyen zaman uyumsuz işlemler bekler.

##  <a name="process_incoming_message"></a> process_incoming_message

Çağrılan zaman uyumsuz işleme işlev. Bu iletileri dequeues ve bunları işlemeye başlar.

```
virtual void process_incoming_message();
```

##  <a name="sync_send"></a> sync_send

Zaman uyumlu iletileri kuyruğa alır ve bu zaten yapılmadıysa bir işleme görevi başlar.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Bir ileti için bir işaretçi.

##  <a name="wait"></a> bekleme

İleti blokları yıkıcılarda tüm zaman uyumsuz işleme görevlerini blok yok etme öncesinde tamamlanması zaman sahip olduğunuzdan emin olmak için kullanılan bir işlemciye özgü dönmesini bekleyin.

```
virtual void wait();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
