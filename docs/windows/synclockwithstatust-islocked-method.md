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
ms.openlocfilehash: 80c744431fe7df32be705fcf91eef0a8691b8fa4
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015804"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked Metodu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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