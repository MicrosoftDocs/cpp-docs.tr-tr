---
title: EventTargetArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray class
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2757589509e4a2b091c5057ef2065866a8829494
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570427"
---
# <a name="eventtargetarray-class"></a>EventTargetArray Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Olay işleyicileri dizisini temsil eder.  
  
 İlişkili olay işleyicileri bir [EventSource](../windows/eventsource-class.md) nesnesi depolanır, korumalı bir **EventTargetArray** veri üyesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventTargetArray::EventTargetArray Oluşturucusu](../windows/eventtargetarray-eventtargetarray-constructor.md)|Yeni bir örneğini başlatır **EventTargetArray** sınıfı.|  
|[EventTargetArray::~EventTargetArray Yıkıcısı](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Geçerli başlatılmasını geri alır **EventTargetArray** sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventTargetArray::AddTail Metodu](../windows/eventtargetarray-addtail-method.md)|Belirtilen olay işleyicisi, olay işleyicileri iç dizi sonuna ekler.|  
|[EventTargetArray::Begin Metodu](../windows/eventtargetarray-begin-method.md)|Olay işleyicilerini iç dizideki ilk öğenin adresi alır.|  
|[EventTargetArray::End Metodu](../windows/eventtargetarray-end-method.md)|Son öğenin adresi olay işleyicileri içinde iç dizisini alır.|  
|[EventTargetArray::Length Metodu](../windows/eventtargetarray-length-method.md)|Olay işleyicilerini iç dizisinde geçerli öğe sayısını alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `EventTargetArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)