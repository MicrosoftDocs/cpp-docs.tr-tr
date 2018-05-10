---
title: source_block sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64b9873ef6da00b4ef0fb03e43f61fa704484389
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="sourceblock-class"></a>source_block Sınıfı
`source_block` Sınıfı, yalnızca kaynak blokları için Özet temel sınıf. Sınıf iyi olarak ortak hata denetimleri temel bağlantı yönetimi işlevselliği sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_TargetLinkRegistry`  
 Hedef bağlantılar tutmak için kullanılacak bağlantı kayıt defteri.  
  
 `_MessageProcessorType`  
 İleti işleme için işlemci türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`target_iterator`|Bağlı hedefleri yol yineleyici.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[source_block](#ctor)|Oluşturan bir `source_block` nesnesi.|  
|[~ source_block yok Edicisi](#dtor)|Bozar `source_block` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Kabul et](#accept)|Bu tarafından sunulan bir iletiyi kabul `source_block` çağırana sahipliğini aktarma nesnesi.|  
|[acquire_ref](#acquire_ref)|Bu başvuru sayısı edinir `source_block` silinmesini önlemek için nesne.|  
|[Kullanma](#consume)|Daha önce bu tarafından sunulan bir ileti tüketir `source_block` nesne ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[link_target](#link_target)|Hedef blok için bağlantılar `source_block` nesnesi.|  
|[Sürüm](#release)|Bir önceki başarılı ileti ayırma serbest bırakır.|  
|[release_ref](#release_ref)|Serbest başvuru sayısı bu `source_block` nesnesi.|  
|[ayırma](#reserve)|Daha önce bu tarafından sunulan bir ileti ayırır `source_block` nesnesi.|  
|[unlink_target](#unlink_target)|Hedef blok bu bağlantıyı keser `source_block` nesnesi.|  
|[unlink_targets](#unlink_targets)|Tüm hedef blokları bu bağlantıyı keser `source_block` nesnesi. (Geçersiz kılmaları [Isource::unlink_targets](isource-class.md#unlink_targets).)|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept_message](#accept_message)|Türetilen bir sınıfta geçersiz kılındığında, kaynak tarafından sunulan bir ileti kabul eder. İleti blokları doğrulamak için bu yöntemi geçersiz kılma `_MsgId` ve bir ileti döndürür.|  
|[async_send](#async_send)|Zaman uyumsuz olarak iletileri kuyruklar ve bu zaten yapılmadıysa yayma görev başlar|  
|[consume_message](#consume_message)|Türetilen bir sınıfta geçersiz kılındığında, önceden ayrılmış bir ileti tüketir.|  
|[enable_batched_processing](#enable_batched_processing)|Bu bloğu için işleme toplu hale olanak tanır.|  
|[initialize_source](#initialize_source)|Başlatır `message_propagator` bu içinde `source_block`.|  
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `source_block` nesnesi.|  
|[process_input_messages](#process_input_messages)|İşlem iletileri girin. Bu yalnızca source_block türetilen yayılması blokları kullanışlıdır|  
|[propagate_output_messages](#propagate_output_messages)|Hedefleri iletileri yayılır.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Türetilen bir sınıfta geçersiz kılındığında, bağlantılı hedefleri bir bölümünü veya tamamını için belirli bir ileti yayar. Bu ileti blokları ana yayma yordamdır.|  
|[release_message](#release_message)|Türetilen bir sınıfta geçersiz kılındığında, bir önceki iletiyi ayırma serbest bırakır.|  
|[remove_targets](#remove_targets)|Bu kaynak bloğu tüm hedef bağlantıları kaldırır. Bu yıkıcı çağrılmalıdır.|  
|[reserve_message](#reserve_message)|Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir ileti ayırır `source_block` nesnesi.|  
|[resume_propagation](#resume_propagation)|Türetilen bir sınıfta geçersiz kılındığında, bir ayırma serbest bırakıldıktan sonra yayma devam ettirir.|  
|[sync_send](#sync_send)|Zaman uyumlu olarak iletileri kuyruklar ve bu zaten yapılmadıysa yayma görev başlatır.|  
|[unlink_target_notification](#unlink_target_notification)|Bir hedef öğesinden bağlantısız olduğunu bildiren bir geri çağırma `source_block` nesnesi.|  
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Tamamlamak tüm zaman uyumsuz yayma bekler. Bu yayılması özgü döndürme bekleme ileti blokları yıkıcılarda tüm zaman uyumsuz yayma bloğu yok etme önce bitirmek için zamana sahip olduğunuzdan emin olmak için kullanılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 İleti blokları bağlantı yönetimi ve bu sınıf tarafından sağlanan eşitleme yararlanmak için bu bloğunun türetilmelidir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 `source_block`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept"></a> Kabul et 

 Bu tarafından sunulan bir iletiyi kabul `source_block` çağırana sahipliğini aktarma nesnesi.  
  
```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `accept` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu ise parametresi `_PTarget` olan `NULL`.  
  
 `accept` Yöntemi, hedef tarafından çağrıldığında, bir ileti bu tarafından sunulan sırada `ISource` bloğu. İleti işaretçi döndürdü içine geçirilen olandan farklı olabilir `propagate` yöntemi `ITarget` iletinin bir kopyasını oluşturmak bu kaynak karar verirse, engelleyin.  
  
##  <a name="accept_message"></a> accept_message 

 Türetilen bir sınıfta geçersiz kılındığında, kaynak tarafından sunulan bir ileti kabul eder. İleti blokları doğrulamak için bu yöntemi geçersiz kılma `_MsgId` ve bir ileti döndürür.  
  
```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 Çalışma zamanı nesne kimliğini `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi çağıran şimdi sahipliği var. iletisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Sahipliği aktarmak için özgün ileti işaretçi döndürülmelidir. Sahipliği korumak için bir kopyasını ileti yükü yapılan ve döndürülen gerekir.  
  
##  <a name="acquire_ref"></a> acquire_ref 

 Bu başvuru sayısı edinir `source_block` silinmesini önlemek için nesne.  
  
```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` sırasında bu kaynak için bağlantılı nesne `link_target` yöntemi.  
  
##  <a name="async_send"></a> async_send 

 Zaman uyumsuz olarak iletileri kuyruklar ve bu zaten yapılmadıysa yayma görev başlar  
  
```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Msg`  
 Bir işaretçi bir `message` zaman uyumsuz olarak göndermek için nesne.  
  
##  <a name="consume"></a> Kullanma 

 Daha önce bu tarafından sunulan bir ileti tüketir `source_block` nesne ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Ayrılmış, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `consume` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu ise parametresi `_PTarget` olan `NULL`.  
  
 Yöntem oluşturulur bir [bad_target](bad-target-class.md) özel durumu ise parametresi `_PTarget` adlı hedef göstermiyor `reserve`.  
  
 `consume` Yöntemi benzer `accept`, her zaman için yapılan bir çağrı tarafından gelmelidir ancak `reserve` döndürülen `true`.  
  
##  <a name="consume_message"></a> consume_message 

 Türetilen bir sınıfta geçersiz kılındığında, önceden ayrılmış bir ileti tüketir.  
  
```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Kullanılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi çağıran şimdi sahipliği var. iletisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Benzer şekilde `accept`, her zaman için yapılan bir çağrı tarafından öncesinde ancak `reserve`.  
  
##  <a name="enable_batched_processing"></a> enable_batched_processing 

 Bu bloğu için işleme toplu hale olanak tanır.  
  
```
void enable_batched_processing();
```  
  
##  <a name="initialize_source"></a> initialize_source 

 Başlatır `message_propagator` bu içinde `source_block`.  
  
```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PScheduler`  
 Görevleri planlama için kullanılacak Zamanlayıcı.  
  
 `_PScheduleGroup`  
 Görevleri planlama için kullanılacak zamanlamayı grubu.  
  
##  <a name="link_target"></a> link_target 

 Hedef blok için bağlantılar `source_block` nesnesi.  
  
```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bir işaretçi bir `ITarget` Bağlanılacak blok `source_block` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu ise parametresi `_PTarget` olan `NULL`.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `source_block` nesnesi.  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```  
  
##  <a name="process_input_messages"></a> process_input_messages 

 İşlem iletileri girin. Bu yalnızca source_block türetilen yayılması blokları kullanışlıdır  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
  
##  <a name="propagate_output_messages"></a> propagate_output_messages 

 Hedefleri iletileri yayılır.  
  
```
virtual void propagate_output_messages();
```  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Türetilen bir sınıfta geçersiz kılındığında, bağlantılı hedefleri bir bölümünü veya tamamını için belirli bir ileti yayar. Bu ileti blokları ana yayma yordamdır.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Dağıtılmasını iletisini gösteren bir işaretçi.  
  
##  <a name="release"></a> Sürüm 

 Bir önceki başarılı ileti ayırma serbest bırakır.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Ayrılmış, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `release` yöntemi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu ise parametresi `_PTarget` olan `NULL`.  
  
 Yöntem oluşturulur bir [bad_target](bad-target-class.md) özel durumu ise parametresi `_PTarget` adlı hedef göstermiyor `reserve`.  
  
##  <a name="release_message"></a> release_message 

 Türetilen bir sınıfta geçersiz kılındığında, bir önceki iletiyi ayırma serbest bırakır.  
  
```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
##  <a name="release_ref"></a> release_ref 

 Serbest başvuru sayısı bu `source_block` nesnesi.  
  
```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu yöntemin çağrılması hedef blok için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` bu kaynaktan bağlantısız nesnesi. Kaynak blok için hedef blok ayrılan tüm kaynakları serbest bırakmak izin verilmez.  
  
##  <a name="remove_targets"></a> remove_targets 

 Bu kaynak bloğu tüm hedef bağlantıları kaldırır. Bu yıkıcı çağrılmalıdır.  
  
```
void remove_targets();
```  
  
##  <a name="reserve"></a> ayırma 

 Daha önce bu tarafından sunulan bir ileti ayırır `source_block` nesnesi.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `reserve` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` İletiyi başarıyla ayrıldı, `false` Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak sağlanamadı ayırmaları Reddet ve benzeri başka bir hedef tarafından kabul.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu ise parametresi `_PTarget` olan `NULL`.  
  
 Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alın veya ileti elinde sırasıyla vermek için.  
  
##  <a name="reserve_message"></a> reserve_message 

 Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir ileti ayırır `source_block` nesnesi.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Ayrılan nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` İletiyi başarıyla ayrıldı, `false` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonra `reserve` çağrılır, döndürürse `true`, her iki `consume` veya `release` alın veya iletinin sahipliğini serbest bırakmak için çağrılmalıdır.  
  
##  <a name="resume_propagation"></a> resume_propagation 

 Türetilen bir sınıfta geçersiz kılındığında, bir ayırma serbest bırakıldıktan sonra yayma devam ettirir.  
  
```
virtual void resume_propagation() = 0;
```  
  
##  <a name="ctor"></a> source_block 

 Oluşturan bir `source_block` nesnesi.  
  
```
source_block();
```  
  
##  <a name="dtor"></a> ~ source_block 

 Bozar `source_block` nesnesi.  
  
```
virtual ~source_block();
```  
  
##  <a name="sync_send"></a> sync_send 

 Zaman uyumlu olarak iletileri kuyruklar ve bu zaten yapılmadıysa yayma görev başlatır.  
  
```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Msg`  
 Bir işaretçi bir `message` zaman uyumlu olarak göndermek için nesne.  
  
##  <a name="unlink_target"></a> unlink_target 

 Hedef blok bu bağlantıyı keser `source_block` nesnesi.  
  
```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bir işaretçi bir `ITarget` öğesinden bağlantısını kesmek için blok `source_block` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durumu ise parametresi `_PTarget` olan `NULL`.  
  
##  <a name="unlink_target_notification"></a> unlink_target_notification 

 Bir hedef öğesinden bağlantısız olduğunu bildiren bir geri çağırma `source_block` nesnesi.  
  
```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 `ITarget` Bağlantısız bloğu.  
  
##  <a name="unlink_targets"></a> unlink_targets 

 Tüm hedef blokları bu bağlantıyı keser `source_block` nesnesi.  
  
```
virtual void unlink_targets();
```  
  
##  <a name="wait_for_outstanding_async_sends"></a> wait_for_outstanding_async_sends 

 Tamamlamak tüm zaman uyumsuz yayma bekler. Bu yayılması özgü döndürme bekleme ileti blokları yıkıcılarda tüm zaman uyumsuz yayma bloğu yok etme önce bitirmek için zamana sahip olduğunuzdan emin olmak için kullanılır.  
  
```
void wait_for_outstanding_async_sends();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [ISource Sınıfı](isource-class.md)
