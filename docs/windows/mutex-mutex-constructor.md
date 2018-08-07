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
ms.openlocfilehash: 7a7549371ba4648f8fcce03a98a021c8027c676e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605200"
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex Oluşturucusu
Yeni bir örneğini başlatır **Mutex** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *h*  
 Tanıtıcı ya da bir tanıtıcı bir rvalue başvurusu için bir **Mutex** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu başlatan bir **Mutex** nesnesinden belirtilen tanıtıcı. İkinci oluşturucu başlatan bir **Mutex** geçerli nesne belirtilen tanıtıcı, ve ardından mutex sahipliğini taşır **Mutex** nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Mutex sınıfı](../windows/mutex-class1.md)