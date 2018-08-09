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
ms.openlocfilehash: d87c07f7fa4f1dfa6cbb34545d74d75e8a867583
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017090"
---
# <a name="mutexmutex-constructor"></a>Mutex::Mutex Oluşturucusu
Yeni bir örneğini başlatır **Mutex** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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