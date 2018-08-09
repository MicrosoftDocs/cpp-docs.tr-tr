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
ms.openlocfilehash: 1b54813a41a8857e4533f21d1eb0adaf8dcecd25
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010827"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType Numaralandırması
Türünü belirten [RuntimeClass](../windows/runtimeclass-class.md) desteklenen örneği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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