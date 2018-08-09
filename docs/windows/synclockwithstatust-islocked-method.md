---
title: Synclockwithstatust::IsLocked metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebe723811efe62efa85a1cc2fa35736689306c7e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645639"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked Metodu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtir olup olmadığını geçerli **SyncLockWithStatusT** nesnesi bir kaynağa sahiptir; diğer bir deyişle, **SyncLockWithStatusT** nesnedir *kilitli*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** varsa **SyncLockWithStatusT** nesnedir kilitli; Aksi takdirde **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SyncLockWithStatusT Sınıfı](../windows/synclockwithstatust-class.md)