---
title: "CriticalSection::Lock yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs: C++
helpviewer_keywords: Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4df91ea9030ca4917f246bc05be1ba059673680e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [CriticalSection sınıfı](../windows/criticalsection-class.md)