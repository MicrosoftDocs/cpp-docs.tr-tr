---
title: Mutex::Lock yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 61d95072-b690-441e-a080-0bf94a733141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 37044dbd884c4e38c70677bf9a8fa0a51fda0a88
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880878"
---
# <a name="mutexlock-method"></a>Mutex::Lock Yöntemi
Geçerli nesne ya da belirtilen tanıtıcı ile ilişkili Mutex nesne kadar bekler yayımları mutex veya belirtilen zaman aşımı aralığı geçti.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `milliseconds`  
 Milisaniye cinsinden zaman aşımı aralığı. Sonsuza kadar bekler SONSUZ varsayılan değerdir.  
  
 `h`  
 Mutex nesnesi işleci.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Mutex sınıfı](../windows/mutex-class1.md)