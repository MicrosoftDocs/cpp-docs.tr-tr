---
title: "MutexTraits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
dev_langs: C++
helpviewer_keywords: MutexTraits structure
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eebe8ffefedbc28be1f16a0d02a195d4af4ac0c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[MutexTraits::Unlock yöntemi](../windows/mutextraits-unlock-method.md)|Paylaşılan bir kaynağa özel denetimin serbest bırakır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)