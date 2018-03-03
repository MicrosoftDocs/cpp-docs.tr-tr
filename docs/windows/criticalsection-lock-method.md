---
title: "CriticalSection::Lock yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: af996faeebd0fcddb85993badd71ceecd32d494e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock Yöntemi
Belirtilen kritik bölüm nesnenin sahipliğini bekler. Çağıran iş parçacığı sahipliği verildiğinde işlevi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cs`  
 Bir kullanıcı tarafından belirtilen kritik bölüm nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli kritik bölümün kilidini açmak için kullanılan bir kilit nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk **kilit** işlevi geçerli kritik bölüm nesne etkiler. İkinci **kilit** işlevi, kullanıcı tarafından belirtilen kritik bölüm etkiler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSection Sınıfı](../windows/criticalsection-class.md)