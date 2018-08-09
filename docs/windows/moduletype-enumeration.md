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
ms.openlocfilehash: 831f1fbcb2da205fa08286a1fbbbf414e66075d4
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019936"
---
# <a name="moduletype-enumeration"></a>ModuleType Numaralandırması
Bir modülü bir işlem sunucusu veya bir işlem dışı sunucu desteklemesi gerekip gerekmediğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum ModuleType;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`InProc`|Bir işlem sunucusu.|  
|`OutOfProc`|Bir işlem dışı sunucu.|  
|`DisableCaching`|Önbelleğe alma mekanizması modül devre dışı bırakın.|  
|`InProcDisableCaching`|Birleşimi `InProc` ve `DisableCaching`.|  
|`OutOfProcDisableCaching`|Birleşimi `OutOfProc` ve `DisableCaching`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)