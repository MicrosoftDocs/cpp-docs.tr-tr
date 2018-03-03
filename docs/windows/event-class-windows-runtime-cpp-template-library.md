---
title: "Olay sınıfı (Windows çalışma zamanı C++ Şablon kitaplığı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs:
- C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4647a8b1001cd6acd6b70a3d15f127c8e3891c1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="event-class-windows-runtime-c-template-library"></a>Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)
Bir olayı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Event::Event Yapıcı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Olay sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Event::operator= İşleci](../windows/event-operator-assign-operator.md)|Geçerli olay örneği belirtilen olay referansı atar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)