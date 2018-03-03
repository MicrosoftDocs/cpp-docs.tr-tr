---
title: "MutexTraits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs:
- C++
helpviewer_keywords:
- MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd8dac513b5eec049fbb739ab79628d9f41c96b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mutextraits-structure"></a>MutexTraits Yapısı
Ortak özelliklerini tanımlayan [Mutex](../windows/mutex-class1.md) sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct MutexTraits : HANDLENullTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MutexTraits::Unlock Metodu](../windows/mutextraits-unlock-method.md)|Paylaşılan bir kaynağa özel denetimin serbest bırakır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Ad Alanı](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)