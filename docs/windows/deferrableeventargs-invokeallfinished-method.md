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
ms.openlocfilehash: 23d521b8373969abdd739b6e4f48eb334284664d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605179"
---
# <a name="deferrableeventargsinvokeallfinished-method"></a>DeferrableEventArgs::InvokeAllFinished Yöntemi
Ertelenmiş olayı işlemek için tüm işleme tamamlandığını göstermek için çağrılır.
  
## <a name="syntax"></a>Sözdizimi
  
```cpp
void InvokeAllFinished()  
```
  
## <a name="remarks"></a>Açıklamalar
 Olay kaynağı çağrılarını sonra bu yöntemi çağırmanız gerekir [Invokeall](../windows/eventsource-invokeall-method.md). Bu yöntemi çağırmadan, daha fazla gönderilemeyenler gerçekleştirilmesini önler ve hiçbir gönderilemeyenler alınan, yürütülecek tamamlama işleyicisine zorlar.
  
 Kod örneği için bkz: [DeferrableEventArgs sınıfı](../windows/deferrableeventargs-class.md).
  
## <a name="requirements"></a>Gereksinimler
 **Başlık:** event.h
  
 **Namespace:** Microsoft::WRL
  
## <a name="see-also"></a>Ayrıca Bkz.
 [DeferrableEventArgs Sınıfı](../windows/deferrableeventargs-class.md)  
 [EventSource::InvokeAll Metodu](../windows/eventsource-invokeall-method.md)