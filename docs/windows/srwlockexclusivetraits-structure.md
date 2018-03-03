---
title: "SRWLockExclusiveTraits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05e7b2a6814cefffee258909f4bab11fcfe34f1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits Yapısı
SRWLock sınıfı özel kullanım kilidi modunda genel özelliklerini açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Type`|Bir işaretçi için eş anlamlı [SRWLOCK](../windows/srwlock-class.md) sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue Metodu](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Her zaman geçersiz SRWLockExclusiveTraits nesneyi alır.|  
|[SRWLockExclusiveTraits::Unlock Metodu](../windows/srwlockexclusivetraits-unlock-method.md)|Belirtilen SRWLock nesnenin özel denetim serbest bırakır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Ad Alanı](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)