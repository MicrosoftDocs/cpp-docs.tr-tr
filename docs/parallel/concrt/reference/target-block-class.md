---
title: target_block sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 754bc6add99974ff204c977e47f35486cc830d95
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693984"
---
# <a name="targetblock-class"></a>target_block Sınıfı
`target_block` Sınıfı, temel bağlantı yönetim işlevleri sağlayan Özet temel sınıf ve hedef için hata denetimi yalnızca engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_SourceLinkRegistry`  
 Kaynak bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.  
  
 `_MessageProcessorType`  
 İleti işleme için işlemci türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`source_iterator`|Yineleyici için tür `source_link_manager` bu `target_block` nesnesi.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[target_block](#ctor)|Oluşturan bir `target_block` nesnesi.|  
|[~ target_block yok Edicisi](#dtor)|Bozar `target_block` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Yayma](#propagate)|Zaman uyumsuz olarak bir ileti bu hedef blok kaynak bloğundan geçirir.|  
|[Gönder](#send)|Zaman uyumlu olarak bir ileti bu hedef blok kaynak bloğundan geçirir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[async_send](#async_send)|Zaman uyumsuz olarak işlemek için bir ileti gönderir.|  
|[decline_incoming_messages](#decline_incoming_messages)|Blok için yeni ileti reddedildi olduğunu gösterir.|  
|[enable_batched_processing](#enable_batched_processing)|Bu bloğu için işleme toplu hale olanak tanır.|  
|[initialize_target](#initialize_target)|Temel nesneyi başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.|  
|[link_source](#link_source)|Belirtilen kaynak blok için bağlantılar `target_block` nesnesi.|  
|[process_input_messages](#process_input_messages)|Girdi olarak alınan iletileri işler.|  
|[process_message](#process_message)|Türetilen bir sınıfta geçersiz kılındığında, bunu kabul edildi bir ileti işler `target_block` nesnesi.|  
|[propagate_message](#propagate_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu bloğuna `target_block` nesnesi. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[register_filter](#register_filter)|Alınan her ileti çağrılacak bir filtre yöntemi kaydeder.|  
|[remove_sources](#remove_sources)|Tüm kaynakları bekleyen zaman uyumsuz gönderme işlemleri için bekledikten sonra bağlantıyı keser.|  
|[send_message](#send_message)|Türetilen bir sınıfta geçersiz kılındığında, bu yöntem gelen iletiyi zaman uyumlu olarak geçirir. bir `ISource` bu bloğuna `target_block` nesnesi. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[sync_send](#sync_send)|Eşzamanlı olarak işlemek için bir ileti gönderin.|  
|[unlink_source](#unlink_source)|Belirtilen kaynak blok bu bağlantıyı keser `target_block` nesnesi.|  
|[unlink_sources](#unlink_sources)|Tüm kaynak blokları bu bağlantıyı keser `target_block` nesnesi. (Geçersiz kılmaları [Itarget::unlink_sources](itarget-class.md#unlink_sources).)|  
|[wait_for_async_sends](#wait_for_async_sends)|Tamamlamak tüm zaman uyumsuz yayma bekler.|  
  
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
 `_PMessage`  
 Gönderilen ileti için bir işaretçi.  
  
##  <a name="decline_incoming_messages"></a> decline_incoming_messages 

 Blok için yeni ileti reddedildi olduğunu gösterir.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi yok etme işlemi devam ederken yeni iletiler reddetti emin olmak için yıkıcı tarafından çağrılır.  
  
##  <a name="enable_batched_processing"></a> enable_batched_processing 

 Bu bloğu için işleme toplu hale olanak tanır.  
  
```
void enable_batched_processing();
```  
  
##  <a name="initialize_target"></a> initialize_target 

 Temel nesneyi başlatır. Özellikle, `message_processor` nesnenin başlatılması gerekiyor.  
  
```
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PScheduler`  
 Görevleri planlama için kullanılacak Zamanlayıcı.  
  
 `_PScheduleGroup`  
 Görevleri planlama için kullanılacak zamanlamayı grubu.  
  
##  <a name="link_source"></a> link_source 

 Belirtilen kaynak blok için bağlantılar `target_block` nesnesi.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PSource`  
 Bir işaretçi `ISource` bağlanacağı bloğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev doğrudan çağrılmamalıdır bir `target_block` nesnesi. Blokları birlikte kullanarak bağlanması `link_target` yöntemi `ISource` çağıracağı blokları `link_source` karşılık gelen hedef yöntemi.  
  
##  <a name="process_input_messages"></a> process_input_messages 

 Girdi olarak alınan iletileri işler.  
  
```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
  
##  <a name="process_message"></a> process_message 

 Türetilen bir sınıfta geçersiz kılındığında, bunu kabul edildi bir ileti işler `target_block` nesnesi.  
  
```
virtual void process_message(message<_Source_type> *);
```  
  
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
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) her iki özel durum `_PMessage` veya `_PSource` parametresi `NULL`.  
  
##  <a name="propagate_message"></a> propagate_message 

 Türetilen bir sınıfta geçersiz kılındığında, bu yöntem bir iletiden zaman uyumsuz olarak aktarır. bir `ISource` bu bloğuna `target_block` nesnesi. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
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
  
##  <a name="register_filter"></a> register_filter 

 Alınan her ileti çağrılacak bir filtre yöntemi kaydeder.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filter`  
 Filter yöntemi.  
  
##  <a name="remove_sources"></a> remove_sources 

 Tüm kaynakları bekleyen zaman uyumsuz gönderme işlemleri için bekledikten sonra bağlantıyı keser.  
  
```
void remove_sources();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm hedef blokları kendi yıkıcı kaynakları kaldırmak için bu yordamı çağırmanız gerekir.  
  
##  <a name="send"></a> Gönder 

 Zaman uyumlu olarak bir ileti bu hedef blok kaynak bloğundan geçirir.  
  
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
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) her iki özel durum `_PMessage` veya `_PSource` parametresi `NULL`.  
  
 Kullanarak `send` yöntemi ileti başlatma dışında ve bir ağ içinde ileti yayılmasına tehlikeli ve kilitlenmeye neden olabilir.  
  
 Zaman `send` döndürür, ileti algıladı ya da zaten kabul edildi ve hedef bloğu içine aktarılan ya da hedef tarafından reddedildi.  
  
##  <a name="send_message"></a> send_message 

 Türetilen bir sınıfta geçersiz kılındığında, bu yöntem gelen iletiyi zaman uyumlu olarak geçirir. bir `ISource` bu bloğuna `target_block` nesnesi. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu bloğu döndüren `declined` türetilmiş sınıf tarafından geçersiz kılınmadığı sürece.  
  
##  <a name="sync_send"></a> sync_send 

 Eşzamanlı olarak işlemek için bir ileti gönderin.  
  
```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Gönderilen ileti için bir işaretçi.  
  
##  <a name="ctor"></a> target_block 

 Oluşturan bir `target_block` nesnesi.  
  
```
target_block();
```  
  
##  <a name="dtor"></a> ~ target_block 

 Bozar `target_block` nesnesi.  
  
```
virtual ~target_block();
```  
  
##  <a name="unlink_source"></a> unlink_source 

 Belirtilen kaynak blok bu bağlantıyı keser `target_block` nesnesi.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PSource`  
 Bir işaretçi `ISource` bağlantısız olacak bloğu.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 Tüm kaynak blokları bu bağlantıyı keser `target_block` nesnesi.  
  
```
virtual void unlink_sources();
```  
  
##  <a name="wait_for_async_sends"></a> wait_for_async_sends 

 Tamamlamak tüm zaman uyumsuz yayma bekler.  
  
```
void wait_for_async_sends();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, tüm zaman uyumsuz işlemleri bloğu yok etme önce tamamlamak için bir süre beklendiğinden emin olmak için ileti bloğu Yıkıcılar tarafından kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [ITarget Sınıfı](itarget-class.md)
