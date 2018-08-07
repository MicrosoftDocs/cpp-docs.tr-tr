---
title: EventSource::targetsPointerLock_ veri üyesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::targetsPointerLock_
dev_langs:
- C++
helpviewer_keywords:
- targetsPointerLock_ data member
ms.assetid: 8f08409f-5262-4be7-9cf1-2ed15f19684a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b58aa072af5ff96093f9999d212f8b19ff0571c
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569823"
---
# <a name="eventsourcetargetspointerlock-data-member"></a>EventSource::targetsPointerLock_ Veri Üyesi
Bunun için olay işleyicileri çalışırken bile iç veri üyelerine erişimi eşitler **EventSource** kaldırılan veya çağrılan eklenmektedir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Wrappers::SRWLock targetsPointerLock_;  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [EventSource Sınıfı](../windows/eventsource-class.md)