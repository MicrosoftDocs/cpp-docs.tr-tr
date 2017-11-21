---
title: "GetModuleBase işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::GetModuleBase
dev_langs: C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30ff77fd81b63019f9c6c3bcfc8c6b676a1351f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="getmodulebase-function"></a>GetModuleBase İşlevi
Alır bir [ModuleBase](../windows/modulebase-class.md) artırma ve azaltma için başvuru sayısı izin veren bir işaretçi bir [RuntimeClass](../windows/runtimeclass-class.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `ModuleBase` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev artırmak ve azaltma için dahili olarak kullanılır Nesne başvurusu sayar.  
  
 Başvuru sayıları çağırarak denetlemek için bu işlevi kullanabilirsiniz [Modulebase::ıncrementobjectcount](../windows/modulebase-incrementobjectcount-method.md) ve [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)