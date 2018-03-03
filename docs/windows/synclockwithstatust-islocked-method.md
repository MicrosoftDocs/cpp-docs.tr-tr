---
title: "Synclockwithstatust::IsLocked yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05892ef6448821783fb7017ac8373423e5d37783
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked Metodu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli SyncLockWithStatusT nesne bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, SyncLockWithStatusT nesnesidir *kilitli*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** SyncLockWithStatusT nesne kilitli; Aksi takdirde ise **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SyncLockWithStatusT Sınıfı](../windows/synclockwithstatust-class.md)