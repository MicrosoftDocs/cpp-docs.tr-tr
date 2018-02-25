---
title: "overwrite_buffer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59eeadecdcf5d1a6333f08b68f98976ce9e6ea78
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="overwritebuffer-class"></a>overwrite_buffer Sınıfı
Bir `overwrite_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` aynı anda tek bir ileti depolama yeteneği. Yeni iletiler önceden tutulan olanları üzerine yazın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İleti yükü türünü depolanır ve arabellek yayılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[overwrite_buffer](#ctor)|Fazla Yüklendi. Oluşturan bir `overwrite_buffer` ileti bloğu.|  
|[~ overwrite_buffer yok Edicisi](#dtor)|Bozar `overwrite_buffer` ileti bloğu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[has_value](#has_value)|Denetler olup olmadığını bu `overwrite_buffer` ileti bloğu değerine henüz sahip.|  
|[value](#value)|İçinde depolanan iletinin geçerli yükü bir başvuru edinir `overwrite_buffer` ileti bloğu.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `overwrite_buffer` iletinin bir kopyasını çağırana döndürme ileti bloğu.|  
|[consume_message](#consume_message)|Daha önce tarafından sunulan bir ileti tüketir `overwrite_buffer` blok Mesajlaşma ve iletinin bir kopyasını çağırana döndürme hedef tarafından ayrılmış.|  
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `overwrite_buffer` ileti bloğu.|  
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `overwrite_buffer` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Basamak `message _PMessage` bu `overwrite_buffer` blok Mesajlaşma ve tüm bağlı hedefleri sunar.|  
|[release_message](#release_message)|Bir önceki iletiyi ayırma serbest bırakır. (Overrides [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir ileti ayırır `overwrite_buffer` ileti bloğu. (Overrides [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Bir ayırma serbest bırakıldıktan sonra yayma sürdürür. (Overrides [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `overwrite_buffer` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir `overwrite_buffer` ileti bloğu yayan saklı kendi iletinin her hedeflerine kopyalarını çıkışı.  
  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 [Itarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept_message"></a> accept_message 

 Bu tarafından sunulan bir iletiyi kabul `overwrite_buffer` iletinin bir kopyasını çağırana döndürme ileti bloğu.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `overwrite_buffer` Şu anda tutulan ileti sahipliğini aktarma yerine blok döndürür hedeflerine iletiye kopyalarını Mesajlaşma.  
  
##  <a name="consume_message"></a> consume_message 

 Daha önce tarafından sunulan bir ileti tüketir `overwrite_buffer` blok Mesajlaşma ve iletinin bir kopyasını çağırana döndürme hedef tarafından ayrılmış.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde `accept`, her zaman için yapılan bir çağrı tarafından öncesinde ancak `reserve`.  
  
##  <a name="has_value"></a> has_value 

 Denetler olup olmadığını bu `overwrite_buffer` ileti bloğu değerine henüz sahip.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` bir değer blok aldıysa `false` Aksi takdirde.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `overwrite_buffer` ileti bloğu.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Yeni bağlantılı hedefi için bir işaretçi.  
  
##  <a name="dtor"></a> ~ overwrite_buffer 

 Bozar `overwrite_buffer` ileti bloğu.  
  
```
~overwrite_buffer();
```  
  
##  <a name="ctor"></a> overwrite_buffer 

 Oluşturan bir `overwrite_buffer` ileti bloğu.  
  
```
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filter`  
 Sunulan iletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `overwrite_buffer` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `overwrite_buffer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Türü `filter_method` functor imzaya sahip olduğu `bool (T const &)` hangi çağrılır bu tarafından `overwrite_buffer` sunulan iletisine kabul etmelidir olup olmadığını belirlemek için ileti bloğu.  
  
##  <a name="propagate_message"></a> propagate_message 

 Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `overwrite_buffer` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Basamak `message _PMessage` bu `overwrite_buffer` blok Mesajlaşma ve tüm bağlı hedefleri sunar.  
  
```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi bir `message` nesne bu `overwrite_buffer` sahipliğini sürdü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem geçerli iletisinde üzerine yazar `overwrite_buffer` yeni kabul edilen iletiyle `_PMessage`.  
  
##  <a name="send_message"></a> send_message 

 İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `overwrite_buffer` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
##  <a name="supports_anonymous_source">supports_anonymous_source</a> 

 Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Blok sunulan iletiler erteleyin değil çünkü.  
  
##  <a name="release_message"></a> release_message 

 Bir önceki iletiyi ayırma serbest bırakır.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
##  <a name="reserve_message"></a> reserve_message 

 Daha önce bu tarafından sunulan bir ileti ayırır `overwrite_buffer` ileti bloğu.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Ayrılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` İletiyi başarıyla ayrıldı, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonra `reserve` çağrılır, döndürürse `true`, her iki `consume` veya `release` alın veya iletinin sahipliğini serbest bırakmak için çağrılmalıdır.  
  
##  <a name="resume_propagation"></a> resume_propagation 

 Bir ayırma serbest bırakıldıktan sonra yayma sürdürür.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="value"></a> Değer 

 İçinde depolanan iletinin geçerli yükü bir başvuru edinir `overwrite_buffer` ileti bloğu.  
  
```
T value();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda depolanan ileti yükü.  
  
### <a name="remarks"></a>Açıklamalar  
 Depolanan değeriyle `overwrite_buffer` bu yöntem hemen sonra değiştirebilirsiniz. Bu yöntem, ileti şu anda depolanan, bir ileti geldiğinde kadar bekler `overwrite_buffer`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [unbounded_buffer sınıfı](unbounded-buffer-class.md)   
 [single_assignment Sınıfı](single-assignment-class.md)
