---
title: "Deferrableeventargs::ınvokeallfinished yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ca021d66c615bfec84b8f08df8474eeb20709e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="deferrableeventargsinvokeallfinished-method"></a>DeferrableEventArgs::InvokeAllFinished Yöntemi
Ertelenmiş olayını işlemek için tüm işleme tamamlandığını göstermek için çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void InvokeAllFinished()  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Olay kaynağı çağrılarını sonra bu yöntemi çağırmanız gerekir [Invokeall](../windows/eventsource-invokeall-method.md). Bu yöntemin çağrılması daha fazla gerçekleştirilmesini deferrals engeller ve tamamlanma işleyicinin hiçbir deferrals gerçekleştirilen, yürütmeyi zorlar.  
  
 Kod örneği için bkz: [DeferrableEventArgs sınıfı](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DeferrableEventArgs sınıfı](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll Metodu](../windows/eventsource-invokeall-method.md)