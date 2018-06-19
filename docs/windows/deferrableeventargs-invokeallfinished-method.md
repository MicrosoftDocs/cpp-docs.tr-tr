---
title: Deferrableeventargs::ınvokeallfinished yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1aaaf8c6849b30e26463810ff353234319960048
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883374"
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