---
title: "EventSource sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
dev_langs:
- C++
helpviewer_keywords:
- EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 705260547d5a42b463d61b79c38592874f9dfa19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="eventsource-class"></a>EventSource Sınıfı
Bir olayı temsil eder. EventSource üye işlevleri eklemek, kaldırmak ve olay işleyicilerini çağırma.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename TDelegateInterface  
>  
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
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)