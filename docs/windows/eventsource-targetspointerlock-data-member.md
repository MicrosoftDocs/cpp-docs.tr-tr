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
ms.openlocfilehash: 45c85502b7d0768f5fa3e275393a4071fd8649e4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598871"
---
# <a name="eventsourcetargetspointerlock-data-member"></a>EventSource::targetsPointerLock_ Veri Üyesi

Bunun için olay işleyicileri çalışırken bile iç veri üyelerine erişimi eşitler **EventSource** kaldırılan veya çağrılan eklenmektedir.

## <a name="syntax"></a>Sözdizimi

```cpp
Wrappers::SRWLock targetsPointerLock_;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
[EventSource Sınıfı](../windows/eventsource-class.md)