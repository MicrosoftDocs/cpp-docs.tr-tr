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
ms.openlocfilehash: 6033da1347e116b4b68cf719a461a1cf6ff5d04f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269454"
---
# <a name="targetblock-class"></a>target_block Sınıfı

`target_block` Temel bağlantı yönetim işlevleri sağlayan soyut bir temel sınıfı ve hedef için hata denetimini yalnızca engeller.

## <a name="syntax"></a>Sözdizimi

```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

#### <a name="parameters"></a>Parametreler

*_SourceLinkRegistry*<br/>
Kaynak bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.

*_MessageProcessorType*<br/>
İleti işleme için işlemci türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`source_iterator`|İçin bir yineleyici türü `source_link_manager` bu `target_block` nesne.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[target_block](#ctor)|Oluşturur bir `target_block` nesne.|
|[~ target_block yok Edicisi](#dtor)|Yok eder `target_block` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Yay](#propagate)|Zaman uyumsuz olarak bir ileti bir kaynak bloktaki bu hedef bloğa aktarır.|
|[Gönder](#send)|Zaman uyumlu olarak bir ileti bir kaynak bloktaki bu hedef bloğa aktarır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[async_send](#async_send)|Zaman uyumsuz olarak işlemek için bir ileti gönderir.|
|[decline_incoming_messages](#decline_incoming_messages)|Blokla yeni iletileri reddedilen olduğunu gösterir.|
|[enable_batched_processing](#enable_batched_processing)|Bu blok için işleme toplu olanak tanır.|
|[initialize_target](#initialize_target)|Temel nesnesini başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.|
|[link_source](#link_source)|Belirtilen kaynak bloğu için bağlantı `target_block` nesne.|
|[process_input_messages](#process_input_messages)|Girdi olarak alınan iletileri işler.|
|[process_message](#process_message)|Türetilen bir sınıfta geçersiz kılındığında, bu tarafından kabul edilen iletiyi işleyen `target_block` nesne.|
|[propagate_message](#propagate_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu blok `target_block` nesne. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[register_filter](#register_filter)|Alınan her ileti üzerinde çağrılacak bir filtre yöntemi kaydeder.|
|[remove_sources](#remove_sources)|Tüm kaynakları bekleyen zaman uyumsuz gönderme işlemleri için bekledikten sonra bağlantıyı keser.|
|[send_message](#send_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem zaman uyumlu olarak gelen bir ileti geçirir bir `ISource` bu blok `target_block` nesne. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[sync_send](#sync_send)|Zaman uyumlu işleme için bir ileti gönderin.|
|[unlink_source](#unlink_source)|Bu bir belirtilen kaynak blok olan bağlantısını kesen `target_block` nesne.|
|[unlink_sources](#unlink_sources)|Bu, tüm kaynak bloklar olan bağlantısını kesen `target_block` nesne. (Geçersiz kılmaları [Itarget::unlink_sources](itarget-class.md#unlink_sources).)|
|[wait_for_async_sends](#wait_for_async_sends)|Tamamlamak tüm zaman uyumsuz yayılmaları bekler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Itarget](itarget-class.md)

`target_block`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="async_send"></a> async_send

Zaman uyumsuz olarak işlemek için bir ileti gönderir.

```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Gönderilen iletinin bir işaretçi.

##  <a name="decline_incoming_messages"></a> decline_incoming_messages

Blokla yeni iletileri reddedilen olduğunu gösterir.

```
void decline_incoming_messages();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yok etme işlemi devam ederken yeni iletileri reddedilecek emin olmak için yok edici tarafından çağrılır.

##  <a name="enable_batched_processing"></a> enable_batched_processing

Bu blok için işleme toplu olanak tanır.

```
void enable_batched_processing();
```

##  <a name="initialize_target"></a> initialize_target

Temel nesnesini başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.

```
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Görevleri zamanlamak için kullanılacak Zamanlayıcı.

*_PScheduleGroup*<br/>
Görevleri zamanlamak için kullanılacak zamanlama grubu.

##  <a name="link_source"></a> link_source

Belirtilen kaynak bloğu için bağlantı `target_block` nesne.

```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
Bir işaretçi `ISource` bağlanacak bloğu.

### <a name="remarks"></a>Açıklamalar

Bu işlev üzerinde doğrudan çağrılmamalıdır bir `target_block` nesne. Blokları kullanarak birbirine bağlanması `link_target` metodunda `ISource` çağıracağı blokları, `link_source` karşılık gelen hedef yöntemi.

##  <a name="process_input_messages"></a> process_input_messages

Girdi olarak alınan iletileri işler.

```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek iletisi için bir işaretçi.

##  <a name="process_message"></a> process_message

Türetilen bir sınıfta geçersiz kılındığında, bu tarafından kabul edilen iletiyi işleyen `target_block` nesne.

```
virtual void process_message(message<_Source_type> *);
```

##  <a name="propagate"></a> Yay

Zaman uyumsuz olarak bir ileti bir kaynak bloktaki bu hedef bloğa aktarır.

```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) ya da özel durum `_PMessage` veya `_PSource` parametresi `NULL`.

##  <a name="propagate_message"></a> propagate_message

Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu blok `target_block` nesne. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

##  <a name="register_filter"></a> register_filter

Alınan her ileti üzerinde çağrılacak bir filtre yöntemi kaydeder.

```
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Filtreyi*<br/>
Filter yöntemi.

##  <a name="remove_sources"></a> remove_sources

Tüm kaynakları bekleyen zaman uyumsuz gönderme işlemleri için bekledikten sonra bağlantıyı keser.

```
void remove_sources();
```

### <a name="remarks"></a>Açıklamalar

Tüm hedef blokları, bunların bir yıkıcı kaynakları kaldırmak için bu yordamı çağırmanız gerekir.

##  <a name="send"></a> Gönder

Zaman uyumlu olarak bir ileti bir kaynak bloktaki bu hedef bloğa aktarır.

```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) ya da özel durum `_PMessage` veya `_PSource` parametresi `NULL`.

Kullanarak `send` yöntemi dışında iletisi başlatma ve iletileri bir ağdaki yayılması tehlikelidir ve kilitlenmesine yol açabilir.

Zaman `send` ileti algıladı ya da zaten kabul edildi ve hedef blok aktarılan veya hedef tarafından reddedilen döndürür.

##  <a name="send_message"></a> send_message

Türetilen bir sınıfta geçersiz kılındığında, bu yöntem zaman uyumlu olarak gelen bir ileti geçirir bir `ISource` bu blok `target_block` nesne. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu bloğu döndüren `declined` türetilmiş sınıf tarafından geçersiz kılınmadığı sürece.

##  <a name="sync_send"></a> sync_send

Zaman uyumlu işleme için bir ileti gönderin.

```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Gönderilen iletinin bir işaretçi.

##  <a name="ctor"></a> target_block

Oluşturur bir `target_block` nesne.

```
target_block();
```

##  <a name="dtor"></a> ~ target_block

Yok eder `target_block` nesne.

```
virtual ~target_block();
```

##  <a name="unlink_source"></a> unlink_source

Bu bir belirtilen kaynak blok olan bağlantısını kesen `target_block` nesne.

```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
Bir işaretçi `ISource` bağlantısının kaldırılması için bloğu.

##  <a name="unlink_sources"></a> unlink_sources

Bu, tüm kaynak bloklar olan bağlantısını kesen `target_block` nesne.

```
virtual void unlink_sources();
```

##  <a name="wait_for_async_sends"></a> wait_for_async_sends

Tamamlamak tüm zaman uyumsuz yayılmaları bekler.

```
void wait_for_async_sends();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm zaman uyumsuz işlemler blok yok etme öncesinde tamamlamak için bir süre beklendiğinden emin olmak için ileti bloğu yok ediciler tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ITarget Sınıfı](itarget-class.md)
