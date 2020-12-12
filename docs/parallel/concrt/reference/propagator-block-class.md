---
description: 'Hakkında daha fazla bilgi edinin: propagator_block sınıfı'
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
ms.openlocfilehash: 4dd006829e01f663be20be76a2cc2e0364ef7b38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115293"
---
# <a name="propagator_block-class"></a>propagator_block Sınıfı

`propagator_block`Sınıfı, hem kaynak hem de hedef olan ileti blokları için soyut bir temel sınıftır. Hem hem de sınıflarının işlevlerini birleştirir `source_block` `target_block` .

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>Parametreler

*_TargetLinkRegistry*<br/>
Hedef bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.

*_SourceLinkRegistry*<br/>
Kaynak bağlantılarını tutmak için kullanılacak bağlantı kayıt defteri.

*_MessageProcessorType*<br/>
İleti işleme için işlemci türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`source_iterator`|Bunun için yineleyicinin türü `source_link_manager` `propagator_block` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[propagator_block](#ctor)|Bir `propagator_block` nesnesi oluşturur.|
|[~ propagator_block yok edici](#dtor)|Bir nesneyi yok eder `propagator_block` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[aktarabilirsiniz](#propagate)|Bir kaynak bloğundan bu hedef bloğa zaman uyumsuz bir ileti geçirir.|
|[Gönder](#send)|Zaman uyumlu olarak bu bloğa bir ileti başlatır. Bir blok tarafından çağırılır `ISource` . Bu işlev tamamlandığında, ileti zaten bloğa yayılmış olur.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|Yeni iletilerin reddedime bloğunun olduğunu gösterir.|
|[initialize_source_and_target](#initialize_source_and_target)|Temel nesneyi başlatır. Özellikle, `message_processor` nesnenin başlatılmış olması gerekir.|
|[link_source](#link_source)|Belirtilen kaynak bloğunu bu `propagator_block` nesneye bağlar.|
|[process_input_messages](#process_input_messages)|İşlem girişi iletileri. Bu yalnızca source_block türetilen (geçersiz kılmalar [source_block::p rocess_input_messages](source-block-class.md#process_input_messages)olan yayıcı blokları için yararlıdır.)|
|[propagate_message](#propagate_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem bir `ISource` bloondan bu nesneye zaman uyumsuz bir ileti geçirir `propagator_block` . `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[register_filter](#register_filter)|Alınan her iletide çağrılacak bir filtre yöntemi kaydeder.|
|[remove_network_links](#remove_network_links)|Bu nesneden tüm kaynak ve hedef ağ bağlantılarını kaldırır `propagator_block` .|
|[send_message](#send_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem bir bloğundan bir iletiyi `ISource` Bu nesneye eşzamanlı olarak geçirir `propagator_block` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.|
|[unlink_source](#unlink_source)|Bu nesneden belirtilen kaynak bloğunun bağlantılarını Kaldır `propagator_block` .|
|[unlink_sources](#unlink_sources)|Bu nesneden tüm kaynak bloklarının bağlantılarını Kaldır `propagator_block` . ( [IComparer:: unlink_sources](itarget-class.md#unlink_sources)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

Birden çok devralmayı önlemek için, `propagator_block` sınıf `source_block` sınıfından ve `ITarget` soyut sınıftan devralınır. Sınıftaki işlevlerin çoğu `target_block` burada çoğaltılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="decline_incoming_messages"></a><a name="decline_incoming_messages"></a> decline_incoming_messages

Yeni iletilerin reddedime bloğunun olduğunu gösterir.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yok etme işlemi devam ederken yeni iletilerin reddedildiğini sağlamak için yok edici tarafından çağırılır.

## <a name="initialize_source_and_target"></a><a name="initialize_source_and_target"></a> initialize_source_and_target

Temel nesneyi başlatır. Özellikle, `message_processor` nesnenin başlatılmış olması gerekir.

```cpp
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Görevleri zamanlamak için kullanılacak Zamanlayıcı.

*_PScheduleGroup*<br/>
Görevleri zamanlamak için kullanılacak zamanlama grubu.

## <a name="link_source"></a><a name="link_source"></a> link_source

Belirtilen kaynak bloğunu bu `propagator_block` nesneye bağlar.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
Bağlanılacak bloğa yönelik bir işaretçi `ISource` .

## <a name="process_input_messages"></a><a name="process_input_messages"></a> process_input_messages

İşlem girişi iletileri. Bu yalnızca source_block türetilen yayıcı blokları için yararlıdır

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

## <a name="propagate"></a><a name="propagate"></a> aktarabilirsiniz

Bir kaynak bloğundan bu hedef bloğa zaman uyumsuz bir ileti geçirir.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

`propagate`Yöntemi, bağlantılı bir kaynak bloğu tarafından bir hedef blok üzerinde çağrılır. Zaten kuyruğa alınmış veya Yürütülmeyen bir iletiyi işlemek için zaman uyumsuz bir görev kuyruğa alır.

Ya da parametresi ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum `_PMessage` oluşturur `_PSource` `NULL` .

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem bir `ISource` bloondan bu nesneye zaman uyumsuz bir ileti geçirir `propagator_block` . `propagate`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

## <a name="propagator_block"></a><a name="ctor"></a> propagator_block

Bir `propagator_block` nesnesi oluşturur.

```cpp
propagator_block();
```

## <a name="propagator_block"></a><a name="dtor"></a> ~ propagator_block

Bir nesneyi yok eder `propagator_block` .

```cpp
virtual ~propagator_block();
```

## <a name="register_filter"></a><a name="register_filter"></a> register_filter

Alınan her iletide çağrılacak bir filtre yöntemi kaydeder.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parametreler

*_Filter*<br/>
Filtre yöntemi.

## <a name="remove_network_links"></a><a name="remove_network_links"></a> remove_network_links

Bu nesneden tüm kaynak ve hedef ağ bağlantılarını kaldırır `propagator_block` .

```cpp
void remove_network_links();
```

## <a name="send"></a><a name="send"></a> Gönder

Zaman uyumlu olarak bu bloğa bir ileti başlatır. Bir blok tarafından çağırılır `ISource` . Bu işlev tamamlandığında, ileti zaten bloğa yayılmış olur.

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

Ya da parametresi ise, bu yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_PMessage` `_PSource` `NULL` .

## <a name="send_message"></a><a name="send_message"></a> send_message

Türetilmiş bir sınıfta geçersiz kılınırsa, bu yöntem bir bloğundan bir iletiyi `ISource` Bu nesneye eşzamanlı olarak geçirir `propagator_block` . `send`Kaynak bloğu tarafından çağrıldığında yöntemi tarafından çağrılır.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu blok `declined` türetilmiş bir sınıf tarafından geçersiz kılınmadıkça döndürür.

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

Bu nesneden belirtilen kaynak bloğunun bağlantılarını Kaldır `propagator_block` .

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource`Bağlantısı kaldırılacak bloğa yönelik bir işaretçi.

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

Bu nesneden tüm kaynak bloklarının bağlantılarını Kaldır `propagator_block` .

```cpp
virtual void unlink_sources();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[source_block sınıfı](source-block-class.md)<br/>
[IComparer sınıfı](itarget-class.md)
