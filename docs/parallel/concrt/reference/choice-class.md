---
title: "choice sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
dev_langs: C++
helpviewer_keywords: choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec7383340e9502764514bb61ce8e10f6cb64c616
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="choice-class"></a>seçenek Sınıfı
A `choice` ileti bloğu olan bir kaynak kümesi akış denetimi etkileşim temsil eden birden çok kaynak, tek hedef blok. Seçim bloğu bir iletisi oluşturmak üzere birden çok kaynaktan herhangi biri için bekler ve ileti üretilen kaynak dizini yayılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<
    class T  
>  
class choice: public ISource<size_t>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 A `tuple`-giriş kaynağı yüklerini temsil eden tür tabanlı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`type`|İçin bir tür diğer adı `T`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Seçim](#ctor)|Fazla Yüklendi. Oluşturan bir `choice` ileti bloğu.|  
|[~ choice yok Edicisi](#dtor)|Bozar `choice` ileti bloğu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[kabul et](#accept)|Bu tarafından sunulan bir iletiyi kabul `choice` çağırana sahipliğini aktarma bloğu.|  
|[acquire_ref](#acquire_ref)|Bu başvuru sayısı edinir `choice` silinmesini önlemek için ileti bloğu.|  
|[kullanma](#consume)|Daha önce bu tarafından sunulan bir ileti tüketir `choice` blok Mesajlaşma ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[has_value](#has_value)|Denetler olup olmadığını bu `choice` ileti bloğu başlatıldıysa bir değerle henüz.|  
|[Dizin](#index)|Bir dizine döndürür `tuple` tarafından seçilen öğeyi temsil eden `choice` ileti bloğu.|  
|[link_target](#link_target)|Hedef blok için bağlantılar `choice` ileti bloğu.|  
|[Sürüm](#release)|Bir önceki başarılı ileti ayırma serbest bırakır.|  
|[release_ref](#release_ref)|Serbest başvuru sayısı bu `choice` ileti bloğu.|  
|[ayırma](#reserve)|Daha önce bu tarafından sunulan bir ileti ayırır `choice` ileti bloğu.|  
|[unlink_target](#unlink_target)|Hedef blok bu bağlantıyı keser `choice` ileti bloğu.|  
|[unlink_targets](#unlink_targets)|Tüm hedefleri bu bağlantıyı keser `choice` ileti bloğu. (Geçersiz kılmaları [Isource::unlink_targets](isource-class.md#unlink_targets).)|  
|[value](#value)|Dizinini tarafından seçildiğinde iletisini alır `choice` ileti bloğu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Seçim bloğu gelen iletileri yalnızca biri tüketiliyor sağlar.  
  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Isource](isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept"></a>kabul et 

 Bu tarafından sunulan bir iletiyi kabul `choice` çağırana sahipliğini aktarma bloğu.  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `accept` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi çağıran şimdi sahipliği var. iletisi.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Bu başvuru sayısı edinir `choice` silinmesini önlemek için ileti bloğu.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu yöntemin çağrılması hedef blok için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` sırasında bu kaynak için bağlantılı nesne `link_target` yöntemi.  
  
##  <a name="ctor"></a>Seçim 

 Oluşturan bir `choice` ileti bloğu.  
  
```  
explicit choice(
    T _Tuple);

 
choice(
    Scheduler& _PScheduler,  
    T _Tuple);

 
choice(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
choice(
    choice&& _Choice);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Tuple`  
 A `tuple` seçimi için kaynakları.  
  
 `_PScheduler`  
 `Scheduler` İçinde yayma görev için nesne `choice` ileti bloğu zamanlandı.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` İçinde yayma görev için nesne `choice` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
 `_Choice`  
 A `choice` kopyalamak için ileti bloğu. Özgün nesne, bu bir taşıma oluşturucusuna yapmadan yalnız bırakılmış olduğunu unutmayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.  
  
 Taşıma yapım hafif görevleri uçuş modunda taşıma sırasında emin olmak için kullanıcı kadar olduğu anlamına gelir bir kilit altında yapılmaz. Aksi takdirde, özel durumları veya tutarsız önde gelen çok sayıda diğerleriyle oluşabilir.  
  
##  <a name="dtor"></a>~ Seçimi 

 Bozar `choice` ileti bloğu.  
  
```  
~choice();
```  
  
##  <a name="consume"></a>kullanma 

 Daha önce bu tarafından sunulan bir ileti tüketir `choice` blok Mesajlaşma ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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
  
##  <a name="has_value"></a>has_value 

 Denetler olup olmadığını bu `choice` ileti bloğu başlatıldıysa bir değerle henüz.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`bir değer blok aldıysa `false` Aksi takdirde.  
  
##  <a name="index"></a>Dizin 

 Bir dizine döndürür `tuple` tarafından seçilen öğeyi temsil eden `choice` ileti bloğu.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 İleti yükü kullanarak ayıklanabilir `get` yöntemi.  
  
##  <a name="link_target"></a>link_target 

 Hedef blok için bağlantılar `choice` ileti bloğu.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bir işaretçi bir `ITarget` Bağlanılacak blok `choice` ileti bloğu.  
  
##  <a name="release"></a>Sürüm 

 Bir önceki başarılı ileti ayırma serbest bırakır.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Yayımlanan nesne.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `release` yöntemi.  
  
##  <a name="release_ref"></a>release_ref 

 Serbest başvuru sayısı bu `choice` ileti bloğu.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu yöntemin çağrılması hedef blok için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` bu kaynaktan bağlantısız nesnesi. Kaynak blok için hedef blok ayrılan tüm kaynakları serbest bırakmak izin verilmez.  
  
##  <a name="reserve"></a>ayırma 

 Daha önce bu tarafından sunulan bir ileti ayırır `choice` ileti bloğu.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` , `message` Ayrılan nesne.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `reserve` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`İletiyi başarıyla ayrıldı, `false` Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak sağlanamadı ayırmaları Reddet ve benzeri başka bir hedef tarafından kabul.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alın veya ileti elinde sırasıyla vermek için.  
  
##  <a name="unlink_target"></a>unlink_target 

 Hedef blok bu bağlantıyı keser `choice` ileti bloğu.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bir işaretçi bir `ITarget` öğesinden bağlantısını kesmek için blok `choice` ileti bloğu.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Tüm hedefleri bu bağlantıyı keser `choice` ileti bloğu.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, yıkıcı çünkü çağrılması gerekmez. yıkıcı iç için `single_assignment` blok bağlantısını düzgün.  
  
##  <a name="value"></a>değer 

 Dizinini tarafından seçildiğinde iletisini alır `choice` ileti bloğu.  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>Parametreler  
 `_Payload_type`  
 İleti yükü türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İletinin yükü.  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü bir `choice` ileti bloğu girişleri farklı yükü türleriyle alabilir, alma noktasında yükü türünü belirtmeniz gerekir. Sonucuna göre türü belirleyebilirsiniz `index` yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [join sınıfı](join-class.md)   
 [single_assignment Sınıfı](single-assignment-class.md)
