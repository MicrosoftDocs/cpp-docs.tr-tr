---
title: Platform::CallbackContext numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b80fe7749fdb2f91e300cff007c01001edfa557
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603044"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext numaralandırması
Bir geri çağırma işlevi (olay işleyicisi) yürütür iş parçacığı bağlamını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Üyeler  
  
|Türü kodu|Açıklama|  
|---------------|-----------------|  
|Tüm|Geri çağırma işlevi, her iş parçacığı bağlam üzerinde çalıştırabilirsiniz.|  
|Aynı|Zaman uyumsuz işlem başlatılan iş parçacığı bağlamı geri çağırma işlevi yürütebilir.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Sunucu desteklenen en düşük:** Windows Server 2012  
  
 **Namespace:** platformu  
  
 **Meta veri:** platform.winmd