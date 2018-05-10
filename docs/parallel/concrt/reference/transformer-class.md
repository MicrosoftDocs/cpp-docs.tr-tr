---
title: Transformer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- transformer
- AGENTS/concurrency::transformer
- AGENTS/concurrency::transformer::transformer
- AGENTS/concurrency::transformer::accept_message
- AGENTS/concurrency::transformer::consume_message
- AGENTS/concurrency::transformer::link_target_notification
- AGENTS/concurrency::transformer::propagate_message
- AGENTS/concurrency::transformer::propagate_to_any_targets
- AGENTS/concurrency::transformer::release_message
- AGENTS/concurrency::transformer::reserve_message
- AGENTS/concurrency::transformer::resume_propagation
- AGENTS/concurrency::transformer::send_message
- AGENTS/concurrency::transformer::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- transformer class
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9ea43e1d3f6f369b93e92e91fa3606cf7d6af5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="transformer-class"></a>transformer Sınıfı
A `transformer` ileti bloğu bir tek-hedef, çok kaynaklı, sıralı `propagator_block` bir türden iletileri kabul edebilir ve farklı türde bir ileti sınırsız bir sayısı depolayabilen yeteneğine sahiptir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```   
  
#### <a name="parameters"></a>Parametreler  
 `_Input`  
 Arabellek kabul iletileri yük türü.  
  
 `_Output`  
 İleti yükü türünü depolanır ve çıkış arabelleği ile yayılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Transformer](#ctor)|Fazla Yüklendi. Oluşturan bir `transformer` ileti bloğu.|  
|[~ transformer yok Edicisi](#dtor)|Bozar `transformer` ileti bloğu.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `transformer` çağırana sahipliğini aktarma ileti bloğu.|  
|[consume_message](#consume_message)|Daha önce tarafından sunulan bir ileti tüketir `transformer` ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `transformer` ileti bloğu.|  
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `transformer` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Transformer işlevi, giriş iletilerde yürütür.|  
|[release_message](#release_message)|Bir önceki iletiyi ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir ileti ayırır `transformer` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Bir ayırma serbest bırakıldıktan sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `transformer` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 [Itarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `transformer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept_message"></a> accept_message 

 Bu tarafından sunulan bir iletiyi kabul `transformer` çağırana sahipliğini aktarma ileti bloğu.  
  
```
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
##  <a name="consume_message"></a> consume_message 

 Daha önce tarafından sunulan bir ileti tüketir `transformer` ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
```
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde `accept`, her zaman için yapılan bir çağrı tarafından öncesinde ancak `reserve`.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `transformer` ileti bloğu.  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```  
  
##  <a name="propagate_message"></a> propagate_message 

 Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `transformer` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Transformer işlevi, giriş iletilerde yürütür.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```  
  
##  <a name="release_message"></a> release_message 

 Bir önceki iletiyi ayırma serbest bırakır.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
##  <a name="reserve_message"></a> reserve_message 

 Daha önce bu tarafından sunulan bir ileti ayırır `transformer` ileti bloğu.  
  
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

 İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `transformer` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Blok sunulan iletiler erteleyin değil çünkü.  
  
##  <a name="ctor"></a> Transformer 

 Oluşturan bir `transformer` ileti bloğu.  
  
```
transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Func`  
 Kabul edilen her ileti için çağrılacak işlev.  
  
 `_PTarget`  
 Dönüştürücü ile bağlamak için hedef blok için bir işaretçi.  
  
 `_Filter`  
 Sunulan iletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `transformer` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `transformer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Türü `_Transform_method` functor imzaya sahip olduğu `_Output (_Input const &)` hangi çağrılır bu tarafından `transformer` bir iletiyi işlemek için ileti bloğu.  
  
 Türü `filter_method` functor imzaya sahip olduğu `bool (_Input const &)` hangi çağrılır bu tarafından `transformer` sunulan iletisine kabul etmelidir olup olmadığını belirlemek için ileti bloğu.  
  
##  <a name="dtor"></a> ~ transformer 

 Bozar `transformer` ileti bloğu.  
  
```
~transformer();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [call Sınıfı](call-class.md)
