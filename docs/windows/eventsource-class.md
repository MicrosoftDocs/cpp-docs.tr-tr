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
ms.openlocfilehash: 0f740cbfb8aea1a0e2378d1d2ab42d3c88c77137
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644774"
---
# <a name="eventsource-class"></a>EventSource Sınıfı
Çevik olmayan bir olayı temsil eder. **EventSource** üye işlevleri ekleme, kaldırma ve olay işleyicilerini çağırır. Çevik olaylar için kullanın [AgileEventSource](agileeventsource-class.md). 
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename TDelegateInterface>  
class EventSource;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TDelegateInterface*  
 Bir olay işleyicisi temsil eden bir temsilci için arabirim.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventSource::EventSource Oluşturucusu](../windows/eventsource-eventsource-constructor.md)|Yeni bir örneğini başlatır **EventSource** sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventSource::Add Metodu](../windows/eventsource-add-method.md)|Ekler için geçerli olay işleyicileri kümesini belirtilen temsilci arabirimi tarafından temsil edilen olay işleyicisi **EventSource** nesne.|  
|[EventSource::GetSize Metodu](../windows/eventsource-getsize-method.md)|Geçerli ile ilişkili olay işleyicileri sayısını alır **EventSource** nesnesi|  
|[EventSource::InvokeAll Metodu](../windows/eventsource-invokeall-method.md)|Geçerli ile ilgili her olay işleyicisini çağırır **EventSource** belirtilen bağımsız değişken türleri ve bağımsız değişkenleri kullanarak nesne.|  
|[EventSource::Remove Metodu](../windows/eventsource-remove-method.md)|Olay işleyicisi geçerli ile ilişkili olay işleyicileri kümesinden tarafından belirtilen olay kaydı belirtecini temsil siler **EventSource** nesne.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventSource::addRemoveLock_ Veri Üyesi](../windows/eventsource-addremovelock-data-member.md)|Erişimi eşitler [targets_](../windows/eventsource-targets-data-member.md) eklerken dizi, kaldırma veya olay işleyicisi çağırma.|  
|[EventSource::targets_ Veri Üyesi](../windows/eventsource-targets-data-member.md)|Bir veya daha fazla olay işleyicileri dizisi.|  
|[EventSource::targetsPointerLock_ Veri Üyesi](../windows/eventsource-targetspointerlock-data-member.md)|Bu EventSource için olay işleyicileri bile eklenmiş olsa da kaldırılan veya çağrılan iç veri üyelerine erişimi eşitler.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `EventSource`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)  
 [AgileEventSource Sınıfı](agileeventsource-class.md)