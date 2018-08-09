---
title: SRWLockSharedTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db9a16671be21b2df7a4ce4f9d87a8b66e097e33
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020154"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits Yapısı
Genel özelliklerini açıklayan `SRWLock` paylaşılan kilit modu sınıfta.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Type`|İşaretçisi için eş anlamlı [SRWLOCK](../windows/srwlock-class.md) sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue Metodu](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|Alır bir **SRWLockSharedTraits** her zaman geçersiz bir nesne.|  
|[SRWLockSharedTraits::Unlock Metodu](../windows/srwlocksharedtraits-unlock-method.md)|Belirtilen özel denetim serbest `SRWLock` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Ad Alanı](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)