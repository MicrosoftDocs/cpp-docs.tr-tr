---
title: "RuntimeClassType numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26016e8c95807af76484504c491ca1e6e08f8f96
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType Numaralandırması
Türünü belirtir. [RuntimeClass](../windows/runtimeclass-class.md) desteklenen örneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ClassicCom`|Klasik COM çalışma zamanı sınıf.|  
|`Delegate`|Eşdeğer **ClassicCom**.|  
|`InhibitFtmBase`|Devre dışı bırakır `FtmBase` sırasında Destek `__WRL_CONFIGURATION_LEGACY__` tanımlı değil.|  
|`InhibitWeakReference`|Zayıf başvuru desteğini devre dışı bırakır.|  
|`WinRt`|Windows çalışma zamanı sınıf.|  
|`WinRtClassicComMix`|Bir birleşimini `WinRt` ve `ClassicCom`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)