---
title: RuntimeClassType numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4464d236a85e06bf907f738657a4a0707e14a5e1
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603507"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType Numaralandırması
Türünü belirten [RuntimeClass](../windows/runtimeclass-class.md) desteklenen örneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`ClassicCom`|Klasik COM çalışma zamanı sınıf.|  
|`Delegate`|Eşdeğer `ClassicCom`.|  
|`InhibitFtmBase`|Devre dışı bırakır `FtmBase` sırasında Destek `__WRL_CONFIGURATION_LEGACY__` tanımlı değil.|  
|`InhibitWeakReference`|Zayıf başvuru desteği devre dışı bırakır.|  
|`WinRt`|Bir Windows çalışma zamanı sınıf.|  
|`WinRtClassicComMix`|Bir birleşimi `WinRt` ve `ClassicCom`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)