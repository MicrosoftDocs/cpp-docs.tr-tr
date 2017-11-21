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
ms.openlocfilehash: acae8467ceeaaafea6668d4fbf6b5e2f4884b373
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [EventSource::ınvokeall yöntemi](../windows/eventsource-invokeall-method.md)