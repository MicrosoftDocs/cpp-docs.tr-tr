---
title: "RuntimeClassType numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClassType
dev_langs: C++
helpviewer_keywords: RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 222f7d9ada76e43fa71658faa7c61e5369abd3db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)