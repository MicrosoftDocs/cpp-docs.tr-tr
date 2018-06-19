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
ms.openlocfilehash: 4461004a1681d9095449c51fb9cb3973d5017693
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881315"
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
|[EventTargetArray::~EventTargetArray Yıkıcısı](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Geçerli EventTargetArray sınıfı deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[EventTargetArray::AddTail Metodu](../windows/eventtargetarray-addtail-method.md)|Belirtilen olay işleyicisi olay işleyicileri iç dizisi sonuna ekler.|  
|[EventTargetArray::Begin Metodu](../windows/eventtargetarray-begin-method.md)|Olay işleyicileri iç dizisinde ilk öğe adresini alır.|  
|[EventTargetArray::End Metodu](../windows/eventtargetarray-end-method.md)|Olay işleyicileri iç dizide son öğe adresini alır.|  
|[EventTargetArray::Length Metodu](../windows/eventtargetarray-length-method.md)|Olay işleyicileri iç dizisinde geçerli öğe sayısını alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `EventTargetArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)