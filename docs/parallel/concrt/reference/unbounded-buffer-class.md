---
title: "unbounded_buffer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
dev_langs:
- C++
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecddf2327e3b2e29dd3c9a857227c03d9e880ef4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
Bir `unbounded_buffer` ileti bloğu birden çok hedef birden çok kaynak, sıralı `propagator_block` sınırsız bir ileti sayısı depolama yeteneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   class             _Type  
>  
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Type`  
 İleti yükü türünü depolanır ve arabellek yayılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[unbounded_buffer](#ctor)|Fazla Yüklendi. Oluşturan bir `unbounded_buffer` ileti bloğu.|  
|[~unbounded_buffer Destructor](#dtor)|Bozar `unbounded_buffer` ileti bloğu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[dequeue](#dequeue)|Bir öğeden kaldırır `unbounded_buffer` ileti bloğu.|  
|[Sıraya alma](#enqueue)|Bir öğe ekler `unbounded_buffer` ileti bloğu.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `unbounded_buffer` çağırana sahipliğini aktarma ileti bloğu.|  
|[consume_message](#consume_message)|Daha önce tarafından sunulan bir ileti tüketir `unbounded_buffer` blok Mesajlaşma ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `unbounded_buffer` ileti bloğu.|  
|[process_input_messages](#process_input_messages)|Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedefleri sağlamaya çalışır.|  
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `unbounded_buffer` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[propagate_output_messages](#propagate_output_messages)|Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedefleri sağlamaya çalışır. (Overrides [source_block::propagate_output_messages](source-block-class.md#propagate_output_messages).)|  
|[release_message](#release_message)|Bir önceki iletiyi ayırma serbest bırakır. (Overrides [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir ileti ayırır `unbounded_buffer` ileti bloğu. (Overrides [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Bir ayırma serbest bırakıldıktan sonra yayma sürdürür. (Overrides [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `unbounded_buffer` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  

 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 [Itarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `unbounded_buffer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept_message"></a> accept_message 

 Bu tarafından sunulan bir iletiyi kabul `unbounded_buffer` çağırana sahipliğini aktarma ileti bloğu.  
  
```  
virtual message<_Type> * accept_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
##  <a name="consume_message"></a> consume_message 

 Daha önce tarafından sunulan bir ileti tüketir `unbounded_buffer` blok Mesajlaşma ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
```  
virtual message<_Type> * consume_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde `accept`, her zaman için yapılan bir çağrı tarafından öncesinde ancak `reserve`.  
  
##  <a name="dequeue"></a> Dequeue 

 Bir öğeden kaldırır `unbounded_buffer` ileti bloğu.  
  
```  
_Type dequeue();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaldırılmasını iletinin yükü `unbounded_buffer`.  
  
##  <a name="enqueue">Sıraya alma</a> 

 Bir öğe ekler `unbounded_buffer` ileti bloğu.  
  
```  
bool enqueue(  
   _Type const&                 _Item  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Item`  
 Eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` öğesi kabul edildiyse `false` Aksi takdirde.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `unbounded_buffer` ileti bloğu.  
  
```  
virtual void link_target_notification(  
   _Inout_ ITarget<_Type> *                 _PTarget  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Yeni bağlantılı hedefi için bir işaretçi.  
  
##  <a name="propagate_message"></a> propagate_message 

 Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `unbounded_buffer` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```  
virtual message_status propagate_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md#message_status) hedef iletiyle yapmak karar göstergesi.  
  
##  <a name="propagate_output_messages"></a> propagate_output_messages 

 Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedefleri sağlamaya çalışır.  
  
```  
virtual void propagate_output_messages();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başka bir ileti zaten bu öncesinde olup olmadığını `unbounded_buffer`, bağlantılı hedefleri yayma herhangi daha önceki iletileri kabul veya tüketilen kadar gerçekleşmez. İlk hedefine başarıyla bağlandı `accept` veya `consume` ileti aittir ve başka bir hedef sonra ileti alabilirsiniz.  
  
##  <a name="process_input_messages">process_input_messages</a> 

 Basamak `message` `_PMessage` bu `unbounded_buffer` ileti bloğu ve tüm bağlı hedefleri sağlamaya çalışır.  
  
```  
virtual void process_input_messages(  
   _Inout_ message<_Type> *                 _PMessage  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
  
##  <a name="release_message"></a> release_message 

 Bir önceki iletiyi ayırma serbest bırakır.  
  
```  
virtual void release_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
##  <a name="reserve_message"></a> reserve_message 

 Daha önce bu tarafından sunulan bir ileti ayırır `unbounded_buffer` ileti bloğu.  
  
```  
virtual bool reserve_message(  
   runtime_object_identity                 _MsgId  
);  
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

 İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `unbounded_buffer` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
```  
virtual message_status send_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md#message_status) hedef iletiyle yapmak karar göstergesi.  
  
##  <a name="supports_anonymous_source">supports_anonymous_source</a> 

 Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem.  
  
```  
virtual bool supports_anonymous_source();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Blok sunulan iletiler erteleyin değil çünkü.  
  
##  <a name="ctor"></a> unbounded_buffer 

 Oluşturan bir `unbounded_buffer` ileti bloğu.  
  
```  
unbounded_buffer();  
  
unbounded_buffer(  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler,  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup,  
   filter_method const&                 _Filter  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filter`  
 Sunulan iletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `unbounded_buffer` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `unbounded_buffer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Türü `filter_method` functor imzaya sahip olduğu `bool (_Type const &)` hangi çağrılır bu tarafından `unbounded_buffer` sunulan iletisine kabul etmelidir olup olmadığını belirlemek için ileti bloğu.  
  
##  <a name="dtor"></a> ~ unbounded_buffer 

 Bozar `unbounded_buffer` ileti bloğu.  
  
```  
~unbounded_buffer();  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [overwrite_buffer sınıfı](overwrite-buffer-class.md)   
 [single_assignment Sınıfı](single-assignment-class.md)


