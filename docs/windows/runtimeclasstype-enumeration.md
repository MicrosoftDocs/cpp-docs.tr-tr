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
ms.openlocfilehash: 43ab0a738af4c6bc92d42c0884827b574946d2ea
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892409"
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