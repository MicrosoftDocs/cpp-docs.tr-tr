---
title: Süreölçer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8372e32b408b97a6ac652b0ff2ff5cc19de69b54
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693230"
---
# <a name="timer-class"></a>süreölçer Sınıfı
A `timer` ileti bloğu tek hedef `source_block` hedefine belirtilen süre geçtikten sonra veya belirli aralıklarla ileti gönderme yapabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bu bloğu çıktı iletilerinin yük türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Zamanlayıcı](#ctor)|Fazla Yüklendi. Oluşturan bir `timer` belirli bir ileti belirtilen bir zaman aralığından sonra ateşlenir ileti bloğu.|  
|[~ timer yok Edicisi](#dtor)|Bozar bir `timer` ileti bloğu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Duraklat](#pause)|Durakları `timer` ileti bloğu. Yinelenen ise `timer` blok Mesajlaşma, bir sonraki yeniden başlatılmadan `start()` çağırın. Yinelenmeyen için zamanlayıcılar, bu etkisi aynı olarak bir `stop` çağırın.|  
|[Başlat](#start)|Başlatır `timer` ileti bloğu. Bundan sonra milisaniye belirtilen sayıda çağrılır, belirtilen değer yayılır aşağı akış olarak bir `message`.|  
|[Durdur](#stop)|Durakları `timer` ileti bloğu.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `timer` çağırana sahipliğini aktarma ileti bloğu.|  
|[consume_message](#consume_message)|Daha önce tarafından sunulan bir ileti tüketir `timer` ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `timer` ileti bloğu.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Tarafından üretilen ileti sunmaya çalışır `timer` tüm bağlı hedef blok.|  
|[release_message](#release_message)|Bir önceki iletiyi ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir ileti ayırır `timer` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Bir ayırma serbest bırakıldıktan sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 [source_block](source-block-class.md)  
  
 `timer`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept_message"></a> accept_message 

 Bu tarafından sunulan bir iletiyi kabul `timer` çağırana sahipliğini aktarma ileti bloğu.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
##  <a name="consume_message"></a> consume_message 

 Daha önce tarafından sunulan bir ileti tüketir `timer` ve çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
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
  
##  <a name="link_target_notification"></a> link_target_notification 

 Yeni bir hedef için bağlayana olduğunu bildiren bir geri çağırma `timer` ileti bloğu.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Yeni bağlantılı hedefi için bir işaretçi.  
  
##  <a name="pause"></a> Duraklat 

 Durakları `timer` ileti bloğu. Yinelenen ise `timer` blok Mesajlaşma, bir sonraki yeniden başlatılmadan `start()` çağırın. Yinelenmeyen için zamanlayıcılar, bu etkisi aynı olarak bir `stop` çağırın.  
  
```
void pause();
```  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Tarafından üretilen ileti sunmaya çalışır `timer` tüm bağlı hedef blok.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
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

 Daha önce bu tarafından sunulan bir ileti ayırır `timer` ileti bloğu.  
  
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
  
##  <a name="start"></a> Başlat 

 Başlatır `timer` ileti bloğu. Bundan sonra milisaniye belirtilen sayıda çağrılır, belirtilen değer yayılır aşağı akış olarak bir `message`.  
  
```
void start();
```  
  
##  <a name="stop"></a> Durdur 

 Durakları `timer` ileti bloğu.  
  
```
void stop();
```  
  
##  <a name="ctor"></a> Zamanlayıcı 

 Oluşturan bir `timer` belirli bir ileti belirtilen bir zaman aralığından sonra ateşlenir ileti bloğu.  
  
```
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ms`  
 Başlatmak için aşağı yayılması belirtilen ileti çağrısı sonra geçmesi gereken milisaniye sayısı.  
  
 `value`  
 Zamanlayıcı sona erdiğinde aşağı yayılır değeri.  
  
 `_PTarget`  
 Zamanlayıcı kendi ileti yayılır hedefi.  
  
 `_Repeating`  
 TRUE ise, Zamanlayıcı düzenli aralıklarla ateşlenir gösterir her `_Ms` milisaniye.  
  
 `_Scheduler`  
 `Scheduler` İçinde yayma görev için nesne `timer` ileti bloğu zamanlandığı zamanlandı.  
  
 `_ScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `timer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_Scheduler` veya `_ScheduleGroup` parametreleri.  
  
##  <a name="dtor"></a> ~ timer 

 Bozar bir `timer` ileti bloğu.  
  
```
~timer();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
