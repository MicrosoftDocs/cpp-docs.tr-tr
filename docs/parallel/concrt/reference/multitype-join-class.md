---
title: "multitype_join sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 62d91f878a8330b6e4fe60f7e24ad25c779b868d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="multitypejoin-class"></a>multitype_join Sınıfı
A `multitype_join` ileti bloğu her kaynaklarının farklı türlerde iletiler birlikte birleştiren ve hedeflerine birleşik iletileri dizisi sunar çok kaynak, tek hedef ileti bloğu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<
    typename T,  
    join_type _Jtype = non_greedy  
>  
class multitype_join: public ISource<typename _Unwrap<T>::type>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 `tuple` İletileri yükü türü alanına katılan ve bloğu tarafından yayılır.  
  
 `_Jtype`  
 Türü, `join` ya da bu olduğu blok `greedy` veya `non_greedy`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`type`|İçin bir tür diğer adı `T`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[multitype_join](#ctor)|Fazla Yüklendi. Oluşturan bir `multitype_join` ileti bloğu.|  
|[~ multitype_join yok Edicisi](#dtor)|Bozar `multitype_join` ileti bloğu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accept](#accept)|Bu tarafından sunulan bir iletiyi kabul `multitype_join` çağırana sahipliğini aktarma bloğu.|  
|[acquire_ref](#acquire_ref)|Bu başvuru sayısı edinir `multitype_join` silinmesini önlemek için ileti bloğu.|  
|[Kullanma](#consume)|Daha önce tarafından sunulan bir ileti tüketir `multitype_join` blok Mesajlaşma ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[link_target](#link_target)|Hedef blok için bağlantılar `multitype_join` ileti bloğu.|  
|[release](#release)|Bir önceki başarılı ileti ayırma serbest bırakır.|  
|[release_ref](#release_ref)|Serbest başvuru sayısı bu `multiple_join` ileti bloğu.|  
|[reserve](#reserve)|Daha önce bu tarafından sunulan bir ileti ayırır `multitype_join` ileti bloğu.|  
|[unlink_target](#unlink_target)|Hedef blok bu bağlantıyı keser `multitype_join` ileti bloğu.|  
|[unlink_targets](#unlink_targets)|Tüm hedefleri bu bağlantıyı keser `multitype_join` ileti bloğu. (Geçersiz kılmaları [Isource::unlink_targets](isource-class.md#unlink_targets).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept"></a> Kabul et 

 Bu tarafından sunulan bir iletiyi kabul `multitype_join` çağırana sahipliğini aktarma bloğu.  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `accept` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi çağıran şimdi sahipliği var. iletisi.  
  
##  <a name="acquire_ref"></a> acquire_ref 

 Bu başvuru sayısı edinir `multitype_join` silinmesini önlemek için ileti bloğu.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu yöntemin çağrılması hedef blok için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` sırasında bu kaynak için bağlantılı nesne `link_target` yöntemi.  
  
##  <a name="consume">Kullanma</a> 

 Daha önce tarafından sunulan bir ileti tüketir `multitype_join` blok Mesajlaşma ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Ayrılmış, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `consume` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `message` çağıran şimdi sahipliği var. nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `consume` Yöntemi benzer `accept`, her zaman için yapılan bir çağrı tarafından gelmelidir ancak `reserve` döndürülen `true`.  
  
##  <a name="link_target"></a> link_target 

 Hedef blok için bağlantılar `multitype_join` ileti bloğu.  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bir işaretçi bir `ITarget` Bağlanılacak blok `multitype_join` ileti bloğu.  
  
##  <a name="ctor"></a> multitype_join 

 Oluşturan bir `multitype_join` ileti bloğu.  
  
```  
explicit multitype_join(
    T _Tuple);

 
multitype_join(
    Scheduler& _PScheduler,  
    T _Tuple);

 
multitype_join(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
multitype_join(
    multitype_join&& _Join);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Tuple`  
 A `tuple` bu kaynakları `multitype_join` ileti bloğu.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `multitype_join` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `multitype_join` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
 `_Join`  
 A `multitype_join` kopyalamak için ileti bloğu. Özgün nesne, bu bir taşıma oluşturucusuna yapmadan yalnız bırakılmış olduğunu unutmayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Taşıma yapım hafif görevleri uçuş modunda taşıma sırasında emin olmak için kullanıcı kadar olduğu anlamına gelir bir kilit altında yapılmaz. Aksi takdirde, özel durumları veya tutarsız önde gelen çok sayıda diğerleriyle oluşabilir.  
  
##  <a name="dtor"></a> ~ multitype_join 

 Bozar `multitype_join` ileti bloğu.  
  
```  
~multitype_join();
```  
  
##  <a name="release"></a> Sürüm 

 Bir önceki başarılı ileti ayırma serbest bırakır.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `release` yöntemi.  
  
##  <a name="release_ref"></a> release_ref 

 Serbest başvuru sayısı bu `multiple_join` ileti bloğu.  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu yöntemin çağrılması hedef blok için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` bu kaynaktan bağlantısız nesnesi. Kaynak blok için hedef blok ayrılan tüm kaynakları serbest bırakmak izin verilmez.  
  
##  <a name="reserve"></a> ayırma 

 Daha önce bu tarafından sunulan bir ileti ayırır `multitype_join` ileti bloğu.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Ayrılan nesne.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `reserve` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` İletiyi başarıyla ayrıldı, `false` Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak sağlanamadı ayırmaları Reddet ve benzeri başka bir hedef tarafından kabul.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alın veya ileti elinde sırasıyla vermek için.  
  
##  <a name="unlink_target"></a> unlink_target 

 Hedef blok bu bağlantıyı keser `multitype_join` ileti bloğu.  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bir işaretçi bir `ITarget` öğesinden bağlantısını kesmek için blok `multitype_join` ileti bloğu.  
  
##  <a name="unlink_targets"></a> unlink_targets 

 Tüm hedefleri bu bağlantıyı keser `multitype_join` ileti bloğu.  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [seçenek sınıfı](choice-class.md)   
 [join Sınıfı](join-class.md)
