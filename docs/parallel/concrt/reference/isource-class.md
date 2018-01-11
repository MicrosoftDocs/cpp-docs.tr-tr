---
title: "Isource sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
dev_langs: C++
helpviewer_keywords: ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6db1fe614de8a3f47bae989ccb26512c375cec50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="isource-class"></a>ISource Sınıfı
`ISource` Sınıftır arabirimi tüm blokları kaynağı için. Kaynak blokları yayılması iletileri `ITarget` engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Yükü kaynak bloğu tarafından üretilen iletileri içinde veri türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`source_type`|İçin bir tür diğer adı `T`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[~ Isource yok Edicisi](#dtor)|Bozar `ISource` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[kabul et](#accept)|Türetilen bir sınıfta geçersiz kılındığında, bu tarafından sunulan bir iletiyi kabul `ISource` çağırana sahipliğini aktarma bloğu.|  
|[acquire_ref](#acquire_ref)|Türetilen bir sınıfta geçersiz kılındığında, bir başvuru sayısı bu edinir `ISource` silinmesini önlemek için blok.|  
|[kullanma](#consume)|Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir ileti tüketir `ISource` engelleme ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.|  
|[link_target](#link_target)|Türetilen bir sınıfta geçersiz kılındığında, bir hedef blok için bağlantılar `ISource` bloğu.|  
|[Sürüm](#release)|Türetilen bir sınıfta geçersiz kılındığında, bir önceki başarılı ileti ayırma serbest bırakır.|  
|[release_ref](#release_ref)|Türetilen bir sınıfta geçersiz kılındığında, serbest başvuru sayısı bu `ISource` bloğu.|  
|[ayırma](#reserve)|Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir ileti ayırır `ISource` bloğu.|  
|[unlink_target](#unlink_target)|Türetilen bir sınıfta geçersiz kılındığında, bir hedef blok bu bağlantıyı keser `ISource` , bloke önceden bağlanması bulundu.|  
|[unlink_targets](#unlink_targets)|Türetilen bir sınıfta geçersiz kılındığında, tüm hedef blokları bu bağlantıyı keser `ISource` bloğu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ISource`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="accept"></a>kabul et 

 Türetilen bir sınıfta geçersiz kılındığında, bu tarafından sunulan bir iletiyi kabul `ISource` çağırana sahipliğini aktarma bloğu.  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `accept` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi çağıran şimdi sahipliği var. iletisi.  
  
### <a name="remarks"></a>Açıklamalar  
 `accept` Yöntemi, hedef tarafından çağrıldığında, bir ileti bu tarafından sunulan sırada `ISource` bloğu. İleti işaretçi döndürdü içine geçirilen olandan farklı olabilir `propagate` yöntemi `ITarget` iletinin bir kopyasını oluşturmak bu kaynak karar verirse, engelleyin.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Türetilen bir sınıfta geçersiz kılındığında, bir başvuru sayısı bu edinir `ISource` silinmesini önlemek için blok.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu yöntemin çağrılması hedef blok için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` sırasında bu kaynak için bağlantılı nesne `link_target` yöntemi.  
  
##  <a name="consume"></a>kullanma 

 Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir ileti tüketir `ISource` engelleme ve başarıyla çağırana sahipliğini aktarma hedef tarafından ayrılmış.  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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
  
##  <a name="dtor"></a>~ Isource 

 Bozar `ISource` nesnesi.  
  
```
virtual ~ISource();
```  
  
##  <a name="link_target"></a>link_target 

 Türetilen bir sınıfta geçersiz kılındığında, bir hedef blok için bağlantılar `ISource` bloğu.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bunun için bağlantı kurulan hedef blok gösteren bir işaretçi `ISource` bloğu.  
  
##  <a name="release"></a>Sürüm 

 Türetilen bir sınıfta geçersiz kılındığında, bir önceki başarılı ileti ayırma serbest bırakır.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Ayrılmış, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `release` yöntemi.  
  
##  <a name="release_ref"></a>release_ref 

 Türetilen bir sınıfta geçersiz kılındığında, serbest başvuru sayısı bu `ISource` bloğu.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu yöntemin çağrılması hedef blok için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından çağrılır bir `ITarget` bu kaynaktan bağlantısız nesnesi. Kaynak blok için hedef blok ayrılan tüm kaynakları serbest bırakmak izin verilmez.  
  
##  <a name="reserve"></a>ayırma 

 Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir ileti ayırır `ISource` bloğu.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_MsgId`  
 `runtime_object_identity` Sunulan, `message` nesnesi.  
  
 `_PTarget`  
 Çağırma hedef blok gösteren bir işaretçi `reserve` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`İletiyi başarıyla ayrıldı, `false` Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak sağlanamadı ayırmaları Reddet ve benzeri başka bir hedef tarafından kabul.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alın veya ileti elinde sırasıyla vermek için.  
  
##  <a name="unlink_target"></a>unlink_target 

 Türetilen bir sınıfta geçersiz kılındığında, bir hedef blok bu bağlantıyı keser `ISource` , bloke önceden bağlanması bulundu.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu ayrılmış hedef blok gösteren bir işaretçi `ISource` bloğu.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Türetilen bir sınıfta geçersiz kılındığında, tüm hedef blokları bu bağlantıyı keser `ISource` bloğu.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [ITarget Sınıfı](itarget-class.md)
