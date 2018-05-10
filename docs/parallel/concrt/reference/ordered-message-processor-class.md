---
title: ordered_message_processor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27dfb6c1a64d3a4e9df24f3966ec89db1dfbe10c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor Sınıfı
Bir `ordered_message_processor` olan bir `message_processor` sırada alınan iletileri işlemek ileti blokları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class ordered_message_processor : public message_processor<T>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İşlemcisi tarafından işlenen iletiler yük türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`type`|İçin bir tür diğer adı `T`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ordered_message_processor](#ctor)|Oluşturan bir `ordered_message_processor` nesnesi.|  
|[~ ordered_message_processor yok Edicisi](#dtor)|Bozar `ordered_message_processor` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[async_send](#async_send)|Zaman uyumsuz olarak iletileri kuyruklar ve bu zaten yapılmadıysa bir işlem görevi başlar. (Geçersiz kılmaları [message_processor::async_send](message-processor-class.md#async_send).)|  
|[başlatma](#initialize)|Başlatır `ordered_message_processor` uygun geri çağırma işlevi, Zamanlayıcı ve zamanlamasını grup nesnesi.|  
|[initialize_batched_processing](#initialize_batched_processing)|Initialize toplu ileti işleme|  
|[sync_send](#sync_send)|Zaman uyumlu olarak iletileri kuyruklar ve bu zaten yapılmadıysa bir işlem görevi başlar. (Geçersiz kılmaları [message_processor::sync_send](message-processor-class.md#sync_send).)|  
|[bekleme](#wait)|Tüm zaman uyumsuz işleme görevlerini bloğu yok etme önce bitirmek için zamana sahip olduğunuzdan emin olmak için ileti blokları yıkıcılarda kullanılan işlemciye özgü döndürme bekleyin. (Geçersiz kılmaları [message_processor::wait](message-processor-class.md#wait).)|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|Çağrılan zaman uyumsuz işleme işlev. İletileri dequeues ve bunları işlemeye başlar. (Geçersiz kılmaları [message_processor::process_incoming_message](message-processor-class.md#process_incoming_message).)|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="async_send"></a> async_send 

 Zaman uyumsuz olarak iletileri kuyruklar ve bu zaten yapılmadıysa bir işlem görevi başlar.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Msg`  
 Bir ileti için bir işaretçi.  
  
##  <a name="initialize"></a> başlatma 

 Başlatır `ordered_message_processor` uygun geri çağırma işlevi, Zamanlayıcı ve zamanlamasını grup nesnesi.  
  
```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PScheduler`  
 Zamanlayıcı'yı hafif görevleri planlama için kullanılacak işaretçi.  
  
 `_PScheduleGroup`  
 Hafif görevleri planlama için kullanılacak zamanlamayı grubu için bir işaretçi.  
  
 `_Handler`  
 Geri çağırma sırasında çağrılan işleyici functor.  
  
##  <a name="initialize_batched_processing"></a> initialize_batched_processing 

 Initialize toplu ileti işleme  
  
```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Processor`  
 İşlemci functor geri çağırma sırasında çağrılır.  
  
 `_Propagator`  
 Yayılması functor geri çağırma sırasında çağrılır.  
  
##  <a name="ctor"></a> ordered_message_processor 

 Oluşturan bir `ordered_message_processor` nesnesi.  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu `ordered_message_processor` kadar zaman uyumsuz veya zaman uyumlu işleyicileri zamanlamaz `initialize` işlevi çağrılır.  
  
##  <a name="dtor"></a> ~ ordered_message_processor 

 Bozar `ordered_message_processor` nesnesi.  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm bekleyen zaman uyumsuz işlemleri için işlemci yok etme önce bekler.  
  
##  <a name="process_incoming_message"></a> process_incoming_message 

 Çağrılan zaman uyumsuz işleme işlev. İletileri dequeues ve bunları işlemeye başlar.  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="sync_send"></a> sync_send 

 Zaman uyumlu olarak iletileri kuyruklar ve bu zaten yapılmadıysa bir işlem görevi başlar.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Msg`  
 Bir ileti için bir işaretçi.  
  
##  <a name="wait"></a> bekleme 

 Tüm zaman uyumsuz işleme görevlerini bloğu yok etme önce bitirmek için zamana sahip olduğunuzdan emin olmak için ileti blokları yıkıcılarda kullanılan işlemciye özgü döndürme bekleyin.  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
