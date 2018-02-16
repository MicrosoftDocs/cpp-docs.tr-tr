---
title: "Platform::CallbackContext numaralandırma | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9d34f7ef8a953ce60972c27b34e257ea66d62d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext numaralandırması
İçinde bir geri çağırma işlevi (olay işleyicisi) yürüten iş parçacığı içeriği belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Üyeler  
  
|Türü kodu|Açıklama|  
|---------------|-----------------|  
|tüm|Geri çağırma işlevi her iş parçacığı bağlam yürütebilir.|  
|Aynı|Geri çağırma işlevi, zaman uyumsuz işlemi başlatılan iş parçacığı içeriği yürütebilir.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd