---
title: GetModuleBase işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25e4bb6db6114f7d64522dfe145d51ffaabd476a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874213"
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
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)