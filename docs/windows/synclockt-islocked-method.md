---
title: "Synclockt::IsLocked yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 47dc99415fd995f144deddb6ca3bc7a4bb419ca5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="synclocktislocked-method"></a>SyncLockT::IsLocked Metodu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
bool IsLocked() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** SyncLockT nesne kilitli; Aksi takdirde ise **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli SyncLockT nesne bir kaynağa sahip olup olmadığını gösterir; diğer bir deyişle, SyncLockT nesnesidir *kilitli*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SyncLockT Sınıfı](../windows/synclockt-class.md)