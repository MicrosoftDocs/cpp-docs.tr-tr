---
title: target_block Sınıfı
ms.date: 11/04/2016
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
ms.openlocfilehash: 4009133161133a99aeb0ee040f0c82fdbabecaa0
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142650"
---
# <a name="target_block-class"></a>target_block Sınıfı

`target_block` sınıfı, temel bağlantı yönetim işlevselliği ve yalnızca hedef bloklar için hata denetimi sağlayan bir soyut temel sınıftır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>Parametreler

*_SourceLinkRegistry*<br/>
Kaynak bağlantılarını tutmak için kullanılacak bağlantı kayıt defteri.

*_MessageProcessorType*<br/>
İleti işleme için işlemci türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`source_iterator`|Bu `target_block` nesnesinin `source_link_manager` için yineleyicinin türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[target_block](#ctor)|`target_block` nesnesi oluşturur.|
|[~ target_block yok edici](#dtor)|`target_block` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[aktarabilirsiniz](#propagate)|Bir kaynak bloğundan bu hedef bloğa zaman uyumsuz bir ileti geçirir.|
|[Gönder](#send)|Zaman uyumlu olarak bir kaynak bloğundan bu hedef bloğa bir ileti geçirir.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[async_send](#async_send)|Zaman uyumsuz olarak işlenmek üzere bir ileti gönderir.|
|[decline_incoming_messages](#decline_incoming_messages)|Yeni iletilerin reddedime bloğunun olduğunu gösterir.|
|[enable_batched_processing](#enable_batched_processing)|Bu blok için toplu işleme etkinleştirilir.|
|[initialize_target](#initialize_target)|Temel nesneyi başlatır. Özellikle `message_processor` nesnesinin başlatılması gerekir.|
|[link_source](#link_source)|Belirtilen kaynak bloğunu bu `target_block` nesnesine bağlar.|
|[process_input_messages](#process_input_messages)|Giriş olarak alınan iletileri işler.|
|[process_message](#process_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu `target_block` nesnesi tarafından kabul edilen bir iletiyi işler.|
|[propagate_message](#propagate_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem `ISource` bloğundan zaman uyumsuz bir iletiyi bu `target_block` nesnesine geçirir. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.|
|[register_filter](#register_filter)|Alınan her iletide çağrılacak bir filtre yöntemi kaydeder.|
|[remove_sources](#remove_sources)|Bekleyen zaman uyumsuz gönderme işlemlerinin tamamlanmasını bekledikten sonra tüm kaynakların bağlantısını kaldırır.|
|[send_message](#send_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem `ISource` bloğundan zaman uyumlu bir iletiyi bu `target_block` nesnesine geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.|
|[sync_send](#sync_send)|İşleme için zaman uyumlu bir ileti gönderin.|
|[unlink_source](#unlink_source)|Belirtilen bir kaynak bloğunun bu `target_block` nesnesinden bağlantısını kaldırır.|
|[unlink_sources](#unlink_sources)|Bu `target_block` nesnesinden tüm kaynak bloklarının bağlantısını kaldırır. ( [IComparer:: unlink_sources](itarget-class.md#unlink_sources)geçersiz kılar.)|
|[wait_for_async_sends](#wait_for_async_sends)|Tüm zaman uyumsuz yayılmaları tamamlanmasını bekler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ITarget](itarget-class.md)

`target_block`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="async_send"></a>async_send

Zaman uyumsuz olarak işlenmek üzere bir ileti gönderir.

```cpp
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Gönderilmekte olan iletiye yönelik bir işaretçi.

## <a name="decline_incoming_messages"></a>decline_incoming_messages

Yeni iletilerin reddedime bloğunun olduğunu gösterir.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yok etme işlemi devam ederken yeni iletilerin reddedildiğini sağlamak için yok edici tarafından çağırılır.

## <a name="enable_batched_processing"></a>enable_batched_processing

Bu blok için toplu işleme etkinleştirilir.

```cpp
void enable_batched_processing();
```

## <a name="initialize_target"></a>initialize_target

Temel nesneyi başlatır. Özellikle `message_processor` nesnesinin başlatılması gerekir.

```cpp
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Görevleri zamanlamak için kullanılacak Zamanlayıcı.

*_PScheduleGroup*<br/>
Görevleri zamanlamak için kullanılacak zamanlama grubu.

## <a name="link_source"></a>link_source

Belirtilen kaynak bloğunu bu `target_block` nesnesine bağlar.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
Bağlantı yapılacak `ISource` bloğuna yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan bir `target_block` nesnesi üzerinde çağrılmamalıdır. Bloklar, ilgili hedefte `link_source` yöntemini çağıracak `ISource` blokları üzerinde `link_target` yöntemi kullanılarak birbirine bağlanmalıdır.

## <a name="process_input_messages"></a>process_input_messages

Giriş olarak alınan iletileri işler.

```cpp
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

## <a name="process_message"></a>process_message

Türetilmiş bir sınıfta geçersiz kılınırsa, bu `target_block` nesnesi tarafından kabul edilen bir iletiyi işler.

```cpp
virtual void process_message(message<_Source_type> *);
```

## <a name="propagate"></a>aktarabilirsiniz

Bir kaynak bloğundan bu hedef bloğa zaman uyumsuz bir ileti geçirir.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

`_PMessage` veya `_PSource` parametresi `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

## <a name="propagate_message"></a>propagate_message

Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem `ISource` bloğundan zaman uyumsuz bir iletiyi bu `target_block` nesnesine geçirir. Kaynak bloğu tarafından çağrıldığında `propagate` yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="register_filter"></a>register_filter

Alınan her iletide çağrılacak bir filtre yöntemi kaydeder.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Filter*<br/>
Filtre yöntemi.

## <a name="remove_sources"></a>remove_sources

Bekleyen zaman uyumsuz gönderme işlemlerinin tamamlanmasını bekledikten sonra tüm kaynakların bağlantısını kaldırır.

```cpp
void remove_sources();
```

### <a name="remarks"></a>Açıklamalar

Tüm hedef blokları, yıkıcısında kaynakları kaldırmak için bu yordamı çağırmalıdır.

## <a name="send"></a>Gönder

Zaman uyumlu olarak bir kaynak bloğundan bu hedef bloğa bir ileti geçirir.

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

`_PMessage` veya `_PSource` parametresi `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

`send` yönteminin ileti başlatma dışında kullanılması ve iletilerin bir ağ içinde yayılması tehlikelidir ve kilitlenmeye yol açabilir.

`send` döndürüldüğünde ileti zaten kabul edilmiştir ve hedef bloğa aktarılır ya da hedef tarafından reddedildi.

## <a name="send_message"></a>send_message

Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem `ISource` bloğundan zaman uyumlu bir iletiyi bu `target_block` nesnesine geçirir. Kaynak bloğu tarafından çağrıldığında `send` yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu blok türetilmiş bir sınıf tarafından geçersiz kılınmadıkça `declined` döndürür.

## <a name="sync_send"></a>sync_send

İşleme için zaman uyumlu bir ileti gönderin.

```cpp
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Gönderilmekte olan iletiye yönelik bir işaretçi.

## <a name="ctor"></a>target_block

`target_block` nesnesi oluşturur.

```cpp
target_block();
```

## <a name="dtor"></a>~ target_block

`target_block` nesnesini yok eder.

```cpp
virtual ~target_block();
```

## <a name="unlink_source"></a>unlink_source

Belirtilen bir kaynak bloğunun bu `target_block` nesnesinden bağlantısını kaldırır.

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource` bloğunun bağlantısının oluşturulması için bir işaretçi.

## <a name="unlink_sources"></a>unlink_sources

Bu `target_block` nesnesinden tüm kaynak bloklarının bağlantısını kaldırır.

```cpp
virtual void unlink_sources();
```

## <a name="wait_for_async_sends"></a>wait_for_async_sends

Tüm zaman uyumsuz yayılmaları tamamlanmasını bekler.

```cpp
void wait_for_async_sends();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm zaman uyumsuz işlemlerin blok yok etmeden önce bitmesini sağlamak için ileti bloğu yıkıcıları tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ITarget Sınıfı](itarget-class.md)
