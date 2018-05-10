---
title: Itarget sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
dev_langs:
- C++
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9780e4b9ff8950511601b03e8423764c3def77a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="itarget-class"></a>ITarget Sınıfı
`ITarget` Sınıftır arabirimi tüm blokları hedef için. Hedef blokları kullanmak için onlara tarafından sunulan iletiler `ISource` engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class ITarget;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Yükü iletileri içinde veri türü hedef blok tarafından kabul edildi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`filter_method`|İmzasını döndürür bloğu tarafından kullanılan herhangi bir yöntemi, bir `bool` sunulan iletisine kabul edilip edilmeyeceğini belirlemek için değeri.|  
|`type`|İçin bir tür diğer adı `T`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[~ Itarget yok Edicisi](#dtor)|Bozar `ITarget` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Yayma](#propagate)|Zaman uyumsuz olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti bu hedef blok kaynak bloğundan geçirir.|  
|[Gönder](#send)|Zaman uyumlu olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti hedef blok geçirir.|  
|[supports_anonymous_source](#supports_anonymous_source)|Türetilen bir sınıfta geçersiz kılındığında, true veya false ileti bloğu ona bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmemesine bağlı olarak döndürür. Geçersiz kılınan yöntemi döndürürse `true`, ertelenmiş ileti tüketim daha sonra kendi sourse bağlantı kayıt defterinde tanımlanması için kaynak gerektirdiğinden hedef sunulan iletisine erteleyemiyor.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[link_source](#link_source)|Türetilen bir sınıfta geçersiz kılındığında, belirtilen kaynak blok için bağlantılar `ITarget` bloğu.|  
|[unlink_source](#unlink_source)|Türetilen bir sınıfta geçersiz kılındığında, belirtilen kaynak blok bu bağlantıyı keser `ITarget` bloğu.|  
|[unlink_sources](#unlink_sources)|Türetilen bir sınıfta geçersiz kılındığında, tüm kaynak blokları bu bağlantıyı keser `ITarget` bloğu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ITarget`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a> ~ Itarget 

 Bozar `ITarget` nesnesi.  
  
```
virtual ~ITarget();
```  
  
##  <a name="link_source"></a> link_source 

 Türetilen bir sınıfta geçersiz kılındığında, belirtilen kaynak blok için bağlantılar `ITarget` bloğu.  
  
```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PSource`  
 `ISource` İçin bağlantı kurulan engelleme `ITarget` bloğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev doğrudan çağrılmamalıdır bir `ITarget` bloğu. Blokları birlikte kullanarak bağlanması `link_target` yöntemi `ISource` çağıracağı blokları `link_source` karşılık gelen hedef yöntemi.  
  
##  <a name="propagate"></a> Yayma 

 Zaman uyumsuz olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti bu hedef blok kaynak bloğundan geçirir.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) her iki özel durum `_PMessage` veya `_PSource` parametresi `NULL`.  
  
##  <a name="send"></a> Gönder 

 Zaman uyumlu olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti hedef blok geçirir.  
  
```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PMessage`  
 Bir işaretçi `message` nesnesi.  
  
 `_PSource`  
 İleti sunan kaynak bloğu için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [message_status](concurrency-namespace-enums.md) hedef iletiyle yapmak karar göstergesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_argument](../../../standard-library/invalid-argument-class.md) her iki özel durum `_PMessage` veya `_PSource` parametresi `NULL`.  
  
 Kullanarak `send` yöntemi ileti başlatma dışında ve bir ağ içinde ileti yayılmasına tehlikeli ve kilitlenmeye neden olabilir.  
  
 Zaman `send` döndürür, ileti algıladı ya da zaten kabul edildi ve hedef bloğu içine aktarılan ya da hedef tarafından reddedildi.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 Türetilen bir sınıfta geçersiz kılındığında, true veya false ileti bloğu ona bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmemesine bağlı olarak döndürür. Geçersiz kılınan yöntemi döndürürse `true`, ertelenmiş ileti tüketim daha sonra kendi sourse bağlantı kayıt defterinde tanımlanması için kaynak gerektirdiğinden hedef sunulan iletisine erteleyemiyor.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Blok ona bağlı olmayan bir kaynaktan alınan ileti kabul edebiliyorsa `false` Aksi takdirde.  
  
##  <a name="unlink_source"></a> unlink_source 

 Türetilen bir sınıfta geçersiz kılındığında, belirtilen kaynak blok bu bağlantıyı keser `ITarget` bloğu.  
  
```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_PSource`  
 `ISource` Öğesinden bağlantısız engelleme `ITarget` bloğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev doğrudan çağrılmamalıdır bir `ITarget` bloğu. Blokları bağlantısı kesilmiş kullanarak `unlink_target` veya `unlink_targets` yöntemlere `ISource` çağıracağı blokları `unlink_source` karşılık gelen hedef yöntemi.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 Türetilen bir sınıfta geçersiz kılındığında, tüm kaynak blokları bu bağlantıyı keser `ITarget` bloğu.  
  
```
virtual void unlink_sources() = 0;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [ISource Sınıfı](isource-class.md)
