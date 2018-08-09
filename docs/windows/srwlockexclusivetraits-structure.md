---
title: SRWLockExclusiveTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6543ada6840b292d6a7b981eefeab41642c42df
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017938"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits Yapısı
Genel özelliklerini açıklayan `SRWLock` sınıfında özel bir kilit modu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`Type`|İşaretçisi için eş anlamlı [SRWLOCK](../windows/srwlock-class.md) sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue Metodu](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|Alır bir **SRWLockExclusiveTraits** her zaman geçersiz bir nesne.|  
|[SRWLockExclusiveTraits::Unlock Metodu](../windows/srwlockexclusivetraits-unlock-method.md)|Belirtilen özel denetim serbest `SRWLock` nesne.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers::HandleTraits Ad Alanı](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)