---
title: "Synclockwithstatust::IsLocked yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs: C++
helpviewer_keywords: IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e31f0931a53e8bdd977e82fcef56f1bacc45f76b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [SyncLockWithStatusT sınıfı](../windows/synclockwithstatust-class.md)