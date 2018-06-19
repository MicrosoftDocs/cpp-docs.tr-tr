---
title: propagator_block sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb908bf108bb3ddff375506225b9be97b2898ca5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694020"
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
 `_TargetLinkRegistry`  
 Hedef bağlantılar tutmak için kullanılacak bağlantı kayıt defteri.  
  
 `_SourceLinkRegistry`  
 Kaynak bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.  
  
 `_MessageProcessorType`  
 İleti işleme için işlemci türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`source_iterator`|Yineleyici için tür `source_link_manager` bu `propagator_block`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[propagator_block](#ctor)|Oluşturan bir `propagator_block` nesnesi.|  
|[~ propagator_block yok Edicisi](#dtor)|Bozar bir `propagator_block` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Yayma](#propagate)|Zaman uyumsuz olarak bir ileti bu hedef blok kaynak bloğundan geçirir.|  
|[Gönder](#send)|Zaman uyumlu olarak bu bloğu için bir ileti başlatır. Çağıran bir `ISource` bloğu. Bu işlev tamamlandığında, ileti zaten bloğuna yayılan.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[decline_incoming_messages](#decline_incoming_messages)|Blok için yeni ileti reddedildi olduğunu gösterir.|  
|[initialize_source_and_target](#initialize_source_and_target)|Temel nesneyi başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.|  
|[link_source](#link_source)|Belirtilen kaynak blok için bağlantılar `propagator_block` nesnesi.|  
|[process_input_messages](#process_input_messages)|İşlem iletileri girin. Bu yalnızca source_block türetilen yayılması blokları yararlıdır (geçersiz kılmaları [source_block::process_input_messages](source-block-class.md#process_input_messages).)|  
|[propagate_message](#propagate_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu bloğuna `propagator_block` nesnesi. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[register_filter](#register_filter)|Her alınan iletide çağrılacak bir filtre yöntemi kaydeder.|  
|[remove_network_links](#remove_network_links)|Tüm kaynak ve hedef ağ bağlantıları öğesinden kaldırır `propagator_block` nesnesi.|  
|[send_message](#send_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem gelen iletiyi zaman uyumlu olarak geçirir. bir `ISource` bu bloğuna `propagator_block` nesnesi. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[unlink_source](#unlink_source)|Belirtilen kaynak blok bu bağlantıyı keser `propagator_block` nesnesi.|  
|[unlink_sources](#unlink_sources)|Tüm kaynak blokları bu bağlantıyı keser `propagator_block` nesnesi. (Geçersiz kılmaları [Itarget::unlink_sources](itarget-class.md#unlink_sources).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Birden çok devralma önlemek için `propagator_block` sınıfının devraldığı `source_block` sınıfı ve `ITarget` soyut sınıf. Uygulamasındaki işlevselliğin çoğu `target_block` sınıfı burada çoğaltılır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 [Itarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 `propagator_block`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="decline_incoming_messages"></a> decline_incoming_messages 

 Blok için yeni ileti reddedildi olduğunu gösterir.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi yok etme işlemi devam ederken yeni iletiler reddetti emin olmak için yıkıcı tarafından çağrılır.  
  
##  <a name="initialize_source_and_target"></a> initialize_source_and_target 

 Temel nesneyi başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.  
  
```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PScheduler`  
 Görevleri planlama için kullanılacak Zamanlayıcı.  
  
 `_PScheduleGroup`  
 Görevleri planlama için kullanılacak zamanlamayı grubu.  
  
##  <a name="link_source"></a> link_source 

 Belirtilen kaynak blok için bağlantılar `propagator_block` nesnesi.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PSource`  
 Bir işaretçi `ISource` bağlanacağı bloğu.  
  
##  <a name="process_input_messages"></a> process_input_messages 

 İşlem iletileri girin. Bu yalnızca source_block türetilen yayılması blokları kullanışlıdır  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
  
##  <a name="propagate"></a> Yayma 

 Zaman uyumsuz olarak bir ileti bu hedef blok kaynak bloğundan geçirir.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `propagate` Yöntemi, üzerinde hedef blok bağlantılı kaynak blok tarafından çağrılır. Bir değil sırada zaten iletiyi işlemek için zaman uyumsuz bir görevi veya yürütme yukarı sıralar.  
  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) her iki özel durum `_PMessage` veya `_PSource` parametresi `NULL`.  
  
##  <a name="propagate_message"></a> propagate_message 

 Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu bloğuna `propagator_block` nesnesi. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
##  <a name="ctor"></a> propagator_block 

 Oluşturan bir `propagator_block` nesnesi.  
  
```
propagator_block();
```  
  
##  <a name="dtor"></a> ~ propagator_block 

 Bozar bir `propagator_block` nesnesi.  
  
```
virtual ~propagator_block();
```  
  
##  <a name="register_filter"></a> register_filter 

 Her alınan iletide çağrılacak bir filtre yöntemi kaydeder.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filter`  
 Filter yöntemi.  
  
##  <a name="remove_network_links"></a> remove_network_links 

 Tüm kaynak ve hedef ağ bağlantıları öğesinden kaldırır `propagator_block` nesnesi.  
  
```
void remove_network_links();
```  
  
##  <a name="send"></a> Gönder 

 Zaman uyumlu olarak bu bloğu için bir ileti başlatır. Çağıran bir `ISource` bloğu. Bu işlev tamamlandığında, ileti zaten bloğuna yayılan.  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) her iki özel durum `_PMessage` veya `_PSource` parametresi `NULL`.  
  
##  <a name="send_message"></a> send_message 

 Türetilen bir sınıfta geçersiz kılındığında, bu yöntem gelen iletiyi zaman uyumlu olarak geçirir. bir `ISource` bu bloğuna `propagator_block` nesnesi. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu bloğu döndüren `declined` türetilmiş sınıf tarafından geçersiz kılınmadığı sürece.  
  
##  <a name="unlink_source"></a> unlink_source 

 Belirtilen kaynak blok bu bağlantıyı keser `propagator_block` nesnesi.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PSource`  
 Bir işaretçi `ISource` bağlantısız olacak bloğu.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 Tüm kaynak blokları bu bağlantıyı keser `propagator_block` nesnesi.  
  
```
virtual void unlink_sources();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [source_block sınıfı](source-block-class.md)   
 [ITarget Sınıfı](itarget-class.md)
