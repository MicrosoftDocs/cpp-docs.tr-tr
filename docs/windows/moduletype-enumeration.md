---
title: ModuleType numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d36355c9f64f9f5c827ef8c4d5b3cb6a77d17b65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876842"
---
# <a name="moduletype-enumeration"></a>ModuleType Numaralandırması
Bir modülü bir işlem sunucusuna veya bir işlem dışı sunucusuna desteklemesi gerekip gerekmediğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`InProc`|Bir işlem sunucusu.|  
|`OutOfProc`|Bir işlem dışı sunucusu.|  
|`DisableCaching`|Önbelleğe alma mekanizması modül devre dışı bırakın.|  
|`InProcDisableCaching`|Birleşimi `InProc` ve `DisableCaching`.|  
|`OutOfProcDisableCaching`|Birleşimi `OutOfProc` ve `DisableCaching`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)