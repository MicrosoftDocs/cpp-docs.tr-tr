---
title: "Mutex::mutex Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a07aeac0f8d139f71bdbe2473dc8eabf7e14ec2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex Oluşturucusu
Mutex sınıfı yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `h`  
 Bir tanıtıcı veya rvalue başvuru Mutex nesnesi için bir tanıtıcı için.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu, belirtilen tanıtıcı Mutex nesnesinden başlatır. İkinci Oluşturucu, belirtilen tanıtıcı Mutex nesnesinden başlatır ve ardından mutex sahipliğini geçerli Mutex nesnesi taşır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Mutex sınıfı](../windows/mutex-class1.md)