---
title: "ModuleType numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd68d911a3734510bfb35db4b3ee0c4b8e46a4a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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