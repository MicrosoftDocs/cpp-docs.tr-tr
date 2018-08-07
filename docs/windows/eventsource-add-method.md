---
title: EventSource::Add yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Add
dev_langs:
- C++
helpviewer_keywords:
- Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90750f965768d5ecda40e074f9a136407613d2d2
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570395"
---
# <a name="eventsourceadd-method"></a>EventSource::Add Yöntemi
Ekler için geçerli olay işleyicileri kümesini belirtilen temsilci arabirimi tarafından temsil edilen olay işleyicisi **EventSource** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *delegateInterface*  
 Bir olay işleyicisi temsil eden bir temsilci nesnesi için arabirim.  
  
 *Belirteç*  
 Bu işlem tamamlandığında, olayı temsil eden bir işleyici. Parametre olarak bu belirteci kullanmasına [foreach()](../windows/eventsource-remove-method.md) olay işleyicisi atmak için yöntemi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [EventSource Sınıfı](../windows/eventsource-class.md)