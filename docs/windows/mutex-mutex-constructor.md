---
title: Mutex::mutex Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb7782e44fc8598ca3b806ef922f8d0840765e28
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876462"
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