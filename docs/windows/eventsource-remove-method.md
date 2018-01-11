---
title: "EventSource::Remove yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::Remove
dev_langs: C++
helpviewer_keywords: Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a11bce6d70c70bba2a4e75753c55d83bec32329f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="eventsourceremove-method"></a>EventSource::Remove Yöntemi
Geçerli EventSource nesneyle ilişkili olay işleyicileri kümesinden tarafından belirtilen olay kaydı belirtecini temsil olay işleyicisi siler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `token`  
 Olay işleyici temsil eden bir tanıtıcı. Olay işleyicisi tarafından kaydedildiği durumlarda bu belirteci döndürüldü [Add()](../windows/eventsource-add-method.md) yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 EventRegistrationToken yapısı hakkında daha fazla bilgi için Windows çalışma zamanı başvuru belgeleri Windows::Foundation::EventRegistrationToken yapısı konusuna bakın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [EventSource Sınıfı](../windows/eventsource-class.md)