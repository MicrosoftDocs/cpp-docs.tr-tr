---
title: "ModuleType numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ModuleType
dev_langs: C++
helpviewer_keywords: ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a516795124ec3de6bb90102b3ea200d3365f33c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)