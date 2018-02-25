---
title: "single_assignment sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
dev_langs:
- C++
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f4bf3effde2c7012a3ed901c9279bcc161cd670
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="singleassignment-class"></a>single_assignment Sınıfı
A `single_assignment` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` yeteneğine sahip tek bir depolama yazma-sonra `message`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İletinin yükü türü depolanır ve arabellek yayılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[single_assignment](#ctor)|Fazla Yüklendi. Oluşturan bir `single_assignment` ileti bloğu.|  
|[~ single_assignment yok Edicisi](#dtor)|Bozar `single_assignment` ileti bloğu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[has_value](#has_value)|Denetler olup olmadığını bu `single_assignment` ileti bloğu başlatıldıysa bir değerle henüz.|  
|[value](#value)|İçinde depolanan iletinin geçerli yükü bir başvuru edinir `single_assignment` ileti bloğu.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `single_assignment` iletinin bir kopyasını çağırana döndürme ileti bloğu.|  
|[consume_message](#consume_message)|Daha önce tarafından sunulan bir ileti tüketir `single_assignment` ve iletinin bir kopyasını çağırana döndürme hedef tarafından ayrılmış.|  
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `single_assignment` ileti bloğu.|  
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `single_assignment` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Basamak `message _PMessage` bu `single_assignment` blok Mesajlaşma ve tüm bağlı hedefleri sunar.|  
|[release_message](#release_message)|Bir önceki iletiyi ayırma serbest bırakır. (Overrides [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir ileti ayırır `single_assignment` ileti bloğu. (Overrides [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Bir ayırma serbest bırakıldıktan sonra yayma sürdürür. (Overrides [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `single_assignment` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `single_assignment` ileti bloğu yayar, iletinin her hedef kopyalarını çıkışı.  
  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 [Itarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `single_assignment`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept_message"></a> accept_message 

 Bu tarafından sunulan bir iletiyi kabul `single_assignment` iletinin bir kopyasını çağırana döndürme ileti bloğu.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `single_assignment` Şu anda tutulan ileti sahipliğini aktarma yerine blok döndürür hedeflerine iletiye kopyalarını Mesajlaşma.  
  
##  <a name="consume_message"></a> consume_message 

 Daha önce tarafından sunulan bir ileti tüketir `single_assignment` ve iletinin bir kopyasını çağırana döndürme hedef tarafından ayrılmış.  
  
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

 Denetler olup olmadığını bu `single_assignment` ileti bloğu başlatıldıysa bir değerle henüz.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` bir değer blok aldıysa `false` Aksi takdirde.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `single_assignment` ileti bloğu.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Yeni bağlantılı hedefi için bir işaretçi.  
  
##  <a name="propagate_message"></a> propagate_message 

 Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `single_assignment` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
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

 Basamak `message` `_PMessage` bu `single_assignment` blok Mesajlaşma ve tüm bağlı hedefleri sunar.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi bir `message` bu `single_assignment` ileti bloğu sahipliğini gerçekleştirilecek.  
  
##  <a name="release_message"></a> release_message 

 Bir önceki iletiyi ayırma serbest bırakır.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
##  <a name="reserve_message"></a> reserve_message 

 Daha önce bu tarafından sunulan bir ileti ayırır `single_assignment` ileti bloğu.  
  
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
  
##  <a name="send_message"></a> send_message 

 İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `single_assignment` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
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
  
##  <a name="ctor"></a> single_assignment 

 Oluşturan bir `single_assignment` ileti bloğu.  
  
```
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filter`  
 Sunulan iletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `single_assignment` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `single_assignment` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Türü `filter_method` functor imzaya sahip olduğu `bool (T const &)` hangi çağrılır bu tarafından `single_assignment` sunulan iletisine kabul etmelidir olup olmadığını belirlemek için ileti bloğu.  
  
##  <a name="dtor"></a> ~ single_assignment 

 Bozar `single_assignment` ileti bloğu.  
  
```
~single_assignment();
```  
  
##  <a name="value"></a> Değer 

 İçinde depolanan iletinin geçerli yükü bir başvuru edinir `single_assignment` ileti bloğu.  
  
```
T const& value();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı iletinin yükü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, ileti şu anda depolanan, bir ileti geldiğinde kadar bekler `single_assignment` ileti bloğu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [overwrite_buffer sınıfı](overwrite-buffer-class.md)   
 [unbounded_buffer sınıfı](unbounded-buffer-class.md)

