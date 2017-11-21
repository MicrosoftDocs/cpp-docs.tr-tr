---
title: "EventTargetArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::EventTargetArray
dev_langs: C++
helpviewer_keywords: EventTargetArray class
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b7f23265601411c0a1913b1e06b9fffa62bfa07f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="eventtargetarray-class"></a>EventTargetArray Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Olay işleyicileri dizisini temsil eder.  
  
 İlişkili olay işleyicileri bir [EventSource](../windows/eventsource-class.md) nesne korumalı EventTargetArray veri üyesi depolanır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventTargetArray::EventTargetArray Oluşturucusu](../windows/eventtargetarray-eventtargetarray-constructor.md)|EventTargetArray sınıfı yeni bir örneğini başlatır.|  
|[EventTargetArray:: ~ EventTargetArray yok Edicisi](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Geçerli EventTargetArray sınıfı deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventTargetArray::AddTail yöntemi](../windows/eventtargetarray-addtail-method.md)|Belirtilen olay işleyicisi olay işleyicileri iç dizisi sonuna ekler.|  
|[EventTargetArray::Begin yöntemi](../windows/eventtargetarray-begin-method.md)|Olay işleyicileri iç dizisinde ilk öğe adresini alır.|  
|[EventTargetArray::End yöntemi](../windows/eventtargetarray-end-method.md)|Olay işleyicileri iç dizide son öğe adresini alır.|  
|[EventTargetArray::Length yöntemi](../windows/eventtargetarray-length-method.md)|Olay işleyicileri iç dizisinde geçerli öğe sayısını alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `EventTargetArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)