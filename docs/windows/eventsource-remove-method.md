---
title: EventSource::Remove yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Remove
dev_langs:
- C++
helpviewer_keywords:
- Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36a057bbad39e61576828c5a02f6863248b235cf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641411"
---
# <a name="eventsourceremove-method"></a>EventSource::Remove Yöntemi
Olay işleyicisi geçerli ile ilişkili olay işleyicileri kümesinden tarafından belirtilen olay kaydı belirtecini temsil siler **EventSource** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Belirteç*  
 Bir olay işleyicisi temsil eden bir tanıtıcı. Olay işleyicisi tarafından kaydedildiğinde bu belirteci döndürüldü [Add()](../windows/eventsource-add-method.md) yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Hakkında daha fazla bilgi için `EventRegistrationToken` yapısı için bkz: **:: eventregistrationtoken yapısı** konudaki **Windows çalışma zamanı** başvuru belgeleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [EventSource Sınıfı](../windows/eventsource-class.md)