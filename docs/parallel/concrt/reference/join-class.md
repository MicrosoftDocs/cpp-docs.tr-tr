---
title: "join sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
dev_langs: C++
helpviewer_keywords: join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5166dd4d8c57d3d64fb9d794319b7f2b0398e3d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="join-class"></a>join Sınıfı
A `join` ileti bloğu bir tek-hedef, çok kaynaklı, sıralı `propagator_block` bir araya getiren birlikte türden iletileri `T` her kaynaklarının.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```   
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İletilerin yükü türünü alanına katılmış ve bloğu tarafından yayılır.  
  
 `_Jtype`  
 Türü, `join` ya da bu olduğu blok `greedy` veya`non_greedy`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Birleştirme](#ctor)|Fazla Yüklendi. Oluşturan bir `join` ileti bloğu.|  
|[~ join yok Edicisi](#dtor)|Bozar `join` bloğu.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `join` çağırana sahipliğini aktarma ileti bloğu.|  
|[consume_message](#consume_message)|Daha önce tarafından sunulan bir ileti tüketir `join` blok Mesajlaşma ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `join` ileti bloğu.|  
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `join` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Tüm bir ileti yayılan her kaynaktan gelen bir giriş iletisi içeren bir çıktı iletisi oluşturur. Her hedeflerine gönderir Bu çıktı iletisi.|  
|[release_message](#release_message)|Bir önceki iletiyi ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir ileti ayırır `join` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Bir ayırma serbest bırakıldıktan sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 [Itarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `join`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept_message"></a>accept_message 

 Bu tarafından sunulan bir iletiyi kabul `join` çağırana sahipliğini aktarma ileti bloğu.  
  
```
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
##  <a name="consume_message"></a>consume_message 

 Daha önce tarafından sunulan bir ileti tüketir `join` blok Mesajlaşma ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
```
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde `accept`, her zaman için yapılan bir çağrı tarafından öncesinde ancak `reserve`.  
  
##  <a name="ctor"></a>Birleştirme 

 Oluşturan bir `join` ileti bloğu.  
  
```
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_NumInputs`  
 Bu girdi sayısı `join` blok izin verilir.  
  
 `_Filter`  
 Sunulan iletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `join` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `join` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Türü `filter_method` functor imzaya sahip olduğu `bool (T const &)` hangi çağrılır bu tarafından `join` sunulan iletisine kabul etmelidir olup olmadığını belirlemek için ileti bloğu.  
  
##  <a name="dtor"></a>~ Birleştirme 

 Bozar `join` bloğu.  
  
```
~join();
```  
  
##  <a name="link_target_notification"></a>link_target_notification 

 Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `join` ileti bloğu.  
  
```
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```  
  
##  <a name="propagate_message"></a>propagate_message 

 Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `join` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
message_status propagate_message(
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
  
##  <a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 Tüm bir ileti yayılan her kaynaktan gelen bir giriş iletisi içeren bir çıktı iletisi oluşturur. Her hedeflerine gönderir Bu çıktı iletisi.  
  
```
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
```  
  
##  <a name="release_message"></a>release_message 

 Bir önceki iletiyi ayırma serbest bırakır.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
##  <a name="reserve_message"></a>reserve_message 

 Daha önce bu tarafından sunulan bir ileti ayırır `join` ileti bloğu.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`İletiyi başarıyla ayrıldı, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonra `reserve` çağrılır, döndürürse `true`, her iki `consume` veya `release` alın veya iletinin sahipliğini serbest bırakmak için çağrılmalıdır.  
  
##  <a name="resume_propagation"></a>resume_propagation 

 Bir ayırma serbest bırakıldıktan sonra yayma sürdürür.  
  
```
virtual void resume_propagation();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [seçenek sınıfı](choice-class.md)   
 [multitype_join Sınıfı](multitype-join-class.md)
