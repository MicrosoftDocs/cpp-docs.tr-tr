---
title: "Çağrı sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
dev_langs: C++
helpviewer_keywords: call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1c629355db7f2e77ef0854a52c86848adb70c6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="call-class"></a>çağrı Sınıfı
A `call` ileti bloğu, birden çok kaynak sıralı `target_block` , çağırır belirtilen işlevi bir ileti alırken.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bu bloğuna yayılan iletileri yük türü.  
  
 `_FunctorType`  
 Bu bloğu kabul edebilir işlevleri imzası.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Arama](#ctor)|Fazla Yüklendi. Oluşturan bir `call` ileti bloğu.|  
|[~ call yok Edicisi](#dtor)|Bozar `call` ileti bloğu.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[process_input_messages](#process_input_messages)|Çağrı işlevi, giriş iletilerde yürütür.|  
|[process_message](#process_message)|Bunu kabul edildi iletisini işler `call` ileti bloğu.|  
|[propagate_message](#propagate_message)|Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `call` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[send_message](#send_message)|İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `call` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.|  
|[supports_anonymous_source](#supports_anonymous_source)|Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem. (Geçersiz kılmaları [Itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Itarget](itarget-class.md)  
  
 [target_block](target-block-class.md)  
  
 `call`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a>Arama 

 Oluşturan bir `call` ileti bloğu.  
  
```
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Func`  
 Kabul edilen her ileti için çağrılacak işlev.  
  
 `_Filter`  
 Sunulan iletileri kabul edilip edilmeyeceğini belirler bir filtre işlevi.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `call` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `call` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Türü `_Call_method` functor imzaya sahip olduğu `void (T const &)` hangi çağrılır bu tarafından `call` bir iletiyi işlemek için ileti bloğu.  
  
 Türü `filter_method` functor imzaya sahip olduğu `bool (T const &)` hangi çağrılır bu tarafından `call` sunulan iletisine kabul etmelidir olup olmadığını belirlemek için ileti bloğu.  
  
##  <a name="dtor"></a>~ çağırın 

 Bozar `call` ileti bloğu.  
  
```
~call();
```  
  
##  <a name="process_input_messages"></a>process_input_messages 

 Çağrı işlevi, giriş iletilerde yürütür.  
  
```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
  
##  <a name="process_message"></a>process_message 

 Bunu kabul edildi iletisini işler `call` ileti bloğu.  
  
```
virtual void process_message(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi işlenecek iletisi.  
  
##  <a name="propagate_message"></a>propagate_message 

 Zaman uyumsuz olarak bir iletiden geçirmeden bir `ISource` bu bloğuna `call` ileti bloğu. Tarafından çağrılan `propagate` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
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
  
##  <a name="send_message"></a>send_message 

 İletiyi zaman uyumlu olarak geçirir bir `ISource` bu bloğuna `call` ileti bloğu. Tarafından çağrılan `send` kaynak bloğu tarafından çağrıldığında yöntemi.  
  
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
  
##  <a name="supports_anonymous_source"></a>supports_anonymous_source 

 Geçersiz kılmaları `supports_anonymous_source` bu bloğu için bağlantılı olmayan bir kaynak tarafından sunulan iletileri kabul ettiğinizi belirtmek için yöntem.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Blok sunulan iletiler erteleyin değil çünkü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Transformer sınıfı](transformer-class.md)
