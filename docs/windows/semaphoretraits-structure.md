---
title: SemaphoreTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
dev_langs:
- C++
helpviewer_keywords:
- SemaphoreTraits structure
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c953efc6e9f4b3904404ae362b6beca7f88192d2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018275"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits Yapısı
Ortak özelliklerini tanımlayan bir **semafor** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
struct SemaphoreTraits : HANDLENullTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SemaphoreTraits::Unlock Metodu](../windows/semaphoretraits-unlock-method.md)|Paylaşılan bir kaynak denetim yayınlar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HANDLENullTraits`  
  
 `SemaphoreTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Ad Alanı](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)