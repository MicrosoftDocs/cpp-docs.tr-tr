---
title: CriticalSection::Lock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a4fee4991459ddbab0ac370f025776529a6bd1e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464554"
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock Yöntemi
Belirtilen kritik bölüm Nesne sahipliği için bekler. Çağıran iş parçacığını sahipliği verildiğinde işlevi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *cs*  
 Bir kullanıcı tarafından belirtilen kritik bölüm nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli kritik bölümün kilidini açmak için kullanılan nesnesi kilitlenemedi.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk **kilit** işlevi, geçerli kritik bölüm nesnesini etkiler. İkinci **kilit** işlevi kullanıcı tanımlı bir kritik bölüm etkiler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CriticalSection Sınıfı](../windows/criticalsection-class.md)