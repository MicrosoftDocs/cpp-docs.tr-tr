---
title: "CriticalSection::TryLock yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs: C++
helpviewer_keywords: TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 225131a48e6ba5079ef2008b11ac6b22197f71d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock Yöntemi
Önemli bir bölümü engellenmeden girmek çalışır. Çağrı başarılı olursa, çağıran iş parçacığı kritik bölümünün aittir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `cs`  
 Bir kullanıcı tarafından belirtilen kritik bölüm nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kritik bölüm başarıyla girdiyseniz sıfır olmayan bir değer veya geçerli iş parçacığı zaten kritik bölüm sahip olur. Başka bir iş parçacığı zaten kritik bölüm sahipse sıfır.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk **TryLock** işlevi geçerli kritik bölüm nesne etkiler. İkinci **TryLock** işlevi, kullanıcı tarafından belirtilen kritik bölüm etkiler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSection sınıfı](../windows/criticalsection-class.md)