---
title: EventSource sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
dev_langs:
- C++
helpviewer_keywords:
- EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b2d466b317927cd8de259637450b68b6aaf13bd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="eventsource-class"></a>EventSource Sınıfı
Çevik olmayan bir olayı temsil eder. EventSource üye işlevleri eklemek, kaldırmak ve olay işleyicilerini çağırma. Çevik olaylar için kullanın [AgileEventSource](agileeventsource-class.md). 
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename TDelegateInterface>  
class EventSource;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TDelegateInterface`  
 Olay işleyici temsil eden bir temsilci için arabirim.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventSource::EventSource Oluşturucusu](../windows/eventsource-eventsource-constructor.md)|EventSource sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventSource::Add Metodu](../windows/eventsource-add-method.md)|Olay işleyicileri geçerli EventSource nesne için kümesine tarafından belirtilen temsilci arabirimi temsil olay işleyicisi ekler.|  
|[EventSource::GetSize Metodu](../windows/eventsource-getsize-method.md)|Geçerli EventSource nesneyle ilişkili olay işleyicileri sayısını alır.|  
|[EventSource::InvokeAll Metodu](../windows/eventsource-invokeall-method.md)|Belirtilen bağımsız değişken türleri ve bağımsız değişkenler kullanarak geçerli EventSource nesneyle ilişkili her olay işleyicisini çağırır.|  
|[EventSource::Remove Metodu](../windows/eventsource-remove-method.md)|Geçerli EventSource nesneyle ilişkili olay işleyicileri kümesinden tarafından belirtilen olay kaydı belirtecini temsil olay işleyicisi siler.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventSource::addRemoveLock_ Veri Üyesi](../windows/eventsource-addremovelock-data-member.md)|Erişim eşitler [targets_](../windows/eventsource-targets-data-member.md) eklerken dizi, kaldırma veya olay işleyicilerini çağırma.|  
|[EventSource::targets_ Veri Üyesi](../windows/eventsource-targets-data-member.md)|Bir veya daha fazla olay işleyicileri dizisi.|  
|[EventSource::targetsPointerLock_ Veri Üyesi](../windows/eventsource-targetspointerlock-data-member.md)|Olay işleyicileri bu EventSource için bile eklenmiş durumdayken, kaldırıldı veya çağrılan iç veri üyelerine erişimi eşitler.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `EventSource`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)
[AgileEventSource sınıfı](agileeventsource-class.md)