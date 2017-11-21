---
title: "SRWLockSharedTraits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs: C++
helpviewer_keywords: SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3a044baaa463c91c134137214e9708db8c4dfefb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits Yapısı
Paylaşılan kilit modu SRWLock sınıfında genel özelliklerini açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Type`|Bir işaretçi için eş anlamlı [SRWLOCK](../windows/srwlock-class.md) sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Srwlocksharedtraits::getınvalidvalue yöntemi](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Her zaman geçersiz SRWLockSharedTraits nesneyi alır.|  
|[SRWLockSharedTraits::Unlock yöntemi](../windows/srwlocksharedtraits-unlock-method.md)|Belirtilen SRWLock nesnenin özel denetim serbest bırakır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)