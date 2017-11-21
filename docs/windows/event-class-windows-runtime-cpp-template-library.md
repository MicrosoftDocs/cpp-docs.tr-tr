---
title: "Olay sınıfı (Windows çalışma zamanı C++ Şablon kitaplığı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs: C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: df791e5ef12dfeef72ebf48e673b774ddfd6aee5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[Event::Event yapıcı (Windows çalışma zamanı C++ Şablon kitaplığı)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Olay sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Event::operator = işleci](../windows/event-operator-assign-operator.md)|Geçerli olay örneği belirtilen olay referansı atar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)