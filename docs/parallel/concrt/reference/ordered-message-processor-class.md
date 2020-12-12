---
description: 'Hakkında daha fazla bilgi edinin: ordered_message_processor sınıfı'
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
ms.openlocfilehash: bea7f2ae70b6eb87fc30ece578f3bd8c3b35b5ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167545"
---
# <a name="ordered_message_processor-class"></a>ordered_message_processor Sınıfı

`ordered_message_processor` `message_processor` İleti bloklarının iletileri alındıkları sırada işlemesini sağlayan bir ' dir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class ordered_message_processor : public message_processor<T>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
İşlemci tarafından işlenen iletilerin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|İçin bir tür diğer adı `T` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ordered_message_processor](#ctor)|Bir `ordered_message_processor` nesnesi oluşturur.|
|[~ ordered_message_processor yok edici](#dtor)|Nesneyi yok eder `ordered_message_processor` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[async_send](#async_send)|Zaman uyumsuz olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir işleme görevi başlatır. (Geçersiz kılmalar [message_processor:: async_send](message-processor-class.md#async_send).)|
|[Öbek](#initialize)|`ordered_message_processor`Nesneyi uygun geri çağırma işlevi, Zamanlayıcı ve zamanlama grubuyla başlatır.|
|[initialize_batched_processing](#initialize_batched_processing)|Toplu ileti işlemeyi Başlat|
|[sync_send](#sync_send)|Zaman uyumlu olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir işleme görevi başlatır. (Geçersiz kılmalar [message_processor:: sync_send](message-processor-class.md#sync_send).)|
|[bekleneceğini](#wait)|Tüm zaman uyumsuz işleme görevlerinin blok yok etmeden önce tamamlanmasını sağlamak için, işlemciye özgü bir döndürme ileti blokları yıkıcıklarında kullanılır. (Geçersiz kılmalar [message_processor:: wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Zaman uyumsuz olarak çağrılan işleme işlevi. İletileri kuyruktan kaldırır ve işlemeye başlar. (Geçersiz kılmalar [message_processor::p rocess_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="async_send"></a><a name="async_send"></a> async_send

Zaman uyumsuz olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir işleme görevi başlatır.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
İleti işaretçisi.

## <a name="initialize"></a><a name="initialize"></a> Öbek

`ordered_message_processor`Nesneyi uygun geri çağırma işlevi, Zamanlayıcı ve zamanlama grubuyla başlatır.

```cpp
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Açık ağırlığa sahip görevleri zamanlamak için kullanılacak Scheduler için bir işaretçi.

*_PScheduleGroup*<br/>
Hafif görevleri zamanlamak için kullanılacak zamanlama grubuna yönelik bir işaretçi.

*_Handler*<br/>
Geri çağırma sırasında, functor tarafından çağrılan işleyici.

## <a name="initialize_batched_processing"></a><a name="initialize_batched_processing"></a> initialize_batched_processing

Toplu ileti işlemeyi Başlat

```cpp
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>Parametreler

*_Processor*<br/>
Geri arama sırasında çağrılan işlemci functor.

*_Propagator*<br/>
Bir Yayıcı, geri çağırma sırasında çağrılır.

## <a name="ordered_message_processor"></a><a name="ctor"></a> ordered_message_processor

Bir `ordered_message_processor` nesnesi oluşturur.

```cpp
ordered_message_processor();
```

### <a name="remarks"></a>Açıklamalar

Bu `ordered_message_processor` işlem, işlev çağrılana kadar zaman uyumsuz veya zaman uyumlu işleyiciler zamanlayamaz `initialize` .

## <a name="ordered_message_processor"></a><a name="dtor"></a> ~ ordered_message_processor

Nesneyi yok eder `ordered_message_processor` .

```cpp
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>Açıklamalar

İşlemciyi yok etmeden önce tüm bekleyen zaman uyumsuz işlemler için bekler.

## <a name="process_incoming_message"></a><a name="process_incoming_message"></a> process_incoming_message

Zaman uyumsuz olarak çağrılan işleme işlevi. İletileri kuyruktan kaldırır ve işlemeye başlar.

```cpp
virtual void process_incoming_message();
```

## <a name="sync_send"></a><a name="sync_send"></a> sync_send

Zaman uyumlu olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir işleme görevi başlatır.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
İleti işaretçisi.

## <a name="wait"></a><a name="wait"></a> bekleneceğini

Tüm zaman uyumsuz işleme görevlerinin blok yok etmeden önce tamamlanmasını sağlamak için, işlemciye özgü bir döndürme ileti blokları yıkıcıklarında kullanılır.

```cpp
virtual void wait();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
