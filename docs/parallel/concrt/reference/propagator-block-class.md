---
title: propagator_block Sınıfı
ms.date: 11/04/2016
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
ms.openlocfilehash: 7f466ad8f474ddb73d2235d9999c3dbeae627672
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272951"
---
# <a name="propagatorblock-class"></a>propagator_block Sınıfı

`propagator_block` Sınıfı, hem kaynak hem de hedef ileti blokları için Özet temel sınıf. Her ikisi de işlevlerini birleştiren `source_block` ve `target_block` sınıfları.

## <a name="syntax"></a>Sözdizimi

```
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

#### <a name="parameters"></a>Parametreler

*_TargetLinkRegistry*<br/>
Hedef bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.

*_SourceLinkRegistry*<br/>
Kaynak bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.

*_MessageProcessorType*<br/>
İleti işleme için işlemci türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`source_iterator`|İçin bir yineleyici türü `source_link_manager` bu `propagator_block`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[propagator_block](#ctor)|Oluşturur bir `propagator_block` nesne.|
|[~ propagator_block yok Edicisi](#dtor)|Yok eder bir `propagator_block` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Yay](#propagate)|Zaman uyumsuz olarak bir ileti bir kaynak bloktaki bu hedef bloğa aktarır.|
|[Gönder](#send)|Bu blok bir iletiyi zaman uyumlu olarak başlatır. Çağıran bir `ISource` blok. Bu işlev tamamlandığında, ileti bloğunun içine zaten yayıldıktan.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|Blokla yeni iletileri reddedilen olduğunu gösterir.|
|[initialize_source_and_target](#initialize_source_and_target)|Temel nesnesini başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.|
|[link_source](#link_source)|Belirtilen kaynak bloğu için bağlantı `propagator_block` nesne.|
|[process_input_messages](#process_input_messages)|İşlem giriş iletileri. Yalnızca source_block türetilen Yayıcı bloklar için kullanışlıdır (geçersiz kılmaları [source_block::process_input_messages](source-block-class.md#process_input_messages).)|
|[propagate_message](#propagate_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu blok `propagator_block` nesne. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[register_filter](#register_filter)|Alınan her ileti üzerinde çağrılacak bir filtre yöntemi kaydeder.|
|[remove_network_links](#remove_network_links)|Tüm kaynak ve hedef ağ bağlantıları buradan kaldırır `propagator_block` nesne.|
|[send_message](#send_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem zaman uyumlu olarak gelen bir ileti geçirir bir `ISource` bu blok `propagator_block` nesne. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.|
|[unlink_source](#unlink_source)|Bu bir belirtilen kaynak blok olan bağlantısını kesen `propagator_block` nesne.|
|[unlink_sources](#unlink_sources)|Bu, tüm kaynak bloklar olan bağlantısını kesen `propagator_block` nesne. (Geçersiz kılmaları [Itarget::unlink_sources](itarget-class.md#unlink_sources).)|

## <a name="remarks"></a>Açıklamalar

Birden çok devralma önlemek için `propagator_block` sınıfının devraldığı `source_block` sınıfı ve `ITarget` soyut sınıf. İşlevlerin çoğu `target_block` sınıfı burada çoğaltılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

[Itarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="decline_incoming_messages"></a> decline_incoming_messages

Blokla yeni iletileri reddedilen olduğunu gösterir.

```
void decline_incoming_messages();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yok etme işlemi devam ederken yeni iletileri reddedilecek emin olmak için yok edici tarafından çağrılır.

##  <a name="initialize_source_and_target"></a> initialize_source_and_target

Temel nesnesini başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.

```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Görevleri zamanlamak için kullanılacak Zamanlayıcı.

*_PScheduleGroup*<br/>
Görevleri zamanlamak için kullanılacak zamanlama grubu.

##  <a name="link_source"></a> link_source

Belirtilen kaynak bloğu için bağlantı `propagator_block` nesne.

```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
Bir işaretçi `ISource` bağlanacak bloğu.

##  <a name="process_input_messages"></a> process_input_messages

İşlem giriş iletileri. Yalnızca source_block türetilen Yayıcı bloklar için kullanışlıdır

```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek iletisi için bir işaretçi.

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

`propagate` Yöntemi, bir hedef bloğu tarafından bağlı kaynak blok üzerinde çağrılır. Biri değil zaten kuyruğa alınmış, iletiyi işlemek için zaman uyumsuz bir görev veya yürütme yukarı kuyruğa alır.

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) ya da özel durum `_PMessage` veya `_PSource` parametresi `NULL`.

##  <a name="propagate_message"></a> propagate_message

Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu blok `propagator_block` nesne. Tarafından çağrılan `propagate` bir kaynak bloğu tarafından çağrıldığında yöntemi.

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

##  <a name="ctor"></a> propagator_block

Oluşturur bir `propagator_block` nesne.

```
propagator_block();
```

##  <a name="dtor"></a> ~ propagator_block

Yok eder bir `propagator_block` nesne.

```
virtual ~propagator_block();
```

##  <a name="register_filter"></a> register_filter

Alınan her ileti üzerinde çağrılacak bir filtre yöntemi kaydeder.

```
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Filtreyi*<br/>
Filter yöntemi.

##  <a name="remove_network_links"></a> remove_network_links

Tüm kaynak ve hedef ağ bağlantıları buradan kaldırır `propagator_block` nesne.

```
void remove_network_links();
```

##  <a name="send"></a> Gönder

Bu blok bir iletiyi zaman uyumlu olarak başlatır. Çağıran bir `ISource` blok. Bu işlev tamamlandığında, ileti bloğunun içine zaten yayıldıktan.

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

Bu yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) ya da özel durum `_PMessage` veya `_PSource` parametresi `NULL`.

##  <a name="send_message"></a> send_message

Türetilen bir sınıfta geçersiz kılındığında, bu yöntem zaman uyumlu olarak gelen bir ileti geçirir bir `ISource` bu blok `propagator_block` nesne. Tarafından çağrılan `send` bir kaynak bloğu tarafından çağrıldığında yöntemi.

```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu bloğu döndüren `declined` türetilmiş sınıf tarafından geçersiz kılınmadığı sürece.

##  <a name="unlink_source"></a> unlink_source

Bu bir belirtilen kaynak blok olan bağlantısını kesen `propagator_block` nesne.

```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
Bir işaretçi `ISource` bağlantısının kaldırılması için bloğu.

##  <a name="unlink_sources"></a> unlink_sources

Bu, tüm kaynak bloklar olan bağlantısını kesen `propagator_block` nesne.

```
virtual void unlink_sources();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[source_block Sınıfı](source-block-class.md)<br/>
[ITarget Sınıfı](itarget-class.md)
