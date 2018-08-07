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
ms.openlocfilehash: 9dd026158a2bbc76e7a3e195bc5346f65821f2b7
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569501"
---
# <a name="eventsourceremove-method"></a>EventSource::Remove Yöntemi
Olay işleyicisi geçerli ile ilişkili olay işleyicileri kümesinden tarafından belirtilen olay kaydı belirtecini temsil siler **EventSource** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
 EventRegistrationToken yapısı hakkında daha fazla bilgi için bkz. `Windows::Foundation::EventRegistrationToken` yapısı konuda Windows Runtime başvuru belgeleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [EventSource Sınıfı](../windows/eventsource-class.md)